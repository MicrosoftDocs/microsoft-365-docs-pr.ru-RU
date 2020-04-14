---
title: Что позволяют искать типы конфиденциальной информации
f1.keywords:
- CSH
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
ms.openlocfilehash: aa3a08961ccad92c9986db16c1d8180d9b0cd17e
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240290"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="ba5ea-104">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="ba5ea-104">What the sensitive information types look for</span></span>

<span data-ttu-id="ba5ea-105">Защита от потери данных (DLP) в центре безопасности &amp; Office 365 содержит множество типов конфиденциальной информации, готовых к использованию в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="ba5ea-106">В этой статье перечислены все эти типы конфиденциальной информации и показано, каким именно образом политика защиты от потери данных выявляет каждый тип.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="ba5ea-107">Тип конфиденциальной информации определяется шаблоном, который можно идентифицировать регулярным выражением или функцией.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="ba5ea-108">Кроме того, для идентификации типа конфиденциальной информации могут использоваться подкрепляющие доказательства, такие как ключевые слова и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="ba5ea-109">Уровень вероятности и расположение слов и знаков также используются в процессе оценки.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="ba5ea-110">Код банка ABA</span><span class="sxs-lookup"><span data-stu-id="ba5ea-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-111">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-111">Format</span></span>

<span data-ttu-id="ba5ea-112">9 цифр в виде форматированного или неформатированного шаблона.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-113">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-113">Pattern</span></span>

<span data-ttu-id="ba5ea-114">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="ba5ea-114">Formatted:</span></span>
- <span data-ttu-id="ba5ea-115">четыре цифры, начиная с 0, 1, 2, 3, 6, 7 или 8;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="ba5ea-116">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-116">A hyphen</span></span>
- <span data-ttu-id="ba5ea-117">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-117">Four digits</span></span>
- <span data-ttu-id="ba5ea-118">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-118">A hyphen</span></span>
- <span data-ttu-id="ba5ea-119">цифра.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-119">A digit</span></span>

<span data-ttu-id="ba5ea-120">Неформатированные: 9 последовательных цифр, начиная с 0, 1, 2, 3, 6, 7 или 8.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="ba5ea-121">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-121">Checksum</span></span>

<span data-ttu-id="ba5ea-122">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-123">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-123">Definition</span></span>

<span data-ttu-id="ba5ea-124">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-125">функция Func_aba_routing находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-126">находится ключевое слово из Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="ba5ea-127">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="ba5ea-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="ba5ea-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="ba5ea-129">код банка ABA</span><span class="sxs-lookup"><span data-stu-id="ba5ea-129">aba</span></span>
- <span data-ttu-id="ba5ea-130">aba#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-130">aba #</span></span>
- <span data-ttu-id="ba5ea-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-131">aba routing #</span></span>
- <span data-ttu-id="ba5ea-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-132">aba routing number</span></span>
- <span data-ttu-id="ba5ea-133">код банка ABA #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-133">aba#</span></span>
- <span data-ttu-id="ba5ea-134">абараутинг #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-134">abarouting#</span></span>
- <span data-ttu-id="ba5ea-135">aba number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-135">aba number</span></span>
- <span data-ttu-id="ba5ea-136">абараутингнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-136">abaroutingnumber</span></span>
- <span data-ttu-id="ba5ea-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-137">american bank association routing #</span></span>
- <span data-ttu-id="ba5ea-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-138">american bank association routing number</span></span>
- <span data-ttu-id="ba5ea-139">американбанкассоЦиатионраутинг #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="ba5ea-140">американбанкассоЦиатионраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="ba5ea-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-141">bank routing number</span></span>
- <span data-ttu-id="ba5ea-142">банкраутинг #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-142">bankrouting#</span></span>
- <span data-ttu-id="ba5ea-143">банкраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-143">bankroutingnumber</span></span>
- <span data-ttu-id="ba5ea-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-144">routing transit number</span></span>
- <span data-ttu-id="ba5ea-145">ртн</span><span class="sxs-lookup"><span data-stu-id="ba5ea-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="ba5ea-146">Номер внутреннего удостоверения личности для Аргентины (DNI)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-147">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-147">Format</span></span>

<span data-ttu-id="ba5ea-148">Восемь цифр, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-149">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-149">Pattern</span></span>

<span data-ttu-id="ba5ea-150">Восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-150">Eight digits:</span></span>
- <span data-ttu-id="ba5ea-151">две цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-151">Two digits</span></span>
- <span data-ttu-id="ba5ea-152">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-152">A period</span></span>
- <span data-ttu-id="ba5ea-153">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-153">Three digits</span></span>
- <span data-ttu-id="ba5ea-154">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-154">A period</span></span>
- <span data-ttu-id="ba5ea-155">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-156">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-156">Checksum</span></span>

<span data-ttu-id="ba5ea-157">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-158">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-158">Definition</span></span>

<span data-ttu-id="ba5ea-159">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-160">регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-161">находится ключевое слово из Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-162">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="ba5ea-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="ba5ea-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="ba5ea-165">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-165">Identity</span></span> 
- <span data-ttu-id="ba5ea-166">Идентификация национальной идентификационной карточки</span><span class="sxs-lookup"><span data-stu-id="ba5ea-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="ba5ea-167">DNI</span><span class="sxs-lookup"><span data-stu-id="ba5ea-167">DNI</span></span> 
- <span data-ttu-id="ba5ea-168">Национальная реестр пользователей NIC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="ba5ea-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="ba5ea-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="ba5ea-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="ba5ea-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="ba5ea-171">идентидад</span><span class="sxs-lookup"><span data-stu-id="ba5ea-171">Identidad</span></span> 
- <span data-ttu-id="ba5ea-172">идентификаЦиóн</span><span class="sxs-lookup"><span data-stu-id="ba5ea-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="ba5ea-173">Номер банковского счета для Австралии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-174">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-174">Format</span></span>

<span data-ttu-id="ba5ea-175">6–10 цифр с номером филиала банка в штате или без него.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-176">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-176">Pattern</span></span>

<span data-ttu-id="ba5ea-177">Номер счета состоит из 6–10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="ba5ea-178">Номер филиала государственного банка Австралии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="ba5ea-179">три цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-179">Three digits</span></span> 
- <span data-ttu-id="ba5ea-180">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-180">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-181">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-182">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-182">Checksum</span></span>

<span data-ttu-id="ba5ea-183">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-184">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-184">Definition</span></span>

<span data-ttu-id="ba5ea-185">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-186">регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="ba5ea-187">находится ключевое слово из Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="ba5ea-188">регулярное выражение Regex_australia_bank_account_number_bsb находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="ba5ea-189">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-190">регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="ba5ea-191">находится ключевое слово из Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-192">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="ba5ea-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="ba5ea-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-194">swift bank code</span></span>
- <span data-ttu-id="ba5ea-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="ba5ea-195">correspondent bank</span></span>
- <span data-ttu-id="ba5ea-196">base currency</span><span class="sxs-lookup"><span data-stu-id="ba5ea-196">base currency</span></span>
- <span data-ttu-id="ba5ea-197">usa account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-197">usa account</span></span>
- <span data-ttu-id="ba5ea-198">holder address</span><span class="sxs-lookup"><span data-stu-id="ba5ea-198">holder address</span></span>
- <span data-ttu-id="ba5ea-199">bank address</span><span class="sxs-lookup"><span data-stu-id="ba5ea-199">bank address</span></span>
- <span data-ttu-id="ba5ea-200">information account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-200">information account</span></span>
- <span data-ttu-id="ba5ea-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-201">fund transfers</span></span>
- <span data-ttu-id="ba5ea-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="ba5ea-202">bank charges</span></span>
- <span data-ttu-id="ba5ea-203">bank details</span><span class="sxs-lookup"><span data-stu-id="ba5ea-203">bank details</span></span>
- <span data-ttu-id="ba5ea-204">banking information</span><span class="sxs-lookup"><span data-stu-id="ba5ea-204">banking information</span></span>
- <span data-ttu-id="ba5ea-205">full names</span><span class="sxs-lookup"><span data-stu-id="ba5ea-205">full names</span></span>
- <span data-ttu-id="ba5ea-206">иаеа</span><span class="sxs-lookup"><span data-stu-id="ba5ea-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="ba5ea-207">Номер водительского удостоверения для Австралии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-208">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-208">Format</span></span>

<span data-ttu-id="ba5ea-209">Девять букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-210">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-210">Pattern</span></span>

<span data-ttu-id="ba5ea-211">Девять букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="ba5ea-212">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-213">две цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-213">Two digits</span></span> 
- <span data-ttu-id="ba5ea-214">пять цифр или букв (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="ba5ea-215">OR</span><span class="sxs-lookup"><span data-stu-id="ba5ea-215">OR</span></span>

- <span data-ttu-id="ba5ea-216">1–2 дополнительные буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-217">4–9 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-217">4-9 digits</span></span>

<span data-ttu-id="ba5ea-218">OR</span><span class="sxs-lookup"><span data-stu-id="ba5ea-218">OR</span></span>

- <span data-ttu-id="ba5ea-219">девять цифр или букв (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-220">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-220">Checksum</span></span>

<span data-ttu-id="ba5ea-221">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-222">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-222">Definition</span></span>

<span data-ttu-id="ba5ea-223">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-224">регулярное выражение Regex_australia_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-225">находится ключевое слово из Keyword_australia_drivers_license_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="ba5ea-226">ни одно ключевое слово из Keyword_australia_drivers_license_number_exclusions не находится.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-227">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="ba5ea-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="ba5ea-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="ba5ea-229">international driving permits</span></span>
- <span data-ttu-id="ba5ea-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="ba5ea-230">australian automobile association</span></span>
- <span data-ttu-id="ba5ea-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-231">international driving permit</span></span>
- <span data-ttu-id="ba5ea-232">дриверлиценце</span><span class="sxs-lookup"><span data-stu-id="ba5ea-232">DriverLicence</span></span>
- <span data-ttu-id="ba5ea-233">дриверлиценцес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-233">DriverLicences</span></span>
- <span data-ttu-id="ba5ea-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-234">Driver Lic</span></span>
- <span data-ttu-id="ba5ea-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-235">Driver Licence</span></span>
- <span data-ttu-id="ba5ea-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-236">Driver Licences</span></span>
- <span data-ttu-id="ba5ea-237">дриверслик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-237">DriversLic</span></span>
- <span data-ttu-id="ba5ea-238">дриверслиценце</span><span class="sxs-lookup"><span data-stu-id="ba5ea-238">DriversLicence</span></span>
- <span data-ttu-id="ba5ea-239">дриверслиценцес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-239">DriversLicences</span></span>
- <span data-ttu-id="ba5ea-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-240">Drivers Lic</span></span>
- <span data-ttu-id="ba5ea-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-241">Drivers Lics</span></span>
- <span data-ttu-id="ba5ea-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-242">Drivers Licence</span></span>
- <span data-ttu-id="ba5ea-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-243">Drivers Licences</span></span>
- <span data-ttu-id="ba5ea-244">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-244">Driver'Lic</span></span>
- <span data-ttu-id="ba5ea-245">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="ba5ea-245">Driver'Lics</span></span>
- <span data-ttu-id="ba5ea-246">Driver ' Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-246">Driver'Licence</span></span>
- <span data-ttu-id="ba5ea-247">Driver ' Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-247">Driver'Licences</span></span>
- <span data-ttu-id="ba5ea-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-248">Driver' Lic</span></span>
- <span data-ttu-id="ba5ea-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-249">Driver' Lics</span></span>
- <span data-ttu-id="ba5ea-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-250">Driver' Licence</span></span>
- <span data-ttu-id="ba5ea-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-251">Driver' Licences</span></span>
- <span data-ttu-id="ba5ea-252">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-252">Driver'sLic</span></span>
- <span data-ttu-id="ba5ea-253">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-253">Driver'sLics</span></span>
- <span data-ttu-id="ba5ea-254">дривер'слиценце</span><span class="sxs-lookup"><span data-stu-id="ba5ea-254">Driver'sLicence</span></span>
- <span data-ttu-id="ba5ea-255">дривер'слиценцес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-255">Driver'sLicences</span></span>
- <span data-ttu-id="ba5ea-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-256">Driver's Lic</span></span>
- <span data-ttu-id="ba5ea-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-257">Driver's Lics</span></span>
- <span data-ttu-id="ba5ea-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-258">Driver's Licence</span></span>
- <span data-ttu-id="ba5ea-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-259">Driver's Licences</span></span>
- <span data-ttu-id="ba5ea-260">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-260">DriverLic#</span></span>
- <span data-ttu-id="ba5ea-261">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-261">DriverLics#</span></span>
- <span data-ttu-id="ba5ea-262">дриверлиценце #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-262">DriverLicence#</span></span>
- <span data-ttu-id="ba5ea-263">дриверлиценцес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-263">DriverLicences#</span></span>
- <span data-ttu-id="ba5ea-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-264">Driver Lic#</span></span>
- <span data-ttu-id="ba5ea-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-265">Driver Lics#</span></span>
- <span data-ttu-id="ba5ea-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-266">Driver Licence#</span></span>
- <span data-ttu-id="ba5ea-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-267">Driver Licences#</span></span>
- <span data-ttu-id="ba5ea-268">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-268">DriversLic#</span></span>
- <span data-ttu-id="ba5ea-269">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-269">DriversLics#</span></span>
- <span data-ttu-id="ba5ea-270">дриверслиценце #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-270">DriversLicence#</span></span>
- <span data-ttu-id="ba5ea-271">дриверслиценцес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-271">DriversLicences#</span></span>
- <span data-ttu-id="ba5ea-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-272">Drivers Lic#</span></span>
- <span data-ttu-id="ba5ea-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-273">Drivers Lics#</span></span>
- <span data-ttu-id="ba5ea-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-274">Drivers Licence#</span></span>
- <span data-ttu-id="ba5ea-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-275">Drivers Licences#</span></span>
- <span data-ttu-id="ba5ea-276">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-276">Driver'Lic#</span></span>
- <span data-ttu-id="ba5ea-277">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-277">Driver'Lics#</span></span>
- <span data-ttu-id="ba5ea-278">Driver ' Licence #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-278">Driver'Licence#</span></span>
- <span data-ttu-id="ba5ea-279">Driver ' Licences #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-279">Driver'Licences#</span></span>
- <span data-ttu-id="ba5ea-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-280">Driver' Lic#</span></span>
- <span data-ttu-id="ba5ea-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-281">Driver' Lics#</span></span>
- <span data-ttu-id="ba5ea-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-282">Driver' Licence#</span></span>
- <span data-ttu-id="ba5ea-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-283">Driver' Licences#</span></span>
- <span data-ttu-id="ba5ea-284">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-284">Driver'sLic#</span></span>
- <span data-ttu-id="ba5ea-285">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-285">Driver'sLics#</span></span>
- <span data-ttu-id="ba5ea-286">дривер'слиценце #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-286">Driver'sLicence#</span></span>
- <span data-ttu-id="ba5ea-287">дривер'слиценцес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-287">Driver'sLicences#</span></span>
- <span data-ttu-id="ba5ea-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-288">Driver's Lic#</span></span>
- <span data-ttu-id="ba5ea-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-289">Driver's Lics#</span></span>
- <span data-ttu-id="ba5ea-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-290">Driver's Licence#</span></span>
- <span data-ttu-id="ba5ea-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="ba5ea-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="ba5ea-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="ba5ea-293">AAA</span><span class="sxs-lookup"><span data-stu-id="ba5ea-293">aaa</span></span>
- <span data-ttu-id="ba5ea-294">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-294">DriverLicense</span></span>
- <span data-ttu-id="ba5ea-295">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-295">DriverLicenses</span></span>
- <span data-ttu-id="ba5ea-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-296">Driver License</span></span>
- <span data-ttu-id="ba5ea-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-297">Driver Licenses</span></span>
- <span data-ttu-id="ba5ea-298">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-298">DriversLicense</span></span>
- <span data-ttu-id="ba5ea-299">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-299">DriversLicenses</span></span>
- <span data-ttu-id="ba5ea-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-300">Drivers License</span></span>
- <span data-ttu-id="ba5ea-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-301">Drivers Licenses</span></span>
- <span data-ttu-id="ba5ea-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-302">Driver'License</span></span>
- <span data-ttu-id="ba5ea-303">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-303">Driver'Licenses</span></span>
- <span data-ttu-id="ba5ea-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-304">Driver' License</span></span>
- <span data-ttu-id="ba5ea-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-305">Driver' Licenses</span></span>
- <span data-ttu-id="ba5ea-306">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-306">Driver'sLicense</span></span>
- <span data-ttu-id="ba5ea-307">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-307">Driver'sLicenses</span></span>
- <span data-ttu-id="ba5ea-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-308">Driver's License</span></span>
- <span data-ttu-id="ba5ea-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-309">Driver's Licenses</span></span>
- <span data-ttu-id="ba5ea-310">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-310">DriverLicense#</span></span>
- <span data-ttu-id="ba5ea-311">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-311">DriverLicenses#</span></span>
- <span data-ttu-id="ba5ea-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-312">Driver License#</span></span>
- <span data-ttu-id="ba5ea-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-313">Driver Licenses#</span></span>
- <span data-ttu-id="ba5ea-314">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-314">DriversLicense#</span></span>
- <span data-ttu-id="ba5ea-315">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-315">DriversLicenses#</span></span>
- <span data-ttu-id="ba5ea-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-316">Drivers License#</span></span>
- <span data-ttu-id="ba5ea-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-317">Drivers Licenses#</span></span>
- <span data-ttu-id="ba5ea-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-318">Driver'License#</span></span>
- <span data-ttu-id="ba5ea-319">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-319">Driver'Licenses#</span></span>
- <span data-ttu-id="ba5ea-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-320">Driver' License#</span></span>
- <span data-ttu-id="ba5ea-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-321">Driver' Licenses#</span></span>
- <span data-ttu-id="ba5ea-322">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-322">Driver'sLicense#</span></span>
- <span data-ttu-id="ba5ea-323">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="ba5ea-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-324">Driver's License#</span></span>
- <span data-ttu-id="ba5ea-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="ba5ea-326">Номер карты медицинского страхования для Австралии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-327">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-327">Format</span></span>

<span data-ttu-id="ba5ea-328">10–11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-329">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-329">Pattern</span></span>

<span data-ttu-id="ba5ea-330">10–11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-330">10-11 digits:</span></span>
- <span data-ttu-id="ba5ea-331">Первая цифра находится в диапазоне 2–6.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="ba5ea-332">Девятая цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="ba5ea-333">Десятая цифра — цифра серии.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="ba5ea-334">Одиннадцатая цифра (необязательно) — индивидуальный номер.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-335">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-335">Checksum</span></span>

<span data-ttu-id="ba5ea-336">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-337">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-337">Definition</span></span>

<span data-ttu-id="ba5ea-338">Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-339">функция Func_australian_medical_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-340">находится ключевое слово из Keyword_Australia_Medical_Account_Number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="ba5ea-341">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-341">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-342">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-343">функция Func_australian_medical_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-344">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-345">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="ba5ea-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="ba5ea-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="ba5ea-347">bank account details</span></span>
- <span data-ttu-id="ba5ea-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="ba5ea-348">medicare payments</span></span>
- <span data-ttu-id="ba5ea-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-349">mortgage account</span></span>
- <span data-ttu-id="ba5ea-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="ba5ea-350">bank payments</span></span>
- <span data-ttu-id="ba5ea-351">information branch</span><span class="sxs-lookup"><span data-stu-id="ba5ea-351">information branch</span></span>
- <span data-ttu-id="ba5ea-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="ba5ea-352">credit card loan</span></span>
- <span data-ttu-id="ba5ea-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="ba5ea-353">department of human services</span></span>
- <span data-ttu-id="ba5ea-354">local service</span><span class="sxs-lookup"><span data-stu-id="ba5ea-354">local service</span></span>
- <span data-ttu-id="ba5ea-355">медикаре</span><span class="sxs-lookup"><span data-stu-id="ba5ea-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="ba5ea-356">Номер паспорта гражданина Австралии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-357">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-357">Format</span></span>

<span data-ttu-id="ba5ea-358">Буква, за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-359">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-359">Pattern</span></span>

<span data-ttu-id="ba5ea-360">Буква (без учета регистра), за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-361">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-361">Checksum</span></span>

<span data-ttu-id="ba5ea-362">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-363">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-363">Definition</span></span>

<span data-ttu-id="ba5ea-364">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-365">регулярное выражение Regex_australia_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-366">Найдено ключевое слово из Keyword_passport или Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-367">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ba5ea-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-368">Keyword_passport</span></span>

- <span data-ttu-id="ba5ea-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-369">Passport Number</span></span>
- <span data-ttu-id="ba5ea-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="ba5ea-370">Passport No</span></span>
- <span data-ttu-id="ba5ea-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-371">Passport #</span></span>
- <span data-ttu-id="ba5ea-372">Службу #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-372">Passport#</span></span>
- <span data-ttu-id="ba5ea-373">пасспортид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-373">PassportID</span></span>
- <span data-ttu-id="ba5ea-374">пасспортно</span><span class="sxs-lookup"><span data-stu-id="ba5ea-374">Passportno</span></span>
- <span data-ttu-id="ba5ea-375">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-375">passportnumber</span></span>
- <span data-ttu-id="ba5ea-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="ba5ea-376">パスポート</span></span>
- <span data-ttu-id="ba5ea-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-377">パスポート番号</span></span>
- <span data-ttu-id="ba5ea-378">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-378">パスポートのNum</span></span>
- <span data-ttu-id="ba5ea-379">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="ba5ea-379">パスポート ＃</span></span> 
- <span data-ttu-id="ba5ea-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-380">Numéro de passeport</span></span>
- <span data-ttu-id="ba5ea-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-381">Passeport n °</span></span>
- <span data-ttu-id="ba5ea-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ba5ea-382">Passeport Non</span></span>
- <span data-ttu-id="ba5ea-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-383">Passeport #</span></span>
- <span data-ttu-id="ba5ea-384">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-384">Passeport#</span></span>
- <span data-ttu-id="ba5ea-385">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-385">PasseportNon</span></span>
- <span data-ttu-id="ba5ea-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="ba5ea-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="ba5ea-388">службу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-388">passport</span></span>
- <span data-ttu-id="ba5ea-389">passport details</span><span class="sxs-lookup"><span data-stu-id="ba5ea-389">passport details</span></span>
- <span data-ttu-id="ba5ea-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="ba5ea-390">immigration and citizenship</span></span>
- <span data-ttu-id="ba5ea-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="ba5ea-391">commonwealth of australia</span></span>
- <span data-ttu-id="ba5ea-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="ba5ea-392">department of immigration</span></span>
- <span data-ttu-id="ba5ea-393">residential address</span><span class="sxs-lookup"><span data-stu-id="ba5ea-393">residential address</span></span>
- <span data-ttu-id="ba5ea-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="ba5ea-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="ba5ea-395">Visa</span><span class="sxs-lookup"><span data-stu-id="ba5ea-395">visa</span></span>
- <span data-ttu-id="ba5ea-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-396">national identity card</span></span>
- <span data-ttu-id="ba5ea-397">passport number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-397">passport number</span></span>
- <span data-ttu-id="ba5ea-398">travel document</span><span class="sxs-lookup"><span data-stu-id="ba5ea-398">travel document</span></span>
- <span data-ttu-id="ba5ea-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="ba5ea-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="ba5ea-400">Номер налогоплательщика для Австралии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-401">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-401">Format</span></span>

<span data-ttu-id="ba5ea-402">8–9 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-403">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-403">Pattern</span></span>

<span data-ttu-id="ba5ea-404">8–9 цифр, которые обычно разделены пробелами указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="ba5ea-405">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-405">Three digits</span></span> 
- <span data-ttu-id="ba5ea-406">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-406">An optional space</span></span> 
- <span data-ttu-id="ba5ea-407">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-407">Three digits</span></span> 
- <span data-ttu-id="ba5ea-408">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-408">An optional space</span></span> 
- <span data-ttu-id="ba5ea-409">2–3 цифры, причем последняя цифра — контрольная</span><span class="sxs-lookup"><span data-stu-id="ba5ea-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-410">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-410">Checksum</span></span>

<span data-ttu-id="ba5ea-411">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-412">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-412">Definition</span></span>

<span data-ttu-id="ba5ea-413">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-414">функция Func_australian_tax_file_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-415">ни одно ключевое слово из Keyword_Australia_Tax_File_Number или Keyword_number_exclusions не найдено;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="ba5ea-416">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-417">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="ba5ea-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="ba5ea-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-419">australian business number</span></span>
- <span data-ttu-id="ba5ea-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="ba5ea-420">marginal tax rate</span></span>
- <span data-ttu-id="ba5ea-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="ba5ea-421">medicare levy</span></span>
- <span data-ttu-id="ba5ea-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-422">portfolio number</span></span>
- <span data-ttu-id="ba5ea-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="ba5ea-423">service veterans</span></span>
- <span data-ttu-id="ba5ea-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="ba5ea-424">withholding tax</span></span>
- <span data-ttu-id="ba5ea-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="ba5ea-425">individual tax return</span></span>
- <span data-ttu-id="ba5ea-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="ba5ea-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="ba5ea-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="ba5ea-428">00000001</span><span class="sxs-lookup"><span data-stu-id="ba5ea-428">00000000</span></span>
- <span data-ttu-id="ba5ea-429">11111111</span><span class="sxs-lookup"><span data-stu-id="ba5ea-429">11111111</span></span>
- <span data-ttu-id="ba5ea-430">22222222</span><span class="sxs-lookup"><span data-stu-id="ba5ea-430">22222222</span></span>
- <span data-ttu-id="ba5ea-431">33333333</span><span class="sxs-lookup"><span data-stu-id="ba5ea-431">33333333</span></span>
- <span data-ttu-id="ba5ea-432">44444444</span><span class="sxs-lookup"><span data-stu-id="ba5ea-432">44444444</span></span>
- <span data-ttu-id="ba5ea-433">55555555</span><span class="sxs-lookup"><span data-stu-id="ba5ea-433">55555555</span></span>
- <span data-ttu-id="ba5ea-434">66666666</span><span class="sxs-lookup"><span data-stu-id="ba5ea-434">66666666</span></span>
- <span data-ttu-id="ba5ea-435">77777777</span><span class="sxs-lookup"><span data-stu-id="ba5ea-435">77777777</span></span>
- <span data-ttu-id="ba5ea-436">88888888</span><span class="sxs-lookup"><span data-stu-id="ba5ea-436">88888888</span></span>
- <span data-ttu-id="ba5ea-437">99999999</span><span class="sxs-lookup"><span data-stu-id="ba5ea-437">99999999</span></span>
- <span data-ttu-id="ba5ea-438">000000000</span><span class="sxs-lookup"><span data-stu-id="ba5ea-438">000000000</span></span>
- <span data-ttu-id="ba5ea-439">111111111</span><span class="sxs-lookup"><span data-stu-id="ba5ea-439">111111111</span></span>
- <span data-ttu-id="ba5ea-440">222222222</span><span class="sxs-lookup"><span data-stu-id="ba5ea-440">222222222</span></span>
- <span data-ttu-id="ba5ea-441">333333333</span><span class="sxs-lookup"><span data-stu-id="ba5ea-441">333333333</span></span>
- <span data-ttu-id="ba5ea-442">444444444</span><span class="sxs-lookup"><span data-stu-id="ba5ea-442">444444444</span></span>
- <span data-ttu-id="ba5ea-443">555555555</span><span class="sxs-lookup"><span data-stu-id="ba5ea-443">555555555</span></span>
- <span data-ttu-id="ba5ea-444">666666666</span><span class="sxs-lookup"><span data-stu-id="ba5ea-444">666666666</span></span>
- <span data-ttu-id="ba5ea-445">777777777</span><span class="sxs-lookup"><span data-stu-id="ba5ea-445">777777777</span></span>
- <span data-ttu-id="ba5ea-446">888888888</span><span class="sxs-lookup"><span data-stu-id="ba5ea-446">888888888</span></span>
- <span data-ttu-id="ba5ea-447">999999999</span><span class="sxs-lookup"><span data-stu-id="ba5ea-447">999999999</span></span>
- <span data-ttu-id="ba5ea-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="ba5ea-448">0000000000</span></span>
- <span data-ttu-id="ba5ea-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="ba5ea-449">1111111111</span></span>
- <span data-ttu-id="ba5ea-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="ba5ea-450">2222222222</span></span>
- <span data-ttu-id="ba5ea-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="ba5ea-451">3333333333</span></span>
- <span data-ttu-id="ba5ea-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="ba5ea-452">4444444444</span></span>
- <span data-ttu-id="ba5ea-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="ba5ea-453">5555555555</span></span>
- <span data-ttu-id="ba5ea-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="ba5ea-454">6666666666</span></span>
- <span data-ttu-id="ba5ea-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="ba5ea-455">7777777777</span></span>
- <span data-ttu-id="ba5ea-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="ba5ea-456">8888888888</span></span>
- <span data-ttu-id="ba5ea-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="ba5ea-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="ba5ea-458">Ключ проверки подлинности Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="ba5ea-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-459">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-459">Format</span></span>

<span data-ttu-id="ba5ea-460">Строка "DocumentDb", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-461">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-461">Pattern</span></span>

- <span data-ttu-id="ba5ea-462">Строка "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="ba5ea-463">Любая комбинация из 3-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-464">Символ "больше" (>), знак равенства (=), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="ba5ea-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="ba5ea-465">Любая комбинация 86 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ba5ea-466">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-467">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-467">Checksum</span></span>

<span data-ttu-id="ba5ea-468">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-469">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-469">Definition</span></span>

<span data-ttu-id="ba5ea-470">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-471">Регулярное выражение CEP_Regex_AzureDocumentDBAuthKey находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-472">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-473">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-475">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-476">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-476">contoso</span></span>
- <span data-ttu-id="ba5ea-477">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-477">fabrikam</span></span>
- <span data-ttu-id="ba5ea-478">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-478">northwind</span></span>
- <span data-ttu-id="ba5ea-479">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-479">sandbox</span></span>
- <span data-ttu-id="ba5ea-480">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-480">onebox</span></span>
- <span data-ttu-id="ba5ea-481">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-481">localhost</span></span>
- <span data-ttu-id="ba5ea-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-482">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-483">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-484">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-484">com</span></span>
- <span data-ttu-id="ba5ea-485">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-486">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="ba5ea-487">Строка подключения к базе данных Azure IAAS и строка подключения к SQL Azure</span><span class="sxs-lookup"><span data-stu-id="ba5ea-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-488">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-488">Format</span></span>

<span data-ttu-id="ba5ea-489">Строка "Server", "Server" или "Data Source", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "клаудапп. Azure".</span><span class="sxs-lookup"><span data-stu-id="ba5ea-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-490">com "или" клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-491">NET "или" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-492">NET ", а также строку" Password "или" Password "или" pwd ".</span><span class="sxs-lookup"><span data-stu-id="ba5ea-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-493">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-493">Pattern</span></span>

- <span data-ttu-id="ba5ea-494">Строка "Server", "Server" или "Data Source"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="ba5ea-495">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-496">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-496">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-497">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-498">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-499">Строка "клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-500">com "," клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-501">NET "или" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-502">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-502">net"</span></span>
- <span data-ttu-id="ba5ea-503">Любая комбинация из 1-300 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-504">Строка "Password", "Password" или "pwd"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="ba5ea-505">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-506">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-506">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-507">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-508">Один или несколько символов, не отделяющая точку с запятой (;), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="ba5ea-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="ba5ea-509">Точка с запятой (;), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="ba5ea-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-510">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-510">Checksum</span></span>

<span data-ttu-id="ba5ea-511">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-512">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-512">Definition</span></span>

<span data-ttu-id="ba5ea-513">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-514">Регулярное выражение CEP_Regex_AzureConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-515">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-516">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-518">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-519">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-519">contoso</span></span>
- <span data-ttu-id="ba5ea-520">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-520">fabrikam</span></span>
- <span data-ttu-id="ba5ea-521">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-521">northwind</span></span>
- <span data-ttu-id="ba5ea-522">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-522">sandbox</span></span>
- <span data-ttu-id="ba5ea-523">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-523">onebox</span></span>
- <span data-ttu-id="ba5ea-524">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-524">localhost</span></span>
- <span data-ttu-id="ba5ea-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-525">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-526">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-527">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-527">com</span></span>
- <span data-ttu-id="ba5ea-528">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-529">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="ba5ea-530">Строка подключения Azure IoT</span><span class="sxs-lookup"><span data-stu-id="ba5ea-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-531">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-531">Format</span></span>

<span data-ttu-id="ba5ea-532">Строка "HostName", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, включая строки "Azure — Devices.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-533">NET "и" Шаредакцесскэй ".</span><span class="sxs-lookup"><span data-stu-id="ba5ea-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-534">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-534">Pattern</span></span>

- <span data-ttu-id="ba5ea-535">Строка "HostName"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-535">The string "HostName"</span></span>
- <span data-ttu-id="ba5ea-536">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-537">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-537">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-538">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-539">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-540">Строка "Azure — Devices.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-541">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-541">net"</span></span>
- <span data-ttu-id="ba5ea-542">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-543">Строка "Шаредакцесскэй"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="ba5ea-544">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-545">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-545">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-546">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-547">Любая комбинация 43 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ba5ea-548">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-549">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-549">Checksum</span></span>

<span data-ttu-id="ba5ea-550">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-551">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-551">Definition</span></span>

<span data-ttu-id="ba5ea-552">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-553">Регулярное выражение CEP_Regex_AzureIoTConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-554">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-555">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-557">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-558">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-558">contoso</span></span>
- <span data-ttu-id="ba5ea-559">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-559">fabrikam</span></span>
- <span data-ttu-id="ba5ea-560">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-560">northwind</span></span>
- <span data-ttu-id="ba5ea-561">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-561">sandbox</span></span>
- <span data-ttu-id="ba5ea-562">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-562">onebox</span></span>
- <span data-ttu-id="ba5ea-563">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-563">localhost</span></span>
- <span data-ttu-id="ba5ea-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-564">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-565">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-566">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-566">com</span></span>
- <span data-ttu-id="ba5ea-567">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-568">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="ba5ea-569">Пароль для параметра публикации Azure</span><span class="sxs-lookup"><span data-stu-id="ba5ea-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-570">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-570">Format</span></span>

<span data-ttu-id="ba5ea-571">Строка "усерпвд =", за которой следует буквенно-цифровая строка.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-572">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-572">Pattern</span></span>

- <span data-ttu-id="ba5ea-573">Строка "усерпвд ="</span><span class="sxs-lookup"><span data-stu-id="ba5ea-573">The string "userpwd="</span></span>
- <span data-ttu-id="ba5ea-574">Любая комбинация букв или цифр в нижнем регистре 60</span><span class="sxs-lookup"><span data-stu-id="ba5ea-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="ba5ea-575">Знак кавычек (")</span><span class="sxs-lookup"><span data-stu-id="ba5ea-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-576">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-576">Checksum</span></span>

<span data-ttu-id="ba5ea-577">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-578">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-578">Definition</span></span>

<span data-ttu-id="ba5ea-579">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-580">Регулярное выражение CEP_Regex_AzurePublishSettingPasswords находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-581">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="ba5ea-582">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-584">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-585">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-585">contoso</span></span>
- <span data-ttu-id="ba5ea-586">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-586">fabrikam</span></span>
- <span data-ttu-id="ba5ea-587">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-587">northwind</span></span>
- <span data-ttu-id="ba5ea-588">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-588">sandbox</span></span>
- <span data-ttu-id="ba5ea-589">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-589">onebox</span></span>
- <span data-ttu-id="ba5ea-590">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-590">localhost</span></span>
- <span data-ttu-id="ba5ea-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-591">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-592">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-593">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-593">com</span></span>
- <span data-ttu-id="ba5ea-594">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-595">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="ba5ea-596">Строка подключения к кэшу Azure Redis</span><span class="sxs-lookup"><span data-stu-id="ba5ea-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-597">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-597">Format</span></span>

<span data-ttu-id="ba5ea-598">Строка "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-599">NET, за которыми следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "Password" или "pwd".</span><span class="sxs-lookup"><span data-stu-id="ba5ea-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-600">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-600">Pattern</span></span>

- <span data-ttu-id="ba5ea-601">Строка "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-602">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-602">net"</span></span>
- <span data-ttu-id="ba5ea-603">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-604">Строка "Password" или "pwd"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="ba5ea-605">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-606">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-606">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-607">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-608">Любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ba5ea-609">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-610">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-610">Checksum</span></span>

<span data-ttu-id="ba5ea-611">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-612">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-612">Definition</span></span>

<span data-ttu-id="ba5ea-613">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-614">Регулярное выражение CEP_Regex_AzureRedisCacheConnectionString находит содержимое, которое соответствует шаблону..</span><span class="sxs-lookup"><span data-stu-id="ba5ea-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="ba5ea-615">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-616">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-618">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-619">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-619">contoso</span></span>
- <span data-ttu-id="ba5ea-620">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-620">fabrikam</span></span>
- <span data-ttu-id="ba5ea-621">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-621">northwind</span></span>
- <span data-ttu-id="ba5ea-622">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-622">sandbox</span></span>
- <span data-ttu-id="ba5ea-623">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-623">onebox</span></span>
- <span data-ttu-id="ba5ea-624">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-624">localhost</span></span>
- <span data-ttu-id="ba5ea-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-625">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-626">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-627">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-627">com</span></span>
- <span data-ttu-id="ba5ea-628">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-629">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="ba5ea-630">SAS Azure</span><span class="sxs-lookup"><span data-stu-id="ba5ea-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-631">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-631">Format</span></span>

<span data-ttu-id="ba5ea-632">Строка "SIG", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-633">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-633">Pattern</span></span>

- <span data-ttu-id="ba5ea-634">Строка "SIG"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-634">The string "sig"</span></span>
- <span data-ttu-id="ba5ea-635">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-636">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-636">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-637">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-638">Любое сочетание 43-53 символов, которые являются буквами нижнего или верхнего регистра, цифрами или знаком процента (%)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="ba5ea-639">Строка "% 3D"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-639">The string "%3d"</span></span>
- <span data-ttu-id="ba5ea-640">Любой символ, который не является буквой нижнего или верхнего регистра, цифрой или знаком процента (%)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-641">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-641">Checksum</span></span>

<span data-ttu-id="ba5ea-642">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-643">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-643">Definition</span></span>

<span data-ttu-id="ba5ea-644">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-645">Регулярное выражение CEP_Regex_AzureSAS находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="ba5ea-646">Строка подключения к служебной шине Azure</span><span class="sxs-lookup"><span data-stu-id="ba5ea-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-647">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-647">Format</span></span>

<span data-ttu-id="ba5ea-648">Строка "EndPoint", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строки "сервицебус. Windows.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-649">NET "и" Шаредакцескэй ".</span><span class="sxs-lookup"><span data-stu-id="ba5ea-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-650">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-650">Pattern</span></span>

- <span data-ttu-id="ba5ea-651">Строка "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-651">The string "EndPoint"</span></span>
- <span data-ttu-id="ba5ea-652">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-653">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-653">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-654">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-655">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-656">Строка "сервицебус. Windows.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-657">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-657">net"</span></span>
- <span data-ttu-id="ba5ea-658">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-659">Строка "Шаредакцесскэй"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="ba5ea-660">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-661">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-661">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-662">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-663">Любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ba5ea-664">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-665">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-665">Checksum</span></span>

<span data-ttu-id="ba5ea-666">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-667">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-667">Definition</span></span>

<span data-ttu-id="ba5ea-668">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-669">Регулярное выражение CEP_Regex_AzureServiceBusConnectionString находит содержимое, которое соответствует шаблону..</span><span class="sxs-lookup"><span data-stu-id="ba5ea-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="ba5ea-670">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-671">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-673">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-674">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-674">contoso</span></span>
- <span data-ttu-id="ba5ea-675">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-675">fabrikam</span></span>
- <span data-ttu-id="ba5ea-676">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-676">northwind</span></span>
- <span data-ttu-id="ba5ea-677">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-677">sandbox</span></span>
- <span data-ttu-id="ba5ea-678">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-678">onebox</span></span>
- <span data-ttu-id="ba5ea-679">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-679">localhost</span></span>
- <span data-ttu-id="ba5ea-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-680">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-681">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-682">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-682">com</span></span>
- <span data-ttu-id="ba5ea-683">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-684">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="ba5ea-685">Ключ учетной записи хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="ba5ea-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-686">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-686">Format</span></span>

<span data-ttu-id="ba5ea-687">Строка "Дефаултендпоинтспротокол", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="ba5ea-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-688">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-688">Pattern</span></span>

- <span data-ttu-id="ba5ea-689">Строка "Дефаултендпоинтспротокол"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="ba5ea-690">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-691">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-691">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-692">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-693">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-694">Строка "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-694">The string "AccountKey"</span></span>
- <span data-ttu-id="ba5ea-695">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-696">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-696">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-697">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="ba5ea-698">Любое сочетание 86 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ba5ea-699">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-700">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-700">Checksum</span></span>

<span data-ttu-id="ba5ea-701">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-702">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-702">Definition</span></span>

<span data-ttu-id="ba5ea-703">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-704">Регулярное выражение CEP_Regex_AzureStorageAccountKey находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-705">Регулярное выражение CEP_AzureEmulatorStorageAccountFilter не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-706">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-707">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="ba5ea-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="ba5ea-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="ba5ea-709">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/Кбхбексогмгв = =</span><span class="sxs-lookup"><span data-stu-id="ba5ea-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-712">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-713">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-713">contoso</span></span>
- <span data-ttu-id="ba5ea-714">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-714">fabrikam</span></span>
- <span data-ttu-id="ba5ea-715">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-715">northwind</span></span>
- <span data-ttu-id="ba5ea-716">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-716">sandbox</span></span>
- <span data-ttu-id="ba5ea-717">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-717">onebox</span></span>
- <span data-ttu-id="ba5ea-718">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-718">localhost</span></span>
- <span data-ttu-id="ba5ea-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-719">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-720">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-721">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-721">com</span></span>
- <span data-ttu-id="ba5ea-722">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-723">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="ba5ea-724">Ключ учетной записи хранилища Azure (общий)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-725">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-725">Format</span></span>

<span data-ttu-id="ba5ea-726">Любая комбинация 86 строчных или прописных букв, цифр, знаков косой черты (/) или знака плюса (+) перед или за ними следуют символы, указанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-727">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-727">Pattern</span></span>

- <span data-ttu-id="ba5ea-728">0-1 из символа "больше" (>), апостроф ('), знак равенства (=), знак кавычек (") или решетка (#)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="ba5ea-729">Любое сочетание 86 символов, которые представляют собой буквы в нижнем или верхнем регистре, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ba5ea-730">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="ba5ea-731">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-731">Checksum</span></span>

<span data-ttu-id="ba5ea-732">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-733">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-733">Definition</span></span>

<span data-ttu-id="ba5ea-734">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-735">Регулярное выражение CEP_Regex_AzureStorageAccountKeyGeneric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="ba5ea-736">Номер национального документа для Бельгии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-737">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-737">Format</span></span>

<span data-ttu-id="ba5ea-738">11 цифр, а также разделители.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-739">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-739">Pattern</span></span>

<span data-ttu-id="ba5ea-740">11 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="ba5ea-741">шесть цифр и две точки в формате ГГ.ММ.ДД для даты рождения;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="ba5ea-742">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-742">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-743">три последовательные цифры (нечетные для мужчин, четные для женщин);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="ba5ea-744">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-744">A period</span></span> 
- <span data-ttu-id="ba5ea-745">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-746">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-746">Checksum</span></span>

<span data-ttu-id="ba5ea-747">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-748">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-748">Definition</span></span>

<span data-ttu-id="ba5ea-749">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-750">функция Func_belgium_national_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-751">находится ключевое слово из Keyword_belgium_national_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="ba5ea-752">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-753">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="ba5ea-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="ba5ea-755">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-755">Identity</span></span>
- <span data-ttu-id="ba5ea-756">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="ba5ea-756">Registration</span></span>
- <span data-ttu-id="ba5ea-757">Процедура</span><span class="sxs-lookup"><span data-stu-id="ba5ea-757">Identification</span></span> 
- <span data-ttu-id="ba5ea-758">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-758">ID</span></span> 
- <span data-ttu-id="ba5ea-759">идентитеитскаарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-759">Identiteitskaart</span></span>
- <span data-ttu-id="ba5ea-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="ba5ea-760">Registratie nummer</span></span> 
- <span data-ttu-id="ba5ea-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="ba5ea-761">Identificatie nummer</span></span> 
- <span data-ttu-id="ba5ea-762">идентитеит</span><span class="sxs-lookup"><span data-stu-id="ba5ea-762">Identiteit</span></span>
- <span data-ttu-id="ba5ea-763">регистратие</span><span class="sxs-lookup"><span data-stu-id="ba5ea-763">Registratie</span></span>
- <span data-ttu-id="ba5ea-764">идентификатие</span><span class="sxs-lookup"><span data-stu-id="ba5ea-764">Identificatie</span></span> 
- <span data-ttu-id="ba5ea-765">Д'идентитé корзины</span><span class="sxs-lookup"><span data-stu-id="ba5ea-765">Carte d'identité</span></span> 
- <span data-ttu-id="ba5ea-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="ba5ea-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="ba5ea-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-767">numéro d'identification</span></span>
- <span data-ttu-id="ba5ea-768">идентитé</span><span class="sxs-lookup"><span data-stu-id="ba5ea-768">identité</span></span> 
- <span data-ttu-id="ba5ea-769">инскриптион</span><span class="sxs-lookup"><span data-stu-id="ba5ea-769">inscription</span></span> 
- <span data-ttu-id="ba5ea-770">идентификатион</span><span class="sxs-lookup"><span data-stu-id="ba5ea-770">Identifikation</span></span>
- <span data-ttu-id="ba5ea-771">идентифизиерунг</span><span class="sxs-lookup"><span data-stu-id="ba5ea-771">Identifizierung</span></span>
- <span data-ttu-id="ba5ea-772">идентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-772">Identifikationsnummer</span></span>
- <span data-ttu-id="ba5ea-773">персоналаусвеис</span><span class="sxs-lookup"><span data-stu-id="ba5ea-773">Personalausweis</span></span>
- <span data-ttu-id="ba5ea-774">регистриерунг</span><span class="sxs-lookup"><span data-stu-id="ba5ea-774">Registrierung</span></span>
- <span data-ttu-id="ba5ea-775">регистратионснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="ba5ea-776">Номер CPF для Бразилии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-777">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-777">Format</span></span>

<span data-ttu-id="ba5ea-778">11 цифр, которые включают проверочную цифру и могут быть форматированными или неформатированными.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-779">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-779">Pattern</span></span>

<span data-ttu-id="ba5ea-780">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="ba5ea-780">Formatted:</span></span>
- <span data-ttu-id="ba5ea-781">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-781">Three digits</span></span> 
- <span data-ttu-id="ba5ea-782">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-782">A period</span></span> 
- <span data-ttu-id="ba5ea-783">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-783">Three digits</span></span> 
- <span data-ttu-id="ba5ea-784">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-784">A period</span></span> 
- <span data-ttu-id="ba5ea-785">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-785">Three digits</span></span> 
- <span data-ttu-id="ba5ea-786">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-786">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-787">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-787">Two digits which are check digits</span></span>

<span data-ttu-id="ba5ea-788">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="ba5ea-788">Unformatted:</span></span>
- <span data-ttu-id="ba5ea-789">11 цифр, где две последние цифры — проверочные.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-790">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-790">Checksum</span></span>

<span data-ttu-id="ba5ea-791">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-792">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-792">Definition</span></span>

<span data-ttu-id="ba5ea-793">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-794">функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-795">находится ключевое слово из Keyword_brazil_cpf;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="ba5ea-796">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-796">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-797">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-798">функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-799">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-800">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="ba5ea-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="ba5ea-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="ba5ea-802">CPF</span><span class="sxs-lookup"><span data-stu-id="ba5ea-802">CPF</span></span>
- <span data-ttu-id="ba5ea-803">Процедура</span><span class="sxs-lookup"><span data-stu-id="ba5ea-803">Identification</span></span>
- <span data-ttu-id="ba5ea-804">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="ba5ea-804">Registration</span></span>
- <span data-ttu-id="ba5ea-805">Реализации</span><span class="sxs-lookup"><span data-stu-id="ba5ea-805">Revenue</span></span>
- <span data-ttu-id="ba5ea-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="ba5ea-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="ba5ea-807">импосто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-807">Imposto</span></span> 
- <span data-ttu-id="ba5ea-808">идентификаçãо</span><span class="sxs-lookup"><span data-stu-id="ba5ea-808">Identificação</span></span> 
- <span data-ttu-id="ba5ea-809">инскриçãо</span><span class="sxs-lookup"><span data-stu-id="ba5ea-809">Inscrição</span></span> 
- <span data-ttu-id="ba5ea-810">рецеита</span><span class="sxs-lookup"><span data-stu-id="ba5ea-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="ba5ea-811">Номер юридического лица для Бразилии (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-812">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-812">Format</span></span>

<span data-ttu-id="ba5ea-813">14 цифр, которые включают регистрационный номер, номер филиала и проверочные цифры, а также разделители.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-814">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-814">Pattern</span></span>
<span data-ttu-id="ba5ea-815">14 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="ba5ea-816">две цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-816">Two digits</span></span> 
- <span data-ttu-id="ba5ea-817">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-817">A period</span></span> 
- <span data-ttu-id="ba5ea-818">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-818">Three digits</span></span> 
- <span data-ttu-id="ba5ea-819">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-819">A period</span></span> 
- <span data-ttu-id="ba5ea-820">три цифры (эти первые восемь цифр — регистрационный номер);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="ba5ea-821">косая черта;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-821">A forward slash</span></span> 
- <span data-ttu-id="ba5ea-822">номер отделения из четырех цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-822">Four-digit branch number</span></span> 
- <span data-ttu-id="ba5ea-823">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-823">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-824">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-825">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-825">Checksum</span></span>

<span data-ttu-id="ba5ea-826">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-827">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-827">Definition</span></span>

<span data-ttu-id="ba5ea-828">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-829">функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-830">находится ключевое слово из Keyword_brazil_cnpj;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="ba5ea-831">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-831">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-832">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-833">функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-834">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-835">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="ba5ea-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="ba5ea-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="ba5ea-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-837">CNPJ</span></span> 
- <span data-ttu-id="ba5ea-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="ba5ea-838">CNPJ/MF</span></span> 
- <span data-ttu-id="ba5ea-839">CNPJ – MF</span><span class="sxs-lookup"><span data-stu-id="ba5ea-839">CNPJ-MF</span></span> 
- <span data-ttu-id="ba5ea-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="ba5ea-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="ba5ea-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="ba5ea-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="ba5ea-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="ba5ea-842">Legal entity</span></span> 
- <span data-ttu-id="ba5ea-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="ba5ea-843">Legal entities</span></span> 
- <span data-ttu-id="ba5ea-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="ba5ea-844">Registration Status</span></span> 
- <span data-ttu-id="ba5ea-845">Бизнес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-845">Business</span></span> 
- <span data-ttu-id="ba5ea-846">Company</span><span class="sxs-lookup"><span data-stu-id="ba5ea-846">Company</span></span>
- <span data-ttu-id="ba5ea-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-847">CNPJ</span></span> 
- <span data-ttu-id="ba5ea-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="ba5ea-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="ba5ea-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="ba5ea-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="ba5ea-850">кгк</span><span class="sxs-lookup"><span data-stu-id="ba5ea-850">CGC</span></span> 
- <span data-ttu-id="ba5ea-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="ba5ea-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="ba5ea-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="ba5ea-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="ba5ea-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="ba5ea-853">Situação cadastral</span></span> 
- <span data-ttu-id="ba5ea-854">инскриçãо</span><span class="sxs-lookup"><span data-stu-id="ba5ea-854">Inscrição</span></span> 
- <span data-ttu-id="ba5ea-855">емпреса</span><span class="sxs-lookup"><span data-stu-id="ba5ea-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="ba5ea-856">	Номер внутреннего удостоверения личности для Бразилии (RG)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-857">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-857">Format</span></span>

<span data-ttu-id="ba5ea-858">Registro Geral (старый формат): девять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="ba5ea-859">Registro de identidade (RIC) (новый формат): 11 цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-860">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-860">Pattern</span></span>

<span data-ttu-id="ba5ea-861">Registro Geral (старый формат):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="ba5ea-862">две цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-862">Two digits</span></span> 
- <span data-ttu-id="ba5ea-863">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-863">A period</span></span> 
- <span data-ttu-id="ba5ea-864">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-864">Three digits</span></span> 
- <span data-ttu-id="ba5ea-865">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-865">A period</span></span> 
- <span data-ttu-id="ba5ea-866">три цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-866">Three digits</span></span> 
- <span data-ttu-id="ba5ea-867">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-867">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-868">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-868">One digit which is a check digit</span></span>

<span data-ttu-id="ba5ea-869">Registro de identidade (RIC) (новый формат):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="ba5ea-870">10 цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-870">10 digits</span></span> 
- <span data-ttu-id="ba5ea-871">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-871">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-872">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-873">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-873">Checksum</span></span>

<span data-ttu-id="ba5ea-874">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-875">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-875">Definition</span></span>

<span data-ttu-id="ba5ea-876">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-877">функция Func_brazil_rg находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-878">находится ключевое слово из Keyword_brazil_rg;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="ba5ea-879">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-879">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-880">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-881">функция Func_brazil_rg находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-882">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-883">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="ba5ea-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="ba5ea-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="ba5ea-885">Кéдула de identidade Identity Card National ID нúмеро de ррегистро Registro de Иидентидаде Registro Geral RG (это ключевое слово учитывает регистр) RIC (это ключевое слово учитывает регистр).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="ba5ea-886">Номер банковского счета для Канады</span><span class="sxs-lookup"><span data-stu-id="ba5ea-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-887">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-887">Format</span></span>

<span data-ttu-id="ba5ea-888">Семь или двенадцать цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-889">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-889">Pattern</span></span>

<span data-ttu-id="ba5ea-890">Номер банковского счета для Канады — семь или двенадцать цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="ba5ea-891">Транзитный номер банковского счета в Канаде имеет указанный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="ba5ea-892">пять цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-892">Five digits</span></span> 
- <span data-ttu-id="ba5ea-893">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-893">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-894">Три цифры или</span><span class="sxs-lookup"><span data-stu-id="ba5ea-894">Three digits OR</span></span>
- <span data-ttu-id="ba5ea-895">ноль "0";</span><span class="sxs-lookup"><span data-stu-id="ba5ea-895">A zero "0"</span></span> 
- <span data-ttu-id="ba5ea-896">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-897">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-897">Checksum</span></span>

<span data-ttu-id="ba5ea-898">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-899">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-899">Definition</span></span>

<span data-ttu-id="ba5ea-900">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-901">регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-902">находится ключевое слово из Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="ba5ea-903">регулярное выражение Regex_canada_bank_account_transit_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="ba5ea-904">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-905">регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-906">находится ключевое слово из Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-907">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="ba5ea-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="ba5ea-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="ba5ea-909">canada savings bonds</span></span>
- <span data-ttu-id="ba5ea-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="ba5ea-910">canada revenue agency</span></span>
- <span data-ttu-id="ba5ea-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="ba5ea-911">canadian financial institution</span></span>
- <span data-ttu-id="ba5ea-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="ba5ea-912">direct deposit form</span></span>
- <span data-ttu-id="ba5ea-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="ba5ea-913">canadian citizen</span></span>
- <span data-ttu-id="ba5ea-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="ba5ea-914">legal representative</span></span>
- <span data-ttu-id="ba5ea-915">notary public</span><span class="sxs-lookup"><span data-stu-id="ba5ea-915">notary public</span></span>
- <span data-ttu-id="ba5ea-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="ba5ea-916">commissioner for oaths</span></span>
- <span data-ttu-id="ba5ea-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-917">child care benefit</span></span>
- <span data-ttu-id="ba5ea-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="ba5ea-918">universal child care</span></span>
- <span data-ttu-id="ba5ea-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-919">canada child tax benefit</span></span>
- <span data-ttu-id="ba5ea-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-920">income tax benefit</span></span>
- <span data-ttu-id="ba5ea-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="ba5ea-921">harmonized sales tax</span></span>
- <span data-ttu-id="ba5ea-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-922">social insurance number</span></span>
- <span data-ttu-id="ba5ea-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="ba5ea-923">income tax refund</span></span>
- <span data-ttu-id="ba5ea-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-924">child tax benefit</span></span>
- <span data-ttu-id="ba5ea-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="ba5ea-925">territorial payments</span></span>
- <span data-ttu-id="ba5ea-926">institution number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-926">institution number</span></span>
- <span data-ttu-id="ba5ea-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="ba5ea-927">deposit request</span></span>
- <span data-ttu-id="ba5ea-928">banking information</span><span class="sxs-lookup"><span data-stu-id="ba5ea-928">banking information</span></span>
- <span data-ttu-id="ba5ea-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="ba5ea-930">Номер водительского удостоверения для Канады</span><span class="sxs-lookup"><span data-stu-id="ba5ea-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-931">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-931">Format</span></span>

<span data-ttu-id="ba5ea-932">Зависит от провинции.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-933">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-933">Pattern</span></span>

<span data-ttu-id="ba5ea-934">Различные шаблоны, соответствующие провинциям Альберта, Британская Колумбия, Манитоба, Нью-Брансуик, Ньюфаундленд и Лабрадор, Новая Шотландия, Онтарио, Остров Принца Эдуарда, Квебек и Саскачеван.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-935">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-935">Checksum</span></span>

<span data-ttu-id="ba5ea-936">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-937">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-937">Definition</span></span>

<span data-ttu-id="ba5ea-938">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-939">функция Func_[province_name]_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-940">находится ключевое слово из Keyword_[province_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="ba5ea-941">находится ключевое слово из Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-942">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="ba5ea-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="ba5ea-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="ba5ea-944">Аббревиатура провинции, например AB.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="ba5ea-945">Название провинции, например Альберта.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="ba5ea-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="ba5ea-947">DL</span><span class="sxs-lookup"><span data-stu-id="ba5ea-947">DL</span></span>
- <span data-ttu-id="ba5ea-948">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="ba5ea-948">DLS</span></span>
- <span data-ttu-id="ba5ea-949">кдл</span><span class="sxs-lookup"><span data-stu-id="ba5ea-949">CDL</span></span>
- <span data-ttu-id="ba5ea-950">кдлс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-950">CDLS</span></span>
- <span data-ttu-id="ba5ea-951">дриверлик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-951">DriverLic</span></span>
- <span data-ttu-id="ba5ea-952">дриверликс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-952">DriverLics</span></span>
- <span data-ttu-id="ba5ea-953">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-953">DriverLicense</span></span>
- <span data-ttu-id="ba5ea-954">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-954">DriverLicenses</span></span>
- <span data-ttu-id="ba5ea-955">дриверлиценце</span><span class="sxs-lookup"><span data-stu-id="ba5ea-955">DriverLicence</span></span>
- <span data-ttu-id="ba5ea-956">дриверлиценцес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-956">DriverLicences</span></span>
- <span data-ttu-id="ba5ea-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-957">Driver Lic</span></span>
- <span data-ttu-id="ba5ea-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-958">Driver Lics</span></span>
- <span data-ttu-id="ba5ea-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-959">Driver License</span></span>
- <span data-ttu-id="ba5ea-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-960">Driver Licenses</span></span>
- <span data-ttu-id="ba5ea-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-961">Driver Licence</span></span>
- <span data-ttu-id="ba5ea-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-962">Driver Licences</span></span>
- <span data-ttu-id="ba5ea-963">дриверслик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-963">DriversLic</span></span>
- <span data-ttu-id="ba5ea-964">дриверсликс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-964">DriversLics</span></span>
- <span data-ttu-id="ba5ea-965">дриверслиценце</span><span class="sxs-lookup"><span data-stu-id="ba5ea-965">DriversLicence</span></span>
- <span data-ttu-id="ba5ea-966">дриверслиценцес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-966">DriversLicences</span></span>
- <span data-ttu-id="ba5ea-967">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-967">DriversLicense</span></span>
- <span data-ttu-id="ba5ea-968">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-968">DriversLicenses</span></span>
- <span data-ttu-id="ba5ea-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-969">Drivers Lic</span></span>
- <span data-ttu-id="ba5ea-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-970">Drivers Lics</span></span>
- <span data-ttu-id="ba5ea-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-971">Drivers License</span></span>
- <span data-ttu-id="ba5ea-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-972">Drivers Licenses</span></span>
- <span data-ttu-id="ba5ea-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-973">Drivers Licence</span></span>
- <span data-ttu-id="ba5ea-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-974">Drivers Licences</span></span>
- <span data-ttu-id="ba5ea-975">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-975">Driver'Lic</span></span>
- <span data-ttu-id="ba5ea-976">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="ba5ea-976">Driver'Lics</span></span>
- <span data-ttu-id="ba5ea-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-977">Driver'License</span></span>
- <span data-ttu-id="ba5ea-978">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-978">Driver'Licenses</span></span>
- <span data-ttu-id="ba5ea-979">Driver ' Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-979">Driver'Licence</span></span>
- <span data-ttu-id="ba5ea-980">Driver ' Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-980">Driver'Licences</span></span>
- <span data-ttu-id="ba5ea-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-981">Driver' Lic</span></span>
- <span data-ttu-id="ba5ea-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-982">Driver' Lics</span></span>
- <span data-ttu-id="ba5ea-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-983">Driver' License</span></span>
- <span data-ttu-id="ba5ea-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-984">Driver' Licenses</span></span>
- <span data-ttu-id="ba5ea-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-985">Driver' Licence</span></span>
- <span data-ttu-id="ba5ea-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-986">Driver' Licences</span></span>
- <span data-ttu-id="ba5ea-987">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-987">Driver'sLic</span></span>
- <span data-ttu-id="ba5ea-988">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-988">Driver'sLics</span></span>
- <span data-ttu-id="ba5ea-989">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-989">Driver'sLicense</span></span>
- <span data-ttu-id="ba5ea-990">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-990">Driver'sLicenses</span></span>
- <span data-ttu-id="ba5ea-991">дривер'слиценце</span><span class="sxs-lookup"><span data-stu-id="ba5ea-991">Driver'sLicence</span></span>
- <span data-ttu-id="ba5ea-992">дривер'слиценцес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-992">Driver'sLicences</span></span>
- <span data-ttu-id="ba5ea-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-993">Driver's Lic</span></span>
- <span data-ttu-id="ba5ea-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-994">Driver's Lics</span></span>
- <span data-ttu-id="ba5ea-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-995">Driver's License</span></span>
- <span data-ttu-id="ba5ea-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-996">Driver's Licenses</span></span>
- <span data-ttu-id="ba5ea-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-997">Driver's Licence</span></span>
- <span data-ttu-id="ba5ea-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-998">Driver's Licences</span></span>
- <span data-ttu-id="ba5ea-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="ba5ea-999">Permis de Conduire</span></span>
- <span data-ttu-id="ba5ea-1000">id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1000">id</span></span>
- <span data-ttu-id="ba5ea-1001">ids</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1001">ids</span></span>
- <span data-ttu-id="ba5ea-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1002">idcard number</span></span>
- <span data-ttu-id="ba5ea-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1003">idcard numbers</span></span>
- <span data-ttu-id="ba5ea-1004">idcard#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1004">idcard #</span></span>
- <span data-ttu-id="ba5ea-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1005">idcard #s</span></span>
- <span data-ttu-id="ba5ea-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1006">idcard card</span></span>
- <span data-ttu-id="ba5ea-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1007">idcard cards</span></span>
- <span data-ttu-id="ba5ea-1008">идкард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1008">idcard</span></span>
- <span data-ttu-id="ba5ea-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1009">identification number</span></span>
- <span data-ttu-id="ba5ea-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1010">identification numbers</span></span>
- <span data-ttu-id="ba5ea-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1011">identification #</span></span>
- <span data-ttu-id="ba5ea-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1012">identification #s</span></span>
- <span data-ttu-id="ba5ea-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1013">identification card</span></span>
- <span data-ttu-id="ba5ea-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1014">identification cards</span></span>
- <span data-ttu-id="ba5ea-1015">процедура</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1015">identification</span></span> 
- <span data-ttu-id="ba5ea-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1016">DL#</span></span>
- <span data-ttu-id="ba5ea-1017">БИБЛИОТЕК #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1017">DLS#</span></span> 
- <span data-ttu-id="ba5ea-1018">кдл #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1018">CDL#</span></span> 
- <span data-ttu-id="ba5ea-1019">кдлс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1019">CDLS#</span></span> 
- <span data-ttu-id="ba5ea-1020">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1020">DriverLic#</span></span> 
- <span data-ttu-id="ba5ea-1021">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1021">DriverLics#</span></span> 
- <span data-ttu-id="ba5ea-1022">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1022">DriverLicense#</span></span> 
- <span data-ttu-id="ba5ea-1023">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="ba5ea-1024">дриверлиценце #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1024">DriverLicence#</span></span> 
- <span data-ttu-id="ba5ea-1025">дриверлиценцес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1025">DriverLicences#</span></span> 
- <span data-ttu-id="ba5ea-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1026">Driver Lic#</span></span>
- <span data-ttu-id="ba5ea-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1027">Driver Lics#</span></span> 
- <span data-ttu-id="ba5ea-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1028">Driver License#</span></span> 
- <span data-ttu-id="ba5ea-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="ba5ea-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1030">Driver License#</span></span> 
- <span data-ttu-id="ba5ea-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1031">Driver Licences#</span></span> 
- <span data-ttu-id="ba5ea-1032">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1032">DriversLic#</span></span> 
- <span data-ttu-id="ba5ea-1033">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1033">DriversLics#</span></span> 
- <span data-ttu-id="ba5ea-1034">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1034">DriversLicense#</span></span> 
- <span data-ttu-id="ba5ea-1035">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="ba5ea-1036">дриверслиценце #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1036">DriversLicence#</span></span> 
- <span data-ttu-id="ba5ea-1037">дриверслиценцес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1037">DriversLicences#</span></span> 
- <span data-ttu-id="ba5ea-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="ba5ea-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="ba5ea-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1040">Drivers License#</span></span> 
- <span data-ttu-id="ba5ea-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="ba5ea-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="ba5ea-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="ba5ea-1044">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="ba5ea-1045">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="ba5ea-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1046">Driver'License#</span></span> 
- <span data-ttu-id="ba5ea-1047">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="ba5ea-1048">Driver ' Licence #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="ba5ea-1049">Driver ' Licences #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="ba5ea-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="ba5ea-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="ba5ea-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1052">Driver' License#</span></span> 
- <span data-ttu-id="ba5ea-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="ba5ea-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="ba5ea-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="ba5ea-1056">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="ba5ea-1057">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="ba5ea-1058">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="ba5ea-1059">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="ba5ea-1060">дривер'слиценце #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="ba5ea-1061">дривер'слиценцес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="ba5ea-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="ba5ea-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="ba5ea-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1064">Driver's License#</span></span> 
- <span data-ttu-id="ba5ea-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="ba5ea-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="ba5ea-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="ba5ea-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="ba5ea-1069">кодов #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1069">id#</span></span> 
- <span data-ttu-id="ba5ea-1070">идентификаторы #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1070">ids#</span></span> 
- <span data-ttu-id="ba5ea-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1071">idcard card#</span></span> 
- <span data-ttu-id="ba5ea-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1072">idcard cards#</span></span> 
- <span data-ttu-id="ba5ea-1073">идкард #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1073">idcard#</span></span> 
- <span data-ttu-id="ba5ea-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1074">identification card#</span></span> 
- <span data-ttu-id="ba5ea-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1075">identification cards#</span></span> 
- <span data-ttu-id="ba5ea-1076">процедура #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="ba5ea-1077">Номер службы здравоохранения для Канады</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1078">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1078">Format</span></span>

<span data-ttu-id="ba5ea-1079">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1080">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1080">Pattern</span></span>

<span data-ttu-id="ba5ea-1081">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1082">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1082">Checksum</span></span>

<span data-ttu-id="ba5ea-1083">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1084">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1084">Definition</span></span>

<span data-ttu-id="ba5ea-1085">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1086">регулярное выражение Regex_canada_health_service_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1087">находится ключевое слово из Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1088">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="ba5ea-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="ba5ea-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1090">personal health number</span></span>
- <span data-ttu-id="ba5ea-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1091">patient information</span></span>
- <span data-ttu-id="ba5ea-1092">health services</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1092">health services</span></span>
- <span data-ttu-id="ba5ea-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1093">speciality services</span></span>
- <span data-ttu-id="ba5ea-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1094">automobile accident</span></span>
- <span data-ttu-id="ba5ea-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1095">patient hospital</span></span>
- <span data-ttu-id="ba5ea-1096">псичиатрист</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1096">psychiatrist</span></span>
- <span data-ttu-id="ba5ea-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1097">workers compensation</span></span>
- <span data-ttu-id="ba5ea-1098">ограничен</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="ba5ea-1099">Номер паспорта гражданина Канады</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1100">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1100">Format</span></span>

<span data-ttu-id="ba5ea-1101">Две прописные буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1102">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1102">Pattern</span></span>

<span data-ttu-id="ba5ea-1103">Две прописные буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1104">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1104">Checksum</span></span>

<span data-ttu-id="ba5ea-1105">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1106">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1106">Definition</span></span>

<span data-ttu-id="ba5ea-1107">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1108">регулярное выражение Regex_canada_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1109">Найдено ключевое слово из Keyword_canada_passport_number или Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="ba5ea-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="ba5ea-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1112">canadian citizenship</span></span>
- <span data-ttu-id="ba5ea-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1113">canadian passport</span></span>
- <span data-ttu-id="ba5ea-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1114">passport application</span></span>
- <span data-ttu-id="ba5ea-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1115">passport photos</span></span>
- <span data-ttu-id="ba5ea-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1116">certified translator</span></span>
- <span data-ttu-id="ba5ea-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1117">canadian citizens</span></span>
- <span data-ttu-id="ba5ea-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1118">processing times</span></span>
- <span data-ttu-id="ba5ea-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ba5ea-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1120">Keyword_passport</span></span>

- <span data-ttu-id="ba5ea-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1121">Passport Number</span></span>
- <span data-ttu-id="ba5ea-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1122">Passport No</span></span>
- <span data-ttu-id="ba5ea-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1123">Passport #</span></span>
- <span data-ttu-id="ba5ea-1124">Службу #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1124">Passport#</span></span>
- <span data-ttu-id="ba5ea-1125">пасспортид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1125">PassportID</span></span>
- <span data-ttu-id="ba5ea-1126">пасспортно</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1126">Passportno</span></span>
- <span data-ttu-id="ba5ea-1127">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1127">passportnumber</span></span>
- <span data-ttu-id="ba5ea-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1128">パスポート</span></span>
- <span data-ttu-id="ba5ea-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1129">パスポート番号</span></span>
- <span data-ttu-id="ba5ea-1130">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1130">パスポートのNum</span></span>
- <span data-ttu-id="ba5ea-1131">パスポート #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1131">パスポート＃</span></span>
- <span data-ttu-id="ba5ea-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1132">Numéro de passeport</span></span>
- <span data-ttu-id="ba5ea-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1133">Passeport n °</span></span>
- <span data-ttu-id="ba5ea-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1134">Passeport Non</span></span>
- <span data-ttu-id="ba5ea-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1135">Passeport #</span></span>
- <span data-ttu-id="ba5ea-1136">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1136">Passeport#</span></span>
- <span data-ttu-id="ba5ea-1137">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1137">PasseportNon</span></span>
- <span data-ttu-id="ba5ea-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="ba5ea-1139">Персональный идентификационный номер службы здравоохранения для Канады (PHIN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1140">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1140">Format</span></span>

<span data-ttu-id="ba5ea-1141">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1142">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1142">Pattern</span></span>

<span data-ttu-id="ba5ea-1143">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1144">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1144">Checksum</span></span>

<span data-ttu-id="ba5ea-1145">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1146">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1146">Definition</span></span>

<span data-ttu-id="ba5ea-1147">Политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах расстояния от 300 символов: регулярное выражение Regex_canada_phin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="ba5ea-1148">Найдено по крайней мере два ключевых слова из Keyword_canada_phin или Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="ba5ea-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="ba5ea-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1151">social insurance number</span></span>
- <span data-ttu-id="ba5ea-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1152">health information act</span></span>
- <span data-ttu-id="ba5ea-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1153">income tax information</span></span>
- <span data-ttu-id="ba5ea-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1154">manitoba health</span></span>
- <span data-ttu-id="ba5ea-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1155">health registration</span></span>
- <span data-ttu-id="ba5ea-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1156">prescription purchases</span></span>
- <span data-ttu-id="ba5ea-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1157">benefit eligibility</span></span>
- <span data-ttu-id="ba5ea-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1158">personal health</span></span>
- <span data-ttu-id="ba5ea-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1159">power of attorney</span></span>
- <span data-ttu-id="ba5ea-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1160">registration number</span></span>
- <span data-ttu-id="ba5ea-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1161">personal health number</span></span>
- <span data-ttu-id="ba5ea-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1162">practitioner referral</span></span>
- <span data-ttu-id="ba5ea-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1163">wellness professional</span></span>
- <span data-ttu-id="ba5ea-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1164">patient referral</span></span>
- <span data-ttu-id="ba5ea-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="ba5ea-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="ba5ea-1167">нунавут</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1167">Nunavut</span></span>
- <span data-ttu-id="ba5ea-1168">Квебека</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1168">Quebec</span></span>
- <span data-ttu-id="ba5ea-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1169">Northwest Territories</span></span>
- <span data-ttu-id="ba5ea-1170">Онтарио</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1170">Ontario</span></span>
- <span data-ttu-id="ba5ea-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1171">British Columbia</span></span>
- <span data-ttu-id="ba5ea-1172">Альберта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1172">Alberta</span></span>
- <span data-ttu-id="ba5ea-1173">Саскачеван</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1173">Saskatchewan</span></span>
- <span data-ttu-id="ba5ea-1174">Манитоба</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1174">Manitoba</span></span>
- <span data-ttu-id="ba5ea-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1175">Yukon</span></span>
- <span data-ttu-id="ba5ea-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="ba5ea-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1177">New Brunswick</span></span>
- <span data-ttu-id="ba5ea-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1178">Nova Scotia</span></span>
- <span data-ttu-id="ba5ea-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1179">Prince Edward Island</span></span>
- <span data-ttu-id="ba5ea-1180">Канада</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="ba5ea-1181">Номер карты социального страхования для Канады</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1182">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1182">Format</span></span>

<span data-ttu-id="ba5ea-1183">Девять цифр с необязательными дефисами или пробелами.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1184">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1184">Pattern</span></span>

<span data-ttu-id="ba5ea-1185">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1185">Formatted:</span></span>
- <span data-ttu-id="ba5ea-1186">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1186">Three digits</span></span> 
- <span data-ttu-id="ba5ea-1187">Дефис или пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1187">A hyphen or space</span></span> 
- <span data-ttu-id="ba5ea-1188">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1188">Three digits</span></span> 
- <span data-ttu-id="ba5ea-1189">Дефис или пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1189">A hyphen or space</span></span> 
- <span data-ttu-id="ba5ea-1190">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1190">Three digits</span></span>

<span data-ttu-id="ba5ea-1191">Неформатированные: девять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1192">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1192">Checksum</span></span>

<span data-ttu-id="ba5ea-1193">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1194">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1194">Definition</span></span>

<span data-ttu-id="ba5ea-1195">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1196">Функция Func_canadian_sin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1197">Выполняются по меньшей мере два из таких условий:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="ba5ea-1198">найдено ключевое слово из Keyword_sin;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="ba5ea-1199">найдено ключевое слово из Keyword_sin_collaborative;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="ba5ea-1200">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ba5ea-1201">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1201">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-1202">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1203">функция Func_unformatted_canadian_sin находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1204">найдено ключевое слово из Keyword_sin;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="ba5ea-1205">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1206">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="ba5ea-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1207">Keyword_sin</span></span>

- <span data-ttu-id="ba5ea-1208">sin</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1208">sin</span></span> 
- <span data-ttu-id="ba5ea-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1209">social insurance</span></span> 
- <span data-ttu-id="ba5ea-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="ba5ea-1211">грехов</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1211">sins</span></span> 
- <span data-ttu-id="ba5ea-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1212">ssn</span></span> 
- <span data-ttu-id="ba5ea-1213">ssNS</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1213">ssns</span></span> 
- <span data-ttu-id="ba5ea-1214">social security</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1214">social security</span></span> 
- <span data-ttu-id="ba5ea-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="ba5ea-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1216">national identification number</span></span> 
- <span data-ttu-id="ba5ea-1217">national id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1217">national id</span></span> 
- <span data-ttu-id="ba5ea-1218">Синус #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1218">sin#</span></span> 
- <span data-ttu-id="ba5ea-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1219">soc ins</span></span> 
- <span data-ttu-id="ba5ea-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="ba5ea-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="ba5ea-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1222">driver's license</span></span> 
- <span data-ttu-id="ba5ea-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1223">drivers license</span></span> 
- <span data-ttu-id="ba5ea-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1224">driver's licence</span></span> 
- <span data-ttu-id="ba5ea-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1225">drivers licence</span></span> 
- <span data-ttu-id="ba5ea-1226">доб</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1226">DOB</span></span> 
- <span data-ttu-id="ba5ea-1227">Birthdate</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1227">Birthdate</span></span> 
- <span data-ttu-id="ba5ea-1228">День рождения </span><span class="sxs-lookup"><span data-stu-id="ba5ea-1228">Birthday</span></span> 
- <span data-ttu-id="ba5ea-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="ba5ea-1230">	Номер удостоверения личности для Чили</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1231">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1231">Format</span></span>

<span data-ttu-id="ba5ea-1232">7-8 цифр и разделители — контрольная цифра или буква</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1233">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1233">Pattern</span></span>

<span data-ttu-id="ba5ea-1234">7–8 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="ba5ea-1235">1 или 2 цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1235">1-2 digits</span></span> 
- <span data-ttu-id="ba5ea-1236">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1236">A period</span></span> 
- <span data-ttu-id="ba5ea-1237">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-1237">Three digits</span></span> 
- <span data-ttu-id="ba5ea-1238">точка;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1238">A period</span></span> 
- <span data-ttu-id="ba5ea-1239">три цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1239">Three digits</span></span> 
- <span data-ttu-id="ba5ea-1240">тире;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1240">A dash</span></span> 
- <span data-ttu-id="ba5ea-1241">одна цифра или буква (без учета регистра) — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1242">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1242">Checksum</span></span>

<span data-ttu-id="ba5ea-1243">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1244">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1244">Definition</span></span>

<span data-ttu-id="ba5ea-1245">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1246">функция Func_chile_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1247">находится ключевое слово из Keyword_chile_id_card;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="ba5ea-1248">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1248">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-1249">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1250">функция Func_chile_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1251">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1252">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="ba5ea-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="ba5ea-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1254">National Identification Number</span></span> 
- <span data-ttu-id="ba5ea-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1255">Identity card</span></span> 
- <span data-ttu-id="ba5ea-1256">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1256">ID</span></span> 
- <span data-ttu-id="ba5ea-1257">Процедура</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1257">Identification</span></span> 
- <span data-ttu-id="ba5ea-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="ba5ea-1259">ВЫПОЛНЯЕМ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1259">RUN</span></span> 
- <span data-ttu-id="ba5ea-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="ba5ea-1261">СНИЖАТЬСЯ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1261">RUT</span></span> 
- <span data-ttu-id="ba5ea-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="ba5ea-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="ba5ea-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="ba5ea-1265">идентификаЦиóн</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="ba5ea-1266">	Номер удостоверения личности жителя Китая (КНР)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1267">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1267">Format</span></span>

<span data-ttu-id="ba5ea-1268">18 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1269">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1269">Pattern</span></span>

<span data-ttu-id="ba5ea-1270">18 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1270">18 digits:</span></span>
- <span data-ttu-id="ba5ea-1271">шесть цифр — код адреса;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="ba5ea-1272">восемь цифр в виде ГГГГММДД — дата рождения;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ba5ea-1273">три цифры — серия карты;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="ba5ea-1274">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1275">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1275">Checksum</span></span>

<span data-ttu-id="ba5ea-1276">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1277">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1277">Definition</span></span>

<span data-ttu-id="ba5ea-1278">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1279">функция Func_china_resident_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1280">находится ключевое слово из Keyword_china_resident_id;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="ba5ea-1281">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1281">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-1282">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1283">функция Func_china_resident_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1284">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1285">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="ba5ea-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="ba5ea-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="ba5ea-1288">NO7</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1288">PRC</span></span> 
- <span data-ttu-id="ba5ea-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1289">National Identification Card</span></span> 
- <span data-ttu-id="ba5ea-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1290">身份证</span></span> 
- <span data-ttu-id="ba5ea-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1291">居民 身份证</span></span> 
- <span data-ttu-id="ba5ea-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1292">居民身份证</span></span> 
- <span data-ttu-id="ba5ea-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1293">鉴定</span></span> 
- <span data-ttu-id="ba5ea-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1294">身分證</span></span> 
- <span data-ttu-id="ba5ea-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1295">居民 身份證</span></span>
- <span data-ttu-id="ba5ea-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="ba5ea-1297">Номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1298">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1298">Format</span></span>

<span data-ttu-id="ba5ea-1299">14 – 16 цифр, которые можно форматировать или неформатированные (цццццццццццццццц) и которые должны пройти проверку Луна.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1300">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1300">Pattern</span></span>

<span data-ttu-id="ba5ea-1301">Очень сложный и надежный шаблон, который определяет карты всех основных мировых стандартов, включая Visa, MasterCard, Discover Card, JCB, American Express, подарочные карты и карты Diners Club.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1302">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1302">Checksum</span></span>

<span data-ttu-id="ba5ea-1303">Да (рассчитывается по алгоритму Луна).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1304">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1304">Definition</span></span>

<span data-ttu-id="ba5ea-1305">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1306">Функция Func_credit_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1307">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1307">One of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-1308">найдено ключевое слово из Keyword_cc_verification;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="ba5ea-1309">найдено ключевое слово из Keyword_cc_name;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="ba5ea-1310">функция Func_expiration_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ba5ea-1311">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1311">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-1312">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1313">функция Func_credit_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1314">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1315">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="ba5ea-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="ba5ea-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1317">card verification</span></span>
- <span data-ttu-id="ba5ea-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1318">card identification number</span></span>
- <span data-ttu-id="ba5ea-1319">квн</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1319">cvn</span></span>
- <span data-ttu-id="ba5ea-1320">cid</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1320">cid</span></span>
- <span data-ttu-id="ba5ea-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1321">cvc2</span></span>
- <span data-ttu-id="ba5ea-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1322">cvv2</span></span>
- <span data-ttu-id="ba5ea-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1323">pin block</span></span>
- <span data-ttu-id="ba5ea-1324">security code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1324">security code</span></span>
- <span data-ttu-id="ba5ea-1325">security number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1325">security number</span></span>
- <span data-ttu-id="ba5ea-1326">security no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1326">security no</span></span>
- <span data-ttu-id="ba5ea-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1327">issue number</span></span>
- <span data-ttu-id="ba5ea-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1328">issue no</span></span>
- <span data-ttu-id="ba5ea-1329">криптограмме</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1329">cryptogramme</span></span>
- <span data-ttu-id="ba5ea-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1330">numéro de sécurité</span></span>
- <span data-ttu-id="ba5ea-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1331">numero de securite</span></span>
- <span data-ttu-id="ba5ea-1332">кредиткартенпрüфнуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="ba5ea-1333">кредиткартенпруфнуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="ba5ea-1334">прüфзиффер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1334">prüfziffer</span></span>
- <span data-ttu-id="ba5ea-1335">пруфзиффер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1335">prufziffer</span></span>
- <span data-ttu-id="ba5ea-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1336">sicherheits Kode</span></span>
- <span data-ttu-id="ba5ea-1337">сичерхеитскоде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1337">sicherheitscode</span></span>
- <span data-ttu-id="ba5ea-1338">сичерхеитснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="ba5ea-1339">верфаллдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1339">verfalldatum</span></span>
- <span data-ttu-id="ba5ea-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1340">codice di verifica</span></span>
- <span data-ttu-id="ba5ea-1341">наложен.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1341">cod.</span></span> <span data-ttu-id="ba5ea-1342">сикурезза</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1342">sicurezza</span></span>
- <span data-ttu-id="ba5ea-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1343">cod sicurezza</span></span>
- <span data-ttu-id="ba5ea-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1344">n autorizzazione</span></span>
- <span data-ttu-id="ba5ea-1345">кóдиго</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1345">código</span></span>
- <span data-ttu-id="ba5ea-1346">кодиго</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1346">codigo</span></span>
- <span data-ttu-id="ba5ea-1347">наложен.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1347">cod.</span></span> <span data-ttu-id="ba5ea-1348">сег</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1348">seg</span></span>
- <span data-ttu-id="ba5ea-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1349">cod seg</span></span>
- <span data-ttu-id="ba5ea-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1350">código de segurança</span></span>
- <span data-ttu-id="ba5ea-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1351">codigo de seguranca</span></span>
- <span data-ttu-id="ba5ea-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1352">codigo de segurança</span></span>
- <span data-ttu-id="ba5ea-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1353">código de seguranca</span></span>
- <span data-ttu-id="ba5ea-1354">кóд.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1354">cód.</span></span> <span data-ttu-id="ba5ea-1355">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1355">segurança</span></span>
- <span data-ttu-id="ba5ea-1356">наложен.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1356">cod.</span></span> <span data-ttu-id="ba5ea-1357">сегуранка наложенный платеж.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1357">seguranca cod.</span></span> <span data-ttu-id="ba5ea-1358">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1358">segurança</span></span>
- <span data-ttu-id="ba5ea-1359">кóд.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1359">cód.</span></span> <span data-ttu-id="ba5ea-1360">сегуранка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1360">seguranca</span></span>
- <span data-ttu-id="ba5ea-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1361">cód segurança</span></span>
- <span data-ttu-id="ba5ea-1362">наложенный на наложенный сегуранка сегуранçа</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="ba5ea-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1363">cód seguranca</span></span>
- <span data-ttu-id="ba5ea-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1364">número de verificação</span></span>
- <span data-ttu-id="ba5ea-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1365">numero de verificacao</span></span>
- <span data-ttu-id="ba5ea-1366">аблауф</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1366">ablauf</span></span>
- <span data-ttu-id="ba5ea-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1367">gültig bis</span></span>
- <span data-ttu-id="ba5ea-1368">гüлтигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="ba5ea-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1369">gultig bis</span></span>
- <span data-ttu-id="ba5ea-1370">гултигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="ba5ea-1371">скаденза</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1371">scadenza</span></span>
- <span data-ttu-id="ba5ea-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1372">data scad</span></span>
- <span data-ttu-id="ba5ea-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1373">fecha de expiracion</span></span>
- <span data-ttu-id="ba5ea-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1374">fecha de venc</span></span>
- <span data-ttu-id="ba5ea-1375">венЦимиенто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1375">vencimiento</span></span>
- <span data-ttu-id="ba5ea-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1376">válido hasta</span></span>
- <span data-ttu-id="ba5ea-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1377">valido hasta</span></span>
- <span data-ttu-id="ba5ea-1378">вто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1378">vto</span></span>
- <span data-ttu-id="ba5ea-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1379">data de expiração</span></span>
- <span data-ttu-id="ba5ea-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1380">data de expiracao</span></span>
- <span data-ttu-id="ba5ea-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1381">data em que expira</span></span>
- <span data-ttu-id="ba5ea-1382">валидаде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1382">validade</span></span>
- <span data-ttu-id="ba5ea-1383">валор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1383">valor</span></span>
- <span data-ttu-id="ba5ea-1384">венЦименто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1384">vencimento</span></span>
- <span data-ttu-id="ba5ea-1385">венк</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="ba5ea-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="ba5ea-1387">амекс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1387">amex</span></span>
- <span data-ttu-id="ba5ea-1388">american express</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1388">american express</span></span>
- <span data-ttu-id="ba5ea-1389">американекспресс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1389">americanexpress</span></span>
- <span data-ttu-id="ba5ea-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1390">Visa</span></span>
- <span data-ttu-id="ba5ea-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1391">mastercard</span></span>
- <span data-ttu-id="ba5ea-1392">master card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1392">master card</span></span>
- <span data-ttu-id="ba5ea-1393">MC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1393">mc</span></span> 
- <span data-ttu-id="ba5ea-1394">мастеркардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1394">mastercards</span></span>
- <span data-ttu-id="ba5ea-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1395">master cards</span></span>
- <span data-ttu-id="ba5ea-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1396">diner's Club</span></span>
- <span data-ttu-id="ba5ea-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1397">diners club</span></span>
- <span data-ttu-id="ba5ea-1398">динерсклуб</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1398">dinersclub</span></span>
- <span data-ttu-id="ba5ea-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1399">discover card</span></span>
- <span data-ttu-id="ba5ea-1400">дисковеркард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1400">discovercard</span></span>
- <span data-ttu-id="ba5ea-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1401">discover cards</span></span>
- <span data-ttu-id="ba5ea-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1402">JCB</span></span>
- <span data-ttu-id="ba5ea-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1403">japanese card bureau</span></span>
- <span data-ttu-id="ba5ea-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1404">carte blanche</span></span>
- <span data-ttu-id="ba5ea-1405">картебланче</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1405">carteblanche</span></span>
- <span data-ttu-id="ba5ea-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1406">credit card</span></span>
- <span data-ttu-id="ba5ea-1407">Центральной #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1407">cc#</span></span>
- <span data-ttu-id="ba5ea-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1408">cc#:</span></span>
- <span data-ttu-id="ba5ea-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1409">expiration date</span></span>
- <span data-ttu-id="ba5ea-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1410">exp date</span></span>
- <span data-ttu-id="ba5ea-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1411">expiry date</span></span>
- <span data-ttu-id="ba5ea-1412">Дата д'експиратион</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1412">date d'expiration</span></span>
- <span data-ttu-id="ba5ea-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1413">date d'exp</span></span>
- <span data-ttu-id="ba5ea-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1414">date expiration</span></span>
- <span data-ttu-id="ba5ea-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1415">bank card</span></span>
- <span data-ttu-id="ba5ea-1416">банккард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1416">bankcard</span></span>
- <span data-ttu-id="ba5ea-1417">card number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1417">card number</span></span>
- <span data-ttu-id="ba5ea-1418">card num</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1418">card num</span></span>
- <span data-ttu-id="ba5ea-1419">карднумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1419">cardnumber</span></span>
- <span data-ttu-id="ba5ea-1420">карднумберс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1420">cardnumbers</span></span>
- <span data-ttu-id="ba5ea-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1421">card numbers</span></span>
- <span data-ttu-id="ba5ea-1422">кредиткард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1422">creditcard</span></span>
- <span data-ttu-id="ba5ea-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1423">credit cards</span></span>
- <span data-ttu-id="ba5ea-1424">кредиткардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1424">creditcards</span></span>
- <span data-ttu-id="ba5ea-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1425">ccn</span></span>
- <span data-ttu-id="ba5ea-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1426">card holder</span></span>
- <span data-ttu-id="ba5ea-1427">банков</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1427">cardholder</span></span>
- <span data-ttu-id="ba5ea-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1428">card holders</span></span>
- <span data-ttu-id="ba5ea-1429">карты</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1429">cardholders</span></span>
- <span data-ttu-id="ba5ea-1430">check card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1430">check card</span></span>
- <span data-ttu-id="ba5ea-1431">чекккард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1431">checkcard</span></span>
- <span data-ttu-id="ba5ea-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1432">check cards</span></span>
- <span data-ttu-id="ba5ea-1433">чекккардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1433">checkcards</span></span>
- <span data-ttu-id="ba5ea-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1434">debit card</span></span>
- <span data-ttu-id="ba5ea-1435">дебиткард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1435">debitcard</span></span>
- <span data-ttu-id="ba5ea-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1436">debit cards</span></span>
- <span data-ttu-id="ba5ea-1437">дебиткардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1437">debitcards</span></span>
- <span data-ttu-id="ba5ea-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1438">atm card</span></span>
- <span data-ttu-id="ba5ea-1439">атмкард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1439">atmcard</span></span>
- <span data-ttu-id="ba5ea-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1440">atm cards</span></span>
- <span data-ttu-id="ba5ea-1441">атмкардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1441">atmcards</span></span>
- <span data-ttu-id="ba5ea-1442">енрауте</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1442">enroute</span></span>
- <span data-ttu-id="ba5ea-1443">en route</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1443">en route</span></span>
- <span data-ttu-id="ba5ea-1444">card type</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1444">card type</span></span>
- <span data-ttu-id="ba5ea-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1445">carte bancaire</span></span>
- <span data-ttu-id="ba5ea-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1446">carte de crédit</span></span>
- <span data-ttu-id="ba5ea-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1447">carte de credit</span></span>
- <span data-ttu-id="ba5ea-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1448">numéro de carte</span></span>
- <span data-ttu-id="ba5ea-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1449">numero de carte</span></span>
- <span data-ttu-id="ba5ea-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1450">nº de la carte</span></span>
- <span data-ttu-id="ba5ea-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1451">nº de carte</span></span>
- <span data-ttu-id="ba5ea-1452">кредиткарте</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1452">kreditkarte</span></span>
- <span data-ttu-id="ba5ea-1453">карте</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1453">karte</span></span>
- <span data-ttu-id="ba5ea-1454">картенинхабер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1454">karteninhaber</span></span>
- <span data-ttu-id="ba5ea-1455">картенинхаберс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1455">karteninhabers</span></span>
- <span data-ttu-id="ba5ea-1456">кредиткартенинхабер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="ba5ea-1457">кредиткартенинститут</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="ba5ea-1458">кредиткартентип</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1458">kreditkartentyp</span></span>
- <span data-ttu-id="ba5ea-1459">еижентüмернаме</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1459">eigentümername</span></span>
- <span data-ttu-id="ba5ea-1460">картеннр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1460">kartennr</span></span> 
- <span data-ttu-id="ba5ea-1461">картеннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1461">kartennummer</span></span>
- <span data-ttu-id="ba5ea-1462">кредиткартеннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1462">kreditkartennummer</span></span>
- <span data-ttu-id="ba5ea-1463">кредиткартен — нуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="ba5ea-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1464">carta di credito</span></span>
- <span data-ttu-id="ba5ea-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1465">carta credito</span></span>
- <span data-ttu-id="ba5ea-1466">Корзина "</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1466">carta</span></span>
- <span data-ttu-id="ba5ea-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1467">n carta</span></span>
- <span data-ttu-id="ba5ea-1468">НР.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1468">nr.</span></span> <span data-ttu-id="ba5ea-1469">Корзина "</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1469">carta</span></span>
- <span data-ttu-id="ba5ea-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1470">nr carta</span></span>
- <span data-ttu-id="ba5ea-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1471">numero carta</span></span>
- <span data-ttu-id="ba5ea-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1472">numero della carta</span></span>
- <span data-ttu-id="ba5ea-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1473">numero di carta</span></span>
- <span data-ttu-id="ba5ea-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1474">tarjeta credito</span></span>
- <span data-ttu-id="ba5ea-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1475">tarjeta de credito</span></span>
- <span data-ttu-id="ba5ea-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1476">tarjeta crédito</span></span>
- <span data-ttu-id="ba5ea-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="ba5ea-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1478">tarjeta de atm</span></span>
- <span data-ttu-id="ba5ea-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1479">tarjeta atm</span></span>
- <span data-ttu-id="ba5ea-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1480">tarjeta debito</span></span>
- <span data-ttu-id="ba5ea-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1481">tarjeta de debito</span></span>
- <span data-ttu-id="ba5ea-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1482">tarjeta débito</span></span>
- <span data-ttu-id="ba5ea-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1483">tarjeta de débito</span></span>
- <span data-ttu-id="ba5ea-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1484">nº de tarjeta</span></span>
- <span data-ttu-id="ba5ea-1485">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1485">no.</span></span> <span data-ttu-id="ba5ea-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1486">de tarjeta</span></span>
- <span data-ttu-id="ba5ea-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1487">no de tarjeta</span></span>
- <span data-ttu-id="ba5ea-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1488">numero de tarjeta</span></span>
- <span data-ttu-id="ba5ea-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1489">número de tarjeta</span></span>
- <span data-ttu-id="ba5ea-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1490">tarjeta no</span></span>
- <span data-ttu-id="ba5ea-1491">таржетахабиенте</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1491">tarjetahabiente</span></span>
- <span data-ttu-id="ba5ea-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1492">cartão de crédito</span></span>
- <span data-ttu-id="ba5ea-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1493">cartão de credito</span></span>
- <span data-ttu-id="ba5ea-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1494">cartao de crédito</span></span>
- <span data-ttu-id="ba5ea-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1495">cartao de credito</span></span>
- <span data-ttu-id="ba5ea-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1496">cartão de débito</span></span>
- <span data-ttu-id="ba5ea-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1497">cartao de débito</span></span>
- <span data-ttu-id="ba5ea-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1498">cartão de debito</span></span>
- <span data-ttu-id="ba5ea-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1499">cartao de debito</span></span>
- <span data-ttu-id="ba5ea-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1500">débito automático</span></span>
- <span data-ttu-id="ba5ea-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1501">debito automatico</span></span>
- <span data-ttu-id="ba5ea-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1502">número do cartão</span></span>
- <span data-ttu-id="ba5ea-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1503">numero do cartão</span></span> 
- <span data-ttu-id="ba5ea-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1504">número do cartao</span></span>
- <span data-ttu-id="ba5ea-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1505">numero do cartao</span></span>
- <span data-ttu-id="ba5ea-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1506">número de cartão</span></span>
- <span data-ttu-id="ba5ea-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1507">numero de cartão</span></span>
- <span data-ttu-id="ba5ea-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1508">número de cartao</span></span>
- <span data-ttu-id="ba5ea-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1509">numero de cartao</span></span>
- <span data-ttu-id="ba5ea-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1510">nº do cartão</span></span>
- <span data-ttu-id="ba5ea-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1511">nº do cartao</span></span>
- <span data-ttu-id="ba5ea-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1512">nº.</span></span> <span data-ttu-id="ba5ea-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1513">do cartão</span></span>
- <span data-ttu-id="ba5ea-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1514">no do cartão</span></span>
- <span data-ttu-id="ba5ea-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1515">no do cartao</span></span>
- <span data-ttu-id="ba5ea-1516">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1516">no.</span></span> <span data-ttu-id="ba5ea-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1517">do cartão</span></span>
- <span data-ttu-id="ba5ea-1518">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1518">no.</span></span> <span data-ttu-id="ba5ea-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="ba5ea-1520">	Номер удостоверения личности для Хорватии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1521">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1521">Format</span></span>

<span data-ttu-id="ba5ea-1522">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1523">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1523">Pattern</span></span>

<span data-ttu-id="ba5ea-1524">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1525">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1525">Checksum</span></span>

<span data-ttu-id="ba5ea-1526">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1527">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1527">Definition</span></span>

<span data-ttu-id="ba5ea-1528">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1529">функция Func_croatia_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1530">находится ключевое слово из Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-1531">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="ba5ea-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="ba5ea-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1533">Croatian identity card</span></span>
- <span data-ttu-id="ba5ea-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="ba5ea-1535">	Индивидуальный идентификационный номер (OIB) для Хорватии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1536">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1536">Format</span></span>

<span data-ttu-id="ba5ea-1537">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1538">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1538">Pattern</span></span>

<span data-ttu-id="ba5ea-1539">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1539">11 digits:</span></span>
- <span data-ttu-id="ba5ea-1540">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1540">10 digits</span></span> 
- <span data-ttu-id="ba5ea-1541">Последняя цифра — контрольная цифра для международного обмена данными, буквы добавляются до одиннадцати цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1542">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1542">Checksum</span></span>

<span data-ttu-id="ba5ea-1543">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1544">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1544">Definition</span></span>

<span data-ttu-id="ba5ea-1545">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1546">функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1547">находится ключевое слово из Keyword_croatia_oib_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="ba5ea-1548">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1548">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-1549">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1550">функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1551">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1552">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="ba5ea-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="ba5ea-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1554">Personal Identification Number</span></span>
- <span data-ttu-id="ba5ea-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="ba5ea-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="ba5ea-1557">Номер личного удостоверения для чешского языка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1558">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1558">Format</span></span>

<span data-ttu-id="ba5ea-1559">Девять цифр с необязательной косой чертой (старый формат) 10 цифрами с необязательной косой чертой (новый формат)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1560">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1560">Pattern</span></span>

<span data-ttu-id="ba5ea-1561">Девять цифр (старый формат):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="ba5ea-1562">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1562">Nine digits</span></span>

<span data-ttu-id="ba5ea-1563">OR</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1563">OR</span></span>

- <span data-ttu-id="ba5ea-1564">Шесть цифр, представляющих дату рождения</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="ba5ea-1565">косая черта;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1565">A forward slash</span></span>
- <span data-ttu-id="ba5ea-1566">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1566">Three digits</span></span>

<span data-ttu-id="ba5ea-1567">10 цифр (новый формат):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1567">10 digits (new format):</span></span>
- <span data-ttu-id="ba5ea-1568">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1568">10 digits</span></span>

<span data-ttu-id="ba5ea-1569">OR</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1569">OR</span></span>

- <span data-ttu-id="ba5ea-1570">Шесть цифр, представляющих дату рождения</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="ba5ea-1571">косая черта;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1571">A forward slash</span></span> 
- <span data-ttu-id="ba5ea-1572">Четыре цифры, где последняя цифра является контрольной цифрой</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1573">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1573">Checksum</span></span>

<span data-ttu-id="ba5ea-1574">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1575">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1575">Definition</span></span>

<span data-ttu-id="ba5ea-1576">Политика защиты от потери данных — 85% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_czech_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="ba5ea-1577">находится ключевое слово из Keyword_czech_id_card;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="ba5ea-1578">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="ba5ea-1579">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1579">Keywords</span></span>

- <span data-ttu-id="ba5ea-1580">номер личного удостоверения для чешского языка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1580">czech personal identity number</span></span>
- <span data-ttu-id="ba5ea-1581">Роднé číсло</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="ba5ea-1582">	Индивидуальный идентификационный номер для Дании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1583">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1583">Format</span></span>

<span data-ttu-id="ba5ea-1584">10 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1585">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1585">Pattern</span></span>

<span data-ttu-id="ba5ea-1586">10 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1586">10 digits:</span></span>
- <span data-ttu-id="ba5ea-1587">шесть цифр в формате ДДММГГ — дата рождения;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="ba5ea-1588">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1588">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-1589">четыре цифры, где последняя цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1590">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1590">Checksum</span></span>

<span data-ttu-id="ba5ea-1591">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1592">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1592">Definition</span></span>

<span data-ttu-id="ba5ea-1593">Политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах расстояния от 300 символов: регулярное выражение Regex_denmark_id находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="ba5ea-1594">находится ключевое слово из Keyword_denmark_id;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="ba5ea-1595">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-1596">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="ba5ea-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="ba5ea-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1598">Personal Identification Number</span></span>
- <span data-ttu-id="ba5ea-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1599">CPR</span></span>
- <span data-ttu-id="ba5ea-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="ba5ea-1601">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="ba5ea-1602">Номер Управления по борьбе с наркотиками США (DEA)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1603">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1603">Format</span></span>

<span data-ttu-id="ba5ea-1604">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1605">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1605">Pattern</span></span>

<span data-ttu-id="ba5ea-1606">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="ba5ea-1607">Одна буква (без учета регистра) из следующего набора: abcdefghjklmnprstux, представляющая собой код регистрирующегося лица</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="ba5ea-1608">Одна буква (без учета регистра), представляющая собой первую букву фамилии регистрирующегося лица</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="ba5ea-1609">Семь цифр, последняя из которых — контрольная</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1610">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1610">Checksum</span></span>

<span data-ttu-id="ba5ea-1611">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1612">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1612">Definition</span></span>

<span data-ttu-id="ba5ea-1613">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1614">функция Func_dea_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1615">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-1616">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1616">Keywords</span></span>

<span data-ttu-id="ba5ea-1617">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="ba5ea-1618">Номер банковской карты для ЕС</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1619">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1619">Format</span></span>

<span data-ttu-id="ba5ea-1620">16 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1621">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1621">Pattern</span></span>

<span data-ttu-id="ba5ea-1622">Очень сложный и надежный шаблон.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1623">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1623">Checksum</span></span>

<span data-ttu-id="ba5ea-1624">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1625">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1625">Definition</span></span>

<span data-ttu-id="ba5ea-1626">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1627">Функция Func_eu_debit_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1628">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-1629">найдено ключевое слово из Keyword_eu_debit_card;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="ba5ea-1630">найдено ключевое слово из Keyword_card_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="ba5ea-1631">найдено ключевое слово из Keyword_card_security_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="ba5ea-1632">найдено ключевое слово из Keyword_card_expiration_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="ba5ea-1633">функция Func_expiration_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ba5ea-1634">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-1635">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="ba5ea-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="ba5ea-1637">account number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1637">account number</span></span> 
- <span data-ttu-id="ba5ea-1638">card number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1638">card number</span></span> 
- <span data-ttu-id="ba5ea-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1639">card no.</span></span> 
- <span data-ttu-id="ba5ea-1640">security number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1640">security number</span></span> 
- <span data-ttu-id="ba5ea-1641">Центральной #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="ba5ea-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="ba5ea-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1643">acct nbr</span></span> 
- <span data-ttu-id="ba5ea-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1644">acct num</span></span> 
- <span data-ttu-id="ba5ea-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1645">acct no</span></span> 
- <span data-ttu-id="ba5ea-1646">american express</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1646">american express</span></span> 
- <span data-ttu-id="ba5ea-1647">американекспресс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1647">americanexpress</span></span> 
- <span data-ttu-id="ba5ea-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1648">americano espresso</span></span> 
- <span data-ttu-id="ba5ea-1649">амекс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1649">amex</span></span> 
- <span data-ttu-id="ba5ea-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1650">atm card</span></span> 
- <span data-ttu-id="ba5ea-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1651">atm cards</span></span> 
- <span data-ttu-id="ba5ea-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1652">atm kaart</span></span> 
- <span data-ttu-id="ba5ea-1653">атмкард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1653">atmcard</span></span> 
- <span data-ttu-id="ba5ea-1654">атмкардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1654">atmcards</span></span> 
- <span data-ttu-id="ba5ea-1655">атмкаарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1655">atmkaart</span></span> 
- <span data-ttu-id="ba5ea-1656">атмкаартен</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1656">atmkaarten</span></span> 
- <span data-ttu-id="ba5ea-1657">банконтакт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1657">bancontact</span></span> 
- <span data-ttu-id="ba5ea-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1658">bank card</span></span> 
- <span data-ttu-id="ba5ea-1659">банккаарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1659">bankkaart</span></span> 
- <span data-ttu-id="ba5ea-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1660">card holder</span></span> 
- <span data-ttu-id="ba5ea-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1661">card holders</span></span> 
- <span data-ttu-id="ba5ea-1662">card num</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1662">card num</span></span> 
- <span data-ttu-id="ba5ea-1663">card number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1663">card number</span></span> 
- <span data-ttu-id="ba5ea-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1664">card numbers</span></span> 
- <span data-ttu-id="ba5ea-1665">card type</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1665">card type</span></span> 
- <span data-ttu-id="ba5ea-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1666">cardano numerico</span></span> 
- <span data-ttu-id="ba5ea-1667">банков</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1667">cardholder</span></span> 
- <span data-ttu-id="ba5ea-1668">карты</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1668">cardholders</span></span> 
- <span data-ttu-id="ba5ea-1669">карднумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1669">cardnumber</span></span> 
- <span data-ttu-id="ba5ea-1670">карднумберс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1670">cardnumbers</span></span> 
- <span data-ttu-id="ba5ea-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1671">carta bianca</span></span> 
- <span data-ttu-id="ba5ea-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1672">carta credito</span></span> 
- <span data-ttu-id="ba5ea-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1673">carta di credito</span></span> 
- <span data-ttu-id="ba5ea-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1674">cartao de credito</span></span> 
- <span data-ttu-id="ba5ea-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1675">cartao de crédito</span></span> 
- <span data-ttu-id="ba5ea-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1676">cartao de debito</span></span> 
- <span data-ttu-id="ba5ea-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1677">cartao de débito</span></span> 
- <span data-ttu-id="ba5ea-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1678">carte bancaire</span></span> 
- <span data-ttu-id="ba5ea-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1679">carte blanche</span></span> 
- <span data-ttu-id="ba5ea-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1680">carte bleue</span></span> 
- <span data-ttu-id="ba5ea-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1681">carte de credit</span></span> 
- <span data-ttu-id="ba5ea-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1682">carte de crédit</span></span> 
- <span data-ttu-id="ba5ea-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1683">carte di credito</span></span> 
- <span data-ttu-id="ba5ea-1684">картебланче</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1684">carteblanche</span></span> 
- <span data-ttu-id="ba5ea-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1685">cartão de credito</span></span> 
- <span data-ttu-id="ba5ea-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1686">cartão de crédito</span></span> 
- <span data-ttu-id="ba5ea-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1687">cartão de debito</span></span> 
- <span data-ttu-id="ba5ea-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1688">cartão de débito</span></span> 
- <span data-ttu-id="ba5ea-1689">cb</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1689">cb</span></span> 
- <span data-ttu-id="ba5ea-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1690">ccn</span></span> 
- <span data-ttu-id="ba5ea-1691">check card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1691">check card</span></span> 
- <span data-ttu-id="ba5ea-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1692">check cards</span></span> 
- <span data-ttu-id="ba5ea-1693">чекккард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1693">checkcard</span></span>
- <span data-ttu-id="ba5ea-1694">чекккардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1694">checkcards</span></span> 
- <span data-ttu-id="ba5ea-1695">чекуекаарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1695">chequekaart</span></span> 
- <span data-ttu-id="ba5ea-1696">Logic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1696">cirrus</span></span> 
- <span data-ttu-id="ba5ea-1697">Cirrus центр EDC — Маестро</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="ba5ea-1698">контролекаарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1698">controlekaart</span></span> 
- <span data-ttu-id="ba5ea-1699">контролекаартен</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1699">controlekaarten</span></span> 
- <span data-ttu-id="ba5ea-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1700">credit card</span></span> 
- <span data-ttu-id="ba5ea-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1701">credit cards</span></span> 
- <span data-ttu-id="ba5ea-1702">кредиткард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1702">creditcard</span></span> 
- <span data-ttu-id="ba5ea-1703">кредиткардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1703">creditcards</span></span> 
- <span data-ttu-id="ba5ea-1704">дебеткаарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1704">debetkaart</span></span> 
- <span data-ttu-id="ba5ea-1705">дебеткаартен</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1705">debetkaarten</span></span> 
- <span data-ttu-id="ba5ea-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1706">debit card</span></span> 
- <span data-ttu-id="ba5ea-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1707">debit cards</span></span> 
- <span data-ttu-id="ba5ea-1708">дебиткард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1708">debitcard</span></span> 
- <span data-ttu-id="ba5ea-1709">дебиткардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1709">debitcards</span></span> 
- <span data-ttu-id="ba5ea-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1710">debito automatico</span></span> 
- <span data-ttu-id="ba5ea-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1711">diners club</span></span> 
- <span data-ttu-id="ba5ea-1712">динерсклуб</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1712">dinersclub</span></span> 
- <span data-ttu-id="ba5ea-1713">Повтор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1713">discover</span></span> 
- <span data-ttu-id="ba5ea-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1714">discover card</span></span> 
- <span data-ttu-id="ba5ea-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1715">discover cards</span></span> 
- <span data-ttu-id="ba5ea-1716">дисковеркард</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1716">discovercard</span></span> 
- <span data-ttu-id="ba5ea-1717">дисковеркардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1717">discovercards</span></span> 
- <span data-ttu-id="ba5ea-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1718">débito automático</span></span>
- <span data-ttu-id="ba5ea-1719">центр EDC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1719">edc</span></span> 
- <span data-ttu-id="ba5ea-1720">еижентüмернаме</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1720">eigentümername</span></span> 
- <span data-ttu-id="ba5ea-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1721">european debit card</span></span> 
- <span data-ttu-id="ba5ea-1722">хуфдкаарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1722">hoofdkaart</span></span> 
- <span data-ttu-id="ba5ea-1723">хуфдкаартен</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="ba5ea-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1724">in viaggio</span></span> 
- <span data-ttu-id="ba5ea-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1725">japanese card bureau</span></span> 
- <span data-ttu-id="ba5ea-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="ba5ea-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1727">jcb</span></span> 
- <span data-ttu-id="ba5ea-1728">каарт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1728">kaart</span></span> 
- <span data-ttu-id="ba5ea-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1729">kaart num</span></span> 
- <span data-ttu-id="ba5ea-1730">каартаантал</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1730">kaartaantal</span></span> 
- <span data-ttu-id="ba5ea-1731">каартаанталлен</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1731">kaartaantallen</span></span> 
- <span data-ttu-id="ba5ea-1732">каарсаудер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1732">kaarthouder</span></span> 
- <span data-ttu-id="ba5ea-1733">каарсаудерс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1733">kaarthouders</span></span> 
- <span data-ttu-id="ba5ea-1734">карте</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1734">karte</span></span>  
- <span data-ttu-id="ba5ea-1735">картенинхабер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1735">karteninhaber</span></span> 
- <span data-ttu-id="ba5ea-1736">картенинхаберс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1736">karteninhabers</span></span>
- <span data-ttu-id="ba5ea-1737">картеннр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1737">kartennr</span></span> 
- <span data-ttu-id="ba5ea-1738">картеннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1738">kartennummer</span></span> 
- <span data-ttu-id="ba5ea-1739">кредиткарте</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1739">kreditkarte</span></span> 
- <span data-ttu-id="ba5ea-1740">кредиткартен — нуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="ba5ea-1741">кредиткартенинхабер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="ba5ea-1742">кредиткартенинститут</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="ba5ea-1743">кредиткартеннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="ba5ea-1744">кредиткартентип</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="ba5ea-1745">маестро</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1745">maestro</span></span> 
- <span data-ttu-id="ba5ea-1746">master card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1746">master card</span></span> 
- <span data-ttu-id="ba5ea-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1747">master cards</span></span> 
- <span data-ttu-id="ba5ea-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1748">mastercard</span></span> 
- <span data-ttu-id="ba5ea-1749">мастеркардс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1749">mastercards</span></span> 
- <span data-ttu-id="ba5ea-1750">MC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1750">mc</span></span> 
- <span data-ttu-id="ba5ea-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1751">mister cash</span></span> 
- <span data-ttu-id="ba5ea-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1752">n carta</span></span> 
- <span data-ttu-id="ba5ea-1753">Корзина "</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1753">carta</span></span> 
- <span data-ttu-id="ba5ea-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1754">no de tarjeta</span></span> 
- <span data-ttu-id="ba5ea-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1755">no do cartao</span></span> 
- <span data-ttu-id="ba5ea-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1756">no do cartão</span></span> 
- <span data-ttu-id="ba5ea-1757">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1757">no.</span></span> <span data-ttu-id="ba5ea-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1758">de tarjeta</span></span> 
- <span data-ttu-id="ba5ea-1759">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1759">no.</span></span> <span data-ttu-id="ba5ea-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1760">do cartao</span></span> 
- <span data-ttu-id="ba5ea-1761">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1761">no.</span></span> <span data-ttu-id="ba5ea-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1762">do cartão</span></span> 
- <span data-ttu-id="ba5ea-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1763">nr carta</span></span> 
- <span data-ttu-id="ba5ea-1764">НР.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1764">nr.</span></span> <span data-ttu-id="ba5ea-1765">Корзина "</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1765">carta</span></span> 
- <span data-ttu-id="ba5ea-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1766">numeri di scheda</span></span> 
- <span data-ttu-id="ba5ea-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1767">numero carta</span></span> 
- <span data-ttu-id="ba5ea-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1768">numero de cartao</span></span> 
- <span data-ttu-id="ba5ea-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1769">numero de carte</span></span> 
- <span data-ttu-id="ba5ea-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1770">numero de cartão</span></span> 
- <span data-ttu-id="ba5ea-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1771">numero de tarjeta</span></span>
- <span data-ttu-id="ba5ea-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1772">numero della carta</span></span> 
- <span data-ttu-id="ba5ea-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1773">numero di carta</span></span> 
- <span data-ttu-id="ba5ea-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1774">numero di scheda</span></span> 
- <span data-ttu-id="ba5ea-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1775">numero do cartao</span></span> 
- <span data-ttu-id="ba5ea-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1776">numero do cartão</span></span> 
- <span data-ttu-id="ba5ea-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1777">numéro de carte</span></span> 
- <span data-ttu-id="ba5ea-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1778">nº carta</span></span> 
- <span data-ttu-id="ba5ea-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1779">nº de carte</span></span> 
- <span data-ttu-id="ba5ea-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1780">nº de la carte</span></span> 
- <span data-ttu-id="ba5ea-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="ba5ea-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1782">nº do cartao</span></span> 
- <span data-ttu-id="ba5ea-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1783">nº do cartão</span></span> 
- <span data-ttu-id="ba5ea-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1784">nº.</span></span> <span data-ttu-id="ba5ea-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1785">do cartão</span></span> 
- <span data-ttu-id="ba5ea-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1786">número de cartao</span></span> 
- <span data-ttu-id="ba5ea-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1787">número de cartão</span></span> 
- <span data-ttu-id="ba5ea-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1788">número de tarjeta</span></span> 
- <span data-ttu-id="ba5ea-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1789">número do cartao</span></span> 
- <span data-ttu-id="ba5ea-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="ba5ea-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="ba5ea-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="ba5ea-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1793">scheda della banca</span></span> 
- <span data-ttu-id="ba5ea-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1794">scheda di controllo</span></span> 
- <span data-ttu-id="ba5ea-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1795">scheda di debito</span></span> 
- <span data-ttu-id="ba5ea-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1796">scheda matrice</span></span> 
- <span data-ttu-id="ba5ea-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="ba5ea-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1798">schede di controllo</span></span> 
- <span data-ttu-id="ba5ea-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1799">schede di debito</span></span> 
- <span data-ttu-id="ba5ea-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1800">schede matrici</span></span> 
- <span data-ttu-id="ba5ea-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="ba5ea-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1802">scoprono le schede</span></span> 
- <span data-ttu-id="ba5ea-1803">ОС</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1803">solo</span></span> 
- <span data-ttu-id="ba5ea-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1804">supporti di scheda</span></span> 
- <span data-ttu-id="ba5ea-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1805">supporto di scheda</span></span> 
- <span data-ttu-id="ba5ea-1806">отключен</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1806">switch</span></span> 
- <span data-ttu-id="ba5ea-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1807">tarjeta atm</span></span> 
- <span data-ttu-id="ba5ea-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1808">tarjeta credito</span></span> 
- <span data-ttu-id="ba5ea-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="ba5ea-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="ba5ea-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="ba5ea-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1812">tarjeta debito</span></span> 
- <span data-ttu-id="ba5ea-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1813">tarjeta no</span></span>
- <span data-ttu-id="ba5ea-1814">таржетахабиенте</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="ba5ea-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1815">tipo della scheda</span></span> 
- <span data-ttu-id="ba5ea-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="ba5ea-1817">счеда</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1817">scheda</span></span> 
- <span data-ttu-id="ba5ea-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1818">v pay</span></span> 
- <span data-ttu-id="ba5ea-1819">v — оплата</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1819">v-pay</span></span> 
- <span data-ttu-id="ba5ea-1820">Visa</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1820">visa</span></span> 
- <span data-ttu-id="ba5ea-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1821">visa plus</span></span> 
- <span data-ttu-id="ba5ea-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1822">visa electron</span></span> 
- <span data-ttu-id="ba5ea-1823">висто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1823">visto</span></span> 
- <span data-ttu-id="ba5ea-1824">висум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1824">visum</span></span> 
- <span data-ttu-id="ba5ea-1825">впай</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="ba5ea-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="ba5ea-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1827">card identification number</span></span>
- <span data-ttu-id="ba5ea-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1828">card verification</span></span> 
- <span data-ttu-id="ba5ea-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1829">cardi la verifica</span></span> 
- <span data-ttu-id="ba5ea-1830">cid</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1830">cid</span></span> 
- <span data-ttu-id="ba5ea-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1831">cod seg</span></span> 
- <span data-ttu-id="ba5ea-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1832">cod seguranca</span></span> 
- <span data-ttu-id="ba5ea-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1833">cod segurança</span></span> 
- <span data-ttu-id="ba5ea-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1834">cod sicurezza</span></span> 
- <span data-ttu-id="ba5ea-1835">наложен.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1835">cod.</span></span> <span data-ttu-id="ba5ea-1836">сег</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1836">seg</span></span> 
- <span data-ttu-id="ba5ea-1837">наложен.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1837">cod.</span></span> <span data-ttu-id="ba5ea-1838">сегуранка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1838">seguranca</span></span> 
- <span data-ttu-id="ba5ea-1839">наложен.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1839">cod.</span></span> <span data-ttu-id="ba5ea-1840">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1840">segurança</span></span> 
- <span data-ttu-id="ba5ea-1841">наложен.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1841">cod.</span></span> <span data-ttu-id="ba5ea-1842">сикурезза</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1842">sicurezza</span></span> 
- <span data-ttu-id="ba5ea-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="ba5ea-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1844">codice di verifica</span></span> 
- <span data-ttu-id="ba5ea-1845">кодиго</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1845">codigo</span></span> 
- <span data-ttu-id="ba5ea-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="ba5ea-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1847">codigo de segurança</span></span> 
- <span data-ttu-id="ba5ea-1848">криттограмма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1848">crittogramma</span></span> 
- <span data-ttu-id="ba5ea-1849">криптограм</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1849">cryptogram</span></span> 
- <span data-ttu-id="ba5ea-1850">криптограмме</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1850">cryptogramme</span></span> 
- <span data-ttu-id="ba5ea-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1851">cv2</span></span> 
- <span data-ttu-id="ba5ea-1852">квк</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1852">cvc</span></span> 
- <span data-ttu-id="ba5ea-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1853">cvc2</span></span> 
- <span data-ttu-id="ba5ea-1854">квн</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1854">cvn</span></span> 
- <span data-ttu-id="ba5ea-1855">квв</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1855">cvv</span></span> 
- <span data-ttu-id="ba5ea-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1856">cvv2</span></span> 
- <span data-ttu-id="ba5ea-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1857">cód seguranca</span></span> 
- <span data-ttu-id="ba5ea-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1858">cód segurança</span></span> 
- <span data-ttu-id="ba5ea-1859">кóд.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1859">cód.</span></span> <span data-ttu-id="ba5ea-1860">сегуранка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1860">seguranca</span></span> 
- <span data-ttu-id="ba5ea-1861">кóд.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1861">cód.</span></span> <span data-ttu-id="ba5ea-1862">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1862">segurança</span></span> 
- <span data-ttu-id="ba5ea-1863">кóдиго</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1863">código</span></span> 
- <span data-ttu-id="ba5ea-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1864">código de seguranca</span></span> 
- <span data-ttu-id="ba5ea-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1865">código de segurança</span></span> 
- <span data-ttu-id="ba5ea-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1866">de kaart controle</span></span> 
- <span data-ttu-id="ba5ea-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1867">geeft nr uit</span></span> 
- <span data-ttu-id="ba5ea-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1868">issue no</span></span> 
- <span data-ttu-id="ba5ea-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1869">issue number</span></span> 
- <span data-ttu-id="ba5ea-1870">каартидентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="ba5ea-1871">кредиткартенпруфнуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="ba5ea-1872">кредиткартенпрüфнуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="ba5ea-1873">квестиеаантал</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1873">kwestieaantal</span></span> 
- <span data-ttu-id="ba5ea-1874">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1874">no.</span></span> <span data-ttu-id="ba5ea-1875">делл'едизионе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1875">dell'edizione</span></span> 
- <span data-ttu-id="ba5ea-1876">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1876">no.</span></span> <span data-ttu-id="ba5ea-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1877">di sicurezza</span></span> 
- <span data-ttu-id="ba5ea-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1878">numero de securite</span></span> 
- <span data-ttu-id="ba5ea-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1879">numero de verificacao</span></span> 
- <span data-ttu-id="ba5ea-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="ba5ea-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="ba5ea-1882">счеда</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1882">scheda</span></span> 
- <span data-ttu-id="ba5ea-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="ba5ea-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="ba5ea-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="ba5ea-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="ba5ea-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1887">número de verificação</span></span> 
- <span data-ttu-id="ba5ea-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1888">perno il blocco</span></span> 
- <span data-ttu-id="ba5ea-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1889">pin block</span></span> 
- <span data-ttu-id="ba5ea-1890">пруфзиффер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1890">prufziffer</span></span> 
- <span data-ttu-id="ba5ea-1891">прüфзиффер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1891">prüfziffer</span></span> 
- <span data-ttu-id="ba5ea-1892">security code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1892">security code</span></span> 
- <span data-ttu-id="ba5ea-1893">security no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1893">security no</span></span> 
- <span data-ttu-id="ba5ea-1894">security number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1894">security number</span></span> 
- <span data-ttu-id="ba5ea-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1895">sicherheits kode</span></span> 
- <span data-ttu-id="ba5ea-1896">сичерхеитскоде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1896">sicherheitscode</span></span> 
- <span data-ttu-id="ba5ea-1897">сичерхеитснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="ba5ea-1898">спелдблок</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1898">speldblok</span></span> 
- <span data-ttu-id="ba5ea-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1899">veiligheid nr</span></span> 
- <span data-ttu-id="ba5ea-1900">веилигхеидсаантал</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="ba5ea-1901">веилигхеидскоде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1901">veiligheidscode</span></span> 
- <span data-ttu-id="ba5ea-1902">веилигхеидснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="ba5ea-1903">верфаллдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="ba5ea-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="ba5ea-1905">аблауф</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1905">ablauf</span></span> 
- <span data-ttu-id="ba5ea-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1906">data de expiracao</span></span> 
- <span data-ttu-id="ba5ea-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1907">data de expiração</span></span> 
- <span data-ttu-id="ba5ea-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1908">data del exp</span></span> 
- <span data-ttu-id="ba5ea-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1909">data di exp</span></span> 
- <span data-ttu-id="ba5ea-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1910">data di scadenza</span></span> 
- <span data-ttu-id="ba5ea-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1911">data em que expira</span></span> 
- <span data-ttu-id="ba5ea-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1912">data scad</span></span> 
- <span data-ttu-id="ba5ea-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1913">data scadenza</span></span> 
- <span data-ttu-id="ba5ea-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1914">date de validité</span></span> 
- <span data-ttu-id="ba5ea-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1915">datum afloop</span></span> 
- <span data-ttu-id="ba5ea-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1916">datum van exp</span></span> 
- <span data-ttu-id="ba5ea-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1917">de afloop</span></span> 
- <span data-ttu-id="ba5ea-1918">еспира</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1918">espira</span></span> 
- <span data-ttu-id="ba5ea-1919">еспира</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1919">espira</span></span> 
- <span data-ttu-id="ba5ea-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1920">exp date</span></span> 
- <span data-ttu-id="ba5ea-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1921">exp datum</span></span> 
- <span data-ttu-id="ba5ea-1922">срока действия</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1922">expiration</span></span> 
- <span data-ttu-id="ba5ea-1923">истекает</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1923">expire</span></span> 
- <span data-ttu-id="ba5ea-1924">истекает</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1924">expires</span></span> 
- <span data-ttu-id="ba5ea-1925">окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1925">expiry</span></span> 
- <span data-ttu-id="ba5ea-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="ba5ea-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1927">fecha de venc</span></span> 
- <span data-ttu-id="ba5ea-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1928">gultig bis</span></span> 
- <span data-ttu-id="ba5ea-1929">гултигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="ba5ea-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1930">gültig bis</span></span> 
- <span data-ttu-id="ba5ea-1931">гüлтигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="ba5ea-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1932">la scadenza</span></span> 
- <span data-ttu-id="ba5ea-1933">скаденза</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1933">scadenza</span></span> 
- <span data-ttu-id="ba5ea-1934">валабле</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1934">valable</span></span> 
- <span data-ttu-id="ba5ea-1935">валидаде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1935">validade</span></span> 
- <span data-ttu-id="ba5ea-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1936">valido hasta</span></span> 
- <span data-ttu-id="ba5ea-1937">валор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1937">valor</span></span> 
- <span data-ttu-id="ba5ea-1938">венк</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1938">venc</span></span> 
- <span data-ttu-id="ba5ea-1939">венЦименто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1939">vencimento</span></span> 
- <span data-ttu-id="ba5ea-1940">венЦимиенто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1940">vencimiento</span></span> 
- <span data-ttu-id="ba5ea-1941">верлупт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1941">verloopt</span></span> 
- <span data-ttu-id="ba5ea-1942">вервалдаг</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1942">vervaldag</span></span> 
- <span data-ttu-id="ba5ea-1943">вервалдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1943">vervaldatum</span></span> 
- <span data-ttu-id="ba5ea-1944">вто</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1944">vto</span></span> 
- <span data-ttu-id="ba5ea-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="ba5ea-1946">Номер водительского удостоверения для драйвера ЕС</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1946">EU Driver's License Number</span></span>

<span data-ttu-id="ba5ea-1947">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации номера лицензии для драйвера ЕС](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="ba5ea-1948">Национальный идентификационный номер ЕС</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1948">EU National Identification Number</span></span>

<span data-ttu-id="ba5ea-1949">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации для национального идентификационного номера ЕС](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="ba5ea-1950">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1950">EU Passport Number</span></span>

<span data-ttu-id="ba5ea-1951">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации о номере паспорта ЕС](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="ba5ea-1952">Номер социального страхования ЕС или эквивалентный идентификатор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="ba5ea-1953">Чтобы узнать больше, ознакомьтесь со статьей [номер социального страхования ЕС или эквивалентный тип конфиденциальной информации ID](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="ba5ea-1954">Идентификационный номер налогоплательщика ЕС</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="ba5ea-1955">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации для налогового кода ЕС](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="ba5ea-1956">Национальный идентификатор, Финляндия</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1957">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1957">Format</span></span>

<span data-ttu-id="ba5ea-1958">Шесть цифр, а также символ, обозначающий век, три цифры и контрольная цифра.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1959">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1959">Pattern</span></span>

<span data-ttu-id="ba5ea-1960">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="ba5ea-1961">Шесть цифр в формате ДДММГГ, представляющие собой дату рождения</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="ba5ea-1962">Маркер века (символы "-" и "+" или буква "a")</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="ba5ea-1963">Трехзначный личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="ba5ea-1964">Цифра или буква (без учета регистра) — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1965">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1965">Checksum</span></span>

<span data-ttu-id="ba5ea-1966">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1967">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1967">Definition</span></span>

<span data-ttu-id="ba5ea-1968">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1969">функция Func_finnish_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1970">находится ключевое слово из Keyword_finnish_national_id;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="ba5ea-1971">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-1972">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1972">Keywords</span></span>

- <span data-ttu-id="ba5ea-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="ba5ea-1974">сосиаалитурватуннус</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="ba5ea-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="ba5ea-1976">персонбетеккнинг</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1976">Personbeteckning</span></span>
- <span data-ttu-id="ba5ea-1977">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="ba5ea-1978">Номер паспорта для Финляндии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1978">Finland Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1979">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1979">Format</span></span>
<span data-ttu-id="ba5ea-1980">Сочетание из девяти букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1980">Combination of nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1981">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1981">Pattern</span></span>
<span data-ttu-id="ba5ea-1982">Комбинация из девяти букв и цифр: две буквы (без учета регистра) и семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1982">Combination of nine letters and digits: Two letters (not case sensitive) Seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1983">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1983">Checksum</span></span>
<span data-ttu-id="ba5ea-1984">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1984">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-1985">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1985">Definition</span></span>
<span data-ttu-id="ba5ea-1986">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-1987">регулярное выражение Regex_finland_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1987">The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-1988">находится ключевое слово из Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1988">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
```xml
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="ba5ea-1989">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1989">Keywords</span></span>
- <span data-ttu-id="ba5ea-1990">Keyword_finland_passport_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1990">Keyword_finland_passport_number</span></span>
- <span data-ttu-id="ba5ea-1991">Службу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1991">Passport</span></span>
- <span data-ttu-id="ba5ea-1992">пасси</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1992">Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="ba5ea-1993">Номер водительского удостоверения для Франции</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1993">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-1994">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1994">Format</span></span>

<span data-ttu-id="ba5ea-1995">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1995">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-1996">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1996">Pattern</span></span>

<span data-ttu-id="ba5ea-1997">12 цифр с проверкой подлинности, чтобы избежать путаницы с похожими шаблонами, например французскими номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1997">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-1998">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1998">Checksum</span></span>

<span data-ttu-id="ba5ea-1999">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-1999">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2000">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2000">Definition</span></span>

<span data-ttu-id="ba5ea-2001">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2001">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2002">Функция Func_french_drivers_license находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2002">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2003">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2003">At least one of the following is true:</span></span>
- <span data-ttu-id="ba5ea-2004">найдено ключевое слово из Keyword_french_drivers_license;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2004">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="ba5ea-2005">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2005">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2006">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2006">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="ba5ea-2007">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2007">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="ba5ea-2008">drivers licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2008">drivers licence</span></span>
- <span data-ttu-id="ba5ea-2009">drivers license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2009">drivers license</span></span>
- <span data-ttu-id="ba5ea-2010">driving licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2010">driving licence</span></span>
- <span data-ttu-id="ba5ea-2011">driving license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2011">driving license</span></span>
- <span data-ttu-id="ba5ea-2012">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2012">permis de conduire</span></span>
- <span data-ttu-id="ba5ea-2013">licence number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2013">licence number</span></span>
- <span data-ttu-id="ba5ea-2014">license number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2014">license number</span></span>
- <span data-ttu-id="ba5ea-2015">licence numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2015">licence numbers</span></span>
- <span data-ttu-id="ba5ea-2016">license numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2016">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="ba5ea-2017">Номер внутреннего удостоверения личности для Франции (CNI)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2017">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2018">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2018">Format</span></span>

<span data-ttu-id="ba5ea-2019">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2019">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2020">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2020">Pattern</span></span>

<span data-ttu-id="ba5ea-2021">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2021">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2022">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2022">Checksum</span></span>

<span data-ttu-id="ba5ea-2023">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2023">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2024">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2024">Definition</span></span>

<span data-ttu-id="ba5ea-2025">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2025">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2026">регулярное выражение Regex_france_cni находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2026">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2027">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2027">Keywords</span></span>

<span data-ttu-id="ba5ea-2028">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2028">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="ba5ea-2029">Номер паспорта гражданина Франции</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2029">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2030">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2030">Format</span></span>

<span data-ttu-id="ba5ea-2031">Девять цифр и букв.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2031">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2032">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2032">Pattern</span></span>

<span data-ttu-id="ba5ea-2033">Девять цифр и букв</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2033">Nine digits and letters:</span></span>
- <span data-ttu-id="ba5ea-2034">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2034">Two digits</span></span> 
- <span data-ttu-id="ba5ea-2035">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2035">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-2036">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2036">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2037">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2037">Checksum</span></span>

<span data-ttu-id="ba5ea-2038">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2038">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2039">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2039">Definition</span></span>

<span data-ttu-id="ba5ea-2040">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2040">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2041">функция Func_fr_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2041">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2042">находится ключевое слово из Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2042">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2043">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2043">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ba5ea-2044">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2044">Keyword_passport</span></span>

- <span data-ttu-id="ba5ea-2045">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2045">Passport Number</span></span>
- <span data-ttu-id="ba5ea-2046">Passport No</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2046">Passport No</span></span>
- <span data-ttu-id="ba5ea-2047">Passport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2047">Passport #</span></span>
- <span data-ttu-id="ba5ea-2048">Службу #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2048">Passport#</span></span>
- <span data-ttu-id="ba5ea-2049">пасспортид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2049">PassportID</span></span>
- <span data-ttu-id="ba5ea-2050">пасспортно</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2050">Passportno</span></span>
- <span data-ttu-id="ba5ea-2051">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2051">passportnumber</span></span>
- <span data-ttu-id="ba5ea-2052">パスポート</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2052">パスポート</span></span>
- <span data-ttu-id="ba5ea-2053">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2053">パスポート番号</span></span>
- <span data-ttu-id="ba5ea-2054">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2054">パスポートのNum</span></span>
- <span data-ttu-id="ba5ea-2055">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2055">パスポート ＃</span></span> 
- <span data-ttu-id="ba5ea-2056">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2056">Numéro de passeport</span></span>
- <span data-ttu-id="ba5ea-2057">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2057">Passeport n °</span></span>
- <span data-ttu-id="ba5ea-2058">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2058">Passeport Non</span></span>
- <span data-ttu-id="ba5ea-2059">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2059">Passeport #</span></span>
- <span data-ttu-id="ba5ea-2060">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2060">Passeport#</span></span>
- <span data-ttu-id="ba5ea-2061">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2061">PasseportNon</span></span>
- <span data-ttu-id="ba5ea-2062">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2062">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="ba5ea-2063">Страховой номер для Франции (INSEE)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2063">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2064">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2064">Format</span></span>

<span data-ttu-id="ba5ea-2065">15 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2065">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2066">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2066">Pattern</span></span>

<span data-ttu-id="ba5ea-2067">Должен соответствовать одному из двух шаблонов:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2067">Must match one of two patterns:</span></span>
- <span data-ttu-id="ba5ea-2068">13 цифр, за которыми следует пробел, за которым следуют две цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2068">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="ba5ea-2069">или</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2069">or</span></span>
- <span data-ttu-id="ba5ea-2070">15 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2070">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2071">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2071">Checksum</span></span>

<span data-ttu-id="ba5ea-2072">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2072">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2073">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2073">Definition</span></span>

<span data-ttu-id="ba5ea-2074">Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2074">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2075">Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2075">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2076">находится ключевое слово из Keyword_fr_insee;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2076">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="ba5ea-2077">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2077">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-2078">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2078">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2079">Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2079">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2080">ни одно ключевое слово из Keyword_fr_insee не находится;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2080">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="ba5ea-2081">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2081">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2082">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2082">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="ba5ea-2083">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2083">Keyword_fr_insee</span></span>

- <span data-ttu-id="ba5ea-2084">INSEE</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2084">insee</span></span>
- <span data-ttu-id="ba5ea-2085">securité sociale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2085">securité sociale</span></span>
- <span data-ttu-id="ba5ea-2086">securite sociale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2086">securite sociale</span></span>
- <span data-ttu-id="ba5ea-2087">national id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2087">national id</span></span>
- <span data-ttu-id="ba5ea-2088">national identification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2088">national identification</span></span>
- <span data-ttu-id="ba5ea-2089">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2089">numéro d'identité</span></span>
- <span data-ttu-id="ba5ea-2090">no d'identité</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2090">no d'identité</span></span>
- <span data-ttu-id="ba5ea-2091">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2091">no.</span></span> <span data-ttu-id="ba5ea-2092">д'идентитé</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2092">d'identité</span></span>
- <span data-ttu-id="ba5ea-2093">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2093">numero d'identite</span></span>
- <span data-ttu-id="ba5ea-2094">no d'identite</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2094">no d'identite</span></span>
- <span data-ttu-id="ba5ea-2095">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2095">no.</span></span> <span data-ttu-id="ba5ea-2096">д'идентите</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2096">d'identite</span></span>
- <span data-ttu-id="ba5ea-2097">social security number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2097">social security number</span></span>
- <span data-ttu-id="ba5ea-2098">social security code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2098">social security code</span></span>
- <span data-ttu-id="ba5ea-2099">social insurance number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2099">social insurance number</span></span>
- <span data-ttu-id="ba5ea-2100">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2100">le numéro d'identification nationale</span></span>
- <span data-ttu-id="ba5ea-2101">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2101">d'identité nationale</span></span>
- <span data-ttu-id="ba5ea-2102">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2102">numéro de sécurité sociale</span></span>
- <span data-ttu-id="ba5ea-2103">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2103">le code de la sécurité sociale</span></span>
- <span data-ttu-id="ba5ea-2104">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2104">numéro d'assurance sociale</span></span>
- <span data-ttu-id="ba5ea-2105">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2105">numéro de sécu</span></span>
- <span data-ttu-id="ba5ea-2106">code sécu</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2106">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="ba5ea-2107">Номер водительского удостоверения для Германии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2107">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2108">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2108">Format</span></span>

<span data-ttu-id="ba5ea-2109">Сочетание 11 цифр и букв.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2109">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2110">Pattern</span></span>

<span data-ttu-id="ba5ea-2111">11 цифр и букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2111">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="ba5ea-2112">Одна цифра или буква</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2112">A digit or letter</span></span> 
- <span data-ttu-id="ba5ea-2113">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2113">Two digits</span></span> 
- <span data-ttu-id="ba5ea-2114">Шесть цифр или букв</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2114">Six digits or letters</span></span> 
- <span data-ttu-id="ba5ea-2115">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2115">A digit</span></span> 
- <span data-ttu-id="ba5ea-2116">Одна цифра или буква</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2116">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2117">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2117">Checksum</span></span>

<span data-ttu-id="ba5ea-2118">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2118">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2119">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2119">Definition</span></span>

<span data-ttu-id="ba5ea-2120">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2120">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2121">Функция Func_german_drivers_license находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2121">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2122">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2122">At least one of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-2123">найдено ключевое слово из Keyword_german_drivers_license_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2123">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="ba5ea-2124">найдено ключевое слово из Keyword_german_drivers_license_collaborative;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2124">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="ba5ea-2125">найдено ключевое слово из Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2125">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="ba5ea-2126">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2126">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2127">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2127">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="ba5ea-2128">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2128">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="ba5ea-2129">фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2129">Führerschein</span></span>
- <span data-ttu-id="ba5ea-2130">фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2130">Fuhrerschein</span></span>
- <span data-ttu-id="ba5ea-2131">фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2131">Fuehrerschein</span></span>
- <span data-ttu-id="ba5ea-2132">фüхрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2132">Führerscheinnummer</span></span>
- <span data-ttu-id="ba5ea-2133">фухрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2133">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="ba5ea-2134">фуехрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2134">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="ba5ea-2135">Фüхрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2135">Führerschein-</span></span> 
- <span data-ttu-id="ba5ea-2136">Фухрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2136">Fuhrerschein-</span></span> 
- <span data-ttu-id="ba5ea-2137">Фуехрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2137">Fuehrerschein-</span></span> 
- <span data-ttu-id="ba5ea-2138">фüхрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2138">FührerscheinnummerNr</span></span>
- <span data-ttu-id="ba5ea-2139">фухрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2139">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="ba5ea-2140">фуехрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2140">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="ba5ea-2141">фüхрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2141">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="ba5ea-2142">фухрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2142">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="ba5ea-2143">фуехрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2143">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="ba5ea-2144">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2144">Führerschein- Nr</span></span>
- <span data-ttu-id="ba5ea-2145">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2145">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="ba5ea-2146">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2146">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="ba5ea-2147">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2147">Führerschein- Klasse</span></span> 
- <span data-ttu-id="ba5ea-2148">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2148">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="ba5ea-2149">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2149">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="ba5ea-2150">фüхрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2150">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="ba5ea-2151">фухрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2151">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="ba5ea-2152">фуехрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2152">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="ba5ea-2153">фüхрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2153">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="ba5ea-2154">фухрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2154">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="ba5ea-2155">фуехрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2155">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="ba5ea-2156">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2156">Führerschein- Nr</span></span> 
- <span data-ttu-id="ba5ea-2157">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2157">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="ba5ea-2158">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2158">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="ba5ea-2159">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2159">Führerschein- Klasse</span></span> 
- <span data-ttu-id="ba5ea-2160">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2160">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="ba5ea-2161">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2161">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="ba5ea-2162">DL</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2162">DL</span></span> 
- <span data-ttu-id="ba5ea-2163">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2163">DLS</span></span>
- <span data-ttu-id="ba5ea-2164">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2164">Driv Lic</span></span> 
- <span data-ttu-id="ba5ea-2165">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2165">Driv Licen</span></span> 
- <span data-ttu-id="ba5ea-2166">Driv License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2166">Driv License</span></span>
- <span data-ttu-id="ba5ea-2167">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2167">Driv Licenses</span></span> 
- <span data-ttu-id="ba5ea-2168">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2168">Driv Licence</span></span> 
- <span data-ttu-id="ba5ea-2169">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2169">Driv Licences</span></span> 
- <span data-ttu-id="ba5ea-2170">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2170">Driv Lic</span></span> 
- <span data-ttu-id="ba5ea-2171">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2171">Driver Licen</span></span> 
- <span data-ttu-id="ba5ea-2172">Driver License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2172">Driver License</span></span> 
- <span data-ttu-id="ba5ea-2173">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2173">Driver Licenses</span></span> 
- <span data-ttu-id="ba5ea-2174">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2174">Driver Licence</span></span> 
- <span data-ttu-id="ba5ea-2175">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2175">Driver Licences</span></span> 
- <span data-ttu-id="ba5ea-2176">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2176">Drivers Lic</span></span> 
- <span data-ttu-id="ba5ea-2177">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2177">Drivers Licen</span></span> 
- <span data-ttu-id="ba5ea-2178">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2178">Drivers License</span></span> 
- <span data-ttu-id="ba5ea-2179">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2179">Drivers Licenses</span></span> 
- <span data-ttu-id="ba5ea-2180">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2180">Drivers Licence</span></span> 
- <span data-ttu-id="ba5ea-2181">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2181">Drivers Licences</span></span> 
- <span data-ttu-id="ba5ea-2182">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2182">Driver's Lic</span></span> 
- <span data-ttu-id="ba5ea-2183">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2183">Driver's Licen</span></span> 
- <span data-ttu-id="ba5ea-2184">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2184">Driver's License</span></span> 
- <span data-ttu-id="ba5ea-2185">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2185">Driver's Licenses</span></span> 
- <span data-ttu-id="ba5ea-2186">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2186">Driver's Licence</span></span> 
- <span data-ttu-id="ba5ea-2187">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2187">Driver's Licences</span></span> 
- <span data-ttu-id="ba5ea-2188">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2188">Driving Lic</span></span> 
- <span data-ttu-id="ba5ea-2189">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2189">Driving Licen</span></span> 
- <span data-ttu-id="ba5ea-2190">Driving License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2190">Driving License</span></span> 
- <span data-ttu-id="ba5ea-2191">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2191">Driving Licenses</span></span> 
- <span data-ttu-id="ba5ea-2192">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2192">Driving Licence</span></span> 
- <span data-ttu-id="ba5ea-2193">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2193">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="ba5ea-2194">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2194">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="ba5ea-2195">НР — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2195">Nr-Führerschein</span></span> 
- <span data-ttu-id="ba5ea-2196">НР — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2196">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="ba5ea-2197">НР — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2197">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="ba5ea-2198">Нет — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2198">No-Führerschein</span></span> 
- <span data-ttu-id="ba5ea-2199">Нет — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2199">No-Fuhrerschein</span></span> 
- <span data-ttu-id="ba5ea-2200">Нет — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2200">No-Fuehrerschein</span></span> 
- <span data-ttu-id="ba5ea-2201">N — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2201">N-Führerschein</span></span> 
- <span data-ttu-id="ba5ea-2202">N — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2202">N-Fuhrerschein</span></span> 
- <span data-ttu-id="ba5ea-2203">N — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2203">N-Fuehrerschein</span></span>
- <span data-ttu-id="ba5ea-2204">НР — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2204">Nr-Führerschein</span></span> 
- <span data-ttu-id="ba5ea-2205">НР — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2205">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="ba5ea-2206">НР — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2206">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="ba5ea-2207">Нет — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2207">No-Führerschein</span></span> 
- <span data-ttu-id="ba5ea-2208">Нет — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2208">No-Fuhrerschein</span></span> 
- <span data-ttu-id="ba5ea-2209">Нет — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2209">No-Fuehrerschein</span></span> 
- <span data-ttu-id="ba5ea-2210">N — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2210">N-Führerschein</span></span> 
- <span data-ttu-id="ba5ea-2211">N — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2211">N-Fuhrerschein</span></span> 
- <span data-ttu-id="ba5ea-2212">N — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2212">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="ba5ea-2213">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2213">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="ba5ea-2214">аусстеллунгсдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2214">ausstellungsdatum</span></span>
- <span data-ttu-id="ba5ea-2215">аусстеллунгсорт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2215">ausstellungsort</span></span>
- <span data-ttu-id="ba5ea-2216">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2216">ausstellende behöde</span></span>
- <span data-ttu-id="ba5ea-2217">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2217">ausstellende behorde</span></span>
- <span data-ttu-id="ba5ea-2218">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2218">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="ba5ea-2219">Номер паспорта гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2219">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2220">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2220">Format</span></span>

<span data-ttu-id="ba5ea-2221">10 цифр или букв.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2221">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2222">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2222">Pattern</span></span>

<span data-ttu-id="ba5ea-2223">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2223">Pattern must include all of the following:</span></span>
- <span data-ttu-id="ba5ea-2224">Первый символ — цифра или буква из следующего набора: C, F, G, H, J, K.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2224">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="ba5ea-2225">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2225">Three digits</span></span> 
- <span data-ttu-id="ba5ea-2226">Пять цифр или букв из следующего набора: C, F-H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2226">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="ba5ea-2227">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2227">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2228">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2228">Checksum</span></span>

<span data-ttu-id="ba5ea-2229">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2229">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2230">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2230">Definition</span></span>

<span data-ttu-id="ba5ea-2231">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2231">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2232">функция Func_german_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2232">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2233">находится любое ключевое слово из пяти соответствующих списков;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2233">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="ba5ea-2234">контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2234">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-2235">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2236">функция Func_german_passport_data находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2236">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2237">находится любое ключевое слово из пяти соответствующих списков;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2237">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="ba5ea-2238">контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2238">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2239">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2239">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="ba5ea-2240">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2240">Keyword_german_passport</span></span>

- <span data-ttu-id="ba5ea-2241">реисепасс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2241">reisepass</span></span>
- <span data-ttu-id="ba5ea-2242">реисепассе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2242">reisepasse</span></span>
- <span data-ttu-id="ba5ea-2243">реисепасснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2243">reisepassnummer</span></span>
- <span data-ttu-id="ba5ea-2244">службу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2244">passport</span></span>
- <span data-ttu-id="ba5ea-2245">паспорты</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2245">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="ba5ea-2246">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2246">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="ba5ea-2247">жебуртсдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2247">geburtsdatum</span></span>
- <span data-ttu-id="ba5ea-2248">аусстеллунгсдатум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2248">ausstellungsdatum</span></span>
- <span data-ttu-id="ba5ea-2249">аусстеллунгсорт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2249">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="ba5ea-2250">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2250">Keyword_german_passport_number</span></span>

<span data-ttu-id="ba5ea-2251">No — Реисепасс НР — Реисепасс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2251">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="ba5ea-2252">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2252">Keyword_german_passport1</span></span>

<span data-ttu-id="ba5ea-2253">Реисепасс — НР</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2253">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="ba5ea-2254">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2254">Keyword_german_passport2</span></span>

<span data-ttu-id="ba5ea-2255">бнатионалит. t</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2255">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="ba5ea-2256">Номер идентификационной карты гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2256">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2257">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2257">Format</span></span>

<span data-ttu-id="ba5ea-2258">С 1 ноября 2010: девять букв и цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2258">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="ba5ea-2259">От 1 апреля 1987 до 31 октября 2010:10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2259">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2260">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2260">Pattern</span></span>

<span data-ttu-id="ba5ea-2261">С 1 ноября 2010 г.:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2261">Since 1 November 2010:</span></span>
- <span data-ttu-id="ba5ea-2262">одна буква (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2262">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-2263">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2263">Eight digits</span></span>

<span data-ttu-id="ba5ea-2264">От 1 апреля 1987 до 31 октября 2010:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2264">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="ba5ea-2265">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2265">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2266">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2266">Checksum</span></span>

<span data-ttu-id="ba5ea-2267">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2267">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2268">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2268">Definition</span></span>

<span data-ttu-id="ba5ea-2269">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2269">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2270">регулярное выражение Regex_germany_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2270">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2271">находится ключевое слово из Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2271">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2272">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2272">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="ba5ea-2273">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2273">Keyword_germany_id_card</span></span>

- <span data-ttu-id="ba5ea-2274">Identity Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2274">Identity Card</span></span>
- <span data-ttu-id="ba5ea-2275">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2275">ID</span></span>
- <span data-ttu-id="ba5ea-2276">Процедура</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2276">Identification</span></span>
- <span data-ttu-id="ba5ea-2277">персоналаусвеис</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2277">Personalausweis</span></span>
- <span data-ttu-id="ba5ea-2278">идентифизиерунгснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2278">Identifizierungsnummer</span></span>
- <span data-ttu-id="ba5ea-2279">аусвеис</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2279">Ausweis</span></span>
- <span data-ttu-id="ba5ea-2280">идентификатион</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2280">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="ba5ea-2281">Номер внутреннего удостоверения личности для Греции</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2281">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2282">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2282">Format</span></span>

<span data-ttu-id="ba5ea-2283">Сочетание 7–8 букв и чисел, а также тире.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2283">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2284">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2284">Pattern</span></span>

<span data-ttu-id="ba5ea-2285">Семь букв и чисел (старый формат):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2285">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="ba5ea-2286">одна буква (любая буква греческого алфавита);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2286">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="ba5ea-2287">тире;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2287">A dash</span></span> 
- <span data-ttu-id="ba5ea-2288">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2288">Six digits</span></span>

<span data-ttu-id="ba5ea-2289">Восемь букв и чисел (новый формат):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2289">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="ba5ea-2290">две буквы, которые в прописном виде есть как в греческом, так и латинском алфавите (ABEZHIKMNOPTYX);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2290">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="ba5ea-2291">тире;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2291">A dash</span></span> 
- <span data-ttu-id="ba5ea-2292">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2292">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2293">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2293">Checksum</span></span>

<span data-ttu-id="ba5ea-2294">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2294">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2295">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2295">Definition</span></span>

<span data-ttu-id="ba5ea-2296">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2297">регулярное выражение Regex_greece_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2297">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2298">находится ключевое слово из Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2298">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2299">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2299">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="ba5ea-2300">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2300">Keyword_greece_id_card</span></span>

- <span data-ttu-id="ba5ea-2301">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2301">Greek identity Card</span></span>
- <span data-ttu-id="ba5ea-2302">таутотита</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2302">Tautotita</span></span>
- <span data-ttu-id="ba5ea-2303">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2303">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="ba5ea-2304">ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2304">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="ba5ea-2305">Номер удостоверения личности для Гонконга (HKID)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2305">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2306">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2306">Format</span></span>

<span data-ttu-id="ba5ea-2307">Сочетание 8–9 букв и чисел, а также необязательные скобки вокруг последнего символа.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2307">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2308">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2308">Pattern</span></span>

<span data-ttu-id="ba5ea-2309">Сочетание 8–9 букв:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2309">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="ba5ea-2310">1–2 буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2310">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-2311">шесть цифр; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-2311">Six digits</span></span> 
- <span data-ttu-id="ba5ea-2312">последний символ (любая цифра или буква "A") является проверочной цифрой и заключен в скобки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2312">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2313">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2313">Checksum</span></span>

<span data-ttu-id="ba5ea-2314">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2314">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2315">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2315">Definition</span></span>

<span data-ttu-id="ba5ea-2316">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2317">функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2317">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2318">находится ключевое слово из Keyword_hong_kong_id_card;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2318">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="ba5ea-2319">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2319">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-2320">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2320">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2321">функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2321">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2322">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2322">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2323">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2323">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="ba5ea-2324">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2324">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="ba5ea-2325">идентификационная карточка Гонконг</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2325">hong kong identity card</span></span>
- <span data-ttu-id="ba5ea-2326">хкидк</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2326">HKIDC</span></span>
- <span data-ttu-id="ba5ea-2327">id card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2327">id card</span></span>
- <span data-ttu-id="ba5ea-2328">identity card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2328">identity card</span></span>
- <span data-ttu-id="ba5ea-2329">идентификационная карточка HK</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2329">hk identity card</span></span>
- <span data-ttu-id="ba5ea-2330">Идентификатор Гонконг</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2330">hong kong id</span></span>
- <span data-ttu-id="ba5ea-2331">香港身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2331">香港身份證</span></span>
- <span data-ttu-id="ba5ea-2332">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2332">香港永久性居民身份證</span></span>
- <span data-ttu-id="ba5ea-2333">身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2333">身份證</span></span>
- <span data-ttu-id="ba5ea-2334">身份証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2334">身份証</span></span>
- <span data-ttu-id="ba5ea-2335">身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2335">身分證</span></span>
- <span data-ttu-id="ba5ea-2336">身分証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2336">身分証</span></span>
- <span data-ttu-id="ba5ea-2337">香港身份証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2337">香港身份証</span></span>
- <span data-ttu-id="ba5ea-2338">香港身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2338">香港身分證</span></span>
- <span data-ttu-id="ba5ea-2339">香港身分証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2339">香港身分証</span></span>
- <span data-ttu-id="ba5ea-2340">香港身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2340">香港身份證</span></span>
- <span data-ttu-id="ba5ea-2341">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2341">香港居民身份證</span></span>
- <span data-ttu-id="ba5ea-2342">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2342">香港居民身份証</span></span>
- <span data-ttu-id="ba5ea-2343">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2343">香港居民身分證</span></span>
- <span data-ttu-id="ba5ea-2344">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2344">香港居民身分証</span></span>
- <span data-ttu-id="ba5ea-2345">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2345">香港永久性居民身份証</span></span>
- <span data-ttu-id="ba5ea-2346">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2346">香港永久性居民身分證</span></span>
- <span data-ttu-id="ba5ea-2347">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2347">香港永久性居民身分証</span></span>
- <span data-ttu-id="ba5ea-2348">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2348">香港永久性居民身份證</span></span>
- <span data-ttu-id="ba5ea-2349">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2349">香港非永久性居民身份證</span></span>
- <span data-ttu-id="ba5ea-2350">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2350">香港非永久性居民身份証</span></span>
- <span data-ttu-id="ba5ea-2351">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2351">香港非永久性居民身分證</span></span>
- <span data-ttu-id="ba5ea-2352">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2352">香港非永久性居民身分証</span></span>
- <span data-ttu-id="ba5ea-2353">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2353">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="ba5ea-2354">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2354">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="ba5ea-2355">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2355">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="ba5ea-2356">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2356">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="ba5ea-2357">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2357">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="ba5ea-2358">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2358">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="ba5ea-2359">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2359">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="ba5ea-2360">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2360">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="ba5ea-2361">Идентификационный номер налогоплательщика для Индии (PAN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2361">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2362">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2362">Format</span></span>

<span data-ttu-id="ba5ea-2363">10 букв или цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2363">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2364">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2364">Pattern</span></span>

<span data-ttu-id="ba5ea-2365">10 букв или цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2365">10 letters or digits:</span></span>
- <span data-ttu-id="ba5ea-2366">пять букв (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2366">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-2367">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2367">Four digits</span></span> 
- <span data-ttu-id="ba5ea-2368">буква, которая является алфавитным проверочным символом.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2368">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2369">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2369">Checksum</span></span>

<span data-ttu-id="ba5ea-2370">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2370">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2371">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2371">Definition</span></span>

<span data-ttu-id="ba5ea-2372">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2372">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2373">регулярное выражение Regex_india_permanent_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2373">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2374">находится ключевое слово из Keyword_india_permanent_account_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2374">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="ba5ea-2375">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2375">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2376">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2376">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="ba5ea-2377">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2377">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="ba5ea-2378">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2378">Permanent Account Number</span></span> 
- <span data-ttu-id="ba5ea-2379">ПАНОРАМИРОВАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2379">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="ba5ea-2380">Индивидуальный идентификационный номер (Aadhaar) для Индии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2380">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2381">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2381">Format</span></span>

<span data-ttu-id="ba5ea-2382">12 цифр, содержащих необязательные пробелы или тире.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2382">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2383">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2383">Pattern</span></span>

<span data-ttu-id="ba5ea-2384">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2384">12 digits:</span></span>
- <span data-ttu-id="ba5ea-2385">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2385">Four digits</span></span> 
- <span data-ttu-id="ba5ea-2386">необязательный пробел или тире;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2386">An optional space or dash</span></span> 
- <span data-ttu-id="ba5ea-2387">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2387">Four digits</span></span> 
- <span data-ttu-id="ba5ea-2388">необязательный пробел или тире;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2388">An optional space or dash</span></span> 
- <span data-ttu-id="ba5ea-2389">последняя цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2389">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2390">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2390">Checksum</span></span>

<span data-ttu-id="ba5ea-2391">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2391">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2392">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2392">Definition</span></span>

<span data-ttu-id="ba5ea-2393">Политика защиты от потери данных — 85% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_india_aadhaar находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2393">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="ba5ea-2394">находится ключевое слово из Keyword_india_aadhar;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2394">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="ba5ea-2395">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2395">The checksum passes.</span></span>
<span data-ttu-id="ba5ea-2396">Политика защиты от потери данных — 75% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_india_aadhaar находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="ba5ea-2397">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2397">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="ba5ea-2398">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2398">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="ba5ea-2399">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2399">Keyword_india_aadhar</span></span>
- <span data-ttu-id="ba5ea-2400">аадхар</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2400">Aadhar</span></span>
- <span data-ttu-id="ba5ea-2401">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2401">Aadhaar</span></span>
- <span data-ttu-id="ba5ea-2402">UID</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2402">UID</span></span>
- <span data-ttu-id="ba5ea-2403">आधार</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2403">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="ba5ea-2404">Номер удостоверения личности (KTP) для Индонезии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2404">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2405">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2405">Format</span></span>

<span data-ttu-id="ba5ea-2406">16 цифр, содержащих необязательные точки.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2406">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2407">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2407">Pattern</span></span>

<span data-ttu-id="ba5ea-2408">16 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2408">16 digits:</span></span>
- <span data-ttu-id="ba5ea-2409">две цифры (код провинции);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2409">Two-digit province code</span></span> 
- <span data-ttu-id="ba5ea-2410">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2410">A period (optional)</span></span> 
- <span data-ttu-id="ba5ea-2411">две цифры (код округа или города);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2411">Two-digit regency or city code</span></span> 
- <span data-ttu-id="ba5ea-2412">две цифры (код района);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2412">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="ba5ea-2413">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2413">A period (optional)</span></span> 
- <span data-ttu-id="ba5ea-2414">шесть цифр в формате ДДММГГ (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2414">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="ba5ea-2415">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2415">A period (optional)</span></span> 
- <span data-ttu-id="ba5ea-2416">четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2416">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2417">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2417">Checksum</span></span>

<span data-ttu-id="ba5ea-2418">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2419">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2419">Definition</span></span>

<span data-ttu-id="ba5ea-2420">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2421">регулярное выражение Regex_indonesia_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2421">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2422">находится ключевое слово из Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2422">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="ba5ea-2423">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2423">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2424">регулярное выражение Regex_indonesia_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2424">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2425">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2425">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="ba5ea-2426">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2426">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="ba5ea-2427">KTP</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2427">KTP</span></span>
- <span data-ttu-id="ba5ea-2428">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2428">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="ba5ea-2429">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2429">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="ba5ea-2430">Международный номер банковского счета (IBAN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2430">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2431">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2431">Format</span></span>

<span data-ttu-id="ba5ea-2432">Код страны (две буквы), а также проверочные цифры (две) и номер bban (до 30 символов)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2432">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2433">Pattern</span></span>

<span data-ttu-id="ba5ea-2434">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2434">Pattern must include all of the following:</span></span>

- <span data-ttu-id="ba5ea-2435">Двухбуквенный код страны</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2435">Two-letter country code</span></span>
- <span data-ttu-id="ba5ea-2436">Две проверочные цифры (после которых может следовать пробел) </span><span class="sxs-lookup"><span data-stu-id="ba5ea-2436">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="ba5ea-2437">1–7 групп из четырех букв или цифр (могут разделяться пробелами)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2437">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="ba5ea-2438">1–3 буквы или цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2438">1-3 letters or digits</span></span>

<span data-ttu-id="ba5ea-p133">Формат для названия каждой из стран немного отличается. Тип конфиденциальной информации IBAN применяется к следующим 60 странам:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-p133">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="ba5ea-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2442">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2442">Checksum</span></span>

<span data-ttu-id="ba5ea-2443">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2443">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2444">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2444">Definition</span></span>

<span data-ttu-id="ba5ea-2445">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2445">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2446">функция Func_iban находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2446">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2447">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2447">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2448">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2448">Keywords</span></span>

<span data-ttu-id="ba5ea-2449">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2449">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="ba5ea-2450">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2450">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2451">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2451">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="ba5ea-2452">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2452">IPv4:</span></span>
<span data-ttu-id="ba5ea-2453">Сложный шаблон, ответственный за форматированные (с точками) и неформатированные (без точек) версии IPv4-адресов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2453">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="ba5ea-2454">Поддерживающ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2454">IPv6:</span></span>
<span data-ttu-id="ba5ea-2455"> Сложный шаблон, ответственный за форматированные номера IPv6 (вместе с двоеточиями).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2455">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2456">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2456">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2457">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2457">Checksum</span></span>

<span data-ttu-id="ba5ea-2458">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2458">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2459">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2459">Definition</span></span>

<span data-ttu-id="ba5ea-2460">В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2460">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2461">регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2461">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2462">ни одно ключевое слово из Keyword_ipaddress не находится.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2462">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="ba5ea-2463">В случае с протоколом IPv4 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2463">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2464">регулярное выражение Regex_ipv4_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2464">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2465">находится ключевое слово из Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2465">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="ba5ea-2466">В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2466">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2467">регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2467">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2468">ни одно ключевое слово из Keyword_ipaddress не находится.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2468">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2469">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2469">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="ba5ea-2470">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2470">Keyword_ipaddress</span></span>

- <span data-ttu-id="ba5ea-2471">IP (ключевое слово с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2471">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="ba5ea-2472">ip address</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2472">ip address</span></span> 
- <span data-ttu-id="ba5ea-2473">ip addresses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2473">ip addresses</span></span>
- <span data-ttu-id="ba5ea-2474">internet protocol</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2474">internet protocol</span></span>
- <span data-ttu-id="ba5ea-2475">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2475">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="ba5ea-2476">Международная классификация Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2476">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2477">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2477">Format</span></span>

<span data-ttu-id="ba5ea-2478">Dictionary</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2478">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2479">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2479">Pattern</span></span>

<span data-ttu-id="ba5ea-2480">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2480">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2481">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2481">Checksum</span></span>

<span data-ttu-id="ba5ea-2482">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2482">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2483">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2483">Definition</span></span>

<span data-ttu-id="ba5ea-2484">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2485">Найдено ключевое слово из Dictionary_icd_10_updated.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2485">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="ba5ea-2486">Найдено ключевое слово из Dictionary_icd_10_codes.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2486">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="ba5ea-2487">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2487">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2488">Найдено ключевое слово из Dictionary_icd_10_ "Обновлено".</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2488">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="ba5ea-2489">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2489">Keywords</span></span>

<span data-ttu-id="ba5ea-2490">Любой термин из словаря Dictionary_icd_10_updated ключевых слов, основанный на [международной классификации Diseases, десятой версии, Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2490">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="ba5ea-2491">Этот тип ищет только термин, а не коды страхования.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2491">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="ba5ea-2492">Любой термин из словаря Dictionary_icd_10_codes ключевых слов, основанный на [международной классификации Diseases, десятой версии, Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2492">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="ba5ea-2493">Этот тип ищет только страховые коды, а не описание.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2493">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="ba5ea-2494">Международная классификация Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2494">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2495">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2495">Format</span></span>

<span data-ttu-id="ba5ea-2496">Dictionary</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2496">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2497">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2497">Pattern</span></span>

<span data-ttu-id="ba5ea-2498">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2498">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2499">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2499">Checksum</span></span>

<span data-ttu-id="ba5ea-2500">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2500">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2501">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2501">Definition</span></span>

<span data-ttu-id="ba5ea-2502">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2502">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2503">Найдено ключевое слово из Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2503">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="ba5ea-2504">Найдено ключевое слово из Dictionary_icd_9_codes.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2504">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="ba5ea-2505">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2505">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2506">Найдено ключевое слово из Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2506">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2507">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2507">Keywords</span></span>

<span data-ttu-id="ba5ea-2508">Любой термин из словаря Dictionary_icd_9_updated ключевых слов, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2508">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="ba5ea-2509">Этот тип ищет только термин, а не коды страхования.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2509">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="ba5ea-2510">Любой термин из словаря Dictionary_icd_9_codes ключевых слов, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2510">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="ba5ea-2511">Этот тип ищет только страховые коды, а не описание.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2511">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="ba5ea-2512">Индивидуальный социальный номер (PPS) для Ирландии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2512">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2513">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2513">Format</span></span>

<span data-ttu-id="ba5ea-2514">Старый формат (до 31 декабря 2012):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2514">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="ba5ea-2515">семь цифр, за которыми следуют 1–2 буквы. </span><span class="sxs-lookup"><span data-stu-id="ba5ea-2515">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="ba5ea-2516">Новый формат (1 января 2013 и после):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2516">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="ba5ea-2517">семь цифр, за которыми следуют две буквы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2517">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2518">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2518">Pattern</span></span>

<span data-ttu-id="ba5ea-2519">Старый формат (до 31 декабря 2012):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2519">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="ba5ea-2520">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2520">Seven digits</span></span> 
- <span data-ttu-id="ba5ea-2521">1–2 буквы (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2521">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="ba5ea-2522">Новый формат (1 января 2013 и после):</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2522">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="ba5ea-2523">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2523">Seven digits</span></span> 
- <span data-ttu-id="ba5ea-2524">буква (без учета регистра), которая является алфавитным проверочным символом;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2524">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="ba5ea-2525">буква "A" или "H" (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2525">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2526">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2526">Checksum</span></span>

<span data-ttu-id="ba5ea-2527">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2527">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2528">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2528">Definition</span></span>

<span data-ttu-id="ba5ea-2529">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2530">Функция Func_ireland_pps находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2530">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2531">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2531">One of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-2532">найдено ключевое слово из Keyword_ireland_pps;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2532">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="ba5ea-2533">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2533">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ba5ea-2534">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2534">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-2535">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2535">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2536">функция Func_ireland_pps находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2536">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2537">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2537">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2538">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2538">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="ba5ea-2539">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2539">Keyword_ireland_pps</span></span>

- <span data-ttu-id="ba5ea-2540">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2540">Personal Public Service Number</span></span> 
- <span data-ttu-id="ba5ea-2541">PPS Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2541">PPS Number</span></span> 
- <span data-ttu-id="ba5ea-2542">PPS Num</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2542">PPS Num</span></span> 
- <span data-ttu-id="ba5ea-2543">PPS No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2543">PPS No.</span></span> 
- <span data-ttu-id="ba5ea-2544">PPS #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2544">PPS #</span></span> 
- <span data-ttu-id="ba5ea-2545">PPS #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2545">PPS#</span></span> 
- <span data-ttu-id="ba5ea-2546">ппсн</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2546">PPSN</span></span> 
- <span data-ttu-id="ba5ea-2547">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2547">Public Services Card</span></span> 
- <span data-ttu-id="ba5ea-2548">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2548">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="ba5ea-2549">Уимх.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2549">Uimh.</span></span> <span data-ttu-id="ba5ea-2550">НАСТРОЕН</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2550">PSP</span></span> 
- <span data-ttu-id="ba5ea-2551">НАСТРОЕН</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2551">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="ba5ea-2552">Номер банковского счета для Израиля</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2552">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2553">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2553">Format</span></span>

<span data-ttu-id="ba5ea-2554">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2554">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2555">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2555">Pattern</span></span>

<span data-ttu-id="ba5ea-2556">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2556">Formatted:</span></span>
- <span data-ttu-id="ba5ea-2557">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2557">Two digits</span></span> 
- <span data-ttu-id="ba5ea-2558">Тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2558">A dash</span></span> 
- <span data-ttu-id="ba5ea-2559">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2559">Three digits</span></span> 
- <span data-ttu-id="ba5ea-2560">Тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2560">A dash</span></span> 
- <span data-ttu-id="ba5ea-2561">Восемь цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2561">Eight digits</span></span>

<span data-ttu-id="ba5ea-2562">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2562">Unformatted:</span></span>
- <span data-ttu-id="ba5ea-2563">	13 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2563">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2564">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2564">Checksum</span></span>

<span data-ttu-id="ba5ea-2565">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2565">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2566">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2566">Definition</span></span>

<span data-ttu-id="ba5ea-2567">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2568">регулярное выражение Regex_israel_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2568">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2569">находится ключевое слово из Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2569">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2570">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2570">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="ba5ea-2571">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2571">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="ba5ea-2572">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2572">Bank Account Number</span></span> 
- <span data-ttu-id="ba5ea-2573">Bank Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2573">Bank Account</span></span> 
- <span data-ttu-id="ba5ea-2574">Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2574">Account Number</span></span> 
- <span data-ttu-id="ba5ea-2575">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2575">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="ba5ea-2576">Национальный идентификатор для Израиля</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2576">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2577">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2577">Format</span></span>

<span data-ttu-id="ba5ea-2578">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2578">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2579">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2579">Pattern</span></span>

<span data-ttu-id="ba5ea-2580">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2580">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2581">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2581">Checksum</span></span>

<span data-ttu-id="ba5ea-2582">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2582">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2583">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2583">Definition</span></span>

<span data-ttu-id="ba5ea-2584">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2585">функция Func_israeli_national_id_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2585">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2586">находится ключевое слово из Keyword_Israel_National_ID;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2586">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="ba5ea-2587">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2587">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2588">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2588">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="ba5ea-2589">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2589">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="ba5ea-2590">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2590">מספר זהות</span></span> 
- <span data-ttu-id="ba5ea-2591">National ID Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2591">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="ba5ea-2592">Номер водительского удостоверения для Италии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2592">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2593">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2593">Format</span></span>

<span data-ttu-id="ba5ea-2594">Сочетание из 10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2594">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2595">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2595">Pattern</span></span>

- <span data-ttu-id="ba5ea-2596">Сочетание 10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2596">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="ba5ea-2597">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2597">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-2598">Буква "A" или "V" (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2598">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-2599">Семь букв (без учета регистра), цифр или символов подчеркивания</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2599">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="ba5ea-2600">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2600">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2601">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2601">Checksum</span></span>

<span data-ttu-id="ba5ea-2602">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2602">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2603">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2603">Definition</span></span>

<span data-ttu-id="ba5ea-2604">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2604">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2605">регулярное выражение Regex_italy_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2605">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2606">находится ключевое слово из Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2606">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2607">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2607">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="ba5ea-2608">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2608">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="ba5ea-2609">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2609">numero di patente di guida</span></span> 
- <span data-ttu-id="ba5ea-2610">patente di guida</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2610">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="ba5ea-2611">Номер банковского счета для Японии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2611">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2612">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2612">Format</span></span>

<span data-ttu-id="ba5ea-2613">Семь или восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2613">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2614">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2614">Pattern</span></span>

<span data-ttu-id="ba5ea-2615">Номер банковского счета:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2615">Bank account number:</span></span>
- <span data-ttu-id="ba5ea-2616">семь или восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2616">Seven or eight digits</span></span>
- <span data-ttu-id="ba5ea-2617">Код филиала для банковского счета.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2617">Bank account branch code:</span></span>
- <span data-ttu-id="ba5ea-2618">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2618">Four digits</span></span> 
- <span data-ttu-id="ba5ea-2619">Пробел или тире (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2619">A space or dash (optional)</span></span> 
- <span data-ttu-id="ba5ea-2620">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2620">Three digits</span></span>

<span data-ttu-id="ba5ea-2621">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2621">Checksum</span></span>

<span data-ttu-id="ba5ea-2622">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2622">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2623">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2623">Definition</span></span>

<span data-ttu-id="ba5ea-2624">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2625">Функция Func_jp_bank_account находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2625">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2626">Находится ключевое слово из Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2626">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="ba5ea-2627">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2627">One of the following is true:</span></span>
- <span data-ttu-id="ba5ea-2628">функция Func_jp_bank_account_branch_code находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2628">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2629">найдено ключевое слово из Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2629">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="ba5ea-2630">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2631">функция Func_jp_bank_account находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2631">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2632">находится ключевое слово из Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2632">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2633">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2633">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="ba5ea-2634">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2634">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="ba5ea-2635">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2635">Checking Account Number</span></span> 
- <span data-ttu-id="ba5ea-2636">Checking Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2636">Checking Account</span></span> 
- <span data-ttu-id="ba5ea-2637">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2637">Checking Account #</span></span> 
- <span data-ttu-id="ba5ea-2638">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2638">Checking Acct Number</span></span> 
- <span data-ttu-id="ba5ea-2639">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2639">Checking Acct #</span></span> 
- <span data-ttu-id="ba5ea-2640">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2640">Checking Acct No.</span></span> 
- <span data-ttu-id="ba5ea-2641">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2641">Checking Account No.</span></span> 
- <span data-ttu-id="ba5ea-2642">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2642">Bank Account Number</span></span> 
- <span data-ttu-id="ba5ea-2643">Bank Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2643">Bank Account</span></span> 
- <span data-ttu-id="ba5ea-2644">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2644">Bank Account #</span></span> 
- <span data-ttu-id="ba5ea-2645">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2645">Bank Acct Number</span></span> 
- <span data-ttu-id="ba5ea-2646">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2646">Bank Acct #</span></span> 
- <span data-ttu-id="ba5ea-2647">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2647">Bank Acct No.</span></span> 
- <span data-ttu-id="ba5ea-2648">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2648">Bank Account No.</span></span> 
- <span data-ttu-id="ba5ea-2649">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2649">Savings Account Number</span></span> 
- <span data-ttu-id="ba5ea-2650">Savings Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2650">Savings Account</span></span> 
- <span data-ttu-id="ba5ea-2651">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2651">Savings Account #</span></span> 
- <span data-ttu-id="ba5ea-2652">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2652">Savings Acct Number</span></span> 
- <span data-ttu-id="ba5ea-2653">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2653">Savings Acct #</span></span> 
- <span data-ttu-id="ba5ea-2654">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2654">Savings Acct No.</span></span> 
- <span data-ttu-id="ba5ea-2655">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2655">Savings Account No.</span></span> 
- <span data-ttu-id="ba5ea-2656">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2656">Debit Account Number</span></span> 
- <span data-ttu-id="ba5ea-2657">Debit Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2657">Debit Account</span></span> 
- <span data-ttu-id="ba5ea-2658">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2658">Debit Account #</span></span> 
- <span data-ttu-id="ba5ea-2659">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2659">Debit Acct Number</span></span> 
- <span data-ttu-id="ba5ea-2660">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2660">Debit Acct #</span></span> 
- <span data-ttu-id="ba5ea-2661">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2661">Debit Acct No.</span></span> 
- <span data-ttu-id="ba5ea-2662">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2662">Debit Account No.</span></span> 
- <span data-ttu-id="ba5ea-2663">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2663">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="ba5ea-2664">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2664">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="ba5ea-2665">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2665">＃勘定の確認</span></span> 
- <span data-ttu-id="ba5ea-2666">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2666">勘定番号の確認</span></span> 
- <span data-ttu-id="ba5ea-2667">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2667">口座番号の確認</span></span> 
- <span data-ttu-id="ba5ea-2668">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2668">銀行口座番号</span></span> 
- <span data-ttu-id="ba5ea-2669">銀行口座</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2669">銀行口座</span></span> 
- <span data-ttu-id="ba5ea-2670">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2670">銀行口座＃</span></span> 
- <span data-ttu-id="ba5ea-2671">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2671">銀行の勘定番号</span></span> 
- <span data-ttu-id="ba5ea-2672">銀行のаккт #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2672">銀行のacct＃</span></span> 
- <span data-ttu-id="ba5ea-2673">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2673">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="ba5ea-2674">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2674">銀行口座番号</span></span>
- <span data-ttu-id="ba5ea-2675">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2675">普通預金口座番号</span></span> 
- <span data-ttu-id="ba5ea-2676">預金口座</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2676">預金口座</span></span> 
- <span data-ttu-id="ba5ea-2677">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2677">貯蓄口座＃</span></span> 
- <span data-ttu-id="ba5ea-2678">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2678">貯蓄勘定の数</span></span> 
- <span data-ttu-id="ba5ea-2679">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2679">貯蓄勘定＃</span></span> 
- <span data-ttu-id="ba5ea-2680">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2680">貯蓄勘定番号</span></span> 
- <span data-ttu-id="ba5ea-2681">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2681">普通預金口座番号</span></span> 
- <span data-ttu-id="ba5ea-2682">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2682">引き落とし口座番号</span></span> 
- <span data-ttu-id="ba5ea-2683">口座番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2683">口座番号</span></span> 
- <span data-ttu-id="ba5ea-2684">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2684">口座番号＃</span></span> 
- <span data-ttu-id="ba5ea-2685">デビットのаккт番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2685">デビットのacct番号</span></span> 
- <span data-ttu-id="ba5ea-2686">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2686">デビット勘定＃</span></span> 
- <span data-ttu-id="ba5ea-2687">デビットакктの番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2687">デビットACCTの番号</span></span> 
- <span data-ttu-id="ba5ea-2688">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2688">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="ba5ea-2689">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2689">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="ba5ea-2690">отемачи</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2690">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="ba5ea-2691">Номер водительского удостоверения для Японии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2691">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2692">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2692">Format</span></span>

<span data-ttu-id="ba5ea-2693">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2693">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2694">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2694">Pattern</span></span>

<span data-ttu-id="ba5ea-2695">12 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2695">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2696">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2696">Checksum</span></span>

<span data-ttu-id="ba5ea-2697">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2697">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2698">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2698">Definition</span></span>

<span data-ttu-id="ba5ea-2699">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2699">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2700">функция Func_jp_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2700">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2701">находится ключевое слово из Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2701">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2702">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2702">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="ba5ea-2703">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2703">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="ba5ea-2704">DL #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2704">dl#</span></span> 
- <span data-ttu-id="ba5ea-2705">DL</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2705">DL＃</span></span> 
- <span data-ttu-id="ba5ea-2706">библиотек #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2706">dls#</span></span> 
- <span data-ttu-id="ba5ea-2707">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2707">DLS＃</span></span> 
- <span data-ttu-id="ba5ea-2708">driver license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2708">driver license</span></span> 
- <span data-ttu-id="ba5ea-2709">driver licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2709">driver licenses</span></span> 
- <span data-ttu-id="ba5ea-2710">drivers license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2710">drivers license</span></span> 
- <span data-ttu-id="ba5ea-2711">driver's license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2711">driver's license</span></span> 
- <span data-ttu-id="ba5ea-2712">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2712">drivers licenses</span></span> 
- <span data-ttu-id="ba5ea-2713">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2713">driver's licenses</span></span> 
- <span data-ttu-id="ba5ea-2714">driving licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2714">driving licence</span></span> 
- <span data-ttu-id="ba5ea-2715">лик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2715">lic#</span></span> 
- <span data-ttu-id="ba5ea-2716">Лик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2716">LIC＃</span></span> 
- <span data-ttu-id="ba5ea-2717">ликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2717">lics#</span></span> 
- <span data-ttu-id="ba5ea-2718">state id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2718">state id</span></span> 
- <span data-ttu-id="ba5ea-2719">state identification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2719">state identification</span></span> 
- <span data-ttu-id="ba5ea-2720">state identification number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2720">state identification number</span></span> 
- <span data-ttu-id="ba5ea-2721">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2721">低所得国＃</span></span> 
- <span data-ttu-id="ba5ea-2722">免許証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2722">免許証</span></span> 
- <span data-ttu-id="ba5ea-2723">状態ид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2723">状態ID</span></span>
- <span data-ttu-id="ba5ea-2724">状態の識別</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2724">状態の識別</span></span> 
- <span data-ttu-id="ba5ea-2725">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2725">状態の識別番号</span></span> 
- <span data-ttu-id="ba5ea-2726">運転免許</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2726">運転免許</span></span> 
- <span data-ttu-id="ba5ea-2727">運転免許証</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2727">運転免許証</span></span> 
- <span data-ttu-id="ba5ea-2728">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2728">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="ba5ea-2729">Номер паспорта гражданина Японии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2729">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2730">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2730">Format</span></span>

<span data-ttu-id="ba5ea-2731">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2731">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2732">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2732">Pattern</span></span>

<span data-ttu-id="ba5ea-2733">Две буквы (без учета регистра), за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2733">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2734">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2734">Checksum</span></span>

<span data-ttu-id="ba5ea-2735">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2736">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2736">Definition</span></span>

<span data-ttu-id="ba5ea-2737">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2738">функция Func_jp_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2738">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2739">находится ключевое слово из Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2739">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2740">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2740">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="ba5ea-2741">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2741">Keyword_jp_passport</span></span>

- <span data-ttu-id="ba5ea-2742">パスポート</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2742">パスポート</span></span> 
- <span data-ttu-id="ba5ea-2743">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2743">パスポート番号</span></span> 
- <span data-ttu-id="ba5ea-2744">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2744">パスポートのNum</span></span> 
- <span data-ttu-id="ba5ea-2745">パスポート #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2745">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="ba5ea-2746">Номер регистрации резидента Японии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2746">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2747">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2747">Format</span></span>

<span data-ttu-id="ba5ea-2748">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2748">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2749">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2749">Pattern</span></span>

<span data-ttu-id="ba5ea-2750">11 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2750">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2751">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2751">Checksum</span></span>

<span data-ttu-id="ba5ea-2752">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2752">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2753">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2753">Definition</span></span>

<span data-ttu-id="ba5ea-2754">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2755">функция Func_jp_resident_registration_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2755">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2756">находится ключевое слово из Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2756">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2757">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2757">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="ba5ea-2758">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2758">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="ba5ea-2759">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2759">Resident Registration Number</span></span>
- <span data-ttu-id="ba5ea-2760">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2760">Resident Register Number</span></span> 
- <span data-ttu-id="ba5ea-2761">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2761">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="ba5ea-2762">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2762">Resident Registration No.</span></span> 
- <span data-ttu-id="ba5ea-2763">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2763">Resident Register No.</span></span> 
- <span data-ttu-id="ba5ea-2764">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2764">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="ba5ea-2765">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2765">Basic Resident Register No.</span></span> 
- <span data-ttu-id="ba5ea-2766">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2766">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="ba5ea-2767">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2767">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="ba5ea-2768">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2768">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="ba5ea-2769">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2769">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="ba5ea-2770">Номер карты социального страхования для Японии (SIN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2770">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2771">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2771">Format</span></span>

<span data-ttu-id="ba5ea-2772">7–12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2772">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2773">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2773">Pattern</span></span>

<span data-ttu-id="ba5ea-2774">7–12 цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2774">7-12 digits:</span></span>
- <span data-ttu-id="ba5ea-2775">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2775">Four digits</span></span> 
- <span data-ttu-id="ba5ea-2776">Дефис (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2776">A hyphen (optional)</span></span> 
- <span data-ttu-id="ba5ea-2777">Шесть цифр или</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2777">Six digits OR</span></span>
- <span data-ttu-id="ba5ea-2778">7–12 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2778">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2779">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2779">Checksum</span></span>

<span data-ttu-id="ba5ea-2780">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2780">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2781">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2781">Definition</span></span>

<span data-ttu-id="ba5ea-2782">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2782">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2783">функция Func_jp_sin находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2783">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2784">находится ключевое слово из Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2784">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="ba5ea-2785">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2785">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2786">функция Func_jp_sin_pre_1997 находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2786">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2787">находится ключевое слово из Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2787">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2788">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2788">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="ba5ea-2789">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2789">Keyword_jp_sin</span></span>

- <span data-ttu-id="ba5ea-2790">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2790">Social Insurance No.</span></span> 
- <span data-ttu-id="ba5ea-2791">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2791">Social Insurance Num</span></span> 
- <span data-ttu-id="ba5ea-2792">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2792">Social Insurance Number</span></span> 
- <span data-ttu-id="ba5ea-2793">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2793">社会保険のテンキー</span></span> 
- <span data-ttu-id="ba5ea-2794">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2794">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="ba5ea-2795">Номер карточки для японского языка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2795">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2796">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2796">Format</span></span>

<span data-ttu-id="ba5ea-2797">12 букв и цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2797">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2798">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2798">Pattern</span></span>

<span data-ttu-id="ba5ea-2799">12 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2799">12 letters and digits:</span></span>
- <span data-ttu-id="ba5ea-2800">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2800">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="ba5ea-2801">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2801">Eight digits</span></span> 
- <span data-ttu-id="ba5ea-2802">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2802">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2803">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2803">Checksum</span></span>

<span data-ttu-id="ba5ea-2804">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2804">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2805">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2805">Definition</span></span>

<span data-ttu-id="ba5ea-2806">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2807">Регулярное выражение Regex_jp_residence_card_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2807">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2808">Найдено ключевое слово из Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2808">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2809">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2809">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="ba5ea-2810">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2810">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="ba5ea-2811">Номер карточки проживания</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2811">Residence card number</span></span>
- <span data-ttu-id="ba5ea-2812">Номер карточки проживания</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2812">Residence card no</span></span>
- <span data-ttu-id="ba5ea-2813">Карточка проживания #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2813">Residence card #</span></span>
- <span data-ttu-id="ba5ea-2814">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2814">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="ba5ea-2815">Номер удостоверения личности для Малайзии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2815">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2816">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2816">Format</span></span>

<span data-ttu-id="ba5ea-2817">12 цифр, содержащих необязательные дефисы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2817">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2818">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2818">Pattern</span></span>

<span data-ttu-id="ba5ea-2819">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2819">12 digits:</span></span>
- <span data-ttu-id="ba5ea-2820">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2820">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ba5ea-2821">дефис (необязательно);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2821">A dash (optional)</span></span> 
- <span data-ttu-id="ba5ea-2822">код места рождения из двух букв;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2822">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="ba5ea-2823">дефис (необязательно);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2823">A dash (optional)</span></span> 
- <span data-ttu-id="ba5ea-2824">три случайные цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2824">Three random digits</span></span> 
- <span data-ttu-id="ba5ea-2825">код пола из одной цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2825">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2826">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2826">Checksum</span></span>

<span data-ttu-id="ba5ea-2827">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2827">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2828">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2828">Definition</span></span>

<span data-ttu-id="ba5ea-2829">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2829">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2830">регулярное выражение Regex_malaysia_id_card_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2830">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2831">находится ключевое слово из Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2831">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2832">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2832">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="ba5ea-2833">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2833">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="ba5ea-2834">карточка цифрового приложения</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2834">digital application card</span></span>
- <span data-ttu-id="ba5ea-2835">i/c</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2835">i/c</span></span>
- <span data-ttu-id="ba5ea-2836">i/c нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2836">i/c no</span></span>
- <span data-ttu-id="ba5ea-2837">внутренних</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2837">ic</span></span>
- <span data-ttu-id="ba5ea-2838">МФ нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2838">ic no</span></span>
- <span data-ttu-id="ba5ea-2839">id card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2839">id card</span></span>
- <span data-ttu-id="ba5ea-2840">идентификационная карточка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2840">identification Card</span></span>
- <span data-ttu-id="ba5ea-2841">identity card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2841">identity card</span></span>
- <span data-ttu-id="ba5ea-2842">k/p</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2842">k/p</span></span>
- <span data-ttu-id="ba5ea-2843">k/p</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2843">k/p no</span></span>
- <span data-ttu-id="ba5ea-2844">кад акуан Дири</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2844">kad akuan diri</span></span>
- <span data-ttu-id="ba5ea-2845">кад апликаси Digital</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2845">kad aplikasi digital</span></span>
- <span data-ttu-id="ba5ea-2846">кад пенженалан Малайзии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2846">kad pengenalan malaysia</span></span>
- <span data-ttu-id="ba5ea-2847">ключев</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2847">kp</span></span>
- <span data-ttu-id="ba5ea-2848">ключевой номер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2848">kp no</span></span>
- <span data-ttu-id="ba5ea-2849">микад</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2849">mykad</span></span>
- <span data-ttu-id="ba5ea-2850">микас</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2850">mykas</span></span>
- <span data-ttu-id="ba5ea-2851">микид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2851">mykid</span></span>
- <span data-ttu-id="ba5ea-2852">мипр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2852">mypr</span></span>
- <span data-ttu-id="ba5ea-2853">митентера</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2853">mytentera</span></span>
- <span data-ttu-id="ba5ea-2854">идентификационная карточка Малайзии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2854">malaysia identity card</span></span>
- <span data-ttu-id="ba5ea-2855">идентификационная карточка малайсиан</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2855">malaysian identity card</span></span>
- <span data-ttu-id="ba5ea-2856">NRIC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2856">nric</span></span>
- <span data-ttu-id="ba5ea-2857">Личная идентификационная карточка</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2857">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="ba5ea-2858">Номер гражданской службы для Нидерландов (BSN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2858">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2859">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2859">Format</span></span>

<span data-ttu-id="ba5ea-2860">8–9 цифр, содержащих необязательные пробелы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2860">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2861">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2861">Pattern</span></span>

<span data-ttu-id="ba5ea-2862">8–9 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2862">8-9 digits:</span></span>
- <span data-ttu-id="ba5ea-2863">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-2863">Three digits</span></span> 
- <span data-ttu-id="ba5ea-2864">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="ba5ea-2864">A space (optional)</span></span> 
- <span data-ttu-id="ba5ea-2865">три цифры; </span><span class="sxs-lookup"><span data-stu-id="ba5ea-2865">Three digits</span></span> 
- <span data-ttu-id="ba5ea-2866">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="ba5ea-2866">A space (optional)</span></span> 
- <span data-ttu-id="ba5ea-2867">2–3 цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2867">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2868">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2868">Checksum</span></span>

<span data-ttu-id="ba5ea-2869">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2869">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2870">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2870">Definition</span></span>

<span data-ttu-id="ba5ea-2871">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2871">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2872">функция Func_netherlands_bsn находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2872">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2873">находится ключевое слово из Keyword_netherlands_bsn;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2873">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="ba5ea-2874">функция Func_eu_date2 находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2874">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="ba5ea-2875">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2875">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2876">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2876">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="ba5ea-2877">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2877">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="ba5ea-2878">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2878">Citizen service number</span></span> 
- <span data-ttu-id="ba5ea-2879">BSN</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2879">BSN</span></span> 
- <span data-ttu-id="ba5ea-2880">буржерсервиценуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2880">Burgerservicenummer</span></span> 
- <span data-ttu-id="ba5ea-2881">софинуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2881">Sofinummer</span></span> 
- <span data-ttu-id="ba5ea-2882">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2882">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="ba5ea-2883">персунснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2883">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="ba5ea-2884">Номер министерства здравоохранения для Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2884">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2885">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2885">Format</span></span>

<span data-ttu-id="ba5ea-2886">Три буквы, пробел (необязательно) и четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2886">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2887">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2887">Pattern</span></span>

<span data-ttu-id="ba5ea-2888">Три буквы (без учета регистра), пробел (необязательно) из четырех цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2888">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2889">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2889">Checksum</span></span>

<span data-ttu-id="ba5ea-2890">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2890">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2891">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2891">Definition</span></span>

<span data-ttu-id="ba5ea-2892">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2892">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2893">функция Func_new_zealand_ministry_of_health_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2893">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2894">находится ключевое слово из Keyword_nz_terms;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2894">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="ba5ea-2895">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2895">The checksum passes.</span></span>

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

<span data-ttu-id="ba5ea-2896">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2896">Keywords</span></span>

<span data-ttu-id="ba5ea-2897">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2897">Keyword_nz_terms</span></span>

- <span data-ttu-id="ba5ea-2898">нхи</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2898">NHI</span></span> 
- <span data-ttu-id="ba5ea-2899">Новая Зеландия</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2899">New Zealand</span></span> 
- <span data-ttu-id="ba5ea-2900">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2900">Health</span></span> 
- <span data-ttu-id="ba5ea-2901">обращения</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2901">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="ba5ea-2902">Идентификационный номер для Норвегии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2902">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2903">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2903">Format</span></span>

<span data-ttu-id="ba5ea-2904">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2905">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2905">Pattern</span></span>

<span data-ttu-id="ba5ea-2906">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2906">11 digits:</span></span>
- <span data-ttu-id="ba5ea-2907">шесть цифр в формате ДДММГГ (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2907">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="ba5ea-2908">индивидуальный номер из трех цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2908">Three-digit individual number</span></span> 
- <span data-ttu-id="ba5ea-2909">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2909">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2910">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2910">Checksum</span></span>

<span data-ttu-id="ba5ea-2911">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2912">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2912">Definition</span></span>

<span data-ttu-id="ba5ea-2913">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2913">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2914">функция Func_norway_id_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2914">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2915">находится ключевое слово из Keyword_norway_id_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2915">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="ba5ea-2916">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2916">The checksum passes.</span></span>
- <span data-ttu-id="ba5ea-2917">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2917">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2918">функция Func_norway_id_numbe находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2918">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2919">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2919">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2920">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2920">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="ba5ea-2921">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2921">Keyword_norway_id_number</span></span>

- <span data-ttu-id="ba5ea-2922">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2922">Personal identification number</span></span>
- <span data-ttu-id="ba5ea-2923">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2923">Norwegian ID Number</span></span>
- <span data-ttu-id="ba5ea-2924">ID Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2924">ID Number</span></span>
- <span data-ttu-id="ba5ea-2925">Процедура</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2925">Identification</span></span>
- <span data-ttu-id="ba5ea-2926">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2926">Personnummer</span></span>
- <span data-ttu-id="ba5ea-2927">фøдселснуммер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2927">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="ba5ea-2928">Единый многофункциональный идентификационный номер для Филиппин</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2928">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2929">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2929">Format</span></span>

<span data-ttu-id="ba5ea-2930">12 цифр, разделенных дефисами.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2930">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2931">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2931">Pattern</span></span>

<span data-ttu-id="ba5ea-2932">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2932">12 digits:</span></span>
- <span data-ttu-id="ba5ea-2933">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2933">Four digits</span></span> 
- <span data-ttu-id="ba5ea-2934">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2934">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-2935">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2935">Seven digits</span></span> 
- <span data-ttu-id="ba5ea-2936">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2936">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-2937">одна цифра.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2937">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2938">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2938">Checksum</span></span>

<span data-ttu-id="ba5ea-2939">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2939">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2940">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2940">Definition</span></span>

<span data-ttu-id="ba5ea-2941">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2942">регулярное выражение Regex_philippines_unified_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2942">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2943">находится ключевое слово из Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2943">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2944">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2944">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="ba5ea-2945">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2945">Keyword_philippines_id</span></span>

- <span data-ttu-id="ba5ea-2946">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2946">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="ba5ea-2947">умид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2947">UMID</span></span> 
- <span data-ttu-id="ba5ea-2948">Identity Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2948">Identity Card</span></span> 
- <span data-ttu-id="ba5ea-2949">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2949">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="ba5ea-2950">Номер удостоверения личности для Польши</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2950">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2951">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2951">Format</span></span>

<span data-ttu-id="ba5ea-2952">Три буквы и шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2952">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2953">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2953">Pattern</span></span>

<span data-ttu-id="ba5ea-2954">Три буквы (без учета регистра), за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2954">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2955">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2955">Checksum</span></span>

<span data-ttu-id="ba5ea-2956">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2956">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2957">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2957">Definition</span></span>

<span data-ttu-id="ba5ea-2958">Политика защиты от потери данных — 75% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_polish_national_id находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2958">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="ba5ea-2959">находится ключевое слово из Keyword_polish_national_id_passport_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2959">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="ba5ea-2960">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2960">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2961">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2961">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="ba5ea-2962">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2962">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="ba5ea-2963">Довóд особисти</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2963">Dowód osobisty</span></span>
- <span data-ttu-id="ba5ea-2964">Нумер доводу особистего</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2964">Numer dowodu osobistego</span></span>
- <span data-ttu-id="ba5ea-2965">Назва i нумер доводу особистего</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2965">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="ba5ea-2966">Назва i НР доводу особистего</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2966">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="ba5ea-2967">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2967">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="ba5ea-2968">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2968">Dowód Tożsamości</span></span>
- <span data-ttu-id="ba5ea-2969">Dow.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2969">dow.</span></span> <span data-ttu-id="ba5ea-2970">совместим.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2970">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="ba5ea-2971">Национальный идентификатор (PESEL), Польша</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2971">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2972">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2972">Format</span></span>

<span data-ttu-id="ba5ea-2973">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2973">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2974">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2974">Pattern</span></span>

<span data-ttu-id="ba5ea-2975">11 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2975">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2976">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2976">Checksum</span></span>

<span data-ttu-id="ba5ea-2977">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2977">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2978">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2978">Definition</span></span>

<span data-ttu-id="ba5ea-2979">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2979">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2980">функция Func_pesel_identification_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2980">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2981">находится ключевое слово из Keyword_pesel_identification_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2981">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="ba5ea-2982">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2982">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-2983">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2983">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="ba5ea-2984">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2984">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="ba5ea-2985">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2985">Nr PESEL</span></span>
- <span data-ttu-id="ba5ea-2986">PESEL</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2986">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="ba5ea-2987">Номер паспорта для Польши</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2987">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-2988">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2988">Format</span></span>

<span data-ttu-id="ba5ea-2989">Две буквы и семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2989">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-2990">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2990">Pattern</span></span>

<span data-ttu-id="ba5ea-2991">Две буквы (без учета регистра), за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2991">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-2992">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2992">Checksum</span></span>

<span data-ttu-id="ba5ea-2993">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2993">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-2994">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2994">Definition</span></span>

<span data-ttu-id="ba5ea-2995">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2995">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-2996">функция Func_polish_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2996">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-2997">находится ключевое слово из Keyword_polish_national_id_passport_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2997">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="ba5ea-2998">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2998">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-2999">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-2999">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="ba5ea-3000">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3000">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="ba5ea-3001">Нумер пасзпорту</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3001">Numer paszportu</span></span>
- <span data-ttu-id="ba5ea-3002">НР.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3002">Nr.</span></span> <span data-ttu-id="ba5ea-3003">пасзпорту</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3003">Paszportu</span></span>
- <span data-ttu-id="ba5ea-3004">пасзпорт</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3004">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="ba5ea-3005">Номер карты гражданина Португалии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3005">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3006">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3006">Format</span></span>

<span data-ttu-id="ba5ea-3007">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3007">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3008">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3008">Pattern</span></span>

<span data-ttu-id="ba5ea-3009">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3009">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3010">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3010">Checksum</span></span>

<span data-ttu-id="ba5ea-3011">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3011">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3012">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3012">Definition</span></span>

<span data-ttu-id="ba5ea-3013">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3013">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3014">регулярное выражение Regex_portugal_citizen_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3014">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3015">находится ключевое слово из Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3015">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3016">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3016">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="ba5ea-3017">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3017">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="ba5ea-3018">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3018">Citizen Card</span></span>
- <span data-ttu-id="ba5ea-3019">National ID Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3019">National ID Card</span></span>
- <span data-ttu-id="ba5ea-3020">CC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3020">CC</span></span>
- <span data-ttu-id="ba5ea-3021">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3021">Cartão de Cidadão</span></span>
- <span data-ttu-id="ba5ea-3022">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3022">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="ba5ea-3023">Национальный идентификатор для Саудовской Аравии</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3023">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3024">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3024">Format</span></span>

<span data-ttu-id="ba5ea-3025">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3025">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3026">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3026">Pattern</span></span>

<span data-ttu-id="ba5ea-3027">10 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3027">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3028">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3028">Checksum</span></span>

<span data-ttu-id="ba5ea-3029">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3029">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3030">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3030">Definition</span></span>

<span data-ttu-id="ba5ea-3031">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3031">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3032">регулярное выражение Regex_saudi_arabia_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3032">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3033">находится ключевое слово из Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3033">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3034">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3034">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="ba5ea-3035">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3035">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="ba5ea-3036">Identification Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3036">Identification Card</span></span> 
- <span data-ttu-id="ba5ea-3037">I card number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3037">I card number</span></span> 
- <span data-ttu-id="ba5ea-3038">ID number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3038">ID number</span></span> 
- <span data-ttu-id="ba5ea-3039">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3039">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="ba5ea-3040">Номер внутреннего удостоверения личности гражданина Сингапура (NRIC)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3040">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3041">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3041">Format</span></span>

<span data-ttu-id="ba5ea-3042">Девять букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3042">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3043">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3043">Pattern</span></span>

- <span data-ttu-id="ba5ea-3044">Девять букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3044">Nine letters and digits:</span></span>
- <span data-ttu-id="ba5ea-3045">буква "F", "G", "S" или "T" (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3045">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-3046">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3046">Seven digits</span></span> 
- <span data-ttu-id="ba5ea-3047">алфавитный проверочный символ.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3047">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3048">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3048">Checksum</span></span>

<span data-ttu-id="ba5ea-3049">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3049">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3050">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3050">Definition</span></span>

<span data-ttu-id="ba5ea-3051">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3051">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3052">регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3052">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3053">находится ключевое слово из Keyword_singapore_nric;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3053">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="ba5ea-3054">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3054">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-3055">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3055">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3056">регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3056">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3057">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3057">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3058">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3058">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="ba5ea-3059">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3059">Keyword_singapore_nric</span></span>

- <span data-ttu-id="ba5ea-3060">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3060">National Registration Identity Card</span></span> 
- <span data-ttu-id="ba5ea-3061">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3061">Identity Card Number</span></span> 
- <span data-ttu-id="ba5ea-3062">NRIC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3062">NRIC</span></span> 
- <span data-ttu-id="ba5ea-3063">ВНУТРЕННИХ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3063">IC</span></span> 
- <span data-ttu-id="ba5ea-3064">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3064">Foreign Identification Number</span></span> 
- <span data-ttu-id="ba5ea-3065">ПРОЦЕНТ</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3065">FIN</span></span> 
- <span data-ttu-id="ba5ea-3066">身份证</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3066">身份证</span></span> 
- <span data-ttu-id="ba5ea-3067">身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3067">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="ba5ea-3068">Идентификационный номер для Южной Африки</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3068">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3069">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3069">Format</span></span>

<span data-ttu-id="ba5ea-3070">13 цифр, которые могут содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3070">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3071">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3071">Pattern</span></span>

<span data-ttu-id="ba5ea-3072">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3072">13 digits:</span></span>
- <span data-ttu-id="ba5ea-3073">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3073">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ba5ea-3074">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3074">Four digits</span></span> 
- <span data-ttu-id="ba5ea-3075">индикатор гражданства в виде одной цифры;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3075">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="ba5ea-3076">цифра "8" или "9";</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3076">The digit "8" or "9"</span></span> 
- <span data-ttu-id="ba5ea-3077">одна цифра (проверочная).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3077">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3078">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3078">Checksum</span></span>

<span data-ttu-id="ba5ea-3079">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3079">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3080">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3080">Definition</span></span>

<span data-ttu-id="ba5ea-3081">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3082">функция Func_south_africa_identification_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3082">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3083">находится ключевое слово из Keyword_south_africa_identification_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3083">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="ba5ea-3084">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3084">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3085">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3085">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="ba5ea-3086">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3086">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="ba5ea-3087">Identity card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3087">Identity card</span></span>
- <span data-ttu-id="ba5ea-3088">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3088">ID</span></span>
- <span data-ttu-id="ba5ea-3089">Процедура</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3089">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="ba5ea-3090">Регистрационный номер жителя Южной Кореи</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3090">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3091">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3091">Format</span></span>

<span data-ttu-id="ba5ea-3092">13 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3092">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3093">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3093">Pattern</span></span>

<span data-ttu-id="ba5ea-3094">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3094">13 digits:</span></span>
- <span data-ttu-id="ba5ea-3095">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3095">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ba5ea-3096">дефис;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3096">A hyphen</span></span> 
- <span data-ttu-id="ba5ea-3097">одна цифра (определяет век и пол);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3097">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="ba5ea-3098">код региона рождения из четырех цифр;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3098">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="ba5ea-3099">одна цифра, используемая для разграничения людей, у которых предшествующие цифры совпадают;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3099">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="ba5ea-3100">проверочная цифра.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3100">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3101">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3101">Checksum</span></span>

<span data-ttu-id="ba5ea-3102">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3102">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3103">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3103">Definition</span></span>

<span data-ttu-id="ba5ea-3104">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3104">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3105">функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3105">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3106">находится ключевое слово из Keyword_south_korea_resident_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3106">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="ba5ea-3107">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3107">The checksum passes.</span></span>

<span data-ttu-id="ba5ea-3108">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3109">функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3109">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3110">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3110">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3111">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3111">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="ba5ea-3112">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3112">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="ba5ea-3113">National ID card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3113">National ID card</span></span> 
- <span data-ttu-id="ba5ea-3114">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3114">Citizen's Registration Number</span></span> 
- <span data-ttu-id="ba5ea-3115">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3115">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="ba5ea-3116">ррн</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3116">RRN</span></span> 
- <span data-ttu-id="ba5ea-3117">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3117">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="ba5ea-3118">Страховой номер для Испании (SSN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3118">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3119">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3119">Format</span></span>

<span data-ttu-id="ba5ea-3120">11–12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3120">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3121">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3121">Pattern</span></span>

<span data-ttu-id="ba5ea-3122">11-12 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3122">11-12 digits:</span></span>
- <span data-ttu-id="ba5ea-3123">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3123">Two digits</span></span> 
- <span data-ttu-id="ba5ea-3124">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3124">A forward slash (optional)</span></span> 
- <span data-ttu-id="ba5ea-3125">7–8 цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3125">7-8 digits</span></span> 
- <span data-ttu-id="ba5ea-3126">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3126">A forward slash (optional)</span></span> 
- <span data-ttu-id="ba5ea-3127">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3127">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3128">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3128">Checksum</span></span>

<span data-ttu-id="ba5ea-3129">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3129">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3130">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3130">Definition</span></span>

<span data-ttu-id="ba5ea-3131">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3132">функция Func_spanish_social_security_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3132">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3133">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3133">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3134">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3134">Keywords</span></span>

<span data-ttu-id="ba5ea-3135">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3135">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="ba5ea-3136">Строка подключения к SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3136">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3137">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3137">Format</span></span>

<span data-ttu-id="ba5ea-3138">Строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId", за которыми следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3138">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3139">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3139">Pattern</span></span>

- <span data-ttu-id="ba5ea-3140">Строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3140">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="ba5ea-3141">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3141">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ba5ea-3142">Строка "Password" или "pwd", где "pwd" не предшествует буква нижнего регистра</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3142">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="ba5ea-3143">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3143">An equal sign (=)</span></span>
- <span data-ttu-id="ba5ea-3144">Любой символ, не являющийся знаком доллара ($), символ процента (%), символ "больше" (>), символ "@", "символ" (@), знак кавычек ("), точка с запятой (;), левая фигурная скобка ([) или левая квадратная скобка ({)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3144">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="ba5ea-3145">Любая комбинация 7-128 символов, не отделяющая точку с запятой (;), косая черта (/) или кавычки (").</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3145">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="ba5ea-3146">Точка с запятой (;) или кавычки (")</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3146">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3147">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3147">Checksum</span></span>

<span data-ttu-id="ba5ea-3148">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3148">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3149">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3149">Definition</span></span>

<span data-ttu-id="ba5ea-3150">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3150">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3151">Регулярное выражение CEP_Regex_SQLServerConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3151">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3152">**Не** найдено ключевое слово из CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3152">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="ba5ea-3153">Регулярное выражение CEP_PasswordPlaceHolder не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3153">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3154">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3154">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3155">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3155">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="ba5ea-3156">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3156">CEP_GlobalFilter</span></span>

- <span data-ttu-id="ba5ea-3157">Некоторые пароли</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3157">some-password</span></span>
- <span data-ttu-id="ba5ea-3158">сомепассворд</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3158">somepassword</span></span>
- <span data-ttu-id="ba5ea-3159">секретпассворд</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3159">secretPassword</span></span>
- <span data-ttu-id="ba5ea-3160">примером</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3160">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="ba5ea-3161">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3161">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="ba5ea-3162">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3162">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-3163">Пароль или pwd, за которым следует 0-2 пробелов, знак равенства (=), 0-2 пробелы и звездочка (\*)--или--</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3163">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="ba5ea-3164">Пароль или pwd, а затем:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3164">Password or pwd followed by:</span></span>
    - <span data-ttu-id="ba5ea-3165">Знак равенства (=)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3165">Equal sign (=)</span></span>
    - <span data-ttu-id="ba5ea-3166">Символ "меньше" (<)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3166">Less than symbol (<)</span></span>
    - <span data-ttu-id="ba5ea-3167">Любое сочетание 1-200 символов, которые являются буквами верхнего или нижнего регистра, цифрами, звездочкой (\*), дефисом (-), подчеркиванием (_) или символом пробела</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3167">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="ba5ea-3168">Символ "больше" (>)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3168">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ba5ea-3169">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3169">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ba5ea-3170">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3170">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ba5ea-3171">компанией</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3171">contoso</span></span>
- <span data-ttu-id="ba5ea-3172">компании</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3172">fabrikam</span></span>
- <span data-ttu-id="ba5ea-3173">базу</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3173">northwind</span></span>
- <span data-ttu-id="ba5ea-3174">песочниц</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3174">sandbox</span></span>
- <span data-ttu-id="ba5ea-3175">онебокс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3175">onebox</span></span>
- <span data-ttu-id="ba5ea-3176">localhost</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3176">localhost</span></span>
- <span data-ttu-id="ba5ea-3177">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3177">127.0.0.1</span></span>
- <span data-ttu-id="ba5ea-3178">тестакс.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3178">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-3179">порта</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3179">com</span></span>
- <span data-ttu-id="ba5ea-3180">s — int.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3180">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ba5ea-3181">команде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3181">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="ba5ea-3182">Национальный идентификатор для Швеции</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3182">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3183">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3183">Format</span></span>

<span data-ttu-id="ba5ea-3184">10 или 12 цифр и дополнительный разделитель.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3184">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3185">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3185">Pattern</span></span>

<span data-ttu-id="ba5ea-3186">10 или 12 цифр с необязательным разделителем</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3186">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="ba5ea-3187">2–4 цифры (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3187">2-4 digits (optional)</span></span> 
- <span data-ttu-id="ba5ea-3188">Шесть цифр в формате даты ГГММДД.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3188">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="ba5ea-3189">Разделитель - или + (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3189">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="ba5ea-3190">четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3190">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3191">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3191">Checksum</span></span>

<span data-ttu-id="ba5ea-3192">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3192">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3193">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3193">Definition</span></span>

<span data-ttu-id="ba5ea-3194">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3194">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3195">функция Func_swedish_national_identifier находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3195">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3196">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3196">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3197">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3197">Keywords</span></span>

<span data-ttu-id="ba5ea-3198">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3198">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="ba5ea-3199">Номер паспорта гражданина Швеции</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3199">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3200">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3200">Format</span></span>

<span data-ttu-id="ba5ea-3201">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3201">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3202">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3202">Pattern</span></span>

<span data-ttu-id="ba5ea-3203">Восемь последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3203">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3204">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3204">Checksum</span></span>

<span data-ttu-id="ba5ea-3205">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3205">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3206">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3206">Definition</span></span>

<span data-ttu-id="ba5ea-3207">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3208">Регулярное выражение Regex_sweden_passport_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3208">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3209">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3209">One of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-3210">найдено ключевое слово из Keyword_passport;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3210">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="ba5ea-3211">найдено ключевое слово из Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3211">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3212">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3212">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="ba5ea-3213">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3213">Keyword_sweden_passport</span></span>

- <span data-ttu-id="ba5ea-3214">visa requirements</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3214">visa requirements</span></span> 
- <span data-ttu-id="ba5ea-3215">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3215">Alien Registration Card</span></span> 
- <span data-ttu-id="ba5ea-3216">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3216">Schengen visas</span></span> 
- <span data-ttu-id="ba5ea-3217">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3217">Schengen visa</span></span> 
- <span data-ttu-id="ba5ea-3218">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3218">Visa Processing</span></span> 
- <span data-ttu-id="ba5ea-3219">Visa Type</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3219">Visa Type</span></span> 
- <span data-ttu-id="ba5ea-3220">Single Entry</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3220">Single Entry</span></span> 
- <span data-ttu-id="ba5ea-3221">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3221">Multiple Entry</span></span> 
- <span data-ttu-id="ba5ea-3222">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3222">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="ba5ea-3223">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3223">Keyword_passport</span></span>

- <span data-ttu-id="ba5ea-3224">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3224">Passport Number</span></span> 
- <span data-ttu-id="ba5ea-3225">Passport No</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3225">Passport No</span></span> 
- <span data-ttu-id="ba5ea-3226">Passport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3226">Passport #</span></span> 
- <span data-ttu-id="ba5ea-3227">Службу #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3227">Passport#</span></span> 
- <span data-ttu-id="ba5ea-3228">пасспортид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3228">PassportID</span></span> 
- <span data-ttu-id="ba5ea-3229">пасспортно</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3229">Passportno</span></span> 
- <span data-ttu-id="ba5ea-3230">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3230">passportnumber</span></span> 
- <span data-ttu-id="ba5ea-3231">パスポート</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3231">パスポート</span></span> 
- <span data-ttu-id="ba5ea-3232">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3232">パスポート番号</span></span> 
- <span data-ttu-id="ba5ea-3233">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3233">パスポートのNum</span></span> 
- <span data-ttu-id="ba5ea-3234">パスポート #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3234">パスポート＃</span></span> 
- <span data-ttu-id="ba5ea-3235">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3235">Numéro de passeport</span></span> 
- <span data-ttu-id="ba5ea-3236">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3236">Passeport n °</span></span> 
- <span data-ttu-id="ba5ea-3237">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3237">Passeport Non</span></span> 
- <span data-ttu-id="ba5ea-3238">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3238">Passeport #</span></span> 
- <span data-ttu-id="ba5ea-3239">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3239">Passeport#</span></span> 
- <span data-ttu-id="ba5ea-3240">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3240">PasseportNon</span></span> 
- <span data-ttu-id="ba5ea-3241">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3241">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="ba5ea-3242">Код SWIFT</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3242">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3243">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3243">Format</span></span>

<span data-ttu-id="ba5ea-3244">Четыре буквы, за которыми следуют от 5 до 31 буквы или цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3244">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3245">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3245">Pattern</span></span>

<span data-ttu-id="ba5ea-3246">Четыре буквы, за которыми следуют от 5 до 31 буквы или цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3246">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="ba5ea-3247">Четырехбуквенный код банка (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3247">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-3248">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3248">An optional space</span></span> 
- <span data-ttu-id="ba5ea-3249">4–28 букв или цифр (основной номер банковского счета, BBAN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3249">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="ba5ea-3250">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3250">An optional space</span></span> 
- <span data-ttu-id="ba5ea-3251">1–3 буквы или цифры (оставшаяся часть BBAN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3251">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3252">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3252">Checksum</span></span>

<span data-ttu-id="ba5ea-3253">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3253">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3254">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3254">Definition</span></span>

<span data-ttu-id="ba5ea-3255">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3256">регулярное выражение Regex_swift находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3256">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3257">находится ключевое слово из Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3257">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3258">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3258">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="ba5ea-3259">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3259">Keyword_swift</span></span>

- <span data-ttu-id="ba5ea-3260">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3260">international organization for standardization 9362</span></span> 
- <span data-ttu-id="ba5ea-3261">iso 9362</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3261">iso 9362</span></span> 
- <span data-ttu-id="ba5ea-3262">iso9362</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3262">iso9362</span></span> 
- <span data-ttu-id="ba5ea-3263">SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3263">swift\#</span></span> 
- <span data-ttu-id="ba5ea-3264">свифткоде</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3264">swiftcode</span></span> 
- <span data-ttu-id="ba5ea-3265">свифтнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3265">swiftnumber</span></span> 
- <span data-ttu-id="ba5ea-3266">свифтраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3266">swiftroutingnumber</span></span> 
- <span data-ttu-id="ba5ea-3267">swift code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3267">swift code</span></span> 
- <span data-ttu-id="ba5ea-3268">swift number #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3268">swift number #</span></span> 
- <span data-ttu-id="ba5ea-3269">swift routing number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3269">swift routing number</span></span> 
- <span data-ttu-id="ba5ea-3270">bic number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3270">bic number</span></span> 
- <span data-ttu-id="ba5ea-3271">bic code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3271">bic code</span></span> 
- <span data-ttu-id="ba5ea-3272">БИК\#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3272">bic \#</span></span> 
- <span data-ttu-id="ba5ea-3273">БИК\#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3273">bic\#</span></span> 
- <span data-ttu-id="ba5ea-3274">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3274">bank identifier code</span></span> 
- <span data-ttu-id="ba5ea-3275">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3275">標準化9362</span></span> 
- <span data-ttu-id="ba5ea-3276">迅速 #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3276">迅速＃</span></span> 
- <span data-ttu-id="ba5ea-3277">свифтコード</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3277">SWIFTコード</span></span> 
- <span data-ttu-id="ba5ea-3278">свифт番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3278">SWIFT番号</span></span> 
- <span data-ttu-id="ba5ea-3279">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3279">迅速なルーティング番号</span></span> 
- <span data-ttu-id="ba5ea-3280">бик番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3280">BIC番号</span></span> 
- <span data-ttu-id="ba5ea-3281">бикコード</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3281">BICコード</span></span> 
- <span data-ttu-id="ba5ea-3282">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3282">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="ba5ea-3283">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3283">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="ba5ea-3284">Быстрая\#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3284">rapide \#</span></span> 
- <span data-ttu-id="ba5ea-3285">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3285">code SWIFT</span></span> 
- <span data-ttu-id="ba5ea-3286">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3286">le numéro de swift</span></span> 
- <span data-ttu-id="ba5ea-3287">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3287">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="ba5ea-3288">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3288">le numéro BIC</span></span> 
- <span data-ttu-id="ba5ea-3289">\#БИК</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3289">\# BIC</span></span> 
- <span data-ttu-id="ba5ea-3290">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3290">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="ba5ea-3291">Национальный идентификатор, Тайвань</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3291">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3292">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3292">Format</span></span>

<span data-ttu-id="ba5ea-3293">Одна буква (английская), за которой следуют девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3293">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3294">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3294">Pattern</span></span>

<span data-ttu-id="ba5ea-3295">Один символ , за которым следуют девять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3295">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="ba5ea-3296">Один символ (на английском языке, без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3296">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-3297">Цифра 1 или 2</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3297">The digit "1" or "2"</span></span> 
- <span data-ttu-id="ba5ea-3298">Восемь цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3298">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3299">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3299">Checksum</span></span>

<span data-ttu-id="ba5ea-3300">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3300">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3301">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3301">Definition</span></span>

<span data-ttu-id="ba5ea-3302">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3302">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3303">функция Func_taiwanese_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3303">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3304">находится ключевое слово из Keyword_taiwanese_national_id;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3304">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="ba5ea-3305">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3305">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3306">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3306">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="ba5ea-3307">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3307">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="ba5ea-3308">身份證字號</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3308">身份證字號</span></span> 
- <span data-ttu-id="ba5ea-3309">身份證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3309">身份證</span></span> 
- <span data-ttu-id="ba5ea-3310">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3310">身份證號碼</span></span> 
- <span data-ttu-id="ba5ea-3311">身份證號</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3311">身份證號</span></span> 
- <span data-ttu-id="ba5ea-3312">身分證字號</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3312">身分證字號</span></span> 
- <span data-ttu-id="ba5ea-3313">身分證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3313">身分證</span></span> 
- <span data-ttu-id="ba5ea-3314">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3314">身分證號碼</span></span> 
- <span data-ttu-id="ba5ea-3315">身份證號</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3315">身份證號</span></span> 
- <span data-ttu-id="ba5ea-3316">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3316">身分證統一編號</span></span> 
- <span data-ttu-id="ba5ea-3317">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3317">國民身分證統一編號</span></span> 
- <span data-ttu-id="ba5ea-3318">簽名</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3318">簽名</span></span> 
- <span data-ttu-id="ba5ea-3319">蓋章</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3319">蓋章</span></span> 
- <span data-ttu-id="ba5ea-3320">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3320">簽名或蓋章</span></span> 
- <span data-ttu-id="ba5ea-3321">簽章</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3321">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="ba5ea-3322">	Номер паспорта гражданина Тайваня</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3322">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3323">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3323">Format</span></span>

- <span data-ttu-id="ba5ea-3324">Номер биометрического паспорта: девять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3324">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="ba5ea-3325">Номер биометрической службы Passport: девять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3325">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3326">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3326">Pattern</span></span>
<span data-ttu-id="ba5ea-3327">Номер биометрического паспорта:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3327">Biometric passport number:</span></span>
- <span data-ttu-id="ba5ea-3328">цифра "3";</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3328">The digit "3"</span></span> 
- <span data-ttu-id="ba5ea-3329">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3329">Eight digits</span></span>

<span data-ttu-id="ba5ea-3330">Номер биометрической службы Passport:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3330">Non-biometric passport number:</span></span>
- <span data-ttu-id="ba5ea-3331">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3331">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3332">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3332">Checksum</span></span>

<span data-ttu-id="ba5ea-3333">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3333">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3334">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3334">Definition</span></span>

<span data-ttu-id="ba5ea-3335">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3336">регулярное выражение Regex_taiwan_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3336">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3337">находится ключевое слово из Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3337">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3338">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3338">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="ba5ea-3339">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3339">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="ba5ea-3340">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3340">ROC passport number</span></span> 
- <span data-ttu-id="ba5ea-3341">Passport number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3341">Passport number</span></span> 
- <span data-ttu-id="ba5ea-3342">Passport no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3342">Passport no</span></span> 
- <span data-ttu-id="ba5ea-3343">Passport Num</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3343">Passport Num</span></span> 
- <span data-ttu-id="ba5ea-3344">Passport #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3344">Passport #</span></span> 
- <span data-ttu-id="ba5ea-3345">护照</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3345">护照</span></span> 
- <span data-ttu-id="ba5ea-3346">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3346">中華民國護照</span></span> 
- <span data-ttu-id="ba5ea-3347">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3347">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="ba5ea-3348">Номер удостоверения жителя Тайваня (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3348">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3349">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3349">Format</span></span>

<span data-ttu-id="ba5ea-3350">10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3350">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3351">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3351">Pattern</span></span>

<span data-ttu-id="ba5ea-3352">10 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3352">10 letters and digits:</span></span>
- <span data-ttu-id="ba5ea-3353">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3353">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="ba5ea-3354">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3354">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3355">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3355">Checksum</span></span>

<span data-ttu-id="ba5ea-3356">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3356">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3357">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3357">Definition</span></span>

<span data-ttu-id="ba5ea-3358">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3358">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3359">регулярное выражение Regex_taiwan_resident_certificate находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3359">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3360">находится ключевое слово из Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3360">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3361">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3361">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="ba5ea-3362">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3362">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="ba5ea-3363">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3363">Resident Certificate</span></span> 
- <span data-ttu-id="ba5ea-3364">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3364">Resident Cert</span></span> 
- <span data-ttu-id="ba5ea-3365">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3365">Resident Cert.</span></span> 
- <span data-ttu-id="ba5ea-3366">Identification card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3366">Identification card</span></span> 
- <span data-ttu-id="ba5ea-3367">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3367">Alien Resident Certificate</span></span> 
- <span data-ttu-id="ba5ea-3368">ARC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3368">ARC</span></span> 
- <span data-ttu-id="ba5ea-3369">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3369">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="ba5ea-3370">TARC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3370">TARC</span></span> 
- <span data-ttu-id="ba5ea-3371">居留證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3371">居留證</span></span> 
- <span data-ttu-id="ba5ea-3372">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3372">外僑居留證</span></span> 
- <span data-ttu-id="ba5ea-3373">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3373">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="ba5ea-3374">Код идентификации для тайского заполнения</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3374">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3375">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3375">Format</span></span>

<span data-ttu-id="ba5ea-3376">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3376">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3377">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3377">Pattern</span></span>

<span data-ttu-id="ba5ea-3378">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3378">13 digits:</span></span>
- <span data-ttu-id="ba5ea-3379">Первая цифра не равна 0 или 9</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3379">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="ba5ea-3380">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3380">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3381">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3381">Checksum</span></span>

<span data-ttu-id="ba5ea-3382">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3382">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3383">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3383">Definition</span></span>

<span data-ttu-id="ba5ea-3384">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3384">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3385">Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3385">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3386">Найдено ключевое слово из Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3386">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="ba5ea-3387">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3387">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3388">Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3388">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3389">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3389">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="ba5ea-3390">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3390">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="ba5ea-3391">ID Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3391">ID Number</span></span>
- <span data-ttu-id="ba5ea-3392">Идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3392">Identification Number</span></span>
- <span data-ttu-id="ba5ea-3393">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3393">บัตรประชาชน</span></span>
- <span data-ttu-id="ba5ea-3394">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3394">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="ba5ea-3395">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3395">บัตรประชาชน</span></span>
- <span data-ttu-id="ba5ea-3396">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3396">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="ba5ea-3397">Турецкий национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3397">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3398">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3398">Format</span></span>

<span data-ttu-id="ba5ea-3399">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3399">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3400">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3400">Pattern</span></span>

<span data-ttu-id="ba5ea-3401">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3401">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3402">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3402">Checksum</span></span>

<span data-ttu-id="ba5ea-3403">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3403">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3404">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3404">Definition</span></span>

<span data-ttu-id="ba5ea-3405">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3405">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3406">Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3406">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3407">Найдено ключевое слово из Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3407">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="ba5ea-3408">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3408">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3409">Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3409">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3410">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3410">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="ba5ea-3411">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3411">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="ba5ea-3412">TC Кимлик No</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3412">TC Kimlik No</span></span>
- <span data-ttu-id="ba5ea-3413">TC Кимлик нумарасı</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3413">TC Kimlik numarası</span></span>
- <span data-ttu-id="ba5ea-3414">Ватандаşлıк нумарасı</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3414">Vatandaşlık numarası</span></span>
- <span data-ttu-id="ba5ea-3415">Ватандаşлıк нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3415">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="ba5ea-p142">Номер водительского удостоверения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="ba5ea-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3418">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3418">Format</span></span>

<span data-ttu-id="ba5ea-3419">Сочетание 18 букв и цифр в указанном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3419">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3420">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3420">Pattern</span></span>

<span data-ttu-id="ba5ea-3421">18 букв и цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3421">18 letters and digits:</span></span>
- <span data-ttu-id="ba5ea-3422">Пять букв (без учета регистра) или цифра 9 вместо буквы</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3422">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="ba5ea-3423">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3423">One digit</span></span> 
- <span data-ttu-id="ba5ea-3424">Пять цифр в формате даты ММДДИ для даты рождения (седьмой символ увеличивается на 50, если драйвер — гнездо, то есть 51 – 62, а не с 01 – 12)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3424">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="ba5ea-3425">Две буквы (без учета регистра) или цифра 9 вместо буквы</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3425">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="ba5ea-3426">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3426">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3427">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3427">Checksum</span></span>

<span data-ttu-id="ba5ea-3428">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3428">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3429">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3429">Definition</span></span>

<span data-ttu-id="ba5ea-3430">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3430">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3431">функция Func_uk_drivers_license находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3431">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3432">находится ключевое слово из Keyword_uk_drivers_license;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3432">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="ba5ea-3433">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3433">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3434">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3434">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="ba5ea-3435">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3435">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="ba5ea-3436">двла</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3436">DVLA</span></span> 
- <span data-ttu-id="ba5ea-3437">light vans</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3437">light vans</span></span> 
- <span data-ttu-id="ba5ea-3438">куадбикес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3438">quadbikes</span></span> 
- <span data-ttu-id="ba5ea-3439">motor cars</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3439">motor cars</span></span> 
- <span data-ttu-id="ba5ea-3440">125cc</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3440">125cc</span></span> 
- <span data-ttu-id="ba5ea-3441">сидекар</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3441">sidecar</span></span> 
- <span data-ttu-id="ba5ea-3442">трициклес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3442">tricycles</span></span> 
- <span data-ttu-id="ba5ea-3443">моторциклес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3443">motorcycles</span></span> 
- <span data-ttu-id="ba5ea-3444">photocard licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3444">photocard licence</span></span> 
- <span data-ttu-id="ba5ea-3445">learner drivers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3445">learner drivers</span></span> 
- <span data-ttu-id="ba5ea-3446">licence holder</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3446">licence holder</span></span> 
- <span data-ttu-id="ba5ea-3447">licence holders</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3447">licence holders</span></span> 
- <span data-ttu-id="ba5ea-3448">driving licences</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3448">driving licences</span></span> 
- <span data-ttu-id="ba5ea-3449">driving licence</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3449">driving licence</span></span> 
- <span data-ttu-id="ba5ea-3450">dual control car</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3450">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="ba5ea-p143">Регистрационный номер избирателя для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="ba5ea-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3453">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3453">Format</span></span>

<span data-ttu-id="ba5ea-3454">Две буквы, за которыми следуют 1–4 цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3454">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3455">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3455">Pattern</span></span>

<span data-ttu-id="ba5ea-3456">Две буквы (без учета регистра), за которыми следуют 1–4 цифры.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3456">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3457">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3457">Checksum</span></span>

<span data-ttu-id="ba5ea-3458">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3459">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3459">Definition</span></span>

<span data-ttu-id="ba5ea-3460">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3460">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3461">регулярное выражение Regex_uk_electoral находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3461">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3462">находится ключевое слово из Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3462">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3463">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3463">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="ba5ea-3464">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3464">Keyword_uk_electoral</span></span>

- <span data-ttu-id="ba5ea-3465">council nomination</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3465">council nomination</span></span> 
- <span data-ttu-id="ba5ea-3466">nomination form</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3466">nomination form</span></span> 
- <span data-ttu-id="ba5ea-3467">electoral register</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3467">electoral register</span></span> 
- <span data-ttu-id="ba5ea-3468">electoral roll</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3468">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="ba5ea-p144">Номер национальной службы здравоохранения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="ba5ea-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3471">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3471">Format</span></span>

<span data-ttu-id="ba5ea-3472">10–17 цифр, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3472">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3473">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3473">Pattern</span></span>

<span data-ttu-id="ba5ea-3474">10-17 цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3474">10-17 digits:</span></span>
- <span data-ttu-id="ba5ea-3475">3 или 10 цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3475">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="ba5ea-3476">Пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3476">A space</span></span> 
- <span data-ttu-id="ba5ea-3477">Три цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3477">Three digits</span></span> 
- <span data-ttu-id="ba5ea-3478">Пробел</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3478">A space</span></span> 
- <span data-ttu-id="ba5ea-3479">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3479">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3480">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3480">Checksum</span></span>

<span data-ttu-id="ba5ea-3481">Да</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3481">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3482">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3482">Definition</span></span>

<span data-ttu-id="ba5ea-3483">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3483">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3484">Функция Func_uk_nhs_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3484">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3485">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3485">One of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-3486">найдено ключевое слово из Keyword_uk_nhs_number;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3486">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="ba5ea-3487">найдено ключевое слово из Keyword_uk_nhs_number1;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3487">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="ba5ea-3488">найдено ключевое слово из Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3488">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="ba5ea-3489">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3489">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3490">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3490">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="ba5ea-3491">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3491">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="ba5ea-3492">national health service</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3492">national health service</span></span> 
- <span data-ttu-id="ba5ea-3493">NHS</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3493">nhs</span></span> 
- <span data-ttu-id="ba5ea-3494">health services authority</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3494">health services authority</span></span> 
- <span data-ttu-id="ba5ea-3495">health authority</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3495">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="ba5ea-3496">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3496">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="ba5ea-3497">patient id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3497">patient id</span></span> 
- <span data-ttu-id="ba5ea-3498">patient identification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3498">patient identification</span></span> 
- <span data-ttu-id="ba5ea-3499">patient no</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3499">patient no</span></span> 
- <span data-ttu-id="ba5ea-3500">patient number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3500">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="ba5ea-3501">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3501">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="ba5ea-3502">ГРУПП</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3502">GP</span></span> 
- <span data-ttu-id="ba5ea-3503">доб</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3503">DOB</span></span> 
- <span data-ttu-id="ba5ea-3504">D. O. B</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3504">D.O.B</span></span> 
- <span data-ttu-id="ba5ea-3505">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3505">Date of Birth</span></span> 
- <span data-ttu-id="ba5ea-3506">Birth Date</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3506">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="ba5ea-p145">Номер карты национального страхования для Соединенного Королевства (NINO)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3509">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3509">Format</span></span>

<span data-ttu-id="ba5ea-3510">7 символов или 9 символов, разделенных пробелами или тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3510">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3511">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3511">Pattern</span></span>

<span data-ttu-id="ba5ea-3512">Два возможных шаблона:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3512">Two possible patterns:</span></span>

- <span data-ttu-id="ba5ea-3513">Две буквы (допустимые Нинос используют только определенные символы в этом префиксе, которые пропускаются при проверке этого шаблона; без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3513">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="ba5ea-3514">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3514">Six digits</span></span>
- <span data-ttu-id="ba5ea-3515">"A", "B", "C", или "'D" (например, префикс, в суффиксе допускаются только определенные символы; без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3515">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="ba5ea-3516">OR</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3516">OR</span></span>

- <span data-ttu-id="ba5ea-3517">Две буквы</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3517">Two letters</span></span>
- <span data-ttu-id="ba5ea-3518">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3518">A space or dash</span></span>
- <span data-ttu-id="ba5ea-3519">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3519">Two digits</span></span>
- <span data-ttu-id="ba5ea-3520">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3520">A space or dash</span></span>
- <span data-ttu-id="ba5ea-3521">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3521">Two digits</span></span>
- <span data-ttu-id="ba5ea-3522">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3522">A space or dash</span></span>
- <span data-ttu-id="ba5ea-3523">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3523">Two digits</span></span>
- <span data-ttu-id="ba5ea-3524">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3524">A space or dash</span></span>
- <span data-ttu-id="ba5ea-3525">Значение "A", "B", "C" или "'D"</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3525">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3526">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3526">Checksum</span></span>

<span data-ttu-id="ba5ea-3527">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3527">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3528">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3528">Definition</span></span>

<span data-ttu-id="ba5ea-3529">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3530">функция Func_uk_nino находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3530">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3531">находится ключевое слово из Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3531">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="ba5ea-3532">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3532">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3533">функция Func_uk_nino находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3533">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3534">ни одно ключевое слово из Keyword_uk_nino не находится.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3534">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3535">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3535">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="ba5ea-3536">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3536">Keyword_uk_nino</span></span>

- <span data-ttu-id="ba5ea-3537">national insurance number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3537">national insurance number</span></span> 
- <span data-ttu-id="ba5ea-3538">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3538">national insurance contributions</span></span> 
- <span data-ttu-id="ba5ea-3539">protection act</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3539">protection act</span></span> 
- <span data-ttu-id="ba5ea-3540">страхования</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3540">insurance</span></span> 
- <span data-ttu-id="ba5ea-3541">social security number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3541">social security number</span></span> 
- <span data-ttu-id="ba5ea-3542">insurance application</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3542">insurance application</span></span> 
- <span data-ttu-id="ba5ea-3543">medical application</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3543">medical application</span></span> 
- <span data-ttu-id="ba5ea-3544">social insurance</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3544">social insurance</span></span> 
- <span data-ttu-id="ba5ea-3545">medical attention</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3545">medical attention</span></span> 
- <span data-ttu-id="ba5ea-3546">social security</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3546">social security</span></span> 
- <span data-ttu-id="ba5ea-3547">great britain</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3547">great britain</span></span> 
- <span data-ttu-id="ba5ea-3548">страхования</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3548">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="ba5ea-p146">Номер паспорта гражданина США и/или Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="ba5ea-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3551">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3551">Format</span></span>

<span data-ttu-id="ba5ea-3552">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3552">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3553">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3553">Pattern</span></span>

<span data-ttu-id="ba5ea-3554">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3554">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3555">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3555">Checksum</span></span>

<span data-ttu-id="ba5ea-3556">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3556">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3557">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3557">Definition</span></span>

<span data-ttu-id="ba5ea-3558">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3558">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3559">функция Func_usa_uk_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3559">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3560">находится ключевое слово из Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3560">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3561">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3561">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ba5ea-3562">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3562">Keyword_passport</span></span>

- <span data-ttu-id="ba5ea-3563">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3563">Passport Number</span></span> 
- <span data-ttu-id="ba5ea-3564">Passport No</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3564">Passport No</span></span> 
- <span data-ttu-id="ba5ea-3565">Passport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3565">Passport #</span></span> 
- <span data-ttu-id="ba5ea-3566">Службу #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3566">Passport#</span></span> 
- <span data-ttu-id="ba5ea-3567">пасспортид</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3567">PassportID</span></span> 
- <span data-ttu-id="ba5ea-3568">пасспортно</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3568">Passportno</span></span> 
- <span data-ttu-id="ba5ea-3569">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3569">passportnumber</span></span> 
- <span data-ttu-id="ba5ea-3570">パスポート</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3570">パスポート</span></span> 
- <span data-ttu-id="ba5ea-3571">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3571">パスポート番号</span></span> 
- <span data-ttu-id="ba5ea-3572">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3572">パスポートのNum</span></span> 
- <span data-ttu-id="ba5ea-3573">パスポート #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3573">パスポート＃</span></span> 
- <span data-ttu-id="ba5ea-3574">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3574">Numéro de passeport</span></span> 
- <span data-ttu-id="ba5ea-3575">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3575">Passeport n °</span></span> 
- <span data-ttu-id="ba5ea-3576">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3576">Passeport Non</span></span> 
- <span data-ttu-id="ba5ea-3577">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3577">Passeport #</span></span> 
- <span data-ttu-id="ba5ea-3578">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3578">Passeport#</span></span> 
- <span data-ttu-id="ba5ea-3579">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3579">PasseportNon</span></span> 
- <span data-ttu-id="ba5ea-3580">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3580">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="ba5ea-3581">Номер банковского счета для США</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3581">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3582">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3582">Format</span></span>

<span data-ttu-id="ba5ea-3583">8-17 цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3583">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3584">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3584">Pattern</span></span>

<span data-ttu-id="ba5ea-3585">8–17 последовательных цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3585">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3586">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3586">Checksum</span></span>

<span data-ttu-id="ba5ea-3587">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3587">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3588">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3588">Definition</span></span>

<span data-ttu-id="ba5ea-3589">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3589">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3590">регулярное выражение Regex_usa_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3590">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3591">находится ключевое слово из Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3591">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3592">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3592">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="ba5ea-3593">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3593">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="ba5ea-3594">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3594">Checking Account Number</span></span> 
- <span data-ttu-id="ba5ea-3595">Checking Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3595">Checking Account</span></span> 
- <span data-ttu-id="ba5ea-3596">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3596">Checking Account #</span></span> 
- <span data-ttu-id="ba5ea-3597">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3597">Checking Acct Number</span></span> 
- <span data-ttu-id="ba5ea-3598">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3598">Checking Acct #</span></span> 
- <span data-ttu-id="ba5ea-3599">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3599">Checking Acct No.</span></span> 
- <span data-ttu-id="ba5ea-3600">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3600">Checking Account No.</span></span> 
- <span data-ttu-id="ba5ea-3601">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3601">Bank Account Number</span></span> 
- <span data-ttu-id="ba5ea-3602">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3602">Bank Account #</span></span> 
- <span data-ttu-id="ba5ea-3603">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3603">Bank Acct Number</span></span> 
- <span data-ttu-id="ba5ea-3604">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3604">Bank Acct #</span></span> 
- <span data-ttu-id="ba5ea-3605">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3605">Bank Acct No.</span></span> 
- <span data-ttu-id="ba5ea-3606">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3606">Bank Account No.</span></span> 
- <span data-ttu-id="ba5ea-3607">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3607">Savings Account Number</span></span> 
- <span data-ttu-id="ba5ea-3608">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3608">Savings Account.</span></span> 
- <span data-ttu-id="ba5ea-3609">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3609">Savings Account #</span></span> 
- <span data-ttu-id="ba5ea-3610">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3610">Savings Acct Number</span></span> 
- <span data-ttu-id="ba5ea-3611">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3611">Savings Acct #</span></span> 
- <span data-ttu-id="ba5ea-3612">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3612">Savings Acct No.</span></span> 
- <span data-ttu-id="ba5ea-3613">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3613">Savings Account No.</span></span> 
- <span data-ttu-id="ba5ea-3614">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3614">Debit Account Number</span></span> 
- <span data-ttu-id="ba5ea-3615">Debit Account</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3615">Debit Account</span></span> 
- <span data-ttu-id="ba5ea-3616">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3616">Debit Account #</span></span> 
- <span data-ttu-id="ba5ea-3617">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3617">Debit Acct Number</span></span> 
- <span data-ttu-id="ba5ea-3618">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3618">Debit Acct #</span></span> 
- <span data-ttu-id="ba5ea-3619">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3619">Debit Acct No.</span></span> 
- <span data-ttu-id="ba5ea-3620">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3620">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="ba5ea-3621">Номер водительского удостоверения для США</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3621">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3622">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3622">Format</span></span>

<span data-ttu-id="ba5ea-3623">Зависит от штата.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3623">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3624">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3624">Pattern</span></span>

<span data-ttu-id="ba5ea-3625">В зависимости от штата. Например, для Нью-Йорка:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3625">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="ba5ea-3626">Девять цифр, отформатированных как DDD DDD DDD, будут совпадают.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3626">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="ba5ea-3627">Не подойдут девять цифр в формате ццццццццц.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3627">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3628">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3628">Checksum</span></span>

<span data-ttu-id="ba5ea-3629">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3629">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3630">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3630">Definition</span></span>

<span data-ttu-id="ba5ea-3631">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3631">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3632">функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3632">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3633">находится ключевое слово из Keyword_[state_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3633">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="ba5ea-3634">обнаружено ключевое слово из списка Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3634">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="ba5ea-3635">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3635">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3636">функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3636">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3637">находится ключевое слово из Keyword_[state_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3637">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="ba5ea-3638">находится ключевое слово из Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3638">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="ba5ea-3639">ни одно ключевое слово из Keyword_us_drivers_license не находится.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3639">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
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
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3640">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3640">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="ba5ea-3641">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3641">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="ba5ea-3642">DL</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3642">DL</span></span> 
- <span data-ttu-id="ba5ea-3643">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3643">DLS</span></span> 
- <span data-ttu-id="ba5ea-3644">кдл</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3644">CDL</span></span> 
- <span data-ttu-id="ba5ea-3645">кдлс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3645">CDLS</span></span> 
- <span data-ttu-id="ba5ea-3646">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3646">ID</span></span> 
- <span data-ttu-id="ba5ea-3647">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3647">IDs</span></span> 
- <span data-ttu-id="ba5ea-3648">DL #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3648">DL#</span></span> 
- <span data-ttu-id="ba5ea-3649">БИБЛИОТЕК #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3649">DLS#</span></span> 
- <span data-ttu-id="ba5ea-3650">кдл #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3650">CDL#</span></span> 
- <span data-ttu-id="ba5ea-3651">кдлс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3651">CDLS#</span></span> 
- <span data-ttu-id="ba5ea-3652">КОДОВ #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3652">ID#</span></span>
- <span data-ttu-id="ba5ea-3653">Идентификаторы #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3653">IDs#</span></span> 
- <span data-ttu-id="ba5ea-3654">ID number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3654">ID number</span></span> 
- <span data-ttu-id="ba5ea-3655">ID numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3655">ID numbers</span></span> 
- <span data-ttu-id="ba5ea-3656">лик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3656">LIC</span></span> 
- <span data-ttu-id="ba5ea-3657">лик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3657">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="ba5ea-3658">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3658">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="ba5ea-3659">дриверлик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3659">DriverLic</span></span> 
- <span data-ttu-id="ba5ea-3660">дриверликс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3660">DriverLics</span></span> 
- <span data-ttu-id="ba5ea-3661">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3661">DriverLicense</span></span> 
- <span data-ttu-id="ba5ea-3662">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3662">DriverLicenses</span></span> 
- <span data-ttu-id="ba5ea-3663">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3663">Driver Lic</span></span> 
- <span data-ttu-id="ba5ea-3664">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3664">Driver Lics</span></span> 
- <span data-ttu-id="ba5ea-3665">Driver License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3665">Driver License</span></span> 
- <span data-ttu-id="ba5ea-3666">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3666">Driver Licenses</span></span> 
- <span data-ttu-id="ba5ea-3667">дриверслик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3667">DriversLic</span></span> 
- <span data-ttu-id="ba5ea-3668">дриверсликс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3668">DriversLics</span></span> 
- <span data-ttu-id="ba5ea-3669">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3669">DriversLicense</span></span> 
- <span data-ttu-id="ba5ea-3670">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3670">DriversLicenses</span></span> 
- <span data-ttu-id="ba5ea-3671">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3671">Drivers Lic</span></span> 
- <span data-ttu-id="ba5ea-3672">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3672">Drivers Lics</span></span> 
- <span data-ttu-id="ba5ea-3673">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3673">Drivers License</span></span> 
- <span data-ttu-id="ba5ea-3674">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3674">Drivers Licenses</span></span> 
- <span data-ttu-id="ba5ea-3675">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3675">Driver'Lic</span></span> 
- <span data-ttu-id="ba5ea-3676">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3676">Driver'Lics</span></span> 
- <span data-ttu-id="ba5ea-3677">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3677">Driver'License</span></span> 
- <span data-ttu-id="ba5ea-3678">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3678">Driver'Licenses</span></span> 
- <span data-ttu-id="ba5ea-3679">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3679">Driver' Lic</span></span> 
- <span data-ttu-id="ba5ea-3680">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3680">Driver' Lics</span></span> 
- <span data-ttu-id="ba5ea-3681">Driver' License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3681">Driver' License</span></span> 
- <span data-ttu-id="ba5ea-3682">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3682">Driver' Licenses</span></span>
- <span data-ttu-id="ba5ea-3683">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3683">Driver'sLic</span></span> 
- <span data-ttu-id="ba5ea-3684">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3684">Driver'sLics</span></span> 
- <span data-ttu-id="ba5ea-3685">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3685">Driver'sLicense</span></span> 
- <span data-ttu-id="ba5ea-3686">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3686">Driver'sLicenses</span></span> 
- <span data-ttu-id="ba5ea-3687">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3687">Driver's Lic</span></span> 
- <span data-ttu-id="ba5ea-3688">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3688">Driver's Lics</span></span> 
- <span data-ttu-id="ba5ea-3689">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3689">Driver's License</span></span> 
- <span data-ttu-id="ba5ea-3690">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3690">Driver's Licenses</span></span> 
- <span data-ttu-id="ba5ea-3691">identification number</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3691">identification number</span></span> 
- <span data-ttu-id="ba5ea-3692">identification numbers</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3692">identification numbers</span></span> 
- <span data-ttu-id="ba5ea-3693">identification #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3693">identification #</span></span> 
- <span data-ttu-id="ba5ea-3694">id card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3694">id card</span></span> 
- <span data-ttu-id="ba5ea-3695">id cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3695">id cards</span></span> 
- <span data-ttu-id="ba5ea-3696">identification card</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3696">identification card</span></span> 
- <span data-ttu-id="ba5ea-3697">identification cards</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3697">identification cards</span></span> 
- <span data-ttu-id="ba5ea-3698">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3698">DriverLic#</span></span> 
- <span data-ttu-id="ba5ea-3699">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3699">DriverLics#</span></span> 
- <span data-ttu-id="ba5ea-3700">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3700">DriverLicense#</span></span> 
- <span data-ttu-id="ba5ea-3701">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3701">DriverLicenses#</span></span> 
- <span data-ttu-id="ba5ea-3702">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3702">Driver Lic#</span></span> 
- <span data-ttu-id="ba5ea-3703">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3703">Driver Lics#</span></span> 
- <span data-ttu-id="ba5ea-3704">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3704">Driver License#</span></span> 
- <span data-ttu-id="ba5ea-3705">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3705">Driver Licenses#</span></span> 
- <span data-ttu-id="ba5ea-3706">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3706">DriversLic#</span></span> 
- <span data-ttu-id="ba5ea-3707">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3707">DriversLics#</span></span> 
- <span data-ttu-id="ba5ea-3708">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3708">DriversLicense#</span></span> 
- <span data-ttu-id="ba5ea-3709">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3709">DriversLicenses#</span></span> 
- <span data-ttu-id="ba5ea-3710">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3710">Drivers Lic#</span></span> 
- <span data-ttu-id="ba5ea-3711">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3711">Drivers Lics#</span></span> 
- <span data-ttu-id="ba5ea-3712">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3712">Drivers License#</span></span> 
- <span data-ttu-id="ba5ea-3713">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3713">Drivers Licenses#</span></span> 
- <span data-ttu-id="ba5ea-3714">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3714">Driver'Lic#</span></span> 
- <span data-ttu-id="ba5ea-3715">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3715">Driver'Lics#</span></span> 
- <span data-ttu-id="ba5ea-3716">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3716">Driver'License#</span></span> 
- <span data-ttu-id="ba5ea-3717">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3717">Driver'Licenses#</span></span> 
- <span data-ttu-id="ba5ea-3718">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3718">Driver' Lic#</span></span> 
- <span data-ttu-id="ba5ea-3719">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3719">Driver' Lics#</span></span> 
- <span data-ttu-id="ba5ea-3720">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3720">Driver' License#</span></span> 
- <span data-ttu-id="ba5ea-3721">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3721">Driver' Licenses#</span></span> 
- <span data-ttu-id="ba5ea-3722">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3722">Driver'sLic#</span></span> 
- <span data-ttu-id="ba5ea-3723">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3723">Driver'sLics#</span></span> 
- <span data-ttu-id="ba5ea-3724">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3724">Driver'sLicense#</span></span> 
- <span data-ttu-id="ba5ea-3725">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3725">Driver'sLicenses#</span></span> 
- <span data-ttu-id="ba5ea-3726">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3726">Driver's Lic#</span></span> 
- <span data-ttu-id="ba5ea-3727">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3727">Driver's Lics#</span></span> 
- <span data-ttu-id="ba5ea-3728">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3728">Driver's License#</span></span> 
- <span data-ttu-id="ba5ea-3729">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3729">Driver's Licenses#</span></span> 
- <span data-ttu-id="ba5ea-3730">id card#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3730">id card#</span></span> 
- <span data-ttu-id="ba5ea-3731">id cards#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3731">id cards#</span></span> 
- <span data-ttu-id="ba5ea-3732">identification card#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3732">identification card#</span></span> 
- <span data-ttu-id="ba5ea-3733">identification cards#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3733">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="ba5ea-3734">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3734">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="ba5ea-3735">Аббревиатура штата (например, NY)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3735">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="ba5ea-3736">Название штата (например, New York)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3736">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="ba5ea-3737">Идентификационный номер налогоплательщика для США (ITIN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3737">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3738">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3738">Format</span></span>

<span data-ttu-id="ba5ea-3739">Девять цифр, которые начинаются с "9" и содержат "7" или "8" в качестве четвертой цифры, отформатированных с помощью пробелов или тире (необязательно).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3739">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3740">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3740">Pattern</span></span>

<span data-ttu-id="ba5ea-3741">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3741">Formatted:</span></span>
- <span data-ttu-id="ba5ea-3742">Цифра 9</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3742">The digit "9"</span></span> 
- <span data-ttu-id="ba5ea-3743">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3743">Two digits</span></span> 
- <span data-ttu-id="ba5ea-3744">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3744">A space or dash</span></span> 
- <span data-ttu-id="ba5ea-3745">Цифра 7 или 8</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3745">A "7" or "8"</span></span> 
- <span data-ttu-id="ba5ea-3746">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3746">A digit</span></span> 
- <span data-ttu-id="ba5ea-3747">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3747">A space, or dash</span></span> 
- <span data-ttu-id="ba5ea-3748">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3748">Four digits</span></span>

<span data-ttu-id="ba5ea-3749">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3749">Unformatted:</span></span>
- <span data-ttu-id="ba5ea-3750">Цифра 9</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3750">The digit "9"</span></span> 
- <span data-ttu-id="ba5ea-3751">Две цифры</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3751">Two digits</span></span> 
- <span data-ttu-id="ba5ea-3752">Цифра 7 или 8</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3752">A "7" or "8"</span></span> 
- <span data-ttu-id="ba5ea-3753">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3753">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3754">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3754">Checksum</span></span>

<span data-ttu-id="ba5ea-3755">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3755">No</span></span>

### <a name="definition"></a><span data-ttu-id="ba5ea-3756">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3756">Definition</span></span>

<span data-ttu-id="ba5ea-3757">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3757">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3758">Функция Func_formatted_itin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3758">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3759">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3759">At least one of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-3760">найдено ключевое слово из Keyword_itin;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3760">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="ba5ea-3761">функция Func_us_address находит адрес в правильном формате;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3761">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="ba5ea-3762">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3762">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="ba5ea-3763">найдено ключевое слово из Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3763">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="ba5ea-3764">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3765">Функция Func_unformatted_itin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3765">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3766">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3766">At least one of the following is true:</span></span>
    - <span data-ttu-id="ba5ea-3767">найдено ключевое слово из Keyword_itin_collaborative;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3767">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="ba5ea-3768">функция Func_us_address находит адрес в правильном формате;</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3768">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="ba5ea-3769">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3769">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="ba5ea-3770">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3770">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="ba5ea-3771">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3771">Keyword_itin</span></span>

- <span data-ttu-id="ba5ea-3772">дубликат</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3772">taxpayer</span></span> 
- <span data-ttu-id="ba5ea-3773">tax id</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3773">tax id</span></span> 
- <span data-ttu-id="ba5ea-3774">tax identification</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3774">tax identification</span></span> 
- <span data-ttu-id="ba5ea-3775">SharePointв</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3775">itin</span></span> 
- <span data-ttu-id="ba5ea-3776">SSN</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3776">ssn</span></span> 
- <span data-ttu-id="ba5ea-3777">ИНН</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3777">tin</span></span> 
- <span data-ttu-id="ba5ea-3778">social security</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3778">social security</span></span> 
- <span data-ttu-id="ba5ea-3779">tax payer</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3779">tax payer</span></span> 
- <span data-ttu-id="ba5ea-3780">итинс</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3780">itins</span></span> 
- <span data-ttu-id="ba5ea-3781">такси</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3781">taxid</span></span> 
- <span data-ttu-id="ba5ea-3782">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3782">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="ba5ea-3783">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3783">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="ba5ea-3784">Лицензия</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3784">License</span></span> 
- <span data-ttu-id="ba5ea-3785">DL</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3785">DL</span></span> 
- <span data-ttu-id="ba5ea-3786">доб</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3786">DOB</span></span> 
- <span data-ttu-id="ba5ea-3787">Birthdate</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3787">Birthdate</span></span> 
- <span data-ttu-id="ba5ea-3788">День рождения </span><span class="sxs-lookup"><span data-stu-id="ba5ea-3788">Birthday</span></span> 
- <span data-ttu-id="ba5ea-3789">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3789">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="ba5ea-3790">Страховой номер для США (SSN)</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3790">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="ba5ea-3791">Format</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3791">Format</span></span>

<span data-ttu-id="ba5ea-3792">9 цифр в виде форматированного или неформатированного шаблона.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3792">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="ba5ea-3793">Есть SSN выдан до середины 2011 г., он отличается строгим форматированием, при котором определенные части номера должны входить в указанные диапазоны (при этом нет контрольной суммы).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3793">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="ba5ea-3794">Шаблон</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3794">Pattern</span></span>

<span data-ttu-id="ba5ea-3795">Четыре функции выполняют поиск SSN с использованием четырех разных шаблонов:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3795">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="ba5ea-3796">Func_ssn находит SSN со строгим форматированием с тире или пробелами, выданные до 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3796">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="ba5ea-3797">Func_unformatted_ssn находит SSN со строгим форматированием, выданные до 2011 г. (без форматирования в виде девяти последовательных цифр — ццццццццц);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3797">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="ba5ea-3798">Func_randomized_formatted_ssn находит SSN с тире или пробелами, выданные после 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3798">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="ba5ea-3799">Func_randomized_unformatted_ssn находит SSN без форматирования в виде девяти последовательных цифр, выданные после 2011 г. (ццццццццц).</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3799">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="ba5ea-3800">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3800">Checksum</span></span>

<span data-ttu-id="ba5ea-3801">Нет</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3801">No</span></span>


### <a name="definition"></a><span data-ttu-id="ba5ea-3802">Определение</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3802">Definition</span></span>

<span data-ttu-id="ba5ea-3803">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3803">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3804">Функция Func_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3804">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3805">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3805">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="ba5ea-3806">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3807">Функция Func_unformatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3807">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3808">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3808">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="ba5ea-3809">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3809">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3810">Функция Func_randomized_formatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3810">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3811">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3811">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="ba5ea-3812">Политика защиты от потери данных с вероятностью в 55 % верно обнаружила этот тип конфиденциальной информации, если в пределах ближайших 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3812">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ba5ea-3813">Функция Func_randomized_unformatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3813">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ba5ea-3814">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3814">A keyword from Keyword_ssn is found.</span></span>


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ba5ea-3815">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3815">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="ba5ea-3816">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3816">Keyword_ssn</span></span>

- <span data-ttu-id="ba5ea-3817">Social Security</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3817">Social Security</span></span> 
- <span data-ttu-id="ba5ea-3818">Social Security#</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3818">Social Security#</span></span> 
- <span data-ttu-id="ba5ea-3819">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3819">Soc Sec</span></span> 
- <span data-ttu-id="ba5ea-3820">SSN</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3820">SSN</span></span> 
- <span data-ttu-id="ba5ea-3821">SSNS</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3821">SSNS</span></span> 
- <span data-ttu-id="ba5ea-3822">SSN #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3822">SSN#</span></span> 
- <span data-ttu-id="ba5ea-3823">НН #</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3823">SS#</span></span> 
- <span data-ttu-id="ba5ea-3824">SSID</span><span class="sxs-lookup"><span data-stu-id="ba5ea-3824">SSID</span></span> 
   
