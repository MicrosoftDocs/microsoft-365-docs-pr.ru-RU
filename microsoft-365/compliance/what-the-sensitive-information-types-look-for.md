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
ms.openlocfilehash: efd5d2f8003bd79620118a6a058576e5593699b1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601216"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="da5ee-104">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="da5ee-104">What the sensitive information types look for</span></span>

<span data-ttu-id="da5ee-105">Защита от потери данных (DLP) в центре безопасности &amp; Office 365 содержит множество типов конфиденциальной информации, готовых к использованию в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="da5ee-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="da5ee-106">В этой статье перечислены все эти типы конфиденциальной информации и показано, каким именно образом политика защиты от потери данных выявляет каждый тип.</span><span class="sxs-lookup"><span data-stu-id="da5ee-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="da5ee-107">Тип конфиденциальной информации определяется шаблоном, который можно идентифицировать регулярным выражением или функцией.</span><span class="sxs-lookup"><span data-stu-id="da5ee-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="da5ee-108">Кроме того, для идентификации типа конфиденциальной информации могут использоваться подкрепляющие доказательства, такие как ключевые слова и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="da5ee-109">Уровень вероятности и расположение слов и знаков также используются в процессе оценки.</span><span class="sxs-lookup"><span data-stu-id="da5ee-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="da5ee-110">Код банка ABA</span><span class="sxs-lookup"><span data-stu-id="da5ee-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-111">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-111">Format</span></span>

<span data-ttu-id="da5ee-112">9 цифр в виде форматированного или неформатированного шаблона.</span><span class="sxs-lookup"><span data-stu-id="da5ee-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-113">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-113">Pattern</span></span>

<span data-ttu-id="da5ee-114">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="da5ee-114">Formatted:</span></span>
- <span data-ttu-id="da5ee-115">четыре цифры, начиная с 0, 1, 2, 3, 6, 7 или 8;</span><span class="sxs-lookup"><span data-stu-id="da5ee-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="da5ee-116">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-116">A hyphen</span></span>
- <span data-ttu-id="da5ee-117">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-117">Four digits</span></span>
- <span data-ttu-id="da5ee-118">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-118">A hyphen</span></span>
- <span data-ttu-id="da5ee-119">цифра.</span><span class="sxs-lookup"><span data-stu-id="da5ee-119">A digit</span></span>

<span data-ttu-id="da5ee-120">Неформатированные: 9 последовательных цифр, начиная с 0, 1, 2, 3, 6, 7 или 8.</span><span class="sxs-lookup"><span data-stu-id="da5ee-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="da5ee-121">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-121">Checksum</span></span>

<span data-ttu-id="da5ee-122">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-123">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-123">Definition</span></span>

<span data-ttu-id="da5ee-124">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-125">функция Func_aba_routing находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-126">находится ключевое слово из Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="da5ee-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="da5ee-127">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="da5ee-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="da5ee-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="da5ee-129">код банка ABA</span><span class="sxs-lookup"><span data-stu-id="da5ee-129">aba</span></span>
- <span data-ttu-id="da5ee-130">aba#</span><span class="sxs-lookup"><span data-stu-id="da5ee-130">aba #</span></span>
- <span data-ttu-id="da5ee-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="da5ee-131">aba routing #</span></span>
- <span data-ttu-id="da5ee-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="da5ee-132">aba routing number</span></span>
- <span data-ttu-id="da5ee-133">код банка ABA #</span><span class="sxs-lookup"><span data-stu-id="da5ee-133">aba#</span></span>
- <span data-ttu-id="da5ee-134">абараутинг #</span><span class="sxs-lookup"><span data-stu-id="da5ee-134">abarouting#</span></span>
- <span data-ttu-id="da5ee-135">aba number</span><span class="sxs-lookup"><span data-stu-id="da5ee-135">aba number</span></span>
- <span data-ttu-id="da5ee-136">абараутингнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-136">abaroutingnumber</span></span>
- <span data-ttu-id="da5ee-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="da5ee-137">american bank association routing #</span></span>
- <span data-ttu-id="da5ee-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="da5ee-138">american bank association routing number</span></span>
- <span data-ttu-id="da5ee-139">американбанкассоЦиатионраутинг #</span><span class="sxs-lookup"><span data-stu-id="da5ee-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="da5ee-140">американбанкассоЦиатионраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="da5ee-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="da5ee-141">bank routing number</span></span>
- <span data-ttu-id="da5ee-142">банкраутинг #</span><span class="sxs-lookup"><span data-stu-id="da5ee-142">bankrouting#</span></span>
- <span data-ttu-id="da5ee-143">банкраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-143">bankroutingnumber</span></span>
- <span data-ttu-id="da5ee-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="da5ee-144">routing transit number</span></span>
- <span data-ttu-id="da5ee-145">ртн</span><span class="sxs-lookup"><span data-stu-id="da5ee-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="da5ee-146">Номер внутреннего удостоверения личности для Аргентины (DNI)</span><span class="sxs-lookup"><span data-stu-id="da5ee-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-147">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-147">Format</span></span>

<span data-ttu-id="da5ee-148">Восемь цифр, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="da5ee-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-149">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-149">Pattern</span></span>

<span data-ttu-id="da5ee-150">Восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-150">Eight digits:</span></span>
- <span data-ttu-id="da5ee-151">две цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-151">Two digits</span></span>
- <span data-ttu-id="da5ee-152">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-152">A period</span></span>
- <span data-ttu-id="da5ee-153">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-153">Three digits</span></span>
- <span data-ttu-id="da5ee-154">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-154">A period</span></span>
- <span data-ttu-id="da5ee-155">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-156">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-156">Checksum</span></span>

<span data-ttu-id="da5ee-157">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-158">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-158">Definition</span></span>

<span data-ttu-id="da5ee-159">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-160">регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-161">находится ключевое слово из Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="da5ee-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-162">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="da5ee-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="da5ee-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="da5ee-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="da5ee-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="da5ee-165">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="da5ee-165">Identity</span></span> 
- <span data-ttu-id="da5ee-166">Идентификация национальной идентификационной карточки</span><span class="sxs-lookup"><span data-stu-id="da5ee-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="da5ee-167">DNI</span><span class="sxs-lookup"><span data-stu-id="da5ee-167">DNI</span></span> 
- <span data-ttu-id="da5ee-168">Национальная реестр пользователей NIC</span><span class="sxs-lookup"><span data-stu-id="da5ee-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="da5ee-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="da5ee-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="da5ee-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="da5ee-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="da5ee-171">идентидад</span><span class="sxs-lookup"><span data-stu-id="da5ee-171">Identidad</span></span> 
- <span data-ttu-id="da5ee-172">идентификаЦиóн</span><span class="sxs-lookup"><span data-stu-id="da5ee-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="da5ee-173">Номер банковского счета для Австралии</span><span class="sxs-lookup"><span data-stu-id="da5ee-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-174">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-174">Format</span></span>

<span data-ttu-id="da5ee-175">6–10 цифр с номером филиала банка в штате или без него.</span><span class="sxs-lookup"><span data-stu-id="da5ee-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-176">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-176">Pattern</span></span>

<span data-ttu-id="da5ee-177">Номер счета состоит из 6–10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="da5ee-178">Номер филиала государственного банка Австралии</span><span class="sxs-lookup"><span data-stu-id="da5ee-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="da5ee-179">три цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-179">Three digits</span></span> 
- <span data-ttu-id="da5ee-180">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-180">A hyphen</span></span> 
- <span data-ttu-id="da5ee-181">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-182">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-182">Checksum</span></span>

<span data-ttu-id="da5ee-183">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-184">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-184">Definition</span></span>

<span data-ttu-id="da5ee-185">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-186">регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="da5ee-187">находится ключевое слово из Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="da5ee-188">регулярное выражение Regex_australia_bank_account_number_bsb находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="da5ee-189">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-190">регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="da5ee-191">находится ключевое слово из Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-192">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="da5ee-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="da5ee-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="da5ee-194">swift bank code</span></span>
- <span data-ttu-id="da5ee-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="da5ee-195">correspondent bank</span></span>
- <span data-ttu-id="da5ee-196">base currency</span><span class="sxs-lookup"><span data-stu-id="da5ee-196">base currency</span></span>
- <span data-ttu-id="da5ee-197">usa account</span><span class="sxs-lookup"><span data-stu-id="da5ee-197">usa account</span></span>
- <span data-ttu-id="da5ee-198">holder address</span><span class="sxs-lookup"><span data-stu-id="da5ee-198">holder address</span></span>
- <span data-ttu-id="da5ee-199">bank address</span><span class="sxs-lookup"><span data-stu-id="da5ee-199">bank address</span></span>
- <span data-ttu-id="da5ee-200">information account</span><span class="sxs-lookup"><span data-stu-id="da5ee-200">information account</span></span>
- <span data-ttu-id="da5ee-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="da5ee-201">fund transfers</span></span>
- <span data-ttu-id="da5ee-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="da5ee-202">bank charges</span></span>
- <span data-ttu-id="da5ee-203">bank details</span><span class="sxs-lookup"><span data-stu-id="da5ee-203">bank details</span></span>
- <span data-ttu-id="da5ee-204">banking information</span><span class="sxs-lookup"><span data-stu-id="da5ee-204">banking information</span></span>
- <span data-ttu-id="da5ee-205">full names</span><span class="sxs-lookup"><span data-stu-id="da5ee-205">full names</span></span>
- <span data-ttu-id="da5ee-206">иаеа</span><span class="sxs-lookup"><span data-stu-id="da5ee-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="da5ee-207">Номер водительского удостоверения для Австралии</span><span class="sxs-lookup"><span data-stu-id="da5ee-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-208">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-208">Format</span></span>

<span data-ttu-id="da5ee-209">Девять букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-210">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-210">Pattern</span></span>

<span data-ttu-id="da5ee-211">Девять букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="da5ee-212">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-213">две цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-213">Two digits</span></span> 
- <span data-ttu-id="da5ee-214">пять цифр или букв (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="da5ee-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="da5ee-215">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="da5ee-215">OR</span></span>

- <span data-ttu-id="da5ee-216">1–2 дополнительные буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-217">4–9 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-217">4-9 digits</span></span>

<span data-ttu-id="da5ee-218">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="da5ee-218">OR</span></span>

- <span data-ttu-id="da5ee-219">девять цифр или букв (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="da5ee-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-220">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-220">Checksum</span></span>

<span data-ttu-id="da5ee-221">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-222">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-222">Definition</span></span>

<span data-ttu-id="da5ee-223">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-224">регулярное выражение Regex_australia_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-225">находится ключевое слово из Keyword_australia_drivers_license_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="da5ee-226">ни одно ключевое слово из Keyword_australia_drivers_license_number_exclusions не находится.</span><span class="sxs-lookup"><span data-stu-id="da5ee-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-227">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="da5ee-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="da5ee-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="da5ee-229">international driving permits</span></span>
- <span data-ttu-id="da5ee-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="da5ee-230">australian automobile association</span></span>
- <span data-ttu-id="da5ee-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="da5ee-231">international driving permit</span></span>
- <span data-ttu-id="da5ee-232">дриверлиценце</span><span class="sxs-lookup"><span data-stu-id="da5ee-232">DriverLicence</span></span>
- <span data-ttu-id="da5ee-233">дриверлиценцес</span><span class="sxs-lookup"><span data-stu-id="da5ee-233">DriverLicences</span></span>
- <span data-ttu-id="da5ee-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-234">Driver Lic</span></span>
- <span data-ttu-id="da5ee-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-235">Driver Licence</span></span>
- <span data-ttu-id="da5ee-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-236">Driver Licences</span></span>
- <span data-ttu-id="da5ee-237">дриверслик</span><span class="sxs-lookup"><span data-stu-id="da5ee-237">DriversLic</span></span>
- <span data-ttu-id="da5ee-238">дриверслиценце</span><span class="sxs-lookup"><span data-stu-id="da5ee-238">DriversLicence</span></span>
- <span data-ttu-id="da5ee-239">дриверслиценцес</span><span class="sxs-lookup"><span data-stu-id="da5ee-239">DriversLicences</span></span>
- <span data-ttu-id="da5ee-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-240">Drivers Lic</span></span>
- <span data-ttu-id="da5ee-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-241">Drivers Lics</span></span>
- <span data-ttu-id="da5ee-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-242">Drivers Licence</span></span>
- <span data-ttu-id="da5ee-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-243">Drivers Licences</span></span>
- <span data-ttu-id="da5ee-244">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="da5ee-244">Driver'Lic</span></span>
- <span data-ttu-id="da5ee-245">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="da5ee-245">Driver'Lics</span></span>
- <span data-ttu-id="da5ee-246">Driver ' Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-246">Driver'Licence</span></span>
- <span data-ttu-id="da5ee-247">Driver ' Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-247">Driver'Licences</span></span>
- <span data-ttu-id="da5ee-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-248">Driver' Lic</span></span>
- <span data-ttu-id="da5ee-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-249">Driver' Lics</span></span>
- <span data-ttu-id="da5ee-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-250">Driver' Licence</span></span>
- <span data-ttu-id="da5ee-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-251">Driver' Licences</span></span>
- <span data-ttu-id="da5ee-252">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="da5ee-252">Driver'sLic</span></span>
- <span data-ttu-id="da5ee-253">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="da5ee-253">Driver'sLics</span></span>
- <span data-ttu-id="da5ee-254">дривер'слиценце</span><span class="sxs-lookup"><span data-stu-id="da5ee-254">Driver'sLicence</span></span>
- <span data-ttu-id="da5ee-255">дривер'слиценцес</span><span class="sxs-lookup"><span data-stu-id="da5ee-255">Driver'sLicences</span></span>
- <span data-ttu-id="da5ee-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-256">Driver's Lic</span></span>
- <span data-ttu-id="da5ee-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-257">Driver's Lics</span></span>
- <span data-ttu-id="da5ee-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-258">Driver's Licence</span></span>
- <span data-ttu-id="da5ee-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-259">Driver's Licences</span></span>
- <span data-ttu-id="da5ee-260">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-260">DriverLic#</span></span>
- <span data-ttu-id="da5ee-261">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-261">DriverLics#</span></span>
- <span data-ttu-id="da5ee-262">дриверлиценце #</span><span class="sxs-lookup"><span data-stu-id="da5ee-262">DriverLicence#</span></span>
- <span data-ttu-id="da5ee-263">дриверлиценцес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-263">DriverLicences#</span></span>
- <span data-ttu-id="da5ee-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-264">Driver Lic#</span></span>
- <span data-ttu-id="da5ee-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-265">Driver Lics#</span></span>
- <span data-ttu-id="da5ee-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="da5ee-266">Driver Licence#</span></span>
- <span data-ttu-id="da5ee-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-267">Driver Licences#</span></span>
- <span data-ttu-id="da5ee-268">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-268">DriversLic#</span></span>
- <span data-ttu-id="da5ee-269">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-269">DriversLics#</span></span>
- <span data-ttu-id="da5ee-270">дриверслиценце #</span><span class="sxs-lookup"><span data-stu-id="da5ee-270">DriversLicence#</span></span>
- <span data-ttu-id="da5ee-271">дриверслиценцес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-271">DriversLicences#</span></span>
- <span data-ttu-id="da5ee-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-272">Drivers Lic#</span></span>
- <span data-ttu-id="da5ee-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-273">Drivers Lics#</span></span>
- <span data-ttu-id="da5ee-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="da5ee-274">Drivers Licence#</span></span>
- <span data-ttu-id="da5ee-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-275">Drivers Licences#</span></span>
- <span data-ttu-id="da5ee-276">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="da5ee-276">Driver'Lic#</span></span>
- <span data-ttu-id="da5ee-277">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="da5ee-277">Driver'Lics#</span></span>
- <span data-ttu-id="da5ee-278">Driver ' Licence #</span><span class="sxs-lookup"><span data-stu-id="da5ee-278">Driver'Licence#</span></span>
- <span data-ttu-id="da5ee-279">Driver ' Licences #</span><span class="sxs-lookup"><span data-stu-id="da5ee-279">Driver'Licences#</span></span>
- <span data-ttu-id="da5ee-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-280">Driver' Lic#</span></span>
- <span data-ttu-id="da5ee-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-281">Driver' Lics#</span></span>
- <span data-ttu-id="da5ee-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="da5ee-282">Driver' Licence#</span></span>
- <span data-ttu-id="da5ee-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-283">Driver' Licences#</span></span>
- <span data-ttu-id="da5ee-284">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-284">Driver'sLic#</span></span>
- <span data-ttu-id="da5ee-285">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-285">Driver'sLics#</span></span>
- <span data-ttu-id="da5ee-286">дривер'слиценце #</span><span class="sxs-lookup"><span data-stu-id="da5ee-286">Driver'sLicence#</span></span>
- <span data-ttu-id="da5ee-287">дривер'слиценцес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-287">Driver'sLicences#</span></span>
- <span data-ttu-id="da5ee-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-288">Driver's Lic#</span></span>
- <span data-ttu-id="da5ee-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-289">Driver's Lics#</span></span>
- <span data-ttu-id="da5ee-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="da5ee-290">Driver's Licence#</span></span>
- <span data-ttu-id="da5ee-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="da5ee-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="da5ee-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="da5ee-293">AAA</span><span class="sxs-lookup"><span data-stu-id="da5ee-293">aaa</span></span>
- <span data-ttu-id="da5ee-294">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-294">DriverLicense</span></span>
- <span data-ttu-id="da5ee-295">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-295">DriverLicenses</span></span>
- <span data-ttu-id="da5ee-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="da5ee-296">Driver License</span></span>
- <span data-ttu-id="da5ee-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-297">Driver Licenses</span></span>
- <span data-ttu-id="da5ee-298">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-298">DriversLicense</span></span>
- <span data-ttu-id="da5ee-299">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-299">DriversLicenses</span></span>
- <span data-ttu-id="da5ee-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="da5ee-300">Drivers License</span></span>
- <span data-ttu-id="da5ee-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-301">Drivers Licenses</span></span>
- <span data-ttu-id="da5ee-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="da5ee-302">Driver'License</span></span>
- <span data-ttu-id="da5ee-303">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-303">Driver'Licenses</span></span>
- <span data-ttu-id="da5ee-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="da5ee-304">Driver' License</span></span>
- <span data-ttu-id="da5ee-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-305">Driver' Licenses</span></span>
- <span data-ttu-id="da5ee-306">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-306">Driver'sLicense</span></span>
- <span data-ttu-id="da5ee-307">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-307">Driver'sLicenses</span></span>
- <span data-ttu-id="da5ee-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="da5ee-308">Driver's License</span></span>
- <span data-ttu-id="da5ee-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-309">Driver's Licenses</span></span>
- <span data-ttu-id="da5ee-310">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-310">DriverLicense#</span></span>
- <span data-ttu-id="da5ee-311">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-311">DriverLicenses#</span></span>
- <span data-ttu-id="da5ee-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-312">Driver License#</span></span>
- <span data-ttu-id="da5ee-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-313">Driver Licenses#</span></span>
- <span data-ttu-id="da5ee-314">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-314">DriversLicense#</span></span>
- <span data-ttu-id="da5ee-315">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-315">DriversLicenses#</span></span>
- <span data-ttu-id="da5ee-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-316">Drivers License#</span></span>
- <span data-ttu-id="da5ee-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-317">Drivers Licenses#</span></span>
- <span data-ttu-id="da5ee-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="da5ee-318">Driver'License#</span></span>
- <span data-ttu-id="da5ee-319">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="da5ee-319">Driver'Licenses#</span></span>
- <span data-ttu-id="da5ee-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-320">Driver' License#</span></span>
- <span data-ttu-id="da5ee-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-321">Driver' Licenses#</span></span>
- <span data-ttu-id="da5ee-322">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-322">Driver'sLicense#</span></span>
- <span data-ttu-id="da5ee-323">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="da5ee-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-324">Driver's License#</span></span>
- <span data-ttu-id="da5ee-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="da5ee-326">Номер карты медицинского страхования для Австралии</span><span class="sxs-lookup"><span data-stu-id="da5ee-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-327">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-327">Format</span></span>

<span data-ttu-id="da5ee-328">10–11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-329">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-329">Pattern</span></span>

<span data-ttu-id="da5ee-330">10–11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-330">10-11 digits:</span></span>
- <span data-ttu-id="da5ee-331">Первая цифра находится в диапазоне 2–6.</span><span class="sxs-lookup"><span data-stu-id="da5ee-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="da5ee-332">Девятая цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="da5ee-333">Десятая цифра — цифра серии.</span><span class="sxs-lookup"><span data-stu-id="da5ee-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="da5ee-334">Одиннадцатая цифра (необязательно) — индивидуальный номер.</span><span class="sxs-lookup"><span data-stu-id="da5ee-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-335">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-335">Checksum</span></span>

<span data-ttu-id="da5ee-336">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-337">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-337">Definition</span></span>

<span data-ttu-id="da5ee-338">Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-339">функция Func_australian_medical_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-340">находится ключевое слово из Keyword_Australia_Medical_Account_Number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="da5ee-341">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-341">The checksum passes.</span></span>

<span data-ttu-id="da5ee-342">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-343">функция Func_australian_medical_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-344">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-345">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="da5ee-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="da5ee-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="da5ee-347">bank account details</span></span>
- <span data-ttu-id="da5ee-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="da5ee-348">medicare payments</span></span>
- <span data-ttu-id="da5ee-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="da5ee-349">mortgage account</span></span>
- <span data-ttu-id="da5ee-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="da5ee-350">bank payments</span></span>
- <span data-ttu-id="da5ee-351">information branch</span><span class="sxs-lookup"><span data-stu-id="da5ee-351">information branch</span></span>
- <span data-ttu-id="da5ee-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="da5ee-352">credit card loan</span></span>
- <span data-ttu-id="da5ee-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="da5ee-353">department of human services</span></span>
- <span data-ttu-id="da5ee-354">local service</span><span class="sxs-lookup"><span data-stu-id="da5ee-354">local service</span></span>
- <span data-ttu-id="da5ee-355">медикаре</span><span class="sxs-lookup"><span data-stu-id="da5ee-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="da5ee-356">Номер паспорта гражданина Австралии</span><span class="sxs-lookup"><span data-stu-id="da5ee-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-357">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-357">Format</span></span>

<span data-ttu-id="da5ee-358">Буква, за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-359">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-359">Pattern</span></span>

<span data-ttu-id="da5ee-360">Буква (без учета регистра), за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-361">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-361">Checksum</span></span>

<span data-ttu-id="da5ee-362">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-363">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-363">Definition</span></span>

<span data-ttu-id="da5ee-364">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-365">регулярное выражение Regex_australia_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-366">Найдено ключевое слово из Keyword_passport или Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-367">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="da5ee-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-368">Keyword_passport</span></span>

- <span data-ttu-id="da5ee-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-369">Passport Number</span></span>
- <span data-ttu-id="da5ee-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="da5ee-370">Passport No</span></span>
- <span data-ttu-id="da5ee-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-371">Passport #</span></span>
- <span data-ttu-id="da5ee-372">Службу #</span><span class="sxs-lookup"><span data-stu-id="da5ee-372">Passport#</span></span>
- <span data-ttu-id="da5ee-373">пасспортид</span><span class="sxs-lookup"><span data-stu-id="da5ee-373">PassportID</span></span>
- <span data-ttu-id="da5ee-374">пасспортно</span><span class="sxs-lookup"><span data-stu-id="da5ee-374">Passportno</span></span>
- <span data-ttu-id="da5ee-375">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-375">passportnumber</span></span>
- <span data-ttu-id="da5ee-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="da5ee-376">パスポート</span></span>
- <span data-ttu-id="da5ee-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-377">パスポート番号</span></span>
- <span data-ttu-id="da5ee-378">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="da5ee-378">パスポートのNum</span></span>
- <span data-ttu-id="da5ee-379">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="da5ee-379">パスポート ＃</span></span> 
- <span data-ttu-id="da5ee-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="da5ee-380">Numéro de passeport</span></span>
- <span data-ttu-id="da5ee-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="da5ee-381">Passeport n °</span></span>
- <span data-ttu-id="da5ee-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="da5ee-382">Passeport Non</span></span>
- <span data-ttu-id="da5ee-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-383">Passeport #</span></span>
- <span data-ttu-id="da5ee-384">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="da5ee-384">Passeport#</span></span>
- <span data-ttu-id="da5ee-385">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="da5ee-385">PasseportNon</span></span>
- <span data-ttu-id="da5ee-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="da5ee-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="da5ee-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="da5ee-388">службу</span><span class="sxs-lookup"><span data-stu-id="da5ee-388">passport</span></span>
- <span data-ttu-id="da5ee-389">passport details</span><span class="sxs-lookup"><span data-stu-id="da5ee-389">passport details</span></span>
- <span data-ttu-id="da5ee-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="da5ee-390">immigration and citizenship</span></span>
- <span data-ttu-id="da5ee-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="da5ee-391">commonwealth of australia</span></span>
- <span data-ttu-id="da5ee-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="da5ee-392">department of immigration</span></span>
- <span data-ttu-id="da5ee-393">residential address</span><span class="sxs-lookup"><span data-stu-id="da5ee-393">residential address</span></span>
- <span data-ttu-id="da5ee-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="da5ee-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="da5ee-395">Visa</span><span class="sxs-lookup"><span data-stu-id="da5ee-395">visa</span></span>
- <span data-ttu-id="da5ee-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="da5ee-396">national identity card</span></span>
- <span data-ttu-id="da5ee-397">passport number</span><span class="sxs-lookup"><span data-stu-id="da5ee-397">passport number</span></span>
- <span data-ttu-id="da5ee-398">travel document</span><span class="sxs-lookup"><span data-stu-id="da5ee-398">travel document</span></span>
- <span data-ttu-id="da5ee-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="da5ee-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="da5ee-400">Номер налогоплательщика для Австралии</span><span class="sxs-lookup"><span data-stu-id="da5ee-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-401">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-401">Format</span></span>

<span data-ttu-id="da5ee-402">8–9 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-403">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-403">Pattern</span></span>

<span data-ttu-id="da5ee-404">8–9 цифр, которые обычно разделены пробелами указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="da5ee-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="da5ee-405">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-405">Three digits</span></span> 
- <span data-ttu-id="da5ee-406">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-406">An optional space</span></span> 
- <span data-ttu-id="da5ee-407">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-407">Three digits</span></span> 
- <span data-ttu-id="da5ee-408">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-408">An optional space</span></span> 
- <span data-ttu-id="da5ee-409">2–3 цифры, причем последняя цифра — контрольная</span><span class="sxs-lookup"><span data-stu-id="da5ee-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-410">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-410">Checksum</span></span>

<span data-ttu-id="da5ee-411">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-412">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-412">Definition</span></span>

<span data-ttu-id="da5ee-413">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-414">функция Func_australian_tax_file_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-415">ни одно ключевое слово из Keyword_Australia_Tax_File_Number или Keyword_number_exclusions не найдено;</span><span class="sxs-lookup"><span data-stu-id="da5ee-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="da5ee-416">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-417">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="da5ee-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="da5ee-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="da5ee-419">australian business number</span></span>
- <span data-ttu-id="da5ee-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="da5ee-420">marginal tax rate</span></span>
- <span data-ttu-id="da5ee-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="da5ee-421">medicare levy</span></span>
- <span data-ttu-id="da5ee-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="da5ee-422">portfolio number</span></span>
- <span data-ttu-id="da5ee-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="da5ee-423">service veterans</span></span>
- <span data-ttu-id="da5ee-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="da5ee-424">withholding tax</span></span>
- <span data-ttu-id="da5ee-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="da5ee-425">individual tax return</span></span>
- <span data-ttu-id="da5ee-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="da5ee-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="da5ee-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="da5ee-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="da5ee-428">00000001</span><span class="sxs-lookup"><span data-stu-id="da5ee-428">00000000</span></span>
- <span data-ttu-id="da5ee-429">11111111</span><span class="sxs-lookup"><span data-stu-id="da5ee-429">11111111</span></span>
- <span data-ttu-id="da5ee-430">22222222</span><span class="sxs-lookup"><span data-stu-id="da5ee-430">22222222</span></span>
- <span data-ttu-id="da5ee-431">33333333</span><span class="sxs-lookup"><span data-stu-id="da5ee-431">33333333</span></span>
- <span data-ttu-id="da5ee-432">44444444</span><span class="sxs-lookup"><span data-stu-id="da5ee-432">44444444</span></span>
- <span data-ttu-id="da5ee-433">55555555</span><span class="sxs-lookup"><span data-stu-id="da5ee-433">55555555</span></span>
- <span data-ttu-id="da5ee-434">66666666</span><span class="sxs-lookup"><span data-stu-id="da5ee-434">66666666</span></span>
- <span data-ttu-id="da5ee-435">77777777</span><span class="sxs-lookup"><span data-stu-id="da5ee-435">77777777</span></span>
- <span data-ttu-id="da5ee-436">88888888</span><span class="sxs-lookup"><span data-stu-id="da5ee-436">88888888</span></span>
- <span data-ttu-id="da5ee-437">99999999</span><span class="sxs-lookup"><span data-stu-id="da5ee-437">99999999</span></span>
- <span data-ttu-id="da5ee-438">000000000</span><span class="sxs-lookup"><span data-stu-id="da5ee-438">000000000</span></span>
- <span data-ttu-id="da5ee-439">111111111</span><span class="sxs-lookup"><span data-stu-id="da5ee-439">111111111</span></span>
- <span data-ttu-id="da5ee-440">222222222</span><span class="sxs-lookup"><span data-stu-id="da5ee-440">222222222</span></span>
- <span data-ttu-id="da5ee-441">333333333</span><span class="sxs-lookup"><span data-stu-id="da5ee-441">333333333</span></span>
- <span data-ttu-id="da5ee-442">444444444</span><span class="sxs-lookup"><span data-stu-id="da5ee-442">444444444</span></span>
- <span data-ttu-id="da5ee-443">555555555</span><span class="sxs-lookup"><span data-stu-id="da5ee-443">555555555</span></span>
- <span data-ttu-id="da5ee-444">666666666</span><span class="sxs-lookup"><span data-stu-id="da5ee-444">666666666</span></span>
- <span data-ttu-id="da5ee-445">777777777</span><span class="sxs-lookup"><span data-stu-id="da5ee-445">777777777</span></span>
- <span data-ttu-id="da5ee-446">888888888</span><span class="sxs-lookup"><span data-stu-id="da5ee-446">888888888</span></span>
- <span data-ttu-id="da5ee-447">999999999</span><span class="sxs-lookup"><span data-stu-id="da5ee-447">999999999</span></span>
- <span data-ttu-id="da5ee-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="da5ee-448">0000000000</span></span>
- <span data-ttu-id="da5ee-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="da5ee-449">1111111111</span></span>
- <span data-ttu-id="da5ee-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="da5ee-450">2222222222</span></span>
- <span data-ttu-id="da5ee-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="da5ee-451">3333333333</span></span>
- <span data-ttu-id="da5ee-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="da5ee-452">4444444444</span></span>
- <span data-ttu-id="da5ee-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="da5ee-453">5555555555</span></span>
- <span data-ttu-id="da5ee-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="da5ee-454">6666666666</span></span>
- <span data-ttu-id="da5ee-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="da5ee-455">7777777777</span></span>
- <span data-ttu-id="da5ee-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="da5ee-456">8888888888</span></span>
- <span data-ttu-id="da5ee-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="da5ee-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="da5ee-458">Ключ проверки подлинности Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="da5ee-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-459">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-459">Format</span></span>

<span data-ttu-id="da5ee-460">Строка "DocumentDb", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="da5ee-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-461">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-461">Pattern</span></span>

- <span data-ttu-id="da5ee-462">Строка "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="da5ee-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="da5ee-463">Любая комбинация из 3-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-464">Символ "больше" (>), знак равенства (=), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="da5ee-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="da5ee-465">Любая комбинация 86 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).</span><span class="sxs-lookup"><span data-stu-id="da5ee-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="da5ee-466">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="da5ee-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-467">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-467">Checksum</span></span>

<span data-ttu-id="da5ee-468">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-469">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-469">Definition</span></span>

<span data-ttu-id="da5ee-470">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-471">Регулярное выражение CEP_Regex_AzureDocumentDBAuthKey находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-472">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-473">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-475">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-476">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-476">contoso</span></span>
- <span data-ttu-id="da5ee-477">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-477">fabrikam</span></span>
- <span data-ttu-id="da5ee-478">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-478">northwind</span></span>
- <span data-ttu-id="da5ee-479">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-479">sandbox</span></span>
- <span data-ttu-id="da5ee-480">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-480">onebox</span></span>
- <span data-ttu-id="da5ee-481">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-481">localhost</span></span>
- <span data-ttu-id="da5ee-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-482">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-483">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-484">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-484">com</span></span>
- <span data-ttu-id="da5ee-485">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-486">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="da5ee-487">Строка подключения к базе данных Azure IAAS и строка подключения к SQL Azure</span><span class="sxs-lookup"><span data-stu-id="da5ee-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-488">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-488">Format</span></span>

<span data-ttu-id="da5ee-489">Строка "Server", "Server" или "Data Source", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "клаудапп. Azure".</span><span class="sxs-lookup"><span data-stu-id="da5ee-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-490">com "или" клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="da5ee-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-491">NET "или" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="da5ee-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-492">NET ", а также строку" Password "или" Password "или" pwd ".</span><span class="sxs-lookup"><span data-stu-id="da5ee-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-493">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-493">Pattern</span></span>

- <span data-ttu-id="da5ee-494">Строка "Server", "Server" или "Data Source"</span><span class="sxs-lookup"><span data-stu-id="da5ee-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="da5ee-495">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-496">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-496">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-497">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-498">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-499">Строка "клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="da5ee-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-500">com "," клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="da5ee-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-501">NET "или" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="da5ee-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-502">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-502">net"</span></span>
- <span data-ttu-id="da5ee-503">Любая комбинация из 1-300 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-504">Строка "Password", "Password" или "pwd"</span><span class="sxs-lookup"><span data-stu-id="da5ee-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="da5ee-505">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-506">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-506">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-507">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-508">Один или несколько символов, не отделяющая точку с запятой (;), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="da5ee-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="da5ee-509">Точка с запятой (;), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="da5ee-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-510">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-510">Checksum</span></span>

<span data-ttu-id="da5ee-511">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-512">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-512">Definition</span></span>

<span data-ttu-id="da5ee-513">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-514">Регулярное выражение CEP_Regex_AzureConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-515">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-516">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-518">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-519">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-519">contoso</span></span>
- <span data-ttu-id="da5ee-520">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-520">fabrikam</span></span>
- <span data-ttu-id="da5ee-521">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-521">northwind</span></span>
- <span data-ttu-id="da5ee-522">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-522">sandbox</span></span>
- <span data-ttu-id="da5ee-523">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-523">onebox</span></span>
- <span data-ttu-id="da5ee-524">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-524">localhost</span></span>
- <span data-ttu-id="da5ee-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-525">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-526">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-527">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-527">com</span></span>
- <span data-ttu-id="da5ee-528">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-529">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="da5ee-530">Строка подключения Azure IoT</span><span class="sxs-lookup"><span data-stu-id="da5ee-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-531">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-531">Format</span></span>

<span data-ttu-id="da5ee-532">Строка "HostName", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, включая строки "Azure — Devices.</span><span class="sxs-lookup"><span data-stu-id="da5ee-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-533">NET "и" Шаредакцесскэй ".</span><span class="sxs-lookup"><span data-stu-id="da5ee-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-534">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-534">Pattern</span></span>

- <span data-ttu-id="da5ee-535">Строка "HostName"</span><span class="sxs-lookup"><span data-stu-id="da5ee-535">The string "HostName"</span></span>
- <span data-ttu-id="da5ee-536">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-537">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-537">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-538">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-539">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-540">Строка "Azure — Devices.</span><span class="sxs-lookup"><span data-stu-id="da5ee-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-541">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-541">net"</span></span>
- <span data-ttu-id="da5ee-542">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-543">Строка "Шаредакцесскэй"</span><span class="sxs-lookup"><span data-stu-id="da5ee-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="da5ee-544">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-545">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-545">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-546">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-547">Любая комбинация 43 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).</span><span class="sxs-lookup"><span data-stu-id="da5ee-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="da5ee-548">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-549">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-549">Checksum</span></span>

<span data-ttu-id="da5ee-550">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-551">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-551">Definition</span></span>

<span data-ttu-id="da5ee-552">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-553">Регулярное выражение CEP_Regex_AzureIoTConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-554">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-555">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-557">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-558">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-558">contoso</span></span>
- <span data-ttu-id="da5ee-559">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-559">fabrikam</span></span>
- <span data-ttu-id="da5ee-560">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-560">northwind</span></span>
- <span data-ttu-id="da5ee-561">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-561">sandbox</span></span>
- <span data-ttu-id="da5ee-562">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-562">onebox</span></span>
- <span data-ttu-id="da5ee-563">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-563">localhost</span></span>
- <span data-ttu-id="da5ee-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-564">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-565">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-566">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-566">com</span></span>
- <span data-ttu-id="da5ee-567">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-568">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="da5ee-569">Пароль для параметра публикации Azure</span><span class="sxs-lookup"><span data-stu-id="da5ee-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-570">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-570">Format</span></span>

<span data-ttu-id="da5ee-571">Строка "усерпвд =", за которой следует буквенно-цифровая строка.</span><span class="sxs-lookup"><span data-stu-id="da5ee-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-572">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-572">Pattern</span></span>

- <span data-ttu-id="da5ee-573">Строка "усерпвд ="</span><span class="sxs-lookup"><span data-stu-id="da5ee-573">The string "userpwd="</span></span>
- <span data-ttu-id="da5ee-574">Любая комбинация букв или цифр в нижнем регистре 60</span><span class="sxs-lookup"><span data-stu-id="da5ee-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="da5ee-575">Знак кавычек (")</span><span class="sxs-lookup"><span data-stu-id="da5ee-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-576">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-576">Checksum</span></span>

<span data-ttu-id="da5ee-577">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-578">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-578">Definition</span></span>

<span data-ttu-id="da5ee-579">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-580">Регулярное выражение CEP_Regex_AzurePublishSettingPasswords находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-581">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="da5ee-582">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-584">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-585">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-585">contoso</span></span>
- <span data-ttu-id="da5ee-586">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-586">fabrikam</span></span>
- <span data-ttu-id="da5ee-587">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-587">northwind</span></span>
- <span data-ttu-id="da5ee-588">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-588">sandbox</span></span>
- <span data-ttu-id="da5ee-589">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-589">onebox</span></span>
- <span data-ttu-id="da5ee-590">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-590">localhost</span></span>
- <span data-ttu-id="da5ee-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-591">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-592">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-593">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-593">com</span></span>
- <span data-ttu-id="da5ee-594">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-595">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="da5ee-596">Строка подключения к кэшу Azure Redis</span><span class="sxs-lookup"><span data-stu-id="da5ee-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-597">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-597">Format</span></span>

<span data-ttu-id="da5ee-598">Строка "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="da5ee-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-599">NET, за которыми следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "Password" или "pwd".</span><span class="sxs-lookup"><span data-stu-id="da5ee-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-600">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-600">Pattern</span></span>

- <span data-ttu-id="da5ee-601">Строка "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="da5ee-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-602">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-602">net"</span></span>
- <span data-ttu-id="da5ee-603">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-604">Строка "Password" или "pwd"</span><span class="sxs-lookup"><span data-stu-id="da5ee-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="da5ee-605">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-606">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-606">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-607">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-608">Любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="da5ee-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="da5ee-609">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-610">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-610">Checksum</span></span>

<span data-ttu-id="da5ee-611">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-612">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-612">Definition</span></span>

<span data-ttu-id="da5ee-613">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-614">Регулярное выражение CEP_Regex_AzureRedisCacheConnectionString находит содержимое, которое соответствует шаблону..</span><span class="sxs-lookup"><span data-stu-id="da5ee-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="da5ee-615">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-616">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-618">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-619">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-619">contoso</span></span>
- <span data-ttu-id="da5ee-620">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-620">fabrikam</span></span>
- <span data-ttu-id="da5ee-621">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-621">northwind</span></span>
- <span data-ttu-id="da5ee-622">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-622">sandbox</span></span>
- <span data-ttu-id="da5ee-623">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-623">onebox</span></span>
- <span data-ttu-id="da5ee-624">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-624">localhost</span></span>
- <span data-ttu-id="da5ee-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-625">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-626">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-627">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-627">com</span></span>
- <span data-ttu-id="da5ee-628">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-629">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="da5ee-630">SAS Azure</span><span class="sxs-lookup"><span data-stu-id="da5ee-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-631">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-631">Format</span></span>

<span data-ttu-id="da5ee-632">Строка "SIG", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="da5ee-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-633">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-633">Pattern</span></span>

- <span data-ttu-id="da5ee-634">Строка "SIG"</span><span class="sxs-lookup"><span data-stu-id="da5ee-634">The string "sig"</span></span>
- <span data-ttu-id="da5ee-635">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-636">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-636">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-637">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-638">Любое сочетание 43-53 символов, которые являются буквами нижнего или верхнего регистра, цифрами или знаком процента (%)</span><span class="sxs-lookup"><span data-stu-id="da5ee-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="da5ee-639">Строка "% 3D"</span><span class="sxs-lookup"><span data-stu-id="da5ee-639">The string "%3d"</span></span>
- <span data-ttu-id="da5ee-640">Любой символ, который не является буквой нижнего или верхнего регистра, цифрой или знаком процента (%)</span><span class="sxs-lookup"><span data-stu-id="da5ee-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-641">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-641">Checksum</span></span>

<span data-ttu-id="da5ee-642">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-643">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-643">Definition</span></span>

<span data-ttu-id="da5ee-644">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-645">Регулярное выражение CEP_Regex_AzureSAS находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="da5ee-646">Строка подключения к служебной шине Azure</span><span class="sxs-lookup"><span data-stu-id="da5ee-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-647">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-647">Format</span></span>

<span data-ttu-id="da5ee-648">Строка "EndPoint", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строки "сервицебус. Windows.</span><span class="sxs-lookup"><span data-stu-id="da5ee-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-649">NET "и" Шаредакцескэй ".</span><span class="sxs-lookup"><span data-stu-id="da5ee-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-650">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-650">Pattern</span></span>

- <span data-ttu-id="da5ee-651">Строка "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="da5ee-651">The string "EndPoint"</span></span>
- <span data-ttu-id="da5ee-652">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-653">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-653">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-654">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-655">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-656">Строка "сервицебус. Windows.</span><span class="sxs-lookup"><span data-stu-id="da5ee-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-657">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-657">net"</span></span>
- <span data-ttu-id="da5ee-658">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-659">Строка "Шаредакцесскэй"</span><span class="sxs-lookup"><span data-stu-id="da5ee-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="da5ee-660">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-661">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-661">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-662">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-663">Любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="da5ee-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="da5ee-664">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-665">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-665">Checksum</span></span>

<span data-ttu-id="da5ee-666">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-667">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-667">Definition</span></span>

<span data-ttu-id="da5ee-668">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-669">Регулярное выражение CEP_Regex_AzureServiceBusConnectionString находит содержимое, которое соответствует шаблону..</span><span class="sxs-lookup"><span data-stu-id="da5ee-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="da5ee-670">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-671">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-673">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-674">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-674">contoso</span></span>
- <span data-ttu-id="da5ee-675">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-675">fabrikam</span></span>
- <span data-ttu-id="da5ee-676">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-676">northwind</span></span>
- <span data-ttu-id="da5ee-677">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-677">sandbox</span></span>
- <span data-ttu-id="da5ee-678">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-678">onebox</span></span>
- <span data-ttu-id="da5ee-679">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-679">localhost</span></span>
- <span data-ttu-id="da5ee-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-680">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-681">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-682">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-682">com</span></span>
- <span data-ttu-id="da5ee-683">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-684">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="da5ee-685">Ключ учетной записи хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="da5ee-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-686">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-686">Format</span></span>

<span data-ttu-id="da5ee-687">Строка "Дефаултендпоинтспротокол", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="da5ee-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-688">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-688">Pattern</span></span>

- <span data-ttu-id="da5ee-689">Строка "Дефаултендпоинтспротокол"</span><span class="sxs-lookup"><span data-stu-id="da5ee-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="da5ee-690">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-691">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-691">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-692">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-693">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-694">Строка "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="da5ee-694">The string "AccountKey"</span></span>
- <span data-ttu-id="da5ee-695">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-696">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-696">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-697">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="da5ee-698">Любое сочетание 86 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="da5ee-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="da5ee-699">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="da5ee-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-700">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-700">Checksum</span></span>

<span data-ttu-id="da5ee-701">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-702">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-702">Definition</span></span>

<span data-ttu-id="da5ee-703">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-704">Регулярное выражение CEP_Regex_AzureStorageAccountKey находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-705">Регулярное выражение CEP_AzureEmulatorStorageAccountFilter не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-706">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-707">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="da5ee-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="da5ee-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="da5ee-709">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/Кбхбексогмгв = =</span><span class="sxs-lookup"><span data-stu-id="da5ee-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-712">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-713">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-713">contoso</span></span>
- <span data-ttu-id="da5ee-714">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-714">fabrikam</span></span>
- <span data-ttu-id="da5ee-715">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-715">northwind</span></span>
- <span data-ttu-id="da5ee-716">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-716">sandbox</span></span>
- <span data-ttu-id="da5ee-717">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-717">onebox</span></span>
- <span data-ttu-id="da5ee-718">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-718">localhost</span></span>
- <span data-ttu-id="da5ee-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-719">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-720">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-721">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-721">com</span></span>
- <span data-ttu-id="da5ee-722">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-723">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="da5ee-724">Ключ учетной записи хранилища Azure (общий)</span><span class="sxs-lookup"><span data-stu-id="da5ee-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-725">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-725">Format</span></span>

<span data-ttu-id="da5ee-726">Любая комбинация 86 строчных или прописных букв, цифр, знаков косой черты (/) или знака плюса (+) перед или за ними следуют символы, указанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="da5ee-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-727">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-727">Pattern</span></span>

- <span data-ttu-id="da5ee-728">0-1 из символа "больше" (>), апостроф ('), знак равенства (=), знак кавычек (") или решетка (#)</span><span class="sxs-lookup"><span data-stu-id="da5ee-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="da5ee-729">Любое сочетание 86 символов, которые представляют собой буквы в нижнем или верхнем регистре, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="da5ee-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="da5ee-730">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="da5ee-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="da5ee-731">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-731">Checksum</span></span>

<span data-ttu-id="da5ee-732">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-733">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-733">Definition</span></span>

<span data-ttu-id="da5ee-734">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-735">Регулярное выражение CEP_Regex_AzureStorageAccountKeyGeneric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="da5ee-736">Номер национального документа для Бельгии</span><span class="sxs-lookup"><span data-stu-id="da5ee-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-737">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-737">Format</span></span>

<span data-ttu-id="da5ee-738">11 цифр, а также разделители.</span><span class="sxs-lookup"><span data-stu-id="da5ee-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-739">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-739">Pattern</span></span>

<span data-ttu-id="da5ee-740">11 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="da5ee-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="da5ee-741">шесть цифр и две точки в формате ГГ.ММ.ДД для даты рождения;</span><span class="sxs-lookup"><span data-stu-id="da5ee-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="da5ee-742">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-742">A hyphen</span></span> 
- <span data-ttu-id="da5ee-743">три последовательные цифры (нечетные для мужчин, четные для женщин);</span><span class="sxs-lookup"><span data-stu-id="da5ee-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="da5ee-744">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-744">A period</span></span> 
- <span data-ttu-id="da5ee-745">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-746">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-746">Checksum</span></span>

<span data-ttu-id="da5ee-747">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-748">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-748">Definition</span></span>

<span data-ttu-id="da5ee-749">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-750">функция Func_belgium_national_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-751">находится ключевое слово из Keyword_belgium_national_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="da5ee-752">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-753">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="da5ee-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="da5ee-755">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="da5ee-755">Identity</span></span>
- <span data-ttu-id="da5ee-756">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="da5ee-756">Registration</span></span>
- <span data-ttu-id="da5ee-757">Процедура</span><span class="sxs-lookup"><span data-stu-id="da5ee-757">Identification</span></span> 
- <span data-ttu-id="da5ee-758">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="da5ee-758">ID</span></span> 
- <span data-ttu-id="da5ee-759">идентитеитскаарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-759">Identiteitskaart</span></span>
- <span data-ttu-id="da5ee-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="da5ee-760">Registratie nummer</span></span> 
- <span data-ttu-id="da5ee-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="da5ee-761">Identificatie nummer</span></span> 
- <span data-ttu-id="da5ee-762">идентитеит</span><span class="sxs-lookup"><span data-stu-id="da5ee-762">Identiteit</span></span>
- <span data-ttu-id="da5ee-763">регистратие</span><span class="sxs-lookup"><span data-stu-id="da5ee-763">Registratie</span></span>
- <span data-ttu-id="da5ee-764">идентификатие</span><span class="sxs-lookup"><span data-stu-id="da5ee-764">Identificatie</span></span> 
- <span data-ttu-id="da5ee-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="da5ee-765">Carte d’identité</span></span> 
- <span data-ttu-id="da5ee-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="da5ee-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="da5ee-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="da5ee-767">numéro d'identification</span></span>
- <span data-ttu-id="da5ee-768">идентитé</span><span class="sxs-lookup"><span data-stu-id="da5ee-768">identité</span></span> 
- <span data-ttu-id="da5ee-769">инскриптион</span><span class="sxs-lookup"><span data-stu-id="da5ee-769">inscription</span></span> 
- <span data-ttu-id="da5ee-770">идентификатион</span><span class="sxs-lookup"><span data-stu-id="da5ee-770">Identifikation</span></span>
- <span data-ttu-id="da5ee-771">идентифизиерунг</span><span class="sxs-lookup"><span data-stu-id="da5ee-771">Identifizierung</span></span>
- <span data-ttu-id="da5ee-772">идентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-772">Identifikationsnummer</span></span>
- <span data-ttu-id="da5ee-773">персоналаусвеис</span><span class="sxs-lookup"><span data-stu-id="da5ee-773">Personalausweis</span></span>
- <span data-ttu-id="da5ee-774">регистриерунг</span><span class="sxs-lookup"><span data-stu-id="da5ee-774">Registrierung</span></span>
- <span data-ttu-id="da5ee-775">регистратионснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="da5ee-776">Номер CPF для Бразилии</span><span class="sxs-lookup"><span data-stu-id="da5ee-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-777">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-777">Format</span></span>

<span data-ttu-id="da5ee-778">11 цифр, которые включают проверочную цифру и могут быть форматированными или неформатированными.</span><span class="sxs-lookup"><span data-stu-id="da5ee-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-779">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-779">Pattern</span></span>

<span data-ttu-id="da5ee-780">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="da5ee-780">Formatted:</span></span>
- <span data-ttu-id="da5ee-781">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-781">Three digits</span></span> 
- <span data-ttu-id="da5ee-782">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-782">A period</span></span> 
- <span data-ttu-id="da5ee-783">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-783">Three digits</span></span> 
- <span data-ttu-id="da5ee-784">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-784">A period</span></span> 
- <span data-ttu-id="da5ee-785">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-785">Three digits</span></span> 
- <span data-ttu-id="da5ee-786">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-786">A hyphen</span></span> 
- <span data-ttu-id="da5ee-787">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-787">Two digits which are check digits</span></span>

<span data-ttu-id="da5ee-788">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="da5ee-788">Unformatted:</span></span>
- <span data-ttu-id="da5ee-789">11 цифр, где две последние цифры — проверочные.</span><span class="sxs-lookup"><span data-stu-id="da5ee-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-790">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-790">Checksum</span></span>

<span data-ttu-id="da5ee-791">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-792">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-792">Definition</span></span>

<span data-ttu-id="da5ee-793">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-794">функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-795">находится ключевое слово из Keyword_brazil_cpf;</span><span class="sxs-lookup"><span data-stu-id="da5ee-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="da5ee-796">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-796">The checksum passes.</span></span>

<span data-ttu-id="da5ee-797">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-798">функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-799">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-800">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="da5ee-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="da5ee-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="da5ee-802">CPF</span><span class="sxs-lookup"><span data-stu-id="da5ee-802">CPF</span></span>
- <span data-ttu-id="da5ee-803">Процедура</span><span class="sxs-lookup"><span data-stu-id="da5ee-803">Identification</span></span>
- <span data-ttu-id="da5ee-804">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="da5ee-804">Registration</span></span>
- <span data-ttu-id="da5ee-805">Реализации</span><span class="sxs-lookup"><span data-stu-id="da5ee-805">Revenue</span></span>
- <span data-ttu-id="da5ee-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="da5ee-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="da5ee-807">импосто</span><span class="sxs-lookup"><span data-stu-id="da5ee-807">Imposto</span></span> 
- <span data-ttu-id="da5ee-808">идентификаçãо</span><span class="sxs-lookup"><span data-stu-id="da5ee-808">Identificação</span></span> 
- <span data-ttu-id="da5ee-809">инскриçãо</span><span class="sxs-lookup"><span data-stu-id="da5ee-809">Inscrição</span></span> 
- <span data-ttu-id="da5ee-810">рецеита</span><span class="sxs-lookup"><span data-stu-id="da5ee-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="da5ee-811">Номер юридического лица для Бразилии (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="da5ee-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-812">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-812">Format</span></span>

<span data-ttu-id="da5ee-813">14 цифр, которые включают регистрационный номер, номер филиала и проверочные цифры, а также разделители.</span><span class="sxs-lookup"><span data-stu-id="da5ee-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-814">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-814">Pattern</span></span>
<span data-ttu-id="da5ee-815">14 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="da5ee-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="da5ee-816">две цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-816">Two digits</span></span> 
- <span data-ttu-id="da5ee-817">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-817">A period</span></span> 
- <span data-ttu-id="da5ee-818">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-818">Three digits</span></span> 
- <span data-ttu-id="da5ee-819">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-819">A period</span></span> 
- <span data-ttu-id="da5ee-820">три цифры (эти первые восемь цифр — регистрационный номер);</span><span class="sxs-lookup"><span data-stu-id="da5ee-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="da5ee-821">косая черта;</span><span class="sxs-lookup"><span data-stu-id="da5ee-821">A forward slash</span></span> 
- <span data-ttu-id="da5ee-822">номер отделения из четырех цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-822">Four-digit branch number</span></span> 
- <span data-ttu-id="da5ee-823">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-823">A hyphen</span></span> 
- <span data-ttu-id="da5ee-824">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-825">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-825">Checksum</span></span>

<span data-ttu-id="da5ee-826">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-827">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-827">Definition</span></span>

<span data-ttu-id="da5ee-828">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-829">функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-830">находится ключевое слово из Keyword_brazil_cnpj;</span><span class="sxs-lookup"><span data-stu-id="da5ee-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="da5ee-831">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-831">The checksum passes.</span></span>

<span data-ttu-id="da5ee-832">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-833">функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-834">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-835">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="da5ee-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="da5ee-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="da5ee-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="da5ee-837">CNPJ</span></span> 
- <span data-ttu-id="da5ee-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="da5ee-838">CNPJ/MF</span></span> 
- <span data-ttu-id="da5ee-839">CNPJ – MF</span><span class="sxs-lookup"><span data-stu-id="da5ee-839">CNPJ-MF</span></span> 
- <span data-ttu-id="da5ee-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="da5ee-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="da5ee-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="da5ee-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="da5ee-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="da5ee-842">Legal entity</span></span> 
- <span data-ttu-id="da5ee-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="da5ee-843">Legal entities</span></span> 
- <span data-ttu-id="da5ee-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="da5ee-844">Registration Status</span></span> 
- <span data-ttu-id="da5ee-845">Бизнес</span><span class="sxs-lookup"><span data-stu-id="da5ee-845">Business</span></span> 
- <span data-ttu-id="da5ee-846">Company</span><span class="sxs-lookup"><span data-stu-id="da5ee-846">Company</span></span>
- <span data-ttu-id="da5ee-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="da5ee-847">CNPJ</span></span> 
- <span data-ttu-id="da5ee-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="da5ee-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="da5ee-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="da5ee-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="da5ee-850">кгк</span><span class="sxs-lookup"><span data-stu-id="da5ee-850">CGC</span></span> 
- <span data-ttu-id="da5ee-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="da5ee-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="da5ee-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="da5ee-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="da5ee-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="da5ee-853">Situação cadastral</span></span> 
- <span data-ttu-id="da5ee-854">инскриçãо</span><span class="sxs-lookup"><span data-stu-id="da5ee-854">Inscrição</span></span> 
- <span data-ttu-id="da5ee-855">емпреса</span><span class="sxs-lookup"><span data-stu-id="da5ee-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="da5ee-856">	Номер внутреннего удостоверения личности для Бразилии (RG)</span><span class="sxs-lookup"><span data-stu-id="da5ee-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-857">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-857">Format</span></span>

<span data-ttu-id="da5ee-858">Registro Geral (старый формат): девять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="da5ee-859">Registro de identidade (RIC) (новый формат): 11 цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-860">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-860">Pattern</span></span>

<span data-ttu-id="da5ee-861">Registro Geral (старый формат):</span><span class="sxs-lookup"><span data-stu-id="da5ee-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="da5ee-862">две цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-862">Two digits</span></span> 
- <span data-ttu-id="da5ee-863">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-863">A period</span></span> 
- <span data-ttu-id="da5ee-864">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-864">Three digits</span></span> 
- <span data-ttu-id="da5ee-865">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-865">A period</span></span> 
- <span data-ttu-id="da5ee-866">три цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-866">Three digits</span></span> 
- <span data-ttu-id="da5ee-867">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-867">A hyphen</span></span> 
- <span data-ttu-id="da5ee-868">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-868">One digit which is a check digit</span></span>

<span data-ttu-id="da5ee-869">Registro de identidade (RIC) (новый формат):</span><span class="sxs-lookup"><span data-stu-id="da5ee-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="da5ee-870">10 цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-870">10 digits</span></span> 
- <span data-ttu-id="da5ee-871">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-871">A hyphen</span></span> 
- <span data-ttu-id="da5ee-872">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-873">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-873">Checksum</span></span>

<span data-ttu-id="da5ee-874">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-875">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-875">Definition</span></span>

<span data-ttu-id="da5ee-876">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-877">функция Func_brazil_rg находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-878">находится ключевое слово из Keyword_brazil_rg;</span><span class="sxs-lookup"><span data-stu-id="da5ee-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="da5ee-879">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-879">The checksum passes.</span></span>

<span data-ttu-id="da5ee-880">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-881">функция Func_brazil_rg находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-882">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-883">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="da5ee-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="da5ee-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="da5ee-885">Кéдула de identidade Identity Card National ID нúмеро de ррегистро Registro de Иидентидаде Registro Geral RG (это ключевое слово учитывает регистр) RIC (это ключевое слово учитывает регистр).</span><span class="sxs-lookup"><span data-stu-id="da5ee-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="da5ee-886">Номер банковского счета для Канады</span><span class="sxs-lookup"><span data-stu-id="da5ee-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-887">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-887">Format</span></span>

<span data-ttu-id="da5ee-888">Семь или двенадцать цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-889">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-889">Pattern</span></span>

<span data-ttu-id="da5ee-890">Номер банковского счета для Канады — семь или двенадцать цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="da5ee-891">Транзитный номер банковского счета в Канаде имеет указанный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="da5ee-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="da5ee-892">пять цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-892">Five digits</span></span> 
- <span data-ttu-id="da5ee-893">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-893">A hyphen</span></span> 
- <span data-ttu-id="da5ee-894">Три цифры или</span><span class="sxs-lookup"><span data-stu-id="da5ee-894">Three digits OR</span></span>
- <span data-ttu-id="da5ee-895">ноль "0";</span><span class="sxs-lookup"><span data-stu-id="da5ee-895">A zero "0"</span></span> 
- <span data-ttu-id="da5ee-896">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-897">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-897">Checksum</span></span>

<span data-ttu-id="da5ee-898">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-899">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-899">Definition</span></span>

<span data-ttu-id="da5ee-900">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-901">регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-902">находится ключевое слово из Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="da5ee-903">регулярное выражение Regex_canada_bank_account_transit_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="da5ee-904">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-905">регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-906">находится ключевое слово из Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-907">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="da5ee-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="da5ee-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="da5ee-909">canada savings bonds</span></span>
- <span data-ttu-id="da5ee-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="da5ee-910">canada revenue agency</span></span>
- <span data-ttu-id="da5ee-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="da5ee-911">canadian financial institution</span></span>
- <span data-ttu-id="da5ee-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="da5ee-912">direct deposit form</span></span>
- <span data-ttu-id="da5ee-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="da5ee-913">canadian citizen</span></span>
- <span data-ttu-id="da5ee-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="da5ee-914">legal representative</span></span>
- <span data-ttu-id="da5ee-915">notary public</span><span class="sxs-lookup"><span data-stu-id="da5ee-915">notary public</span></span>
- <span data-ttu-id="da5ee-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="da5ee-916">commissioner for oaths</span></span>
- <span data-ttu-id="da5ee-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="da5ee-917">child care benefit</span></span>
- <span data-ttu-id="da5ee-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="da5ee-918">universal child care</span></span>
- <span data-ttu-id="da5ee-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="da5ee-919">canada child tax benefit</span></span>
- <span data-ttu-id="da5ee-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="da5ee-920">income tax benefit</span></span>
- <span data-ttu-id="da5ee-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="da5ee-921">harmonized sales tax</span></span>
- <span data-ttu-id="da5ee-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="da5ee-922">social insurance number</span></span>
- <span data-ttu-id="da5ee-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="da5ee-923">income tax refund</span></span>
- <span data-ttu-id="da5ee-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="da5ee-924">child tax benefit</span></span>
- <span data-ttu-id="da5ee-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="da5ee-925">territorial payments</span></span>
- <span data-ttu-id="da5ee-926">institution number</span><span class="sxs-lookup"><span data-stu-id="da5ee-926">institution number</span></span>
- <span data-ttu-id="da5ee-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="da5ee-927">deposit request</span></span>
- <span data-ttu-id="da5ee-928">banking information</span><span class="sxs-lookup"><span data-stu-id="da5ee-928">banking information</span></span>
- <span data-ttu-id="da5ee-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="da5ee-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="da5ee-930">Номер водительского удостоверения для Канады</span><span class="sxs-lookup"><span data-stu-id="da5ee-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-931">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-931">Format</span></span>

<span data-ttu-id="da5ee-932">Зависит от провинции.</span><span class="sxs-lookup"><span data-stu-id="da5ee-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-933">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-933">Pattern</span></span>

<span data-ttu-id="da5ee-934">Различные шаблоны, соответствующие провинциям Альберта, Британская Колумбия, Манитоба, Нью-Брансуик, Ньюфаундленд и Лабрадор, Новая Шотландия, Онтарио, Остров Принца Эдуарда, Квебек и Саскачеван.</span><span class="sxs-lookup"><span data-stu-id="da5ee-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-935">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-935">Checksum</span></span>

<span data-ttu-id="da5ee-936">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-937">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-937">Definition</span></span>

<span data-ttu-id="da5ee-938">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-939">функция Func_[province_name]_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-940">находится ключевое слово из Keyword_[province_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="da5ee-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="da5ee-941">находится ключевое слово из Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="da5ee-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-942">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="da5ee-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="da5ee-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="da5ee-944">Аббревиатура провинции, например AB.</span><span class="sxs-lookup"><span data-stu-id="da5ee-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="da5ee-945">Название провинции, например Альберта.</span><span class="sxs-lookup"><span data-stu-id="da5ee-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="da5ee-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="da5ee-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="da5ee-947">DL</span><span class="sxs-lookup"><span data-stu-id="da5ee-947">DL</span></span>
- <span data-ttu-id="da5ee-948">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="da5ee-948">DLS</span></span>
- <span data-ttu-id="da5ee-949">кдл</span><span class="sxs-lookup"><span data-stu-id="da5ee-949">CDL</span></span>
- <span data-ttu-id="da5ee-950">кдлс</span><span class="sxs-lookup"><span data-stu-id="da5ee-950">CDLS</span></span>
- <span data-ttu-id="da5ee-951">дриверлик</span><span class="sxs-lookup"><span data-stu-id="da5ee-951">DriverLic</span></span>
- <span data-ttu-id="da5ee-952">дриверликс</span><span class="sxs-lookup"><span data-stu-id="da5ee-952">DriverLics</span></span>
- <span data-ttu-id="da5ee-953">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-953">DriverLicense</span></span>
- <span data-ttu-id="da5ee-954">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-954">DriverLicenses</span></span>
- <span data-ttu-id="da5ee-955">дриверлиценце</span><span class="sxs-lookup"><span data-stu-id="da5ee-955">DriverLicence</span></span>
- <span data-ttu-id="da5ee-956">дриверлиценцес</span><span class="sxs-lookup"><span data-stu-id="da5ee-956">DriverLicences</span></span>
- <span data-ttu-id="da5ee-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-957">Driver Lic</span></span>
- <span data-ttu-id="da5ee-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-958">Driver Lics</span></span>
- <span data-ttu-id="da5ee-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="da5ee-959">Driver License</span></span>
- <span data-ttu-id="da5ee-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-960">Driver Licenses</span></span>
- <span data-ttu-id="da5ee-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-961">Driver Licence</span></span>
- <span data-ttu-id="da5ee-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-962">Driver Licences</span></span>
- <span data-ttu-id="da5ee-963">дриверслик</span><span class="sxs-lookup"><span data-stu-id="da5ee-963">DriversLic</span></span>
- <span data-ttu-id="da5ee-964">дриверсликс</span><span class="sxs-lookup"><span data-stu-id="da5ee-964">DriversLics</span></span>
- <span data-ttu-id="da5ee-965">дриверслиценце</span><span class="sxs-lookup"><span data-stu-id="da5ee-965">DriversLicence</span></span>
- <span data-ttu-id="da5ee-966">дриверслиценцес</span><span class="sxs-lookup"><span data-stu-id="da5ee-966">DriversLicences</span></span>
- <span data-ttu-id="da5ee-967">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-967">DriversLicense</span></span>
- <span data-ttu-id="da5ee-968">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-968">DriversLicenses</span></span>
- <span data-ttu-id="da5ee-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-969">Drivers Lic</span></span>
- <span data-ttu-id="da5ee-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-970">Drivers Lics</span></span>
- <span data-ttu-id="da5ee-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="da5ee-971">Drivers License</span></span>
- <span data-ttu-id="da5ee-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-972">Drivers Licenses</span></span>
- <span data-ttu-id="da5ee-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-973">Drivers Licence</span></span>
- <span data-ttu-id="da5ee-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-974">Drivers Licences</span></span>
- <span data-ttu-id="da5ee-975">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="da5ee-975">Driver'Lic</span></span>
- <span data-ttu-id="da5ee-976">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="da5ee-976">Driver'Lics</span></span>
- <span data-ttu-id="da5ee-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="da5ee-977">Driver'License</span></span>
- <span data-ttu-id="da5ee-978">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-978">Driver'Licenses</span></span>
- <span data-ttu-id="da5ee-979">Driver ' Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-979">Driver'Licence</span></span>
- <span data-ttu-id="da5ee-980">Driver ' Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-980">Driver'Licences</span></span>
- <span data-ttu-id="da5ee-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-981">Driver' Lic</span></span>
- <span data-ttu-id="da5ee-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-982">Driver' Lics</span></span>
- <span data-ttu-id="da5ee-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="da5ee-983">Driver' License</span></span>
- <span data-ttu-id="da5ee-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-984">Driver' Licenses</span></span>
- <span data-ttu-id="da5ee-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-985">Driver' Licence</span></span>
- <span data-ttu-id="da5ee-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-986">Driver' Licences</span></span>
- <span data-ttu-id="da5ee-987">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="da5ee-987">Driver'sLic</span></span>
- <span data-ttu-id="da5ee-988">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="da5ee-988">Driver'sLics</span></span>
- <span data-ttu-id="da5ee-989">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-989">Driver'sLicense</span></span>
- <span data-ttu-id="da5ee-990">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-990">Driver'sLicenses</span></span>
- <span data-ttu-id="da5ee-991">дривер'слиценце</span><span class="sxs-lookup"><span data-stu-id="da5ee-991">Driver'sLicence</span></span>
- <span data-ttu-id="da5ee-992">дривер'слиценцес</span><span class="sxs-lookup"><span data-stu-id="da5ee-992">Driver'sLicences</span></span>
- <span data-ttu-id="da5ee-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-993">Driver's Lic</span></span>
- <span data-ttu-id="da5ee-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-994">Driver's Lics</span></span>
- <span data-ttu-id="da5ee-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="da5ee-995">Driver's License</span></span>
- <span data-ttu-id="da5ee-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-996">Driver's Licenses</span></span>
- <span data-ttu-id="da5ee-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-997">Driver's Licence</span></span>
- <span data-ttu-id="da5ee-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-998">Driver's Licences</span></span>
- <span data-ttu-id="da5ee-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="da5ee-999">Permis de Conduire</span></span>
- <span data-ttu-id="da5ee-1000">id</span><span class="sxs-lookup"><span data-stu-id="da5ee-1000">id</span></span>
- <span data-ttu-id="da5ee-1001">ids</span><span class="sxs-lookup"><span data-stu-id="da5ee-1001">ids</span></span>
- <span data-ttu-id="da5ee-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1002">idcard number</span></span>
- <span data-ttu-id="da5ee-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-1003">idcard numbers</span></span>
- <span data-ttu-id="da5ee-1004">idcard#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1004">idcard #</span></span>
- <span data-ttu-id="da5ee-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="da5ee-1005">idcard #s</span></span>
- <span data-ttu-id="da5ee-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1006">idcard card</span></span>
- <span data-ttu-id="da5ee-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1007">idcard cards</span></span>
- <span data-ttu-id="da5ee-1008">идкард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1008">idcard</span></span>
- <span data-ttu-id="da5ee-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1009">identification number</span></span>
- <span data-ttu-id="da5ee-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-1010">identification numbers</span></span>
- <span data-ttu-id="da5ee-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1011">identification #</span></span>
- <span data-ttu-id="da5ee-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="da5ee-1012">identification #s</span></span>
- <span data-ttu-id="da5ee-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1013">identification card</span></span>
- <span data-ttu-id="da5ee-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1014">identification cards</span></span>
- <span data-ttu-id="da5ee-1015">процедура</span><span class="sxs-lookup"><span data-stu-id="da5ee-1015">identification</span></span> 
- <span data-ttu-id="da5ee-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1016">DL#</span></span>
- <span data-ttu-id="da5ee-1017">БИБЛИОТЕК #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1017">DLS#</span></span> 
- <span data-ttu-id="da5ee-1018">кдл #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1018">CDL#</span></span> 
- <span data-ttu-id="da5ee-1019">кдлс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1019">CDLS#</span></span> 
- <span data-ttu-id="da5ee-1020">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1020">DriverLic#</span></span> 
- <span data-ttu-id="da5ee-1021">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1021">DriverLics#</span></span> 
- <span data-ttu-id="da5ee-1022">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1022">DriverLicense#</span></span> 
- <span data-ttu-id="da5ee-1023">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="da5ee-1024">дриверлиценце #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1024">DriverLicence#</span></span> 
- <span data-ttu-id="da5ee-1025">дриверлиценцес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1025">DriverLicences#</span></span> 
- <span data-ttu-id="da5ee-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1026">Driver Lic#</span></span>
- <span data-ttu-id="da5ee-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1027">Driver Lics#</span></span> 
- <span data-ttu-id="da5ee-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1028">Driver License#</span></span> 
- <span data-ttu-id="da5ee-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="da5ee-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1030">Driver License#</span></span> 
- <span data-ttu-id="da5ee-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1031">Driver Licences#</span></span> 
- <span data-ttu-id="da5ee-1032">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1032">DriversLic#</span></span> 
- <span data-ttu-id="da5ee-1033">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1033">DriversLics#</span></span> 
- <span data-ttu-id="da5ee-1034">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1034">DriversLicense#</span></span> 
- <span data-ttu-id="da5ee-1035">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="da5ee-1036">дриверслиценце #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1036">DriversLicence#</span></span> 
- <span data-ttu-id="da5ee-1037">дриверслиценцес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1037">DriversLicences#</span></span> 
- <span data-ttu-id="da5ee-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="da5ee-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="da5ee-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1040">Drivers License#</span></span> 
- <span data-ttu-id="da5ee-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="da5ee-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="da5ee-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="da5ee-1044">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="da5ee-1045">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="da5ee-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1046">Driver'License#</span></span> 
- <span data-ttu-id="da5ee-1047">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="da5ee-1048">Driver ' Licence #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="da5ee-1049">Driver ' Licences #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="da5ee-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="da5ee-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="da5ee-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1052">Driver' License#</span></span> 
- <span data-ttu-id="da5ee-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="da5ee-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="da5ee-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="da5ee-1056">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="da5ee-1057">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="da5ee-1058">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="da5ee-1059">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="da5ee-1060">дривер'слиценце #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="da5ee-1061">дривер'слиценцес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="da5ee-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="da5ee-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="da5ee-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1064">Driver's License#</span></span> 
- <span data-ttu-id="da5ee-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="da5ee-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="da5ee-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="da5ee-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="da5ee-1069">кодов #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1069">id#</span></span> 
- <span data-ttu-id="da5ee-1070">идентификаторы #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1070">ids#</span></span> 
- <span data-ttu-id="da5ee-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1071">idcard card#</span></span> 
- <span data-ttu-id="da5ee-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1072">idcard cards#</span></span> 
- <span data-ttu-id="da5ee-1073">идкард #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1073">idcard#</span></span> 
- <span data-ttu-id="da5ee-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1074">identification card#</span></span> 
- <span data-ttu-id="da5ee-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1075">identification cards#</span></span> 
- <span data-ttu-id="da5ee-1076">процедура #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="da5ee-1077">Номер службы здравоохранения для Канады</span><span class="sxs-lookup"><span data-stu-id="da5ee-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1078">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1078">Format</span></span>

<span data-ttu-id="da5ee-1079">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1080">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1080">Pattern</span></span>

<span data-ttu-id="da5ee-1081">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1082">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1082">Checksum</span></span>

<span data-ttu-id="da5ee-1083">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1084">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1084">Definition</span></span>

<span data-ttu-id="da5ee-1085">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1086">регулярное выражение Regex_canada_health_service_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1087">находится ключевое слово из Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1088">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="da5ee-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="da5ee-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1090">personal health number</span></span>
- <span data-ttu-id="da5ee-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="da5ee-1091">patient information</span></span>
- <span data-ttu-id="da5ee-1092">health services</span><span class="sxs-lookup"><span data-stu-id="da5ee-1092">health services</span></span>
- <span data-ttu-id="da5ee-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="da5ee-1093">speciality services</span></span>
- <span data-ttu-id="da5ee-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="da5ee-1094">automobile accident</span></span>
- <span data-ttu-id="da5ee-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="da5ee-1095">patient hospital</span></span>
- <span data-ttu-id="da5ee-1096">псичиатрист</span><span class="sxs-lookup"><span data-stu-id="da5ee-1096">psychiatrist</span></span>
- <span data-ttu-id="da5ee-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="da5ee-1097">workers compensation</span></span>
- <span data-ttu-id="da5ee-1098">ограничен</span><span class="sxs-lookup"><span data-stu-id="da5ee-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="da5ee-1099">Номер паспорта гражданина Канады</span><span class="sxs-lookup"><span data-stu-id="da5ee-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1100">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1100">Format</span></span>

<span data-ttu-id="da5ee-1101">Две прописные буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1102">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1102">Pattern</span></span>

<span data-ttu-id="da5ee-1103">Две прописные буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1104">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1104">Checksum</span></span>

<span data-ttu-id="da5ee-1105">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1106">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1106">Definition</span></span>

<span data-ttu-id="da5ee-1107">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1108">регулярное выражение Regex_canada_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1109">Найдено ключевое слово из Keyword_canada_passport_number или Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="da5ee-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="da5ee-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="da5ee-1112">canadian citizenship</span></span>
- <span data-ttu-id="da5ee-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-1113">canadian passport</span></span>
- <span data-ttu-id="da5ee-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="da5ee-1114">passport application</span></span>
- <span data-ttu-id="da5ee-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="da5ee-1115">passport photos</span></span>
- <span data-ttu-id="da5ee-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="da5ee-1116">certified translator</span></span>
- <span data-ttu-id="da5ee-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="da5ee-1117">canadian citizens</span></span>
- <span data-ttu-id="da5ee-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="da5ee-1118">processing times</span></span>
- <span data-ttu-id="da5ee-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="da5ee-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="da5ee-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-1120">Keyword_passport</span></span>

- <span data-ttu-id="da5ee-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1121">Passport Number</span></span>
- <span data-ttu-id="da5ee-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="da5ee-1122">Passport No</span></span>
- <span data-ttu-id="da5ee-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1123">Passport #</span></span>
- <span data-ttu-id="da5ee-1124">Службу #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1124">Passport#</span></span>
- <span data-ttu-id="da5ee-1125">пасспортид</span><span class="sxs-lookup"><span data-stu-id="da5ee-1125">PassportID</span></span>
- <span data-ttu-id="da5ee-1126">пасспортно</span><span class="sxs-lookup"><span data-stu-id="da5ee-1126">Passportno</span></span>
- <span data-ttu-id="da5ee-1127">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1127">passportnumber</span></span>
- <span data-ttu-id="da5ee-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="da5ee-1128">パスポート</span></span>
- <span data-ttu-id="da5ee-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-1129">パスポート番号</span></span>
- <span data-ttu-id="da5ee-1130">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1130">パスポートのNum</span></span>
- <span data-ttu-id="da5ee-1131">パスポート #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1131">パスポート＃</span></span>
- <span data-ttu-id="da5ee-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="da5ee-1132">Numéro de passeport</span></span>
- <span data-ttu-id="da5ee-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="da5ee-1133">Passeport n °</span></span>
- <span data-ttu-id="da5ee-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="da5ee-1134">Passeport Non</span></span>
- <span data-ttu-id="da5ee-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-1135">Passeport #</span></span>
- <span data-ttu-id="da5ee-1136">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1136">Passeport#</span></span>
- <span data-ttu-id="da5ee-1137">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1137">PasseportNon</span></span>
- <span data-ttu-id="da5ee-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="da5ee-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="da5ee-1139">Персональный идентификационный номер службы здравоохранения для Канады (PHIN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1140">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1140">Format</span></span>

<span data-ttu-id="da5ee-1141">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1142">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1142">Pattern</span></span>

<span data-ttu-id="da5ee-1143">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1144">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1144">Checksum</span></span>

<span data-ttu-id="da5ee-1145">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1146">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1146">Definition</span></span>

<span data-ttu-id="da5ee-1147">Политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах расстояния от 300 символов: регулярное выражение Regex_canada_phin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="da5ee-1148">Найдено по крайней мере два ключевых слова из Keyword_canada_phin или Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="da5ee-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="da5ee-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="da5ee-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="da5ee-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1151">social insurance number</span></span>
- <span data-ttu-id="da5ee-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="da5ee-1152">health information act</span></span>
- <span data-ttu-id="da5ee-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="da5ee-1153">income tax information</span></span>
- <span data-ttu-id="da5ee-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="da5ee-1154">manitoba health</span></span>
- <span data-ttu-id="da5ee-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="da5ee-1155">health registration</span></span>
- <span data-ttu-id="da5ee-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="da5ee-1156">prescription purchases</span></span>
- <span data-ttu-id="da5ee-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="da5ee-1157">benefit eligibility</span></span>
- <span data-ttu-id="da5ee-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="da5ee-1158">personal health</span></span>
- <span data-ttu-id="da5ee-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="da5ee-1159">power of attorney</span></span>
- <span data-ttu-id="da5ee-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1160">registration number</span></span>
- <span data-ttu-id="da5ee-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1161">personal health number</span></span>
- <span data-ttu-id="da5ee-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="da5ee-1162">practitioner referral</span></span>
- <span data-ttu-id="da5ee-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="da5ee-1163">wellness professional</span></span>
- <span data-ttu-id="da5ee-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="da5ee-1164">patient referral</span></span>
- <span data-ttu-id="da5ee-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="da5ee-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="da5ee-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="da5ee-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="da5ee-1167">нунавут</span><span class="sxs-lookup"><span data-stu-id="da5ee-1167">Nunavut</span></span>
- <span data-ttu-id="da5ee-1168">Квебека</span><span class="sxs-lookup"><span data-stu-id="da5ee-1168">Quebec</span></span>
- <span data-ttu-id="da5ee-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="da5ee-1169">Northwest Territories</span></span>
- <span data-ttu-id="da5ee-1170">Онтарио</span><span class="sxs-lookup"><span data-stu-id="da5ee-1170">Ontario</span></span>
- <span data-ttu-id="da5ee-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="da5ee-1171">British Columbia</span></span>
- <span data-ttu-id="da5ee-1172">Альберта</span><span class="sxs-lookup"><span data-stu-id="da5ee-1172">Alberta</span></span>
- <span data-ttu-id="da5ee-1173">Саскачеван</span><span class="sxs-lookup"><span data-stu-id="da5ee-1173">Saskatchewan</span></span>
- <span data-ttu-id="da5ee-1174">Манитоба</span><span class="sxs-lookup"><span data-stu-id="da5ee-1174">Manitoba</span></span>
- <span data-ttu-id="da5ee-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="da5ee-1175">Yukon</span></span>
- <span data-ttu-id="da5ee-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="da5ee-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="da5ee-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="da5ee-1177">New Brunswick</span></span>
- <span data-ttu-id="da5ee-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="da5ee-1178">Nova Scotia</span></span>
- <span data-ttu-id="da5ee-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="da5ee-1179">Prince Edward Island</span></span>
- <span data-ttu-id="da5ee-1180">Канада</span><span class="sxs-lookup"><span data-stu-id="da5ee-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="da5ee-1181">Номер карты социального страхования для Канады</span><span class="sxs-lookup"><span data-stu-id="da5ee-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1182">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1182">Format</span></span>

<span data-ttu-id="da5ee-1183">Девять цифр с необязательными дефисами или пробелами.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1184">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1184">Pattern</span></span>

<span data-ttu-id="da5ee-1185">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="da5ee-1185">Formatted:</span></span>
- <span data-ttu-id="da5ee-1186">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-1186">Three digits</span></span> 
- <span data-ttu-id="da5ee-1187">Дефис или пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-1187">A hyphen or space</span></span> 
- <span data-ttu-id="da5ee-1188">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-1188">Three digits</span></span> 
- <span data-ttu-id="da5ee-1189">Дефис или пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-1189">A hyphen or space</span></span> 
- <span data-ttu-id="da5ee-1190">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-1190">Three digits</span></span>

<span data-ttu-id="da5ee-1191">Неформатированные: девять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1192">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1192">Checksum</span></span>

<span data-ttu-id="da5ee-1193">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1194">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1194">Definition</span></span>

<span data-ttu-id="da5ee-1195">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1196">Функция Func_canadian_sin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1197">Выполняются по меньшей мере два из таких условий:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="da5ee-1198">найдено ключевое слово из Keyword_sin;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="da5ee-1199">найдено ключевое слово из Keyword_sin_collaborative;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="da5ee-1200">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-1201">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1201">The checksum passes.</span></span>

<span data-ttu-id="da5ee-1202">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1203">функция Func_unformatted_canadian_sin находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1204">найдено ключевое слово из Keyword_sin;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="da5ee-1205">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1206">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="da5ee-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="da5ee-1207">Keyword_sin</span></span>

- <span data-ttu-id="da5ee-1208">sin</span><span class="sxs-lookup"><span data-stu-id="da5ee-1208">sin</span></span> 
- <span data-ttu-id="da5ee-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="da5ee-1209">social insurance</span></span> 
- <span data-ttu-id="da5ee-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="da5ee-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="da5ee-1211">грехов</span><span class="sxs-lookup"><span data-stu-id="da5ee-1211">sins</span></span> 
- <span data-ttu-id="da5ee-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="da5ee-1212">ssn</span></span> 
- <span data-ttu-id="da5ee-1213">ssNS</span><span class="sxs-lookup"><span data-stu-id="da5ee-1213">ssns</span></span> 
- <span data-ttu-id="da5ee-1214">social security</span><span class="sxs-lookup"><span data-stu-id="da5ee-1214">social security</span></span> 
- <span data-ttu-id="da5ee-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="da5ee-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="da5ee-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1216">national identification number</span></span> 
- <span data-ttu-id="da5ee-1217">national id</span><span class="sxs-lookup"><span data-stu-id="da5ee-1217">national id</span></span> 
- <span data-ttu-id="da5ee-1218">Синус #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1218">sin#</span></span> 
- <span data-ttu-id="da5ee-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="da5ee-1219">soc ins</span></span> 
- <span data-ttu-id="da5ee-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="da5ee-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="da5ee-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="da5ee-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="da5ee-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="da5ee-1222">driver's license</span></span> 
- <span data-ttu-id="da5ee-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="da5ee-1223">drivers license</span></span> 
- <span data-ttu-id="da5ee-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-1224">driver's licence</span></span> 
- <span data-ttu-id="da5ee-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-1225">drivers licence</span></span> 
- <span data-ttu-id="da5ee-1226">доб</span><span class="sxs-lookup"><span data-stu-id="da5ee-1226">DOB</span></span> 
- <span data-ttu-id="da5ee-1227">Birthdate</span><span class="sxs-lookup"><span data-stu-id="da5ee-1227">Birthdate</span></span> 
- <span data-ttu-id="da5ee-1228">День рождения </span><span class="sxs-lookup"><span data-stu-id="da5ee-1228">Birthday</span></span> 
- <span data-ttu-id="da5ee-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="da5ee-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="da5ee-1230">	Номер удостоверения личности для Чили</span><span class="sxs-lookup"><span data-stu-id="da5ee-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1231">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1231">Format</span></span>

<span data-ttu-id="da5ee-1232">7-8 цифр и разделители — контрольная цифра или буква</span><span class="sxs-lookup"><span data-stu-id="da5ee-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1233">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1233">Pattern</span></span>

<span data-ttu-id="da5ee-1234">7–8 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="da5ee-1235">1 или 2 цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1235">1-2 digits</span></span> 
- <span data-ttu-id="da5ee-1236">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1236">A period</span></span> 
- <span data-ttu-id="da5ee-1237">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-1237">Three digits</span></span> 
- <span data-ttu-id="da5ee-1238">точка;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1238">A period</span></span> 
- <span data-ttu-id="da5ee-1239">три цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1239">Three digits</span></span> 
- <span data-ttu-id="da5ee-1240">тире;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1240">A dash</span></span> 
- <span data-ttu-id="da5ee-1241">одна цифра или буква (без учета регистра) — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1242">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1242">Checksum</span></span>

<span data-ttu-id="da5ee-1243">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1244">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1244">Definition</span></span>

<span data-ttu-id="da5ee-1245">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1246">функция Func_chile_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1247">находится ключевое слово из Keyword_chile_id_card;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="da5ee-1248">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1248">The checksum passes.</span></span>

<span data-ttu-id="da5ee-1249">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1250">функция Func_chile_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1251">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1252">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="da5ee-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="da5ee-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1254">National Identification Number</span></span> 
- <span data-ttu-id="da5ee-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1255">Identity card</span></span> 
- <span data-ttu-id="da5ee-1256">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="da5ee-1256">ID</span></span> 
- <span data-ttu-id="da5ee-1257">Процедура</span><span class="sxs-lookup"><span data-stu-id="da5ee-1257">Identification</span></span> 
- <span data-ttu-id="da5ee-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="da5ee-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="da5ee-1259">ВЫПОЛНЯЕМ</span><span class="sxs-lookup"><span data-stu-id="da5ee-1259">RUN</span></span> 
- <span data-ttu-id="da5ee-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="da5ee-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="da5ee-1261">СНИЖАТЬСЯ</span><span class="sxs-lookup"><span data-stu-id="da5ee-1261">RUT</span></span> 
- <span data-ttu-id="da5ee-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="da5ee-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="da5ee-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="da5ee-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="da5ee-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="da5ee-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="da5ee-1265">идентификаЦиóн</span><span class="sxs-lookup"><span data-stu-id="da5ee-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="da5ee-1266">	Номер удостоверения личности жителя Китая (КНР)</span><span class="sxs-lookup"><span data-stu-id="da5ee-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1267">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1267">Format</span></span>

<span data-ttu-id="da5ee-1268">18 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1269">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1269">Pattern</span></span>

<span data-ttu-id="da5ee-1270">18 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1270">18 digits:</span></span>
- <span data-ttu-id="da5ee-1271">шесть цифр — код адреса;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="da5ee-1272">восемь цифр в виде ГГГГММДД — дата рождения;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="da5ee-1273">три цифры — серия карты;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="da5ee-1274">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1275">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1275">Checksum</span></span>

<span data-ttu-id="da5ee-1276">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1277">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1277">Definition</span></span>

<span data-ttu-id="da5ee-1278">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1279">функция Func_china_resident_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1280">находится ключевое слово из Keyword_china_resident_id;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="da5ee-1281">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1281">The checksum passes.</span></span>

<span data-ttu-id="da5ee-1282">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1283">функция Func_china_resident_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1284">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1285">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="da5ee-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="da5ee-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="da5ee-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="da5ee-1288">NO7</span><span class="sxs-lookup"><span data-stu-id="da5ee-1288">PRC</span></span> 
- <span data-ttu-id="da5ee-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1289">National Identification Card</span></span> 
- <span data-ttu-id="da5ee-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="da5ee-1290">身份证</span></span> 
- <span data-ttu-id="da5ee-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="da5ee-1291">居民 身份证</span></span> 
- <span data-ttu-id="da5ee-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="da5ee-1292">居民身份证</span></span> 
- <span data-ttu-id="da5ee-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="da5ee-1293">鉴定</span></span> 
- <span data-ttu-id="da5ee-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-1294">身分證</span></span> 
- <span data-ttu-id="da5ee-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-1295">居民 身份證</span></span>
- <span data-ttu-id="da5ee-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="da5ee-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="da5ee-1297">Номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="da5ee-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1298">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1298">Format</span></span>

<span data-ttu-id="da5ee-1299">16 цифр, которые могут быть форматированными или неформатированными (цццццццццццццццц) и должны пройти проверку Луна.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1300">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1300">Pattern</span></span>

<span data-ttu-id="da5ee-1301">Очень сложный и надежный шаблон, который определяет карты всех основных мировых стандартов, включая Visa, MasterCard, Discover Card, JCB, American Express, подарочные карты и карты Diners Club.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1302">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1302">Checksum</span></span>

<span data-ttu-id="da5ee-1303">Да (рассчитывается по алгоритму Луна).</span><span class="sxs-lookup"><span data-stu-id="da5ee-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1304">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1304">Definition</span></span>

<span data-ttu-id="da5ee-1305">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1306">Функция Func_credit_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1307">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1307">One of the following is true:</span></span>
    - <span data-ttu-id="da5ee-1308">найдено ключевое слово из Keyword_cc_verification;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="da5ee-1309">найдено ключевое слово из Keyword_cc_name;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="da5ee-1310">функция Func_expiration_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-1311">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1311">The checksum passes.</span></span>

<span data-ttu-id="da5ee-1312">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1313">функция Func_credit_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1314">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1315">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="da5ee-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="da5ee-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="da5ee-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="da5ee-1317">card verification</span></span>
- <span data-ttu-id="da5ee-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1318">card identification number</span></span>
- <span data-ttu-id="da5ee-1319">квн</span><span class="sxs-lookup"><span data-stu-id="da5ee-1319">cvn</span></span>
- <span data-ttu-id="da5ee-1320">cid</span><span class="sxs-lookup"><span data-stu-id="da5ee-1320">cid</span></span>
- <span data-ttu-id="da5ee-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="da5ee-1321">cvc2</span></span>
- <span data-ttu-id="da5ee-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="da5ee-1322">cvv2</span></span>
- <span data-ttu-id="da5ee-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="da5ee-1323">pin block</span></span>
- <span data-ttu-id="da5ee-1324">security code</span><span class="sxs-lookup"><span data-stu-id="da5ee-1324">security code</span></span>
- <span data-ttu-id="da5ee-1325">security number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1325">security number</span></span>
- <span data-ttu-id="da5ee-1326">security no</span><span class="sxs-lookup"><span data-stu-id="da5ee-1326">security no</span></span>
- <span data-ttu-id="da5ee-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1327">issue number</span></span>
- <span data-ttu-id="da5ee-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="da5ee-1328">issue no</span></span>
- <span data-ttu-id="da5ee-1329">криптограмме</span><span class="sxs-lookup"><span data-stu-id="da5ee-1329">cryptogramme</span></span>
- <span data-ttu-id="da5ee-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="da5ee-1330">numéro de sécurité</span></span>
- <span data-ttu-id="da5ee-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="da5ee-1331">numero de securite</span></span>
- <span data-ttu-id="da5ee-1332">кредиткартенпрüфнуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="da5ee-1333">кредиткартенпруфнуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="da5ee-1334">прüфзиффер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1334">prüfziffer</span></span>
- <span data-ttu-id="da5ee-1335">пруфзиффер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1335">prufziffer</span></span>
- <span data-ttu-id="da5ee-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="da5ee-1336">sicherheits Kode</span></span>
- <span data-ttu-id="da5ee-1337">сичерхеитскоде</span><span class="sxs-lookup"><span data-stu-id="da5ee-1337">sicherheitscode</span></span>
- <span data-ttu-id="da5ee-1338">сичерхеитснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="da5ee-1339">верфаллдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1339">verfalldatum</span></span>
- <span data-ttu-id="da5ee-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="da5ee-1340">codice di verifica</span></span>
- <span data-ttu-id="da5ee-1341">наложен.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1341">cod.</span></span> <span data-ttu-id="da5ee-1342">сикурезза</span><span class="sxs-lookup"><span data-stu-id="da5ee-1342">sicurezza</span></span>
- <span data-ttu-id="da5ee-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1343">cod sicurezza</span></span>
- <span data-ttu-id="da5ee-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="da5ee-1344">n autorizzazione</span></span>
- <span data-ttu-id="da5ee-1345">кóдиго</span><span class="sxs-lookup"><span data-stu-id="da5ee-1345">código</span></span>
- <span data-ttu-id="da5ee-1346">кодиго</span><span class="sxs-lookup"><span data-stu-id="da5ee-1346">codigo</span></span>
- <span data-ttu-id="da5ee-1347">наложен.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1347">cod.</span></span> <span data-ttu-id="da5ee-1348">сег</span><span class="sxs-lookup"><span data-stu-id="da5ee-1348">seg</span></span>
- <span data-ttu-id="da5ee-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="da5ee-1349">cod seg</span></span>
- <span data-ttu-id="da5ee-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="da5ee-1350">código de segurança</span></span>
- <span data-ttu-id="da5ee-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1351">codigo de seguranca</span></span>
- <span data-ttu-id="da5ee-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="da5ee-1352">codigo de segurança</span></span>
- <span data-ttu-id="da5ee-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1353">código de seguranca</span></span>
- <span data-ttu-id="da5ee-1354">кóд.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1354">cód.</span></span> <span data-ttu-id="da5ee-1355">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="da5ee-1355">segurança</span></span>
- <span data-ttu-id="da5ee-1356">наложен.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1356">cod.</span></span> <span data-ttu-id="da5ee-1357">сегуранка наложенный платеж.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1357">seguranca cod.</span></span> <span data-ttu-id="da5ee-1358">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="da5ee-1358">segurança</span></span>
- <span data-ttu-id="da5ee-1359">кóд.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1359">cód.</span></span> <span data-ttu-id="da5ee-1360">сегуранка</span><span class="sxs-lookup"><span data-stu-id="da5ee-1360">seguranca</span></span>
- <span data-ttu-id="da5ee-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="da5ee-1361">cód segurança</span></span>
- <span data-ttu-id="da5ee-1362">наложенный на наложенный сегуранка сегуранçа</span><span class="sxs-lookup"><span data-stu-id="da5ee-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="da5ee-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1363">cód seguranca</span></span>
- <span data-ttu-id="da5ee-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="da5ee-1364">número de verificação</span></span>
- <span data-ttu-id="da5ee-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1365">numero de verificacao</span></span>
- <span data-ttu-id="da5ee-1366">аблауф</span><span class="sxs-lookup"><span data-stu-id="da5ee-1366">ablauf</span></span>
- <span data-ttu-id="da5ee-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="da5ee-1367">gültig bis</span></span>
- <span data-ttu-id="da5ee-1368">гüлтигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="da5ee-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="da5ee-1369">gultig bis</span></span>
- <span data-ttu-id="da5ee-1370">гултигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="da5ee-1371">скаденза</span><span class="sxs-lookup"><span data-stu-id="da5ee-1371">scadenza</span></span>
- <span data-ttu-id="da5ee-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="da5ee-1372">data scad</span></span>
- <span data-ttu-id="da5ee-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="da5ee-1373">fecha de expiracion</span></span>
- <span data-ttu-id="da5ee-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="da5ee-1374">fecha de venc</span></span>
- <span data-ttu-id="da5ee-1375">венЦимиенто</span><span class="sxs-lookup"><span data-stu-id="da5ee-1375">vencimiento</span></span>
- <span data-ttu-id="da5ee-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1376">válido hasta</span></span>
- <span data-ttu-id="da5ee-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1377">valido hasta</span></span>
- <span data-ttu-id="da5ee-1378">вто</span><span class="sxs-lookup"><span data-stu-id="da5ee-1378">vto</span></span>
- <span data-ttu-id="da5ee-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="da5ee-1379">data de expiração</span></span>
- <span data-ttu-id="da5ee-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1380">data de expiracao</span></span>
- <span data-ttu-id="da5ee-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="da5ee-1381">data em que expira</span></span>
- <span data-ttu-id="da5ee-1382">валидаде</span><span class="sxs-lookup"><span data-stu-id="da5ee-1382">validade</span></span>
- <span data-ttu-id="da5ee-1383">валор</span><span class="sxs-lookup"><span data-stu-id="da5ee-1383">valor</span></span>
- <span data-ttu-id="da5ee-1384">венЦименто</span><span class="sxs-lookup"><span data-stu-id="da5ee-1384">vencimento</span></span>
- <span data-ttu-id="da5ee-1385">венк</span><span class="sxs-lookup"><span data-stu-id="da5ee-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="da5ee-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="da5ee-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="da5ee-1387">амекс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1387">amex</span></span>
- <span data-ttu-id="da5ee-1388">american express</span><span class="sxs-lookup"><span data-stu-id="da5ee-1388">american express</span></span>
- <span data-ttu-id="da5ee-1389">американекспресс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1389">americanexpress</span></span>
- <span data-ttu-id="da5ee-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="da5ee-1390">Visa</span></span>
- <span data-ttu-id="da5ee-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="da5ee-1391">mastercard</span></span>
- <span data-ttu-id="da5ee-1392">master card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1392">master card</span></span>
- <span data-ttu-id="da5ee-1393">MC</span><span class="sxs-lookup"><span data-stu-id="da5ee-1393">mc</span></span> 
- <span data-ttu-id="da5ee-1394">мастеркардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1394">mastercards</span></span>
- <span data-ttu-id="da5ee-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1395">master cards</span></span>
- <span data-ttu-id="da5ee-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="da5ee-1396">diner's Club</span></span>
- <span data-ttu-id="da5ee-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="da5ee-1397">diners club</span></span>
- <span data-ttu-id="da5ee-1398">динерсклуб</span><span class="sxs-lookup"><span data-stu-id="da5ee-1398">dinersclub</span></span>
- <span data-ttu-id="da5ee-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1399">discover card</span></span>
- <span data-ttu-id="da5ee-1400">дисковеркард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1400">discovercard</span></span>
- <span data-ttu-id="da5ee-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1401">discover cards</span></span>
- <span data-ttu-id="da5ee-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="da5ee-1402">JCB</span></span>
- <span data-ttu-id="da5ee-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="da5ee-1403">japanese card bureau</span></span>
- <span data-ttu-id="da5ee-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="da5ee-1404">carte blanche</span></span>
- <span data-ttu-id="da5ee-1405">картебланче</span><span class="sxs-lookup"><span data-stu-id="da5ee-1405">carteblanche</span></span>
- <span data-ttu-id="da5ee-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1406">credit card</span></span>
- <span data-ttu-id="da5ee-1407">Центральной #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1407">cc#</span></span>
- <span data-ttu-id="da5ee-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1408">cc#:</span></span>
- <span data-ttu-id="da5ee-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="da5ee-1409">expiration date</span></span>
- <span data-ttu-id="da5ee-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="da5ee-1410">exp date</span></span>
- <span data-ttu-id="da5ee-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="da5ee-1411">expiry date</span></span>
- <span data-ttu-id="da5ee-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="da5ee-1412">date d’expiration</span></span>
- <span data-ttu-id="da5ee-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="da5ee-1413">date d'exp</span></span>
- <span data-ttu-id="da5ee-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="da5ee-1414">date expiration</span></span>
- <span data-ttu-id="da5ee-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1415">bank card</span></span>
- <span data-ttu-id="da5ee-1416">банккард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1416">bankcard</span></span>
- <span data-ttu-id="da5ee-1417">card number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1417">card number</span></span>
- <span data-ttu-id="da5ee-1418">card num</span><span class="sxs-lookup"><span data-stu-id="da5ee-1418">card num</span></span>
- <span data-ttu-id="da5ee-1419">карднумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1419">cardnumber</span></span>
- <span data-ttu-id="da5ee-1420">карднумберс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1420">cardnumbers</span></span>
- <span data-ttu-id="da5ee-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-1421">card numbers</span></span>
- <span data-ttu-id="da5ee-1422">кредиткард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1422">creditcard</span></span>
- <span data-ttu-id="da5ee-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1423">credit cards</span></span>
- <span data-ttu-id="da5ee-1424">кредиткардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1424">creditcards</span></span>
- <span data-ttu-id="da5ee-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="da5ee-1425">ccn</span></span>
- <span data-ttu-id="da5ee-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="da5ee-1426">card holder</span></span>
- <span data-ttu-id="da5ee-1427">банков</span><span class="sxs-lookup"><span data-stu-id="da5ee-1427">cardholder</span></span>
- <span data-ttu-id="da5ee-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="da5ee-1428">card holders</span></span>
- <span data-ttu-id="da5ee-1429">карты</span><span class="sxs-lookup"><span data-stu-id="da5ee-1429">cardholders</span></span>
- <span data-ttu-id="da5ee-1430">check card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1430">check card</span></span>
- <span data-ttu-id="da5ee-1431">чекккард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1431">checkcard</span></span>
- <span data-ttu-id="da5ee-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1432">check cards</span></span>
- <span data-ttu-id="da5ee-1433">чекккардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1433">checkcards</span></span>
- <span data-ttu-id="da5ee-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1434">debit card</span></span>
- <span data-ttu-id="da5ee-1435">дебиткард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1435">debitcard</span></span>
- <span data-ttu-id="da5ee-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1436">debit cards</span></span>
- <span data-ttu-id="da5ee-1437">дебиткардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1437">debitcards</span></span>
- <span data-ttu-id="da5ee-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1438">atm card</span></span>
- <span data-ttu-id="da5ee-1439">атмкард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1439">atmcard</span></span>
- <span data-ttu-id="da5ee-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1440">atm cards</span></span>
- <span data-ttu-id="da5ee-1441">атмкардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1441">atmcards</span></span>
- <span data-ttu-id="da5ee-1442">енрауте</span><span class="sxs-lookup"><span data-stu-id="da5ee-1442">enroute</span></span>
- <span data-ttu-id="da5ee-1443">en route</span><span class="sxs-lookup"><span data-stu-id="da5ee-1443">en route</span></span>
- <span data-ttu-id="da5ee-1444">card type</span><span class="sxs-lookup"><span data-stu-id="da5ee-1444">card type</span></span>
- <span data-ttu-id="da5ee-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="da5ee-1445">carte bancaire</span></span>
- <span data-ttu-id="da5ee-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="da5ee-1446">carte de crédit</span></span>
- <span data-ttu-id="da5ee-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="da5ee-1447">carte de credit</span></span>
- <span data-ttu-id="da5ee-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1448">numéro de carte</span></span>
- <span data-ttu-id="da5ee-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1449">numero de carte</span></span>
- <span data-ttu-id="da5ee-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1450">nº de la carte</span></span>
- <span data-ttu-id="da5ee-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1451">nº de carte</span></span>
- <span data-ttu-id="da5ee-1452">кредиткарте</span><span class="sxs-lookup"><span data-stu-id="da5ee-1452">kreditkarte</span></span>
- <span data-ttu-id="da5ee-1453">карте</span><span class="sxs-lookup"><span data-stu-id="da5ee-1453">karte</span></span>
- <span data-ttu-id="da5ee-1454">картенинхабер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1454">karteninhaber</span></span>
- <span data-ttu-id="da5ee-1455">картенинхаберс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1455">karteninhabers</span></span>
- <span data-ttu-id="da5ee-1456">кредиткартенинхабер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="da5ee-1457">кредиткартенинститут</span><span class="sxs-lookup"><span data-stu-id="da5ee-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="da5ee-1458">кредиткартентип</span><span class="sxs-lookup"><span data-stu-id="da5ee-1458">kreditkartentyp</span></span>
- <span data-ttu-id="da5ee-1459">еижентüмернаме</span><span class="sxs-lookup"><span data-stu-id="da5ee-1459">eigentümername</span></span>
- <span data-ttu-id="da5ee-1460">картеннр</span><span class="sxs-lookup"><span data-stu-id="da5ee-1460">kartennr</span></span> 
- <span data-ttu-id="da5ee-1461">картеннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1461">kartennummer</span></span>
- <span data-ttu-id="da5ee-1462">кредиткартеннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1462">kreditkartennummer</span></span>
- <span data-ttu-id="da5ee-1463">кредиткартен — нуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="da5ee-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1464">carta di credito</span></span>
- <span data-ttu-id="da5ee-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1465">carta credito</span></span>
- <span data-ttu-id="da5ee-1466">Корзина "</span><span class="sxs-lookup"><span data-stu-id="da5ee-1466">carta</span></span>
- <span data-ttu-id="da5ee-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1467">n carta</span></span>
- <span data-ttu-id="da5ee-1468">НР.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1468">nr.</span></span> <span data-ttu-id="da5ee-1469">Корзина "</span><span class="sxs-lookup"><span data-stu-id="da5ee-1469">carta</span></span>
- <span data-ttu-id="da5ee-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1470">nr carta</span></span>
- <span data-ttu-id="da5ee-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1471">numero carta</span></span>
- <span data-ttu-id="da5ee-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1472">numero della carta</span></span>
- <span data-ttu-id="da5ee-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1473">numero di carta</span></span>
- <span data-ttu-id="da5ee-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1474">tarjeta credito</span></span>
- <span data-ttu-id="da5ee-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1475">tarjeta de credito</span></span>
- <span data-ttu-id="da5ee-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1476">tarjeta crédito</span></span>
- <span data-ttu-id="da5ee-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="da5ee-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="da5ee-1478">tarjeta de atm</span></span>
- <span data-ttu-id="da5ee-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="da5ee-1479">tarjeta atm</span></span>
- <span data-ttu-id="da5ee-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1480">tarjeta debito</span></span>
- <span data-ttu-id="da5ee-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1481">tarjeta de debito</span></span>
- <span data-ttu-id="da5ee-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1482">tarjeta débito</span></span>
- <span data-ttu-id="da5ee-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1483">tarjeta de débito</span></span>
- <span data-ttu-id="da5ee-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1484">nº de tarjeta</span></span>
- <span data-ttu-id="da5ee-1485">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1485">no.</span></span> <span data-ttu-id="da5ee-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1486">de tarjeta</span></span>
- <span data-ttu-id="da5ee-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1487">no de tarjeta</span></span>
- <span data-ttu-id="da5ee-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1488">numero de tarjeta</span></span>
- <span data-ttu-id="da5ee-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1489">número de tarjeta</span></span>
- <span data-ttu-id="da5ee-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="da5ee-1490">tarjeta no</span></span>
- <span data-ttu-id="da5ee-1491">таржетахабиенте</span><span class="sxs-lookup"><span data-stu-id="da5ee-1491">tarjetahabiente</span></span>
- <span data-ttu-id="da5ee-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1492">cartão de crédito</span></span>
- <span data-ttu-id="da5ee-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1493">cartão de credito</span></span>
- <span data-ttu-id="da5ee-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1494">cartao de crédito</span></span>
- <span data-ttu-id="da5ee-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1495">cartao de credito</span></span>
- <span data-ttu-id="da5ee-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1496">cartão de débito</span></span>
- <span data-ttu-id="da5ee-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1497">cartao de débito</span></span>
- <span data-ttu-id="da5ee-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1498">cartão de debito</span></span>
- <span data-ttu-id="da5ee-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1499">cartao de debito</span></span>
- <span data-ttu-id="da5ee-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="da5ee-1500">débito automático</span></span>
- <span data-ttu-id="da5ee-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="da5ee-1501">debito automatico</span></span>
- <span data-ttu-id="da5ee-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1502">número do cartão</span></span>
- <span data-ttu-id="da5ee-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1503">numero do cartão</span></span> 
- <span data-ttu-id="da5ee-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1504">número do cartao</span></span>
- <span data-ttu-id="da5ee-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1505">numero do cartao</span></span>
- <span data-ttu-id="da5ee-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1506">número de cartão</span></span>
- <span data-ttu-id="da5ee-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1507">numero de cartão</span></span>
- <span data-ttu-id="da5ee-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1508">número de cartao</span></span>
- <span data-ttu-id="da5ee-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1509">numero de cartao</span></span>
- <span data-ttu-id="da5ee-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1510">nº do cartão</span></span>
- <span data-ttu-id="da5ee-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1511">nº do cartao</span></span>
- <span data-ttu-id="da5ee-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1512">nº.</span></span> <span data-ttu-id="da5ee-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1513">do cartão</span></span>
- <span data-ttu-id="da5ee-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1514">no do cartão</span></span>
- <span data-ttu-id="da5ee-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1515">no do cartao</span></span>
- <span data-ttu-id="da5ee-1516">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1516">no.</span></span> <span data-ttu-id="da5ee-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1517">do cartão</span></span>
- <span data-ttu-id="da5ee-1518">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1518">no.</span></span> <span data-ttu-id="da5ee-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="da5ee-1520">	Номер удостоверения личности для Хорватии</span><span class="sxs-lookup"><span data-stu-id="da5ee-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1521">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1521">Format</span></span>

<span data-ttu-id="da5ee-1522">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1523">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1523">Pattern</span></span>

<span data-ttu-id="da5ee-1524">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1525">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1525">Checksum</span></span>

<span data-ttu-id="da5ee-1526">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1527">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1527">Definition</span></span>

<span data-ttu-id="da5ee-1528">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1529">функция Func_croatia_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1530">находится ключевое слово из Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-1531">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="da5ee-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="da5ee-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1533">Croatian identity card</span></span>
- <span data-ttu-id="da5ee-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="da5ee-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="da5ee-1535">	Индивидуальный идентификационный номер (OIB) для Хорватии</span><span class="sxs-lookup"><span data-stu-id="da5ee-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1536">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1536">Format</span></span>

<span data-ttu-id="da5ee-1537">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1538">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1538">Pattern</span></span>

<span data-ttu-id="da5ee-1539">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1539">11 digits:</span></span>
- <span data-ttu-id="da5ee-1540">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1540">10 digits</span></span> 
- <span data-ttu-id="da5ee-1541">Последняя цифра — контрольная цифра для международного обмена данными, буквы добавляются до одиннадцати цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1542">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1542">Checksum</span></span>

<span data-ttu-id="da5ee-1543">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1544">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1544">Definition</span></span>

<span data-ttu-id="da5ee-1545">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1546">функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1547">находится ключевое слово из Keyword_croatia_oib_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="da5ee-1548">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1548">The checksum passes.</span></span>

<span data-ttu-id="da5ee-1549">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1550">функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1551">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1552">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="da5ee-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="da5ee-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1554">Personal Identification Number</span></span>
- <span data-ttu-id="da5ee-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="da5ee-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="da5ee-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="da5ee-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="da5ee-1557">Номер личного удостоверения для чешского языка</span><span class="sxs-lookup"><span data-stu-id="da5ee-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1558">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1558">Format</span></span>

<span data-ttu-id="da5ee-1559">Девять цифр с необязательной косой чертой (старый формат) 10 цифрами с необязательной косой чертой (новый формат)</span><span class="sxs-lookup"><span data-stu-id="da5ee-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1560">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1560">Pattern</span></span>

<span data-ttu-id="da5ee-1561">Девять цифр (старый формат):</span><span class="sxs-lookup"><span data-stu-id="da5ee-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="da5ee-1562">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1562">Nine digits</span></span>

<span data-ttu-id="da5ee-1563">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="da5ee-1563">OR</span></span>

- <span data-ttu-id="da5ee-1564">Шесть цифр, представляющих дату рождения</span><span class="sxs-lookup"><span data-stu-id="da5ee-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="da5ee-1565">косая черта;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1565">A forward slash</span></span>
- <span data-ttu-id="da5ee-1566">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-1566">Three digits</span></span>

<span data-ttu-id="da5ee-1567">10 цифр (новый формат):</span><span class="sxs-lookup"><span data-stu-id="da5ee-1567">10 digits (new format):</span></span>
- <span data-ttu-id="da5ee-1568">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1568">10 digits</span></span>

<span data-ttu-id="da5ee-1569">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="da5ee-1569">OR</span></span>

- <span data-ttu-id="da5ee-1570">Шесть цифр, представляющих дату рождения</span><span class="sxs-lookup"><span data-stu-id="da5ee-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="da5ee-1571">косая черта;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1571">A forward slash</span></span> 
- <span data-ttu-id="da5ee-1572">Четыре цифры, где последняя цифра является контрольной цифрой</span><span class="sxs-lookup"><span data-stu-id="da5ee-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1573">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1573">Checksum</span></span>

<span data-ttu-id="da5ee-1574">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1575">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1575">Definition</span></span>

<span data-ttu-id="da5ee-1576">Политика защиты от потери данных — 85% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_czech_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="da5ee-1577">находится ключевое слово из Keyword_czech_id_card;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="da5ee-1578">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="da5ee-1579">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1579">Keywords</span></span>

- <span data-ttu-id="da5ee-1580">номер личного удостоверения для чешского языка</span><span class="sxs-lookup"><span data-stu-id="da5ee-1580">czech personal identity number</span></span>
- <span data-ttu-id="da5ee-1581">Роднé číсло</span><span class="sxs-lookup"><span data-stu-id="da5ee-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="da5ee-1582">	Индивидуальный идентификационный номер для Дании</span><span class="sxs-lookup"><span data-stu-id="da5ee-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1583">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1583">Format</span></span>

<span data-ttu-id="da5ee-1584">10 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1585">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1585">Pattern</span></span>

<span data-ttu-id="da5ee-1586">10 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1586">10 digits:</span></span>
- <span data-ttu-id="da5ee-1587">шесть цифр в формате ДДММГГ — дата рождения;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="da5ee-1588">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1588">A hyphen</span></span> 
- <span data-ttu-id="da5ee-1589">четыре цифры, где последняя цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1590">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1590">Checksum</span></span>

<span data-ttu-id="da5ee-1591">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1592">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1592">Definition</span></span>

<span data-ttu-id="da5ee-1593">Политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах расстояния от 300 символов: регулярное выражение Regex_denmark_id находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="da5ee-1594">находится ключевое слово из Keyword_denmark_id;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="da5ee-1595">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-1596">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="da5ee-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="da5ee-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="da5ee-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1598">Personal Identification Number</span></span>
- <span data-ttu-id="da5ee-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="da5ee-1599">CPR</span></span>
- <span data-ttu-id="da5ee-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="da5ee-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="da5ee-1601">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="da5ee-1602">Номер Управления по борьбе с наркотиками США (DEA)</span><span class="sxs-lookup"><span data-stu-id="da5ee-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1603">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1603">Format</span></span>

<span data-ttu-id="da5ee-1604">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1605">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1605">Pattern</span></span>

<span data-ttu-id="da5ee-1606">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="da5ee-1607">Одна буква (без учета регистра) из следующего набора: abcdefghjklmnprstux, представляющая собой код регистрирующегося лица</span><span class="sxs-lookup"><span data-stu-id="da5ee-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="da5ee-1608">Одна буква (без учета регистра), представляющая собой первую букву фамилии регистрирующегося лица</span><span class="sxs-lookup"><span data-stu-id="da5ee-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="da5ee-1609">Семь цифр, последняя из которых — контрольная</span><span class="sxs-lookup"><span data-stu-id="da5ee-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1610">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1610">Checksum</span></span>

<span data-ttu-id="da5ee-1611">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1612">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1612">Definition</span></span>

<span data-ttu-id="da5ee-1613">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1614">функция Func_dea_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1615">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-1616">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1616">Keywords</span></span>

<span data-ttu-id="da5ee-1617">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="da5ee-1618">Номер банковской карты для ЕС</span><span class="sxs-lookup"><span data-stu-id="da5ee-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1619">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1619">Format</span></span>

<span data-ttu-id="da5ee-1620">16 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1621">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1621">Pattern</span></span>

<span data-ttu-id="da5ee-1622">Очень сложный и надежный шаблон.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1623">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1623">Checksum</span></span>

<span data-ttu-id="da5ee-1624">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1625">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1625">Definition</span></span>

<span data-ttu-id="da5ee-1626">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1627">Функция Func_eu_debit_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1628">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="da5ee-1629">найдено ключевое слово из Keyword_eu_debit_card;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="da5ee-1630">найдено ключевое слово из Keyword_card_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="da5ee-1631">найдено ключевое слово из Keyword_card_security_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="da5ee-1632">найдено ключевое слово из Keyword_card_expiration_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="da5ee-1633">функция Func_expiration_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-1634">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1635">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="da5ee-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="da5ee-1637">account number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1637">account number</span></span> 
- <span data-ttu-id="da5ee-1638">card number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1638">card number</span></span> 
- <span data-ttu-id="da5ee-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1639">card no.</span></span> 
- <span data-ttu-id="da5ee-1640">security number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1640">security number</span></span> 
- <span data-ttu-id="da5ee-1641">Центральной #</span><span class="sxs-lookup"><span data-stu-id="da5ee-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="da5ee-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="da5ee-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="da5ee-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="da5ee-1643">acct nbr</span></span> 
- <span data-ttu-id="da5ee-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="da5ee-1644">acct num</span></span> 
- <span data-ttu-id="da5ee-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="da5ee-1645">acct no</span></span> 
- <span data-ttu-id="da5ee-1646">american express</span><span class="sxs-lookup"><span data-stu-id="da5ee-1646">american express</span></span> 
- <span data-ttu-id="da5ee-1647">американекспресс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1647">americanexpress</span></span> 
- <span data-ttu-id="da5ee-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="da5ee-1648">americano espresso</span></span> 
- <span data-ttu-id="da5ee-1649">амекс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1649">amex</span></span> 
- <span data-ttu-id="da5ee-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1650">atm card</span></span> 
- <span data-ttu-id="da5ee-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1651">atm cards</span></span> 
- <span data-ttu-id="da5ee-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="da5ee-1652">atm kaart</span></span> 
- <span data-ttu-id="da5ee-1653">атмкард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1653">atmcard</span></span> 
- <span data-ttu-id="da5ee-1654">атмкардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1654">atmcards</span></span> 
- <span data-ttu-id="da5ee-1655">атмкаарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1655">atmkaart</span></span> 
- <span data-ttu-id="da5ee-1656">атмкаартен</span><span class="sxs-lookup"><span data-stu-id="da5ee-1656">atmkaarten</span></span> 
- <span data-ttu-id="da5ee-1657">банконтакт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1657">bancontact</span></span> 
- <span data-ttu-id="da5ee-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1658">bank card</span></span> 
- <span data-ttu-id="da5ee-1659">банккаарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1659">bankkaart</span></span> 
- <span data-ttu-id="da5ee-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="da5ee-1660">card holder</span></span> 
- <span data-ttu-id="da5ee-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="da5ee-1661">card holders</span></span> 
- <span data-ttu-id="da5ee-1662">card num</span><span class="sxs-lookup"><span data-stu-id="da5ee-1662">card num</span></span> 
- <span data-ttu-id="da5ee-1663">card number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1663">card number</span></span> 
- <span data-ttu-id="da5ee-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-1664">card numbers</span></span> 
- <span data-ttu-id="da5ee-1665">card type</span><span class="sxs-lookup"><span data-stu-id="da5ee-1665">card type</span></span> 
- <span data-ttu-id="da5ee-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="da5ee-1666">cardano numerico</span></span> 
- <span data-ttu-id="da5ee-1667">банков</span><span class="sxs-lookup"><span data-stu-id="da5ee-1667">cardholder</span></span> 
- <span data-ttu-id="da5ee-1668">карты</span><span class="sxs-lookup"><span data-stu-id="da5ee-1668">cardholders</span></span> 
- <span data-ttu-id="da5ee-1669">карднумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1669">cardnumber</span></span> 
- <span data-ttu-id="da5ee-1670">карднумберс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1670">cardnumbers</span></span> 
- <span data-ttu-id="da5ee-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1671">carta bianca</span></span> 
- <span data-ttu-id="da5ee-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1672">carta credito</span></span> 
- <span data-ttu-id="da5ee-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1673">carta di credito</span></span> 
- <span data-ttu-id="da5ee-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1674">cartao de credito</span></span> 
- <span data-ttu-id="da5ee-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1675">cartao de crédito</span></span> 
- <span data-ttu-id="da5ee-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1676">cartao de debito</span></span> 
- <span data-ttu-id="da5ee-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1677">cartao de débito</span></span> 
- <span data-ttu-id="da5ee-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="da5ee-1678">carte bancaire</span></span> 
- <span data-ttu-id="da5ee-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="da5ee-1679">carte blanche</span></span> 
- <span data-ttu-id="da5ee-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="da5ee-1680">carte bleue</span></span> 
- <span data-ttu-id="da5ee-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="da5ee-1681">carte de credit</span></span> 
- <span data-ttu-id="da5ee-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="da5ee-1682">carte de crédit</span></span> 
- <span data-ttu-id="da5ee-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1683">carte di credito</span></span> 
- <span data-ttu-id="da5ee-1684">картебланче</span><span class="sxs-lookup"><span data-stu-id="da5ee-1684">carteblanche</span></span> 
- <span data-ttu-id="da5ee-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1685">cartão de credito</span></span> 
- <span data-ttu-id="da5ee-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1686">cartão de crédito</span></span> 
- <span data-ttu-id="da5ee-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1687">cartão de debito</span></span> 
- <span data-ttu-id="da5ee-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1688">cartão de débito</span></span> 
- <span data-ttu-id="da5ee-1689">cb</span><span class="sxs-lookup"><span data-stu-id="da5ee-1689">cb</span></span> 
- <span data-ttu-id="da5ee-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="da5ee-1690">ccn</span></span> 
- <span data-ttu-id="da5ee-1691">check card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1691">check card</span></span> 
- <span data-ttu-id="da5ee-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1692">check cards</span></span> 
- <span data-ttu-id="da5ee-1693">чекккард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1693">checkcard</span></span>
- <span data-ttu-id="da5ee-1694">чекккардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1694">checkcards</span></span> 
- <span data-ttu-id="da5ee-1695">чекуекаарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1695">chequekaart</span></span> 
- <span data-ttu-id="da5ee-1696">Logic</span><span class="sxs-lookup"><span data-stu-id="da5ee-1696">cirrus</span></span> 
- <span data-ttu-id="da5ee-1697">Cirrus центр EDC — Маестро</span><span class="sxs-lookup"><span data-stu-id="da5ee-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="da5ee-1698">контролекаарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1698">controlekaart</span></span> 
- <span data-ttu-id="da5ee-1699">контролекаартен</span><span class="sxs-lookup"><span data-stu-id="da5ee-1699">controlekaarten</span></span> 
- <span data-ttu-id="da5ee-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1700">credit card</span></span> 
- <span data-ttu-id="da5ee-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1701">credit cards</span></span> 
- <span data-ttu-id="da5ee-1702">кредиткард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1702">creditcard</span></span> 
- <span data-ttu-id="da5ee-1703">кредиткардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1703">creditcards</span></span> 
- <span data-ttu-id="da5ee-1704">дебеткаарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1704">debetkaart</span></span> 
- <span data-ttu-id="da5ee-1705">дебеткаартен</span><span class="sxs-lookup"><span data-stu-id="da5ee-1705">debetkaarten</span></span> 
- <span data-ttu-id="da5ee-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1706">debit card</span></span> 
- <span data-ttu-id="da5ee-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1707">debit cards</span></span> 
- <span data-ttu-id="da5ee-1708">дебиткард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1708">debitcard</span></span> 
- <span data-ttu-id="da5ee-1709">дебиткардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1709">debitcards</span></span> 
- <span data-ttu-id="da5ee-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="da5ee-1710">debito automatico</span></span> 
- <span data-ttu-id="da5ee-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="da5ee-1711">diners club</span></span> 
- <span data-ttu-id="da5ee-1712">динерсклуб</span><span class="sxs-lookup"><span data-stu-id="da5ee-1712">dinersclub</span></span> 
- <span data-ttu-id="da5ee-1713">Повтор</span><span class="sxs-lookup"><span data-stu-id="da5ee-1713">discover</span></span> 
- <span data-ttu-id="da5ee-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1714">discover card</span></span> 
- <span data-ttu-id="da5ee-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1715">discover cards</span></span> 
- <span data-ttu-id="da5ee-1716">дисковеркард</span><span class="sxs-lookup"><span data-stu-id="da5ee-1716">discovercard</span></span> 
- <span data-ttu-id="da5ee-1717">дисковеркардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1717">discovercards</span></span> 
- <span data-ttu-id="da5ee-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="da5ee-1718">débito automático</span></span>
- <span data-ttu-id="da5ee-1719">центр EDC</span><span class="sxs-lookup"><span data-stu-id="da5ee-1719">edc</span></span> 
- <span data-ttu-id="da5ee-1720">еижентüмернаме</span><span class="sxs-lookup"><span data-stu-id="da5ee-1720">eigentümername</span></span> 
- <span data-ttu-id="da5ee-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1721">european debit card</span></span> 
- <span data-ttu-id="da5ee-1722">хуфдкаарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1722">hoofdkaart</span></span> 
- <span data-ttu-id="da5ee-1723">хуфдкаартен</span><span class="sxs-lookup"><span data-stu-id="da5ee-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="da5ee-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="da5ee-1724">in viaggio</span></span> 
- <span data-ttu-id="da5ee-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="da5ee-1725">japanese card bureau</span></span> 
- <span data-ttu-id="da5ee-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="da5ee-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="da5ee-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="da5ee-1727">jcb</span></span> 
- <span data-ttu-id="da5ee-1728">каарт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1728">kaart</span></span> 
- <span data-ttu-id="da5ee-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="da5ee-1729">kaart num</span></span> 
- <span data-ttu-id="da5ee-1730">каартаантал</span><span class="sxs-lookup"><span data-stu-id="da5ee-1730">kaartaantal</span></span> 
- <span data-ttu-id="da5ee-1731">каартаанталлен</span><span class="sxs-lookup"><span data-stu-id="da5ee-1731">kaartaantallen</span></span> 
- <span data-ttu-id="da5ee-1732">каарсаудер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1732">kaarthouder</span></span> 
- <span data-ttu-id="da5ee-1733">каарсаудерс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1733">kaarthouders</span></span> 
- <span data-ttu-id="da5ee-1734">карте</span><span class="sxs-lookup"><span data-stu-id="da5ee-1734">karte</span></span>  
- <span data-ttu-id="da5ee-1735">картенинхабер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1735">karteninhaber</span></span> 
- <span data-ttu-id="da5ee-1736">картенинхаберс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1736">karteninhabers</span></span>
- <span data-ttu-id="da5ee-1737">картеннр</span><span class="sxs-lookup"><span data-stu-id="da5ee-1737">kartennr</span></span> 
- <span data-ttu-id="da5ee-1738">картеннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1738">kartennummer</span></span> 
- <span data-ttu-id="da5ee-1739">кредиткарте</span><span class="sxs-lookup"><span data-stu-id="da5ee-1739">kreditkarte</span></span> 
- <span data-ttu-id="da5ee-1740">кредиткартен — нуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="da5ee-1741">кредиткартенинхабер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="da5ee-1742">кредиткартенинститут</span><span class="sxs-lookup"><span data-stu-id="da5ee-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="da5ee-1743">кредиткартеннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="da5ee-1744">кредиткартентип</span><span class="sxs-lookup"><span data-stu-id="da5ee-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="da5ee-1745">маестро</span><span class="sxs-lookup"><span data-stu-id="da5ee-1745">maestro</span></span> 
- <span data-ttu-id="da5ee-1746">master card</span><span class="sxs-lookup"><span data-stu-id="da5ee-1746">master card</span></span> 
- <span data-ttu-id="da5ee-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-1747">master cards</span></span> 
- <span data-ttu-id="da5ee-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="da5ee-1748">mastercard</span></span> 
- <span data-ttu-id="da5ee-1749">мастеркардс</span><span class="sxs-lookup"><span data-stu-id="da5ee-1749">mastercards</span></span> 
- <span data-ttu-id="da5ee-1750">MC</span><span class="sxs-lookup"><span data-stu-id="da5ee-1750">mc</span></span> 
- <span data-ttu-id="da5ee-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="da5ee-1751">mister cash</span></span> 
- <span data-ttu-id="da5ee-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1752">n carta</span></span> 
- <span data-ttu-id="da5ee-1753">Корзина "</span><span class="sxs-lookup"><span data-stu-id="da5ee-1753">carta</span></span> 
- <span data-ttu-id="da5ee-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1754">no de tarjeta</span></span> 
- <span data-ttu-id="da5ee-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1755">no do cartao</span></span> 
- <span data-ttu-id="da5ee-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1756">no do cartão</span></span> 
- <span data-ttu-id="da5ee-1757">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1757">no.</span></span> <span data-ttu-id="da5ee-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1758">de tarjeta</span></span> 
- <span data-ttu-id="da5ee-1759">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1759">no.</span></span> <span data-ttu-id="da5ee-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1760">do cartao</span></span> 
- <span data-ttu-id="da5ee-1761">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1761">no.</span></span> <span data-ttu-id="da5ee-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1762">do cartão</span></span> 
- <span data-ttu-id="da5ee-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1763">nr carta</span></span> 
- <span data-ttu-id="da5ee-1764">НР.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1764">nr.</span></span> <span data-ttu-id="da5ee-1765">Корзина "</span><span class="sxs-lookup"><span data-stu-id="da5ee-1765">carta</span></span> 
- <span data-ttu-id="da5ee-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="da5ee-1766">numeri di scheda</span></span> 
- <span data-ttu-id="da5ee-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1767">numero carta</span></span> 
- <span data-ttu-id="da5ee-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1768">numero de cartao</span></span> 
- <span data-ttu-id="da5ee-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1769">numero de carte</span></span> 
- <span data-ttu-id="da5ee-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1770">numero de cartão</span></span> 
- <span data-ttu-id="da5ee-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1771">numero de tarjeta</span></span>
- <span data-ttu-id="da5ee-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1772">numero della carta</span></span> 
- <span data-ttu-id="da5ee-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1773">numero di carta</span></span> 
- <span data-ttu-id="da5ee-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="da5ee-1774">numero di scheda</span></span> 
- <span data-ttu-id="da5ee-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1775">numero do cartao</span></span> 
- <span data-ttu-id="da5ee-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1776">numero do cartão</span></span> 
- <span data-ttu-id="da5ee-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1777">numéro de carte</span></span> 
- <span data-ttu-id="da5ee-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1778">nº carta</span></span> 
- <span data-ttu-id="da5ee-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1779">nº de carte</span></span> 
- <span data-ttu-id="da5ee-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="da5ee-1780">nº de la carte</span></span> 
- <span data-ttu-id="da5ee-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="da5ee-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1782">nº do cartao</span></span> 
- <span data-ttu-id="da5ee-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1783">nº do cartão</span></span> 
- <span data-ttu-id="da5ee-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1784">nº.</span></span> <span data-ttu-id="da5ee-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1785">do cartão</span></span> 
- <span data-ttu-id="da5ee-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1786">número de cartao</span></span> 
- <span data-ttu-id="da5ee-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="da5ee-1787">número de cartão</span></span> 
- <span data-ttu-id="da5ee-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1788">número de tarjeta</span></span> 
- <span data-ttu-id="da5ee-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1789">número do cartao</span></span> 
- <span data-ttu-id="da5ee-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="da5ee-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="da5ee-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="da5ee-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="da5ee-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="da5ee-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="da5ee-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1793">scheda della banca</span></span> 
- <span data-ttu-id="da5ee-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="da5ee-1794">scheda di controllo</span></span> 
- <span data-ttu-id="da5ee-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1795">scheda di debito</span></span> 
- <span data-ttu-id="da5ee-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="da5ee-1796">scheda matrice</span></span> 
- <span data-ttu-id="da5ee-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="da5ee-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="da5ee-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="da5ee-1798">schede di controllo</span></span> 
- <span data-ttu-id="da5ee-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1799">schede di debito</span></span> 
- <span data-ttu-id="da5ee-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="da5ee-1800">schede matrici</span></span> 
- <span data-ttu-id="da5ee-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="da5ee-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="da5ee-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="da5ee-1802">scoprono le schede</span></span> 
- <span data-ttu-id="da5ee-1803">ОС</span><span class="sxs-lookup"><span data-stu-id="da5ee-1803">solo</span></span> 
- <span data-ttu-id="da5ee-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="da5ee-1804">supporti di scheda</span></span> 
- <span data-ttu-id="da5ee-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="da5ee-1805">supporto di scheda</span></span> 
- <span data-ttu-id="da5ee-1806">отключен</span><span class="sxs-lookup"><span data-stu-id="da5ee-1806">switch</span></span> 
- <span data-ttu-id="da5ee-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="da5ee-1807">tarjeta atm</span></span> 
- <span data-ttu-id="da5ee-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1808">tarjeta credito</span></span> 
- <span data-ttu-id="da5ee-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="da5ee-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="da5ee-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="da5ee-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="da5ee-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="da5ee-1812">tarjeta debito</span></span> 
- <span data-ttu-id="da5ee-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="da5ee-1813">tarjeta no</span></span>
- <span data-ttu-id="da5ee-1814">таржетахабиенте</span><span class="sxs-lookup"><span data-stu-id="da5ee-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="da5ee-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="da5ee-1815">tipo della scheda</span></span> 
- <span data-ttu-id="da5ee-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="da5ee-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="da5ee-1817">счеда</span><span class="sxs-lookup"><span data-stu-id="da5ee-1817">scheda</span></span> 
- <span data-ttu-id="da5ee-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="da5ee-1818">v pay</span></span> 
- <span data-ttu-id="da5ee-1819">v — оплата</span><span class="sxs-lookup"><span data-stu-id="da5ee-1819">v-pay</span></span> 
- <span data-ttu-id="da5ee-1820">Visa</span><span class="sxs-lookup"><span data-stu-id="da5ee-1820">visa</span></span> 
- <span data-ttu-id="da5ee-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="da5ee-1821">visa plus</span></span> 
- <span data-ttu-id="da5ee-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="da5ee-1822">visa electron</span></span> 
- <span data-ttu-id="da5ee-1823">висто</span><span class="sxs-lookup"><span data-stu-id="da5ee-1823">visto</span></span> 
- <span data-ttu-id="da5ee-1824">висум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1824">visum</span></span> 
- <span data-ttu-id="da5ee-1825">впай</span><span class="sxs-lookup"><span data-stu-id="da5ee-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="da5ee-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="da5ee-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="da5ee-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1827">card identification number</span></span>
- <span data-ttu-id="da5ee-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="da5ee-1828">card verification</span></span> 
- <span data-ttu-id="da5ee-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="da5ee-1829">cardi la verifica</span></span> 
- <span data-ttu-id="da5ee-1830">cid</span><span class="sxs-lookup"><span data-stu-id="da5ee-1830">cid</span></span> 
- <span data-ttu-id="da5ee-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="da5ee-1831">cod seg</span></span> 
- <span data-ttu-id="da5ee-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1832">cod seguranca</span></span> 
- <span data-ttu-id="da5ee-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="da5ee-1833">cod segurança</span></span> 
- <span data-ttu-id="da5ee-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1834">cod sicurezza</span></span> 
- <span data-ttu-id="da5ee-1835">наложен.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1835">cod.</span></span> <span data-ttu-id="da5ee-1836">сег</span><span class="sxs-lookup"><span data-stu-id="da5ee-1836">seg</span></span> 
- <span data-ttu-id="da5ee-1837">наложен.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1837">cod.</span></span> <span data-ttu-id="da5ee-1838">сегуранка</span><span class="sxs-lookup"><span data-stu-id="da5ee-1838">seguranca</span></span> 
- <span data-ttu-id="da5ee-1839">наложен.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1839">cod.</span></span> <span data-ttu-id="da5ee-1840">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="da5ee-1840">segurança</span></span> 
- <span data-ttu-id="da5ee-1841">наложен.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1841">cod.</span></span> <span data-ttu-id="da5ee-1842">сикурезза</span><span class="sxs-lookup"><span data-stu-id="da5ee-1842">sicurezza</span></span> 
- <span data-ttu-id="da5ee-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="da5ee-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="da5ee-1844">codice di verifica</span></span> 
- <span data-ttu-id="da5ee-1845">кодиго</span><span class="sxs-lookup"><span data-stu-id="da5ee-1845">codigo</span></span> 
- <span data-ttu-id="da5ee-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="da5ee-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="da5ee-1847">codigo de segurança</span></span> 
- <span data-ttu-id="da5ee-1848">криттограмма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1848">crittogramma</span></span> 
- <span data-ttu-id="da5ee-1849">криптограм</span><span class="sxs-lookup"><span data-stu-id="da5ee-1849">cryptogram</span></span> 
- <span data-ttu-id="da5ee-1850">криптограмме</span><span class="sxs-lookup"><span data-stu-id="da5ee-1850">cryptogramme</span></span> 
- <span data-ttu-id="da5ee-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="da5ee-1851">cv2</span></span> 
- <span data-ttu-id="da5ee-1852">квк</span><span class="sxs-lookup"><span data-stu-id="da5ee-1852">cvc</span></span> 
- <span data-ttu-id="da5ee-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="da5ee-1853">cvc2</span></span> 
- <span data-ttu-id="da5ee-1854">квн</span><span class="sxs-lookup"><span data-stu-id="da5ee-1854">cvn</span></span> 
- <span data-ttu-id="da5ee-1855">квв</span><span class="sxs-lookup"><span data-stu-id="da5ee-1855">cvv</span></span> 
- <span data-ttu-id="da5ee-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="da5ee-1856">cvv2</span></span> 
- <span data-ttu-id="da5ee-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1857">cód seguranca</span></span> 
- <span data-ttu-id="da5ee-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="da5ee-1858">cód segurança</span></span> 
- <span data-ttu-id="da5ee-1859">кóд.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1859">cód.</span></span> <span data-ttu-id="da5ee-1860">сегуранка</span><span class="sxs-lookup"><span data-stu-id="da5ee-1860">seguranca</span></span> 
- <span data-ttu-id="da5ee-1861">кóд.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1861">cód.</span></span> <span data-ttu-id="da5ee-1862">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="da5ee-1862">segurança</span></span> 
- <span data-ttu-id="da5ee-1863">кóдиго</span><span class="sxs-lookup"><span data-stu-id="da5ee-1863">código</span></span> 
- <span data-ttu-id="da5ee-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="da5ee-1864">código de seguranca</span></span> 
- <span data-ttu-id="da5ee-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="da5ee-1865">código de segurança</span></span> 
- <span data-ttu-id="da5ee-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="da5ee-1866">de kaart controle</span></span> 
- <span data-ttu-id="da5ee-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="da5ee-1867">geeft nr uit</span></span> 
- <span data-ttu-id="da5ee-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="da5ee-1868">issue no</span></span> 
- <span data-ttu-id="da5ee-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1869">issue number</span></span> 
- <span data-ttu-id="da5ee-1870">каартидентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="da5ee-1871">кредиткартенпруфнуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="da5ee-1872">кредиткартенпрüфнуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="da5ee-1873">квестиеаантал</span><span class="sxs-lookup"><span data-stu-id="da5ee-1873">kwestieaantal</span></span> 
- <span data-ttu-id="da5ee-1874">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1874">no.</span></span> <span data-ttu-id="da5ee-1875">делл'едизионе</span><span class="sxs-lookup"><span data-stu-id="da5ee-1875">dell'edizione</span></span> 
- <span data-ttu-id="da5ee-1876">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1876">no.</span></span> <span data-ttu-id="da5ee-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1877">di sicurezza</span></span> 
- <span data-ttu-id="da5ee-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="da5ee-1878">numero de securite</span></span> 
- <span data-ttu-id="da5ee-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1879">numero de verificacao</span></span> 
- <span data-ttu-id="da5ee-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="da5ee-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="da5ee-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="da5ee-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="da5ee-1882">счеда</span><span class="sxs-lookup"><span data-stu-id="da5ee-1882">scheda</span></span> 
- <span data-ttu-id="da5ee-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="da5ee-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="da5ee-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="da5ee-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="da5ee-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="da5ee-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="da5ee-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="da5ee-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="da5ee-1887">número de verificação</span></span> 
- <span data-ttu-id="da5ee-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="da5ee-1888">perno il blocco</span></span> 
- <span data-ttu-id="da5ee-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="da5ee-1889">pin block</span></span> 
- <span data-ttu-id="da5ee-1890">пруфзиффер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1890">prufziffer</span></span> 
- <span data-ttu-id="da5ee-1891">прüфзиффер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1891">prüfziffer</span></span> 
- <span data-ttu-id="da5ee-1892">security code</span><span class="sxs-lookup"><span data-stu-id="da5ee-1892">security code</span></span> 
- <span data-ttu-id="da5ee-1893">security no</span><span class="sxs-lookup"><span data-stu-id="da5ee-1893">security no</span></span> 
- <span data-ttu-id="da5ee-1894">security number</span><span class="sxs-lookup"><span data-stu-id="da5ee-1894">security number</span></span> 
- <span data-ttu-id="da5ee-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="da5ee-1895">sicherheits kode</span></span> 
- <span data-ttu-id="da5ee-1896">сичерхеитскоде</span><span class="sxs-lookup"><span data-stu-id="da5ee-1896">sicherheitscode</span></span> 
- <span data-ttu-id="da5ee-1897">сичерхеитснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="da5ee-1898">спелдблок</span><span class="sxs-lookup"><span data-stu-id="da5ee-1898">speldblok</span></span> 
- <span data-ttu-id="da5ee-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="da5ee-1899">veiligheid nr</span></span> 
- <span data-ttu-id="da5ee-1900">веилигхеидсаантал</span><span class="sxs-lookup"><span data-stu-id="da5ee-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="da5ee-1901">веилигхеидскоде</span><span class="sxs-lookup"><span data-stu-id="da5ee-1901">veiligheidscode</span></span> 
- <span data-ttu-id="da5ee-1902">веилигхеидснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="da5ee-1903">верфаллдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="da5ee-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="da5ee-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="da5ee-1905">аблауф</span><span class="sxs-lookup"><span data-stu-id="da5ee-1905">ablauf</span></span> 
- <span data-ttu-id="da5ee-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="da5ee-1906">data de expiracao</span></span> 
- <span data-ttu-id="da5ee-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="da5ee-1907">data de expiração</span></span> 
- <span data-ttu-id="da5ee-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="da5ee-1908">data del exp</span></span> 
- <span data-ttu-id="da5ee-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="da5ee-1909">data di exp</span></span> 
- <span data-ttu-id="da5ee-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1910">data di scadenza</span></span> 
- <span data-ttu-id="da5ee-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="da5ee-1911">data em que expira</span></span> 
- <span data-ttu-id="da5ee-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="da5ee-1912">data scad</span></span> 
- <span data-ttu-id="da5ee-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1913">data scadenza</span></span> 
- <span data-ttu-id="da5ee-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="da5ee-1914">date de validité</span></span> 
- <span data-ttu-id="da5ee-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="da5ee-1915">datum afloop</span></span> 
- <span data-ttu-id="da5ee-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="da5ee-1916">datum van exp</span></span> 
- <span data-ttu-id="da5ee-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="da5ee-1917">de afloop</span></span> 
- <span data-ttu-id="da5ee-1918">еспира</span><span class="sxs-lookup"><span data-stu-id="da5ee-1918">espira</span></span> 
- <span data-ttu-id="da5ee-1919">еспира</span><span class="sxs-lookup"><span data-stu-id="da5ee-1919">espira</span></span> 
- <span data-ttu-id="da5ee-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="da5ee-1920">exp date</span></span> 
- <span data-ttu-id="da5ee-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="da5ee-1921">exp datum</span></span> 
- <span data-ttu-id="da5ee-1922">срока действия</span><span class="sxs-lookup"><span data-stu-id="da5ee-1922">expiration</span></span> 
- <span data-ttu-id="da5ee-1923">истекает</span><span class="sxs-lookup"><span data-stu-id="da5ee-1923">expire</span></span> 
- <span data-ttu-id="da5ee-1924">истекает</span><span class="sxs-lookup"><span data-stu-id="da5ee-1924">expires</span></span> 
- <span data-ttu-id="da5ee-1925">окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="da5ee-1925">expiry</span></span> 
- <span data-ttu-id="da5ee-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="da5ee-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="da5ee-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="da5ee-1927">fecha de venc</span></span> 
- <span data-ttu-id="da5ee-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="da5ee-1928">gultig bis</span></span> 
- <span data-ttu-id="da5ee-1929">гултигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="da5ee-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="da5ee-1930">gültig bis</span></span> 
- <span data-ttu-id="da5ee-1931">гüлтигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="da5ee-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="da5ee-1932">la scadenza</span></span> 
- <span data-ttu-id="da5ee-1933">скаденза</span><span class="sxs-lookup"><span data-stu-id="da5ee-1933">scadenza</span></span> 
- <span data-ttu-id="da5ee-1934">валабле</span><span class="sxs-lookup"><span data-stu-id="da5ee-1934">valable</span></span> 
- <span data-ttu-id="da5ee-1935">валидаде</span><span class="sxs-lookup"><span data-stu-id="da5ee-1935">validade</span></span> 
- <span data-ttu-id="da5ee-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1936">valido hasta</span></span> 
- <span data-ttu-id="da5ee-1937">валор</span><span class="sxs-lookup"><span data-stu-id="da5ee-1937">valor</span></span> 
- <span data-ttu-id="da5ee-1938">венк</span><span class="sxs-lookup"><span data-stu-id="da5ee-1938">venc</span></span> 
- <span data-ttu-id="da5ee-1939">венЦименто</span><span class="sxs-lookup"><span data-stu-id="da5ee-1939">vencimento</span></span> 
- <span data-ttu-id="da5ee-1940">венЦимиенто</span><span class="sxs-lookup"><span data-stu-id="da5ee-1940">vencimiento</span></span> 
- <span data-ttu-id="da5ee-1941">верлупт</span><span class="sxs-lookup"><span data-stu-id="da5ee-1941">verloopt</span></span> 
- <span data-ttu-id="da5ee-1942">вервалдаг</span><span class="sxs-lookup"><span data-stu-id="da5ee-1942">vervaldag</span></span> 
- <span data-ttu-id="da5ee-1943">вервалдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-1943">vervaldatum</span></span> 
- <span data-ttu-id="da5ee-1944">вто</span><span class="sxs-lookup"><span data-stu-id="da5ee-1944">vto</span></span> 
- <span data-ttu-id="da5ee-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="da5ee-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="da5ee-1946">Номер водительского удостоверения для драйвера ЕС</span><span class="sxs-lookup"><span data-stu-id="da5ee-1946">EU Driver's License Number</span></span>

<span data-ttu-id="da5ee-1947">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации номера лицензии для драйвера ЕС](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="da5ee-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="da5ee-1948">Национальный идентификационный номер ЕС</span><span class="sxs-lookup"><span data-stu-id="da5ee-1948">EU National Identification Number</span></span>

<span data-ttu-id="da5ee-1949">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации для национального идентификационного номера ЕС](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="da5ee-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="da5ee-1950">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="da5ee-1950">EU Passport Number</span></span>

<span data-ttu-id="da5ee-1951">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации о номере паспорта ЕС](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="da5ee-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="da5ee-1952">Номер социального страхования ЕС или эквивалентный идентификатор</span><span class="sxs-lookup"><span data-stu-id="da5ee-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="da5ee-1953">Чтобы узнать больше, ознакомьтесь со статьей [номер социального страхования ЕС или эквивалентный тип конфиденциальной информации ID](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="da5ee-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="da5ee-1954">Идентификационный номер налогоплательщика ЕС</span><span class="sxs-lookup"><span data-stu-id="da5ee-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="da5ee-1955">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации для налогового кода ЕС](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="da5ee-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="da5ee-1956">Национальный идентификатор, Финляндия</span><span class="sxs-lookup"><span data-stu-id="da5ee-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1957">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1957">Format</span></span>

<span data-ttu-id="da5ee-1958">Шесть цифр, а также символ, обозначающий век, три цифры и контрольная цифра.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1959">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1959">Pattern</span></span>

<span data-ttu-id="da5ee-1960">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="da5ee-1961">Шесть цифр в формате ДДММГГ, представляющие собой дату рождения</span><span class="sxs-lookup"><span data-stu-id="da5ee-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="da5ee-1962">Маркер века (символы "-" и "+" или буква "a")</span><span class="sxs-lookup"><span data-stu-id="da5ee-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="da5ee-1963">Трехзначный личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="da5ee-1964">Цифра или буква (без учета регистра) — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1965">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1965">Checksum</span></span>

<span data-ttu-id="da5ee-1966">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1967">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1967">Definition</span></span>

<span data-ttu-id="da5ee-1968">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1969">функция Func_finnish_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1970">находится ключевое слово из Keyword_finnish_national_id;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="da5ee-1971">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-1972">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1972">Keywords</span></span>

- <span data-ttu-id="da5ee-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="da5ee-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="da5ee-1974">сосиаалитурватуннус</span><span class="sxs-lookup"><span data-stu-id="da5ee-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="da5ee-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="da5ee-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="da5ee-1976">персонбетеккнинг</span><span class="sxs-lookup"><span data-stu-id="da5ee-1976">Personbeteckning</span></span>
- <span data-ttu-id="da5ee-1977">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="da5ee-1978">Номер паспорта для Финляндии</span><span class="sxs-lookup"><span data-stu-id="da5ee-1978">Finland Passport Number</span></span>

<span data-ttu-id="da5ee-1979">Комбинация, состоящая из девяти букв и цифр, комбинация из девяти букв и цифр: две буквы (без учета регистра) семь цифр контрольная сумма нет определения политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации определен, если в близость от 300 символов: регулярное выражение Regex_finland_passport_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="da5ee-1980">находится ключевое слово из Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="da5ee-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="da5ee-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="da5ee-1982">Ключевые слова Keyword_finland_passport_number Passport Пасси</span><span class="sxs-lookup"><span data-stu-id="da5ee-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="da5ee-1983">Номер водительского удостоверения для Франции</span><span class="sxs-lookup"><span data-stu-id="da5ee-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-1984">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-1984">Format</span></span>

<span data-ttu-id="da5ee-1985">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-1986">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-1986">Pattern</span></span>

<span data-ttu-id="da5ee-1987">12 цифр с проверкой подлинности, чтобы избежать путаницы с похожими шаблонами, например французскими номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-1988">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-1988">Checksum</span></span>

<span data-ttu-id="da5ee-1989">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-1990">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-1990">Definition</span></span>

<span data-ttu-id="da5ee-1991">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-1992">Функция Func_french_drivers_license находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-1993">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="da5ee-1994">найдено ключевое слово из Keyword_french_drivers_license;</span><span class="sxs-lookup"><span data-stu-id="da5ee-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="da5ee-1995">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-1996">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="da5ee-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="da5ee-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="da5ee-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-1998">drivers licence</span></span>
- <span data-ttu-id="da5ee-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="da5ee-1999">drivers license</span></span>
- <span data-ttu-id="da5ee-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-2000">driving licence</span></span>
- <span data-ttu-id="da5ee-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="da5ee-2001">driving license</span></span>
- <span data-ttu-id="da5ee-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="da5ee-2002">permis de conduire</span></span>
- <span data-ttu-id="da5ee-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2003">licence number</span></span>
- <span data-ttu-id="da5ee-2004">license number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2004">license number</span></span>
- <span data-ttu-id="da5ee-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-2005">licence numbers</span></span>
- <span data-ttu-id="da5ee-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="da5ee-2007">Номер внутреннего удостоверения личности для Франции (CNI)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2008">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2008">Format</span></span>

<span data-ttu-id="da5ee-2009">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2010">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2010">Pattern</span></span>

<span data-ttu-id="da5ee-2011">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2012">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2012">Checksum</span></span>

<span data-ttu-id="da5ee-2013">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2014">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2014">Definition</span></span>

<span data-ttu-id="da5ee-2015">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2016">регулярное выражение Regex_france_cni находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2017">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2017">Keywords</span></span>

<span data-ttu-id="da5ee-2018">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="da5ee-2019">Номер паспорта гражданина Франции</span><span class="sxs-lookup"><span data-stu-id="da5ee-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2020">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2020">Format</span></span>

<span data-ttu-id="da5ee-2021">Девять цифр и букв.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2022">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2022">Pattern</span></span>

<span data-ttu-id="da5ee-2023">Девять цифр и букв</span><span class="sxs-lookup"><span data-stu-id="da5ee-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="da5ee-2024">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2024">Two digits</span></span> 
- <span data-ttu-id="da5ee-2025">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-2026">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2027">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2027">Checksum</span></span>

<span data-ttu-id="da5ee-2028">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2029">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2029">Definition</span></span>

<span data-ttu-id="da5ee-2030">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2031">функция Func_fr_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2032">находится ключевое слово из Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2033">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="da5ee-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-2034">Keyword_passport</span></span>

- <span data-ttu-id="da5ee-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2035">Passport Number</span></span>
- <span data-ttu-id="da5ee-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="da5ee-2036">Passport No</span></span>
- <span data-ttu-id="da5ee-2037">Passport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-2037">Passport #</span></span>
- <span data-ttu-id="da5ee-2038">Службу #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2038">Passport#</span></span>
- <span data-ttu-id="da5ee-2039">пасспортид</span><span class="sxs-lookup"><span data-stu-id="da5ee-2039">PassportID</span></span>
- <span data-ttu-id="da5ee-2040">пасспортно</span><span class="sxs-lookup"><span data-stu-id="da5ee-2040">Passportno</span></span>
- <span data-ttu-id="da5ee-2041">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2041">passportnumber</span></span>
- <span data-ttu-id="da5ee-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="da5ee-2042">パスポート</span></span>
- <span data-ttu-id="da5ee-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2043">パスポート番号</span></span>
- <span data-ttu-id="da5ee-2044">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="da5ee-2044">パスポートのNum</span></span>
- <span data-ttu-id="da5ee-2045">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="da5ee-2045">パスポート ＃</span></span> 
- <span data-ttu-id="da5ee-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="da5ee-2046">Numéro de passeport</span></span>
- <span data-ttu-id="da5ee-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="da5ee-2047">Passeport n °</span></span>
- <span data-ttu-id="da5ee-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="da5ee-2048">Passeport Non</span></span>
- <span data-ttu-id="da5ee-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-2049">Passeport #</span></span>
- <span data-ttu-id="da5ee-2050">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2050">Passeport#</span></span>
- <span data-ttu-id="da5ee-2051">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2051">PasseportNon</span></span>
- <span data-ttu-id="da5ee-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="da5ee-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="da5ee-2053">Страховой номер для Франции (INSEE)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2054">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2054">Format</span></span>

<span data-ttu-id="da5ee-2055">15 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2056">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2056">Pattern</span></span>

<span data-ttu-id="da5ee-2057">Должен соответствовать одному из двух шаблонов:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="da5ee-2058">13 цифр, за которыми следует пробел, за которым следуют две цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="da5ee-2059">или</span><span class="sxs-lookup"><span data-stu-id="da5ee-2059">or</span></span>
- <span data-ttu-id="da5ee-2060">15 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2061">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2061">Checksum</span></span>

<span data-ttu-id="da5ee-2062">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2063">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2063">Definition</span></span>

<span data-ttu-id="da5ee-2064">Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2065">Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2066">находится ключевое слово из Keyword_fr_insee;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="da5ee-2067">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2067">The checksum passes.</span></span>

<span data-ttu-id="da5ee-2068">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2069">Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2070">ни одно ключевое слово из Keyword_fr_insee не находится;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="da5ee-2071">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2072">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="da5ee-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="da5ee-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="da5ee-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="da5ee-2074">insee</span></span>
- <span data-ttu-id="da5ee-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="da5ee-2075">securité sociale</span></span>
- <span data-ttu-id="da5ee-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="da5ee-2076">securite sociale</span></span>
- <span data-ttu-id="da5ee-2077">national id</span><span class="sxs-lookup"><span data-stu-id="da5ee-2077">national id</span></span>
- <span data-ttu-id="da5ee-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="da5ee-2078">national identification</span></span>
- <span data-ttu-id="da5ee-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="da5ee-2079">numéro d'identité</span></span>
- <span data-ttu-id="da5ee-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="da5ee-2080">no d'identité</span></span>
- <span data-ttu-id="da5ee-2081">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2081">no.</span></span> <span data-ttu-id="da5ee-2082">д'идентитé</span><span class="sxs-lookup"><span data-stu-id="da5ee-2082">d'identité</span></span>
- <span data-ttu-id="da5ee-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="da5ee-2083">numero d'identite</span></span>
- <span data-ttu-id="da5ee-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="da5ee-2084">no d'identite</span></span>
- <span data-ttu-id="da5ee-2085">Нет.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2085">no.</span></span> <span data-ttu-id="da5ee-2086">д'идентите</span><span class="sxs-lookup"><span data-stu-id="da5ee-2086">d'identite</span></span>
- <span data-ttu-id="da5ee-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2087">social security number</span></span>
- <span data-ttu-id="da5ee-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="da5ee-2088">social security code</span></span>
- <span data-ttu-id="da5ee-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2089">social insurance number</span></span>
- <span data-ttu-id="da5ee-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="da5ee-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="da5ee-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="da5ee-2091">d'identité nationale</span></span>
- <span data-ttu-id="da5ee-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="da5ee-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="da5ee-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="da5ee-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="da5ee-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="da5ee-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="da5ee-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="da5ee-2095">numéro de sécu</span></span>
- <span data-ttu-id="da5ee-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="da5ee-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="da5ee-2097">Номер водительского удостоверения для Германии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2098">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2098">Format</span></span>

<span data-ttu-id="da5ee-2099">Сочетание 11 цифр и букв.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2100">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2100">Pattern</span></span>

<span data-ttu-id="da5ee-2101">11 цифр и букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="da5ee-2102">Одна цифра или буква</span><span class="sxs-lookup"><span data-stu-id="da5ee-2102">A digit or letter</span></span> 
- <span data-ttu-id="da5ee-2103">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2103">Two digits</span></span> 
- <span data-ttu-id="da5ee-2104">Шесть цифр или букв</span><span class="sxs-lookup"><span data-stu-id="da5ee-2104">Six digits or letters</span></span> 
- <span data-ttu-id="da5ee-2105">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="da5ee-2105">A digit</span></span> 
- <span data-ttu-id="da5ee-2106">Одна цифра или буква</span><span class="sxs-lookup"><span data-stu-id="da5ee-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2107">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2107">Checksum</span></span>

<span data-ttu-id="da5ee-2108">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2109">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2109">Definition</span></span>

<span data-ttu-id="da5ee-2110">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2111">Функция Func_german_drivers_license находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2112">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="da5ee-2113">найдено ключевое слово из Keyword_german_drivers_license_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="da5ee-2114">найдено ключевое слово из Keyword_german_drivers_license_collaborative;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="da5ee-2115">найдено ключевое слово из Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="da5ee-2116">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2117">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="da5ee-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="da5ee-2119">фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2119">Führerschein</span></span>
- <span data-ttu-id="da5ee-2120">фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2120">Fuhrerschein</span></span>
- <span data-ttu-id="da5ee-2121">фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2121">Fuehrerschein</span></span>
- <span data-ttu-id="da5ee-2122">фüхрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="da5ee-2123">фухрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="da5ee-2124">фуехрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="da5ee-2125">Фüхрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="da5ee-2125">Führerschein-</span></span> 
- <span data-ttu-id="da5ee-2126">Фухрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="da5ee-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="da5ee-2127">Фуехрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="da5ee-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="da5ee-2128">фüхрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="da5ee-2129">фухрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="da5ee-2130">фуехрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="da5ee-2131">фüхрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="da5ee-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="da5ee-2132">фухрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="da5ee-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="da5ee-2133">фуехрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="da5ee-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="da5ee-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="da5ee-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="da5ee-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="da5ee-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="da5ee-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="da5ee-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="da5ee-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="da5ee-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="da5ee-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="da5ee-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="da5ee-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="da5ee-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="da5ee-2140">фüхрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="da5ee-2141">фухрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="da5ee-2142">фуехрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="da5ee-2143">фüхрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="da5ee-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="da5ee-2144">фухрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="da5ee-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="da5ee-2145">фуехрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="da5ee-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="da5ee-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="da5ee-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="da5ee-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="da5ee-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="da5ee-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="da5ee-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="da5ee-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="da5ee-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="da5ee-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="da5ee-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="da5ee-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="da5ee-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="da5ee-2152">DL</span><span class="sxs-lookup"><span data-stu-id="da5ee-2152">DL</span></span> 
- <span data-ttu-id="da5ee-2153">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="da5ee-2153">DLS</span></span>
- <span data-ttu-id="da5ee-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-2154">Driv Lic</span></span> 
- <span data-ttu-id="da5ee-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="da5ee-2155">Driv Licen</span></span> 
- <span data-ttu-id="da5ee-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="da5ee-2156">Driv License</span></span>
- <span data-ttu-id="da5ee-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2157">Driv Licenses</span></span> 
- <span data-ttu-id="da5ee-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-2158">Driv Licence</span></span> 
- <span data-ttu-id="da5ee-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-2159">Driv Licences</span></span> 
- <span data-ttu-id="da5ee-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-2160">Driv Lic</span></span> 
- <span data-ttu-id="da5ee-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="da5ee-2161">Driver Licen</span></span> 
- <span data-ttu-id="da5ee-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="da5ee-2162">Driver License</span></span> 
- <span data-ttu-id="da5ee-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2163">Driver Licenses</span></span> 
- <span data-ttu-id="da5ee-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-2164">Driver Licence</span></span> 
- <span data-ttu-id="da5ee-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-2165">Driver Licences</span></span> 
- <span data-ttu-id="da5ee-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-2166">Drivers Lic</span></span> 
- <span data-ttu-id="da5ee-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="da5ee-2167">Drivers Licen</span></span> 
- <span data-ttu-id="da5ee-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="da5ee-2168">Drivers License</span></span> 
- <span data-ttu-id="da5ee-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="da5ee-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-2170">Drivers Licence</span></span> 
- <span data-ttu-id="da5ee-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-2171">Drivers Licences</span></span> 
- <span data-ttu-id="da5ee-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-2172">Driver's Lic</span></span> 
- <span data-ttu-id="da5ee-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="da5ee-2173">Driver's Licen</span></span> 
- <span data-ttu-id="da5ee-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="da5ee-2174">Driver's License</span></span> 
- <span data-ttu-id="da5ee-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="da5ee-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-2176">Driver's Licence</span></span> 
- <span data-ttu-id="da5ee-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-2177">Driver's Licences</span></span> 
- <span data-ttu-id="da5ee-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-2178">Driving Lic</span></span> 
- <span data-ttu-id="da5ee-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="da5ee-2179">Driving Licen</span></span> 
- <span data-ttu-id="da5ee-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="da5ee-2180">Driving License</span></span> 
- <span data-ttu-id="da5ee-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2181">Driving Licenses</span></span> 
- <span data-ttu-id="da5ee-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-2182">Driving Licence</span></span> 
- <span data-ttu-id="da5ee-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="da5ee-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="da5ee-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="da5ee-2185">НР — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="da5ee-2186">НР — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="da5ee-2187">НР — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="da5ee-2188">Нет — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2188">No-Führerschein</span></span> 
- <span data-ttu-id="da5ee-2189">Нет — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="da5ee-2190">Нет — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="da5ee-2191">N — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2191">N-Führerschein</span></span> 
- <span data-ttu-id="da5ee-2192">N — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="da5ee-2193">N — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="da5ee-2194">НР — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="da5ee-2195">НР — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="da5ee-2196">НР — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="da5ee-2197">Нет — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2197">No-Führerschein</span></span> 
- <span data-ttu-id="da5ee-2198">Нет — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="da5ee-2199">Нет — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="da5ee-2200">N — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2200">N-Führerschein</span></span> 
- <span data-ttu-id="da5ee-2201">N — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="da5ee-2202">N — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="da5ee-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="da5ee-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="da5ee-2204">аусстеллунгсдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="da5ee-2205">аусстеллунгсорт</span><span class="sxs-lookup"><span data-stu-id="da5ee-2205">ausstellungsort</span></span>
- <span data-ttu-id="da5ee-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="da5ee-2206">ausstellende behöde</span></span>
- <span data-ttu-id="da5ee-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="da5ee-2207">ausstellende behorde</span></span>
- <span data-ttu-id="da5ee-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="da5ee-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="da5ee-2209">Номер паспорта гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2210">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2210">Format</span></span>

<span data-ttu-id="da5ee-2211">10 цифр или букв.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2212">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2212">Pattern</span></span>

<span data-ttu-id="da5ee-2213">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="da5ee-2214">Первый символ — цифра или буква из следующего набора: C, F, G, H, J, K.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="da5ee-2215">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2215">Three digits</span></span> 
- <span data-ttu-id="da5ee-2216">Пять цифр или букв из следующего набора: C, F-H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="da5ee-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="da5ee-2217">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="da5ee-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2218">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2218">Checksum</span></span>

<span data-ttu-id="da5ee-2219">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2220">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2220">Definition</span></span>

<span data-ttu-id="da5ee-2221">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2222">функция Func_german_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2223">находится любое ключевое слово из пяти соответствующих списков;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="da5ee-2224">контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2224">The checksum passes.</span></span>

<span data-ttu-id="da5ee-2225">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2226">функция Func_german_passport_data находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2227">находится любое ключевое слово из пяти соответствующих списков;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="da5ee-2228">контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2229">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="da5ee-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="da5ee-2231">реисепасс</span><span class="sxs-lookup"><span data-stu-id="da5ee-2231">reisepass</span></span>
- <span data-ttu-id="da5ee-2232">реисепассе</span><span class="sxs-lookup"><span data-stu-id="da5ee-2232">reisepasse</span></span>
- <span data-ttu-id="da5ee-2233">реисепасснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2233">reisepassnummer</span></span>
- <span data-ttu-id="da5ee-2234">службу</span><span class="sxs-lookup"><span data-stu-id="da5ee-2234">passport</span></span>
- <span data-ttu-id="da5ee-2235">паспорты</span><span class="sxs-lookup"><span data-stu-id="da5ee-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="da5ee-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="da5ee-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="da5ee-2237">жебуртсдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-2237">geburtsdatum</span></span>
- <span data-ttu-id="da5ee-2238">аусстеллунгсдатум</span><span class="sxs-lookup"><span data-stu-id="da5ee-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="da5ee-2239">аусстеллунгсорт</span><span class="sxs-lookup"><span data-stu-id="da5ee-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="da5ee-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="da5ee-2241">No — Реисепасс НР — Реисепасс</span><span class="sxs-lookup"><span data-stu-id="da5ee-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="da5ee-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="da5ee-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="da5ee-2243">Реисепасс — НР</span><span class="sxs-lookup"><span data-stu-id="da5ee-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="da5ee-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="da5ee-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="da5ee-2245">бнатионалит. t</span><span class="sxs-lookup"><span data-stu-id="da5ee-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="da5ee-2246">Номер идентификационной карты гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2247">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2247">Format</span></span>

<span data-ttu-id="da5ee-2248">С 1 ноября 2010: девять букв и цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="da5ee-2249">От 1 апреля 1987 до 31 октября 2010:10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2250">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2250">Pattern</span></span>

<span data-ttu-id="da5ee-2251">С 1 ноября 2010 г.:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="da5ee-2252">одна буква (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-2253">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2253">Eight digits</span></span>

<span data-ttu-id="da5ee-2254">От 1 апреля 1987 до 31 октября 2010:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="da5ee-2255">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2256">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2256">Checksum</span></span>

<span data-ttu-id="da5ee-2257">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2258">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2258">Definition</span></span>

<span data-ttu-id="da5ee-2259">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2260">регулярное выражение Regex_germany_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2261">находится ключевое слово из Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2262">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="da5ee-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="da5ee-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2264">Identity Card</span></span>
- <span data-ttu-id="da5ee-2265">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="da5ee-2265">ID</span></span>
- <span data-ttu-id="da5ee-2266">Процедура</span><span class="sxs-lookup"><span data-stu-id="da5ee-2266">Identification</span></span>
- <span data-ttu-id="da5ee-2267">персоналаусвеис</span><span class="sxs-lookup"><span data-stu-id="da5ee-2267">Personalausweis</span></span>
- <span data-ttu-id="da5ee-2268">идентифизиерунгснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="da5ee-2269">аусвеис</span><span class="sxs-lookup"><span data-stu-id="da5ee-2269">Ausweis</span></span>
- <span data-ttu-id="da5ee-2270">идентификатион</span><span class="sxs-lookup"><span data-stu-id="da5ee-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="da5ee-2271">Номер внутреннего удостоверения личности для Греции</span><span class="sxs-lookup"><span data-stu-id="da5ee-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2272">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2272">Format</span></span>

<span data-ttu-id="da5ee-2273">Сочетание 7–8 букв и чисел, а также тире.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2274">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2274">Pattern</span></span>

<span data-ttu-id="da5ee-2275">Семь букв и чисел (старый формат):</span><span class="sxs-lookup"><span data-stu-id="da5ee-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="da5ee-2276">одна буква (любая буква греческого алфавита);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="da5ee-2277">тире;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2277">A dash</span></span> 
- <span data-ttu-id="da5ee-2278">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2278">Six digits</span></span>

<span data-ttu-id="da5ee-2279">Восемь букв и чисел (новый формат):</span><span class="sxs-lookup"><span data-stu-id="da5ee-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="da5ee-2280">две буквы, которые в прописном виде есть как в греческом, так и латинском алфавите (ABEZHIKMNOPTYX);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="da5ee-2281">тире;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2281">A dash</span></span> 
- <span data-ttu-id="da5ee-2282">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2283">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2283">Checksum</span></span>

<span data-ttu-id="da5ee-2284">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2285">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2285">Definition</span></span>

<span data-ttu-id="da5ee-2286">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2287">регулярное выражение Regex_greece_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2288">находится ключевое слово из Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2289">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="da5ee-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="da5ee-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2291">Greek identity Card</span></span>
- <span data-ttu-id="da5ee-2292">таутотита</span><span class="sxs-lookup"><span data-stu-id="da5ee-2292">Tautotita</span></span>
- <span data-ttu-id="da5ee-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="da5ee-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="da5ee-2294">ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="da5ee-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="da5ee-2295">Номер удостоверения личности для Гонконга (HKID)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2296">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2296">Format</span></span>

<span data-ttu-id="da5ee-2297">Сочетание 8–9 букв и чисел, а также необязательные скобки вокруг последнего символа.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2298">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2298">Pattern</span></span>

<span data-ttu-id="da5ee-2299">Сочетание 8–9 букв:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="da5ee-2300">1–2 буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-2301">шесть цифр; </span><span class="sxs-lookup"><span data-stu-id="da5ee-2301">Six digits</span></span> 
- <span data-ttu-id="da5ee-2302">последний символ (любая цифра или буква "A") является проверочной цифрой и заключен в скобки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2303">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2303">Checksum</span></span>

<span data-ttu-id="da5ee-2304">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2305">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2305">Definition</span></span>

<span data-ttu-id="da5ee-2306">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2307">функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2308">находится ключевое слово из Keyword_hong_kong_id_card;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="da5ee-2309">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2309">The checksum passes.</span></span>

<span data-ttu-id="da5ee-2310">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2311">функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2312">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2313">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="da5ee-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="da5ee-2315">идентификационная карточка Гонконг</span><span class="sxs-lookup"><span data-stu-id="da5ee-2315">hong kong identity card</span></span>
- <span data-ttu-id="da5ee-2316">хкидк</span><span class="sxs-lookup"><span data-stu-id="da5ee-2316">HKIDC</span></span>
- <span data-ttu-id="da5ee-2317">id card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2317">id card</span></span>
- <span data-ttu-id="da5ee-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2318">identity card</span></span>
- <span data-ttu-id="da5ee-2319">идентификационная карточка HK</span><span class="sxs-lookup"><span data-stu-id="da5ee-2319">hk identity card</span></span>
- <span data-ttu-id="da5ee-2320">Идентификатор Гонконг</span><span class="sxs-lookup"><span data-stu-id="da5ee-2320">hong kong id</span></span>
- <span data-ttu-id="da5ee-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2321">香港身份證</span></span>
- <span data-ttu-id="da5ee-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="da5ee-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2323">身份證</span></span>
- <span data-ttu-id="da5ee-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2324">身份証</span></span>
- <span data-ttu-id="da5ee-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2325">身分證</span></span>
- <span data-ttu-id="da5ee-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2326">身分証</span></span>
- <span data-ttu-id="da5ee-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2327">香港身份証</span></span>
- <span data-ttu-id="da5ee-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2328">香港身分證</span></span>
- <span data-ttu-id="da5ee-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2329">香港身分証</span></span>
- <span data-ttu-id="da5ee-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2330">香港身份證</span></span>
- <span data-ttu-id="da5ee-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2331">香港居民身份證</span></span>
- <span data-ttu-id="da5ee-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2332">香港居民身份証</span></span>
- <span data-ttu-id="da5ee-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2333">香港居民身分證</span></span>
- <span data-ttu-id="da5ee-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2334">香港居民身分証</span></span>
- <span data-ttu-id="da5ee-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="da5ee-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="da5ee-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="da5ee-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="da5ee-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="da5ee-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="da5ee-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="da5ee-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="da5ee-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="da5ee-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="da5ee-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="da5ee-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="da5ee-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="da5ee-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="da5ee-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="da5ee-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="da5ee-2351">Идентификационный номер налогоплательщика для Индии (PAN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2352">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2352">Format</span></span>

<span data-ttu-id="da5ee-2353">10 букв или цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2354">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2354">Pattern</span></span>

<span data-ttu-id="da5ee-2355">10 букв или цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2355">10 letters or digits:</span></span>
- <span data-ttu-id="da5ee-2356">пять букв (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-2357">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2357">Four digits</span></span> 
- <span data-ttu-id="da5ee-2358">буква, которая является алфавитным проверочным символом.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2359">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2359">Checksum</span></span>

<span data-ttu-id="da5ee-2360">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2361">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2361">Definition</span></span>

<span data-ttu-id="da5ee-2362">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2363">регулярное выражение Regex_india_permanent_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2364">находится ключевое слово из Keyword_india_permanent_account_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="da5ee-2365">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2366">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="da5ee-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="da5ee-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="da5ee-2369">ПАНОРАМИРОВАНИЕ</span><span class="sxs-lookup"><span data-stu-id="da5ee-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="da5ee-2370">Индивидуальный идентификационный номер (Aadhaar) для Индии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2371">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2371">Format</span></span>

<span data-ttu-id="da5ee-2372">12 цифр, содержащих необязательные пробелы или тире.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2373">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2373">Pattern</span></span>

<span data-ttu-id="da5ee-2374">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2374">12 digits:</span></span>
- <span data-ttu-id="da5ee-2375">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2375">Four digits</span></span> 
- <span data-ttu-id="da5ee-2376">необязательный пробел или тире;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2376">An optional space or dash</span></span> 
- <span data-ttu-id="da5ee-2377">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2377">Four digits</span></span> 
- <span data-ttu-id="da5ee-2378">необязательный пробел или тире;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2378">An optional space or dash</span></span> 
- <span data-ttu-id="da5ee-2379">последняя цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2380">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2380">Checksum</span></span>

<span data-ttu-id="da5ee-2381">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2382">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2382">Definition</span></span>

<span data-ttu-id="da5ee-2383">Политика защиты от потери данных — 85% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_india_aadhaar находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="da5ee-2384">находится ключевое слово из Keyword_india_aadhar;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="da5ee-2385">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2385">The checksum passes.</span></span>
<span data-ttu-id="da5ee-2386">Политика защиты от потери данных — 75% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_india_aadhaar находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="da5ee-2387">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="da5ee-2388">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="da5ee-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="da5ee-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="da5ee-2390">аадхар</span><span class="sxs-lookup"><span data-stu-id="da5ee-2390">Aadhar</span></span>
- <span data-ttu-id="da5ee-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="da5ee-2391">Aadhaar</span></span>
- <span data-ttu-id="da5ee-2392">UID</span><span class="sxs-lookup"><span data-stu-id="da5ee-2392">UID</span></span>
- <span data-ttu-id="da5ee-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="da5ee-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="da5ee-2394">Номер удостоверения личности (KTP) для Индонезии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2395">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2395">Format</span></span>

<span data-ttu-id="da5ee-2396">16 цифр, содержащих необязательные точки.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2397">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2397">Pattern</span></span>

<span data-ttu-id="da5ee-2398">16 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2398">16 digits:</span></span>
- <span data-ttu-id="da5ee-2399">две цифры (код провинции);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2399">Two-digit province code</span></span> 
- <span data-ttu-id="da5ee-2400">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2400">A period (optional)</span></span> 
- <span data-ttu-id="da5ee-2401">две цифры (код округа или города);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="da5ee-2402">две цифры (код района);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="da5ee-2403">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2403">A period (optional)</span></span> 
- <span data-ttu-id="da5ee-2404">шесть цифр в формате ДДММГГ (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="da5ee-2405">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2405">A period (optional)</span></span> 
- <span data-ttu-id="da5ee-2406">четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2407">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2407">Checksum</span></span>

<span data-ttu-id="da5ee-2408">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2409">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2409">Definition</span></span>

<span data-ttu-id="da5ee-2410">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2411">регулярное выражение Regex_indonesia_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2412">находится ключевое слово из Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="da5ee-2413">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2414">регулярное выражение Regex_indonesia_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2415">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="da5ee-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="da5ee-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="da5ee-2417">KTP</span></span>
- <span data-ttu-id="da5ee-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="da5ee-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="da5ee-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="da5ee-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="da5ee-2420">Международный номер банковского счета (IBAN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2421">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2421">Format</span></span>

<span data-ttu-id="da5ee-2422">Код страны (две буквы), а также проверочные цифры (две) и номер bban (до 30 символов)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2423">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2423">Pattern</span></span>

<span data-ttu-id="da5ee-2424">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="da5ee-2425">Двухбуквенный код страны</span><span class="sxs-lookup"><span data-stu-id="da5ee-2425">Two-letter country code</span></span>
- <span data-ttu-id="da5ee-2426">Две проверочные цифры (после которых может следовать пробел) </span><span class="sxs-lookup"><span data-stu-id="da5ee-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="da5ee-2427">1–7 групп из четырех букв или цифр (могут разделяться пробелами)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="da5ee-2428">1–3 буквы или цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2428">1-3 letters or digits</span></span>

<span data-ttu-id="da5ee-p135">Формат для названия каждой из стран немного отличается. Тип конфиденциальной информации IBAN применяется к следующим 60 странам:</span><span class="sxs-lookup"><span data-stu-id="da5ee-p135">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="da5ee-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="da5ee-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2432">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2432">Checksum</span></span>

<span data-ttu-id="da5ee-2433">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2434">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2434">Definition</span></span>

<span data-ttu-id="da5ee-2435">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2436">функция Func_iban находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2437">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2438">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2438">Keywords</span></span>

<span data-ttu-id="da5ee-2439">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="da5ee-2440">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="da5ee-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2441">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="da5ee-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="da5ee-2442">IPv4:</span></span>
<span data-ttu-id="da5ee-2443">Сложный шаблон, ответственный за форматированные (с точками) и неформатированные (без точек) версии IPv4-адресов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="da5ee-2444">Поддерживающ</span><span class="sxs-lookup"><span data-stu-id="da5ee-2444">IPv6:</span></span>
<span data-ttu-id="da5ee-2445"> Сложный шаблон, ответственный за форматированные номера IPv6 (вместе с двоеточиями).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2446">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2447">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2447">Checksum</span></span>

<span data-ttu-id="da5ee-2448">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2449">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2449">Definition</span></span>

<span data-ttu-id="da5ee-2450">В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2451">регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2452">ни одно ключевое слово из Keyword_ipaddress не находится.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="da5ee-2453">В случае с протоколом IPv4 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2454">регулярное выражение Regex_ipv4_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2455">находится ключевое слово из Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="da5ee-2456">В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2457">регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2458">ни одно ключевое слово из Keyword_ipaddress не находится.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2459">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="da5ee-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="da5ee-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="da5ee-2461">IP (ключевое слово с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="da5ee-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="da5ee-2462">ip address</span></span> 
- <span data-ttu-id="da5ee-2463">ip addresses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2463">ip addresses</span></span>
- <span data-ttu-id="da5ee-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="da5ee-2464">internet protocol</span></span>
- <span data-ttu-id="da5ee-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="da5ee-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="da5ee-2466">Международная классификация Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2467">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2467">Format</span></span>

<span data-ttu-id="da5ee-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="da5ee-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2469">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2469">Pattern</span></span>

<span data-ttu-id="da5ee-2470">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="da5ee-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2471">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2471">Checksum</span></span>

<span data-ttu-id="da5ee-2472">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2473">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2473">Definition</span></span>

<span data-ttu-id="da5ee-2474">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2475">Найдено ключевое слово из Dictionary_icd_10_updated.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="da5ee-2476">Найдено ключевое слово из Dictionary_icd_10_codes.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="da5ee-2477">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2478">Найдено ключевое слово из Dictionary_icd_10_ "Обновлено".</span><span class="sxs-lookup"><span data-stu-id="da5ee-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="da5ee-2479">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2479">Keywords</span></span>

<span data-ttu-id="da5ee-2480">Любой термин из словаря Dictionary_icd_10_updated ключевых слов, основанный на [международной классификации Diseases, десятой версии, Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="da5ee-2481">Этот тип ищет только термин, а не коды страхования.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="da5ee-2482">Любой термин из словаря Dictionary_icd_10_codes ключевых слов, основанный на [международной классификации Diseases, десятой версии, Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="da5ee-2483">Этот тип ищет только страховые коды, а не описание.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="da5ee-2484">Международная классификация Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2485">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2485">Format</span></span>

<span data-ttu-id="da5ee-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="da5ee-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2487">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2487">Pattern</span></span>

<span data-ttu-id="da5ee-2488">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="da5ee-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2489">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2489">Checksum</span></span>

<span data-ttu-id="da5ee-2490">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2491">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2491">Definition</span></span>

<span data-ttu-id="da5ee-2492">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2493">Найдено ключевое слово из Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="da5ee-2494">Найдено ключевое слово из Dictionary_icd_9_codes.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="da5ee-2495">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2496">Найдено ключевое слово из Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2497">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2497">Keywords</span></span>

<span data-ttu-id="da5ee-2498">Любой термин из словаря Dictionary_icd_9_updated ключевых слов, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="da5ee-2499">Этот тип ищет только термин, а не коды страхования.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="da5ee-2500">Любой термин из словаря Dictionary_icd_9_codes ключевых слов, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="da5ee-2501">Этот тип ищет только страховые коды, а не описание.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="da5ee-2502">Индивидуальный социальный номер (PPS) для Ирландии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2503">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2503">Format</span></span>

<span data-ttu-id="da5ee-2504">Старый формат (до 31 декабря 2012):</span><span class="sxs-lookup"><span data-stu-id="da5ee-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="da5ee-2505">семь цифр, за которыми следуют 1–2 буквы. </span><span class="sxs-lookup"><span data-stu-id="da5ee-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="da5ee-2506">Новый формат (1 января 2013 и после):</span><span class="sxs-lookup"><span data-stu-id="da5ee-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="da5ee-2507">семь цифр, за которыми следуют две буквы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2508">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2508">Pattern</span></span>

<span data-ttu-id="da5ee-2509">Старый формат (до 31 декабря 2012):</span><span class="sxs-lookup"><span data-stu-id="da5ee-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="da5ee-2510">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2510">Seven digits</span></span> 
- <span data-ttu-id="da5ee-2511">1–2 буквы (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="da5ee-2512">Новый формат (1 января 2013 и после):</span><span class="sxs-lookup"><span data-stu-id="da5ee-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="da5ee-2513">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2513">Seven digits</span></span> 
- <span data-ttu-id="da5ee-2514">буква (без учета регистра), которая является алфавитным проверочным символом;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="da5ee-2515">буква "A" или "H" (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="da5ee-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2516">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2516">Checksum</span></span>

<span data-ttu-id="da5ee-2517">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2518">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2518">Definition</span></span>

<span data-ttu-id="da5ee-2519">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2520">Функция Func_ireland_pps находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2521">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2521">One of the following is true:</span></span>
    - <span data-ttu-id="da5ee-2522">найдено ключевое слово из Keyword_ireland_pps;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="da5ee-2523">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-2524">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2524">The checksum passes.</span></span>

<span data-ttu-id="da5ee-2525">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2526">функция Func_ireland_pps находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2527">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2528">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="da5ee-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="da5ee-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="da5ee-2530">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="da5ee-2531">PPS Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2531">PPS Number</span></span> 
- <span data-ttu-id="da5ee-2532">PPS Num</span><span class="sxs-lookup"><span data-stu-id="da5ee-2532">PPS Num</span></span> 
- <span data-ttu-id="da5ee-2533">PPS No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2533">PPS No.</span></span> 
- <span data-ttu-id="da5ee-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2534">PPS #</span></span> 
- <span data-ttu-id="da5ee-2535">PPS #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2535">PPS#</span></span> 
- <span data-ttu-id="da5ee-2536">ппсн</span><span class="sxs-lookup"><span data-stu-id="da5ee-2536">PPSN</span></span> 
- <span data-ttu-id="da5ee-2537">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2537">Public Services Card</span></span> 
- <span data-ttu-id="da5ee-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="da5ee-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="da5ee-2539">Уимх.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2539">Uimh.</span></span> <span data-ttu-id="da5ee-2540">НАСТРОЕН</span><span class="sxs-lookup"><span data-stu-id="da5ee-2540">PSP</span></span> 
- <span data-ttu-id="da5ee-2541">НАСТРОЕН</span><span class="sxs-lookup"><span data-stu-id="da5ee-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="da5ee-2542">Номер банковского счета для Израиля</span><span class="sxs-lookup"><span data-stu-id="da5ee-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2543">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2543">Format</span></span>

<span data-ttu-id="da5ee-2544">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2545">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2545">Pattern</span></span>

<span data-ttu-id="da5ee-2546">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="da5ee-2546">Formatted:</span></span>
- <span data-ttu-id="da5ee-2547">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2547">Two digits</span></span> 
- <span data-ttu-id="da5ee-2548">Тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-2548">A dash</span></span> 
- <span data-ttu-id="da5ee-2549">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2549">Three digits</span></span> 
- <span data-ttu-id="da5ee-2550">Тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-2550">A dash</span></span> 
- <span data-ttu-id="da5ee-2551">Восемь цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2551">Eight digits</span></span>

<span data-ttu-id="da5ee-2552">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="da5ee-2552">Unformatted:</span></span>
- <span data-ttu-id="da5ee-2553">	13 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2554">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2554">Checksum</span></span>

<span data-ttu-id="da5ee-2555">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2556">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2556">Definition</span></span>

<span data-ttu-id="da5ee-2557">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2558">регулярное выражение Regex_israel_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2559">находится ключевое слово из Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2560">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="da5ee-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="da5ee-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2562">Bank Account Number</span></span> 
- <span data-ttu-id="da5ee-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-2563">Bank Account</span></span> 
- <span data-ttu-id="da5ee-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2564">Account Number</span></span> 
- <span data-ttu-id="da5ee-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="da5ee-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="da5ee-2566">Национальный идентификатор для Израиля</span><span class="sxs-lookup"><span data-stu-id="da5ee-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2567">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2567">Format</span></span>

<span data-ttu-id="da5ee-2568">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2569">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2569">Pattern</span></span>

<span data-ttu-id="da5ee-2570">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2571">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2571">Checksum</span></span>

<span data-ttu-id="da5ee-2572">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2573">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2573">Definition</span></span>

<span data-ttu-id="da5ee-2574">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2575">функция Func_israeli_national_id_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2576">находится ключевое слово из Keyword_Israel_National_ID;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="da5ee-2577">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2578">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="da5ee-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="da5ee-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="da5ee-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="da5ee-2580">מספר זהות</span></span> 
- <span data-ttu-id="da5ee-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="da5ee-2582">Номер водительского удостоверения для Италии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2583">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2583">Format</span></span>

<span data-ttu-id="da5ee-2584">Сочетание из 10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2585">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2585">Pattern</span></span>

- <span data-ttu-id="da5ee-2586">Сочетание 10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="da5ee-2587">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-2588">Буква "A" или "V" (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-2589">Семь букв (без учета регистра), цифр или символов подчеркивания</span><span class="sxs-lookup"><span data-stu-id="da5ee-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="da5ee-2590">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2591">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2591">Checksum</span></span>

<span data-ttu-id="da5ee-2592">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2593">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2593">Definition</span></span>

<span data-ttu-id="da5ee-2594">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2595">регулярное выражение Regex_italy_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2596">находится ключевое слово из Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2597">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="da5ee-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="da5ee-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="da5ee-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="da5ee-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="da5ee-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="da5ee-2601">Номер банковского счета для Японии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2602">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2602">Format</span></span>

<span data-ttu-id="da5ee-2603">Семь или восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2604">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2604">Pattern</span></span>

<span data-ttu-id="da5ee-2605">Номер банковского счета:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2605">Bank account number:</span></span>
- <span data-ttu-id="da5ee-2606">семь или восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2606">Seven or eight digits</span></span>
- <span data-ttu-id="da5ee-2607">Код филиала для банковского счета.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2607">Bank account branch code:</span></span>
- <span data-ttu-id="da5ee-2608">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2608">Four digits</span></span> 
- <span data-ttu-id="da5ee-2609">Пробел или тире (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="da5ee-2610">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2610">Three digits</span></span>

<span data-ttu-id="da5ee-2611">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2611">Checksum</span></span>

<span data-ttu-id="da5ee-2612">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2613">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2613">Definition</span></span>

<span data-ttu-id="da5ee-2614">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2615">Функция Func_jp_bank_account находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2616">Находится ключевое слово из Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="da5ee-2617">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2617">One of the following is true:</span></span>
- <span data-ttu-id="da5ee-2618">функция Func_jp_bank_account_branch_code находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2619">найдено ключевое слово из Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="da5ee-2620">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2621">функция Func_jp_bank_account находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2622">находится ключевое слово из Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2623">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="da5ee-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="da5ee-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="da5ee-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2625">Checking Account Number</span></span> 
- <span data-ttu-id="da5ee-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-2626">Checking Account</span></span> 
- <span data-ttu-id="da5ee-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2627">Checking Account #</span></span> 
- <span data-ttu-id="da5ee-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="da5ee-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2629">Checking Acct #</span></span> 
- <span data-ttu-id="da5ee-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="da5ee-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2631">Checking Account No.</span></span> 
- <span data-ttu-id="da5ee-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2632">Bank Account Number</span></span> 
- <span data-ttu-id="da5ee-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-2633">Bank Account</span></span> 
- <span data-ttu-id="da5ee-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2634">Bank Account #</span></span> 
- <span data-ttu-id="da5ee-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="da5ee-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2636">Bank Acct #</span></span> 
- <span data-ttu-id="da5ee-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="da5ee-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2638">Bank Account No.</span></span> 
- <span data-ttu-id="da5ee-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2639">Savings Account Number</span></span> 
- <span data-ttu-id="da5ee-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-2640">Savings Account</span></span> 
- <span data-ttu-id="da5ee-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2641">Savings Account #</span></span> 
- <span data-ttu-id="da5ee-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="da5ee-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2643">Savings Acct #</span></span> 
- <span data-ttu-id="da5ee-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="da5ee-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2645">Savings Account No.</span></span> 
- <span data-ttu-id="da5ee-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2646">Debit Account Number</span></span> 
- <span data-ttu-id="da5ee-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-2647">Debit Account</span></span> 
- <span data-ttu-id="da5ee-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2648">Debit Account #</span></span> 
- <span data-ttu-id="da5ee-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="da5ee-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2650">Debit Acct #</span></span> 
- <span data-ttu-id="da5ee-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="da5ee-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2652">Debit Account No.</span></span> 
- <span data-ttu-id="da5ee-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="da5ee-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="da5ee-2654">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="da5ee-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="da5ee-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="da5ee-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="da5ee-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="da5ee-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="da5ee-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="da5ee-2657">口座番号の確認</span></span> 
- <span data-ttu-id="da5ee-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2658">銀行口座番号</span></span> 
- <span data-ttu-id="da5ee-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="da5ee-2659">銀行口座</span></span> 
- <span data-ttu-id="da5ee-2660">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2660">銀行口座＃</span></span> 
- <span data-ttu-id="da5ee-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="da5ee-2662">銀行のаккт #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="da5ee-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="da5ee-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="da5ee-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2664">銀行口座番号</span></span>
- <span data-ttu-id="da5ee-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="da5ee-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="da5ee-2666">預金口座</span></span> 
- <span data-ttu-id="da5ee-2667">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="da5ee-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="da5ee-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="da5ee-2669">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="da5ee-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="da5ee-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="da5ee-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="da5ee-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2673">口座番号</span></span> 
- <span data-ttu-id="da5ee-2674">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2674">口座番号＃</span></span> 
- <span data-ttu-id="da5ee-2675">デビットのаккт番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="da5ee-2676">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="da5ee-2677">デビットакктの番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="da5ee-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="da5ee-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="da5ee-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="da5ee-2680">отемачи</span><span class="sxs-lookup"><span data-stu-id="da5ee-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="da5ee-2681">Номер водительского удостоверения для Японии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2682">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2682">Format</span></span>

<span data-ttu-id="da5ee-2683">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2684">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2684">Pattern</span></span>

<span data-ttu-id="da5ee-2685">12 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2686">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2686">Checksum</span></span>

<span data-ttu-id="da5ee-2687">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2688">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2688">Definition</span></span>

<span data-ttu-id="da5ee-2689">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2690">функция Func_jp_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2691">находится ключевое слово из Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2692">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="da5ee-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="da5ee-2694">DL #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2694">dl#</span></span> 
- <span data-ttu-id="da5ee-2695">DL</span><span class="sxs-lookup"><span data-stu-id="da5ee-2695">DL＃</span></span> 
- <span data-ttu-id="da5ee-2696">библиотек #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2696">dls#</span></span> 
- <span data-ttu-id="da5ee-2697">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="da5ee-2697">DLS＃</span></span> 
- <span data-ttu-id="da5ee-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="da5ee-2698">driver license</span></span> 
- <span data-ttu-id="da5ee-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2699">driver licenses</span></span> 
- <span data-ttu-id="da5ee-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="da5ee-2700">drivers license</span></span> 
- <span data-ttu-id="da5ee-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="da5ee-2701">driver's license</span></span> 
- <span data-ttu-id="da5ee-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2702">drivers licenses</span></span> 
- <span data-ttu-id="da5ee-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-2703">driver's licenses</span></span> 
- <span data-ttu-id="da5ee-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-2704">driving licence</span></span> 
- <span data-ttu-id="da5ee-2705">лик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2705">lic#</span></span> 
- <span data-ttu-id="da5ee-2706">Лик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2706">LIC＃</span></span> 
- <span data-ttu-id="da5ee-2707">ликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2707">lics#</span></span> 
- <span data-ttu-id="da5ee-2708">state id</span><span class="sxs-lookup"><span data-stu-id="da5ee-2708">state id</span></span> 
- <span data-ttu-id="da5ee-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="da5ee-2709">state identification</span></span> 
- <span data-ttu-id="da5ee-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2710">state identification number</span></span> 
- <span data-ttu-id="da5ee-2711">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2711">低所得国＃</span></span> 
- <span data-ttu-id="da5ee-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2712">免許証</span></span> 
- <span data-ttu-id="da5ee-2713">状態ид</span><span class="sxs-lookup"><span data-stu-id="da5ee-2713">状態ID</span></span>
- <span data-ttu-id="da5ee-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="da5ee-2714">状態の識別</span></span> 
- <span data-ttu-id="da5ee-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2715">状態の識別番号</span></span> 
- <span data-ttu-id="da5ee-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="da5ee-2716">運転免許</span></span> 
- <span data-ttu-id="da5ee-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="da5ee-2717">運転免許証</span></span> 
- <span data-ttu-id="da5ee-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="da5ee-2719">Номер паспорта гражданина Японии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2720">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2720">Format</span></span>

<span data-ttu-id="da5ee-2721">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2722">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2722">Pattern</span></span>

<span data-ttu-id="da5ee-2723">Две буквы (без учета регистра), за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2724">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2724">Checksum</span></span>

<span data-ttu-id="da5ee-2725">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2726">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2726">Definition</span></span>

<span data-ttu-id="da5ee-2727">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2728">функция Func_jp_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2729">находится ключевое слово из Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2730">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="da5ee-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="da5ee-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="da5ee-2732">パスポート</span></span> 
- <span data-ttu-id="da5ee-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2733">パスポート番号</span></span> 
- <span data-ttu-id="da5ee-2734">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="da5ee-2734">パスポートのNum</span></span> 
- <span data-ttu-id="da5ee-2735">パスポート #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="da5ee-2736">Номер регистрации резидента Японии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2737">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2737">Format</span></span>

<span data-ttu-id="da5ee-2738">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2739">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2739">Pattern</span></span>

<span data-ttu-id="da5ee-2740">11 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2741">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2741">Checksum</span></span>

<span data-ttu-id="da5ee-2742">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2743">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2743">Definition</span></span>

<span data-ttu-id="da5ee-2744">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2745">функция Func_jp_resident_registration_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2746">находится ключевое слово из Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2747">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="da5ee-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="da5ee-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2749">Resident Registration Number</span></span>
- <span data-ttu-id="da5ee-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2750">Resident Register Number</span></span> 
- <span data-ttu-id="da5ee-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="da5ee-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="da5ee-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2753">Resident Register No.</span></span> 
- <span data-ttu-id="da5ee-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="da5ee-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="da5ee-2756">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="da5ee-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="da5ee-2757">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="da5ee-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="da5ee-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="da5ee-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="da5ee-2760">Номер карты социального страхования для Японии (SIN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2761">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2761">Format</span></span>

<span data-ttu-id="da5ee-2762">7–12 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2763">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2763">Pattern</span></span>

<span data-ttu-id="da5ee-2764">7–12 цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2764">7-12 digits:</span></span>
- <span data-ttu-id="da5ee-2765">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-2765">Four digits</span></span> 
- <span data-ttu-id="da5ee-2766">Дефис (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="da5ee-2767">Шесть цифр или</span><span class="sxs-lookup"><span data-stu-id="da5ee-2767">Six digits OR</span></span>
- <span data-ttu-id="da5ee-2768">7–12 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2769">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2769">Checksum</span></span>

<span data-ttu-id="da5ee-2770">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2771">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2771">Definition</span></span>

<span data-ttu-id="da5ee-2772">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2773">функция Func_jp_sin находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2774">находится ключевое слово из Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="da5ee-2775">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2776">функция Func_jp_sin_pre_1997 находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2777">находится ключевое слово из Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2778">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="da5ee-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="da5ee-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="da5ee-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="da5ee-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="da5ee-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="da5ee-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="da5ee-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="da5ee-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="da5ee-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="da5ee-2785">Номер карточки для японского языка</span><span class="sxs-lookup"><span data-stu-id="da5ee-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2786">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2786">Format</span></span>

<span data-ttu-id="da5ee-2787">12 букв и цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2788">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2788">Pattern</span></span>

<span data-ttu-id="da5ee-2789">12 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2789">12 letters and digits:</span></span>
- <span data-ttu-id="da5ee-2790">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="da5ee-2791">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2791">Eight digits</span></span> 
- <span data-ttu-id="da5ee-2792">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2793">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2793">Checksum</span></span>

<span data-ttu-id="da5ee-2794">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2795">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2795">Definition</span></span>

<span data-ttu-id="da5ee-2796">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2797">Регулярное выражение Regex_jp_residence_card_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2798">Найдено ключевое слово из Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2799">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="da5ee-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="da5ee-2801">Номер карточки проживания</span><span class="sxs-lookup"><span data-stu-id="da5ee-2801">Residence card number</span></span>
- <span data-ttu-id="da5ee-2802">Номер карточки проживания</span><span class="sxs-lookup"><span data-stu-id="da5ee-2802">Residence card no</span></span>
- <span data-ttu-id="da5ee-2803">Карточка проживания #</span><span class="sxs-lookup"><span data-stu-id="da5ee-2803">Residence card #</span></span>
- <span data-ttu-id="da5ee-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="da5ee-2805">Номер удостоверения личности для Малайзии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2806">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2806">Format</span></span>

<span data-ttu-id="da5ee-2807">12 цифр, содержащих необязательные дефисы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2808">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2808">Pattern</span></span>

<span data-ttu-id="da5ee-2809">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2809">12 digits:</span></span>
- <span data-ttu-id="da5ee-2810">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="da5ee-2811">дефис (необязательно);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2811">A dash (optional)</span></span> 
- <span data-ttu-id="da5ee-2812">код места рождения из двух букв;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="da5ee-2813">дефис (необязательно);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2813">A dash (optional)</span></span> 
- <span data-ttu-id="da5ee-2814">три случайные цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2814">Three random digits</span></span> 
- <span data-ttu-id="da5ee-2815">код пола из одной цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2816">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2816">Checksum</span></span>

<span data-ttu-id="da5ee-2817">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2818">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2818">Definition</span></span>

<span data-ttu-id="da5ee-2819">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2820">регулярное выражение Regex_malaysia_id_card_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2821">находится ключевое слово из Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2822">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="da5ee-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="da5ee-2824">карточка цифрового приложения</span><span class="sxs-lookup"><span data-stu-id="da5ee-2824">digital application card</span></span>
- <span data-ttu-id="da5ee-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="da5ee-2825">i/c</span></span>
- <span data-ttu-id="da5ee-2826">i/c нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2826">i/c no</span></span>
- <span data-ttu-id="da5ee-2827">внутренних</span><span class="sxs-lookup"><span data-stu-id="da5ee-2827">ic</span></span>
- <span data-ttu-id="da5ee-2828">МФ нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2828">ic no</span></span>
- <span data-ttu-id="da5ee-2829">id card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2829">id card</span></span>
- <span data-ttu-id="da5ee-2830">идентификационная карточка</span><span class="sxs-lookup"><span data-stu-id="da5ee-2830">identification Card</span></span>
- <span data-ttu-id="da5ee-2831">identity card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2831">identity card</span></span>
- <span data-ttu-id="da5ee-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="da5ee-2832">k/p</span></span>
- <span data-ttu-id="da5ee-2833">k/p</span><span class="sxs-lookup"><span data-stu-id="da5ee-2833">k/p no</span></span>
- <span data-ttu-id="da5ee-2834">кад акуан Дири</span><span class="sxs-lookup"><span data-stu-id="da5ee-2834">kad akuan diri</span></span>
- <span data-ttu-id="da5ee-2835">кад апликаси Digital</span><span class="sxs-lookup"><span data-stu-id="da5ee-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="da5ee-2836">кад пенженалан Малайзии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="da5ee-2837">ключев</span><span class="sxs-lookup"><span data-stu-id="da5ee-2837">kp</span></span>
- <span data-ttu-id="da5ee-2838">ключевой номер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2838">kp no</span></span>
- <span data-ttu-id="da5ee-2839">микад</span><span class="sxs-lookup"><span data-stu-id="da5ee-2839">mykad</span></span>
- <span data-ttu-id="da5ee-2840">микас</span><span class="sxs-lookup"><span data-stu-id="da5ee-2840">mykas</span></span>
- <span data-ttu-id="da5ee-2841">микид</span><span class="sxs-lookup"><span data-stu-id="da5ee-2841">mykid</span></span>
- <span data-ttu-id="da5ee-2842">мипр</span><span class="sxs-lookup"><span data-stu-id="da5ee-2842">mypr</span></span>
- <span data-ttu-id="da5ee-2843">митентера</span><span class="sxs-lookup"><span data-stu-id="da5ee-2843">mytentera</span></span>
- <span data-ttu-id="da5ee-2844">идентификационная карточка Малайзии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2844">malaysia identity card</span></span>
- <span data-ttu-id="da5ee-2845">идентификационная карточка малайсиан</span><span class="sxs-lookup"><span data-stu-id="da5ee-2845">malaysian identity card</span></span>
- <span data-ttu-id="da5ee-2846">NRIC</span><span class="sxs-lookup"><span data-stu-id="da5ee-2846">nric</span></span>
- <span data-ttu-id="da5ee-2847">Личная идентификационная карточка</span><span class="sxs-lookup"><span data-stu-id="da5ee-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="da5ee-2848">Номер гражданской службы для Нидерландов (BSN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2849">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2849">Format</span></span>

<span data-ttu-id="da5ee-2850">8–9 цифр, содержащих необязательные пробелы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2851">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2851">Pattern</span></span>

<span data-ttu-id="da5ee-2852">8–9 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2852">8-9 digits:</span></span>
- <span data-ttu-id="da5ee-2853">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-2853">Three digits</span></span> 
- <span data-ttu-id="da5ee-2854">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="da5ee-2854">A space (optional)</span></span> 
- <span data-ttu-id="da5ee-2855">три цифры; </span><span class="sxs-lookup"><span data-stu-id="da5ee-2855">Three digits</span></span> 
- <span data-ttu-id="da5ee-2856">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="da5ee-2856">A space (optional)</span></span> 
- <span data-ttu-id="da5ee-2857">2–3 цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2858">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2858">Checksum</span></span>

<span data-ttu-id="da5ee-2859">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2860">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2860">Definition</span></span>

<span data-ttu-id="da5ee-2861">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2862">функция Func_netherlands_bsn находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2863">находится ключевое слово из Keyword_netherlands_bsn;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="da5ee-2864">функция Func_eu_date2 находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-2865">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2866">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="da5ee-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="da5ee-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="da5ee-2868">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2868">Citizen service number</span></span> 
- <span data-ttu-id="da5ee-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="da5ee-2869">BSN</span></span> 
- <span data-ttu-id="da5ee-2870">буржерсервиценуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="da5ee-2871">софинуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2871">Sofinummer</span></span> 
- <span data-ttu-id="da5ee-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="da5ee-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="da5ee-2873">персунснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="da5ee-2874">Номер министерства здравоохранения для Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2875">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2875">Format</span></span>

<span data-ttu-id="da5ee-2876">Три буквы, пробел (необязательно) и четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2877">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2877">Pattern</span></span>

<span data-ttu-id="da5ee-2878">Три буквы (без учета регистра), пробел (необязательно) из четырех цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2879">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2879">Checksum</span></span>

<span data-ttu-id="da5ee-2880">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2881">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2881">Definition</span></span>

<span data-ttu-id="da5ee-2882">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2883">функция Func_new_zealand_ministry_of_health_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2884">находится ключевое слово из Keyword_nz_terms;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="da5ee-2885">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2885">The checksum passes.</span></span>

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

<span data-ttu-id="da5ee-2886">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2886">Keywords</span></span>

<span data-ttu-id="da5ee-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="da5ee-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="da5ee-2888">нхи</span><span class="sxs-lookup"><span data-stu-id="da5ee-2888">NHI</span></span> 
- <span data-ttu-id="da5ee-2889">Новая Зеландия</span><span class="sxs-lookup"><span data-stu-id="da5ee-2889">New Zealand</span></span> 
- <span data-ttu-id="da5ee-2890">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2890">Health</span></span> 
- <span data-ttu-id="da5ee-2891">обращения</span><span class="sxs-lookup"><span data-stu-id="da5ee-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="da5ee-2892">Идентификационный номер для Норвегии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2893">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2893">Format</span></span>

<span data-ttu-id="da5ee-2894">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2895">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2895">Pattern</span></span>

<span data-ttu-id="da5ee-2896">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2896">11 digits:</span></span>
- <span data-ttu-id="da5ee-2897">шесть цифр в формате ДДММГГ (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="da5ee-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="da5ee-2898">индивидуальный номер из трех цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="da5ee-2899">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2900">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2900">Checksum</span></span>

<span data-ttu-id="da5ee-2901">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2902">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2902">Definition</span></span>

<span data-ttu-id="da5ee-2903">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2904">функция Func_norway_id_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2905">находится ключевое слово из Keyword_norway_id_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="da5ee-2906">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2906">The checksum passes.</span></span>
- <span data-ttu-id="da5ee-2907">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2908">функция Func_norway_id_numbe находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2909">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2910">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="da5ee-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="da5ee-2912">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2912">Personal identification number</span></span>
- <span data-ttu-id="da5ee-2913">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="da5ee-2914">ID Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2914">ID Number</span></span>
- <span data-ttu-id="da5ee-2915">Процедура</span><span class="sxs-lookup"><span data-stu-id="da5ee-2915">Identification</span></span>
- <span data-ttu-id="da5ee-2916">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2916">Personnummer</span></span>
- <span data-ttu-id="da5ee-2917">фøдселснуммер</span><span class="sxs-lookup"><span data-stu-id="da5ee-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="da5ee-2918">Единый многофункциональный идентификационный номер для Филиппин</span><span class="sxs-lookup"><span data-stu-id="da5ee-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2919">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2919">Format</span></span>

<span data-ttu-id="da5ee-2920">12 цифр, разделенных дефисами.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2921">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2921">Pattern</span></span>

<span data-ttu-id="da5ee-2922">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2922">12 digits:</span></span>
- <span data-ttu-id="da5ee-2923">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2923">Four digits</span></span> 
- <span data-ttu-id="da5ee-2924">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2924">A hyphen</span></span> 
- <span data-ttu-id="da5ee-2925">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2925">Seven digits</span></span> 
- <span data-ttu-id="da5ee-2926">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2926">A hyphen</span></span> 
- <span data-ttu-id="da5ee-2927">одна цифра.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2928">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2928">Checksum</span></span>

<span data-ttu-id="da5ee-2929">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2930">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2930">Definition</span></span>

<span data-ttu-id="da5ee-2931">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2932">регулярное выражение Regex_philippines_unified_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2933">находится ключевое слово из Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2934">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="da5ee-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="da5ee-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="da5ee-2936">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="da5ee-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="da5ee-2937">умид</span><span class="sxs-lookup"><span data-stu-id="da5ee-2937">UMID</span></span> 
- <span data-ttu-id="da5ee-2938">Identity Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-2938">Identity Card</span></span> 
- <span data-ttu-id="da5ee-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="da5ee-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="da5ee-2940">Номер удостоверения личности для Польши</span><span class="sxs-lookup"><span data-stu-id="da5ee-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2941">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2941">Format</span></span>

<span data-ttu-id="da5ee-2942">Три буквы и шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2943">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2943">Pattern</span></span>

<span data-ttu-id="da5ee-2944">Три буквы (без учета регистра), за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2945">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2945">Checksum</span></span>

<span data-ttu-id="da5ee-2946">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2947">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2947">Definition</span></span>

<span data-ttu-id="da5ee-2948">Политика защиты от потери данных — 75% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_polish_national_id находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="da5ee-2949">находится ключевое слово из Keyword_polish_national_id_passport_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="da5ee-2950">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2951">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="da5ee-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="da5ee-2953">Довóд особисти</span><span class="sxs-lookup"><span data-stu-id="da5ee-2953">Dowód osobisty</span></span>
- <span data-ttu-id="da5ee-2954">Нумер доводу особистего</span><span class="sxs-lookup"><span data-stu-id="da5ee-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="da5ee-2955">Назва i нумер доводу особистего</span><span class="sxs-lookup"><span data-stu-id="da5ee-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="da5ee-2956">Назва i НР доводу особистего</span><span class="sxs-lookup"><span data-stu-id="da5ee-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="da5ee-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="da5ee-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="da5ee-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="da5ee-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="da5ee-2959">Dow.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2959">dow.</span></span> <span data-ttu-id="da5ee-2960">совместим.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="da5ee-2961">Национальный идентификатор (PESEL), Польша</span><span class="sxs-lookup"><span data-stu-id="da5ee-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2962">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2962">Format</span></span>

<span data-ttu-id="da5ee-2963">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2964">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2964">Pattern</span></span>

<span data-ttu-id="da5ee-2965">11 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2966">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2966">Checksum</span></span>

<span data-ttu-id="da5ee-2967">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2968">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2968">Definition</span></span>

<span data-ttu-id="da5ee-2969">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2970">функция Func_pesel_identification_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2971">находится ключевое слово из Keyword_pesel_identification_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="da5ee-2972">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-2973">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="da5ee-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="da5ee-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="da5ee-2975">Nr PESEL</span></span>
- <span data-ttu-id="da5ee-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="da5ee-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="da5ee-2977">Номер паспорта для Польши</span><span class="sxs-lookup"><span data-stu-id="da5ee-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2978">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2978">Format</span></span>

<span data-ttu-id="da5ee-2979">Две буквы и семь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2980">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2980">Pattern</span></span>

<span data-ttu-id="da5ee-2981">Две буквы (без учета регистра), за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-2982">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-2982">Checksum</span></span>

<span data-ttu-id="da5ee-2983">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-2984">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-2984">Definition</span></span>

<span data-ttu-id="da5ee-2985">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-2986">функция Func_polish_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-2987">находится ключевое слово из Keyword_polish_national_id_passport_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="da5ee-2988">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-2989">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="da5ee-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="da5ee-2991">Нумер пасзпорту</span><span class="sxs-lookup"><span data-stu-id="da5ee-2991">Numer paszportu</span></span>
- <span data-ttu-id="da5ee-2992">НР.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2992">Nr.</span></span> <span data-ttu-id="da5ee-2993">пасзпорту</span><span class="sxs-lookup"><span data-stu-id="da5ee-2993">Paszportu</span></span>
- <span data-ttu-id="da5ee-2994">пасзпорт</span><span class="sxs-lookup"><span data-stu-id="da5ee-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="da5ee-2995">Номер карты гражданина Португалии</span><span class="sxs-lookup"><span data-stu-id="da5ee-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-2996">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-2996">Format</span></span>

<span data-ttu-id="da5ee-2997">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-2998">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-2998">Pattern</span></span>

<span data-ttu-id="da5ee-2999">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3000">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3000">Checksum</span></span>

<span data-ttu-id="da5ee-3001">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3002">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3002">Definition</span></span>

<span data-ttu-id="da5ee-3003">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3004">регулярное выражение Regex_portugal_citizen_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3005">находится ключевое слово из Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3006">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="da5ee-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="da5ee-3008">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3008">Citizen Card</span></span>
- <span data-ttu-id="da5ee-3009">National ID Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3009">National ID Card</span></span>
- <span data-ttu-id="da5ee-3010">CC</span><span class="sxs-lookup"><span data-stu-id="da5ee-3010">CC</span></span>
- <span data-ttu-id="da5ee-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="da5ee-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="da5ee-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="da5ee-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="da5ee-3013">Национальный идентификатор для Саудовской Аравии</span><span class="sxs-lookup"><span data-stu-id="da5ee-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3014">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3014">Format</span></span>

<span data-ttu-id="da5ee-3015">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3016">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3016">Pattern</span></span>

<span data-ttu-id="da5ee-3017">10 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3018">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3018">Checksum</span></span>

<span data-ttu-id="da5ee-3019">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3020">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3020">Definition</span></span>

<span data-ttu-id="da5ee-3021">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3022">регулярное выражение Regex_saudi_arabia_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3023">находится ключевое слово из Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3024">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="da5ee-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="da5ee-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="da5ee-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3026">Identification Card</span></span> 
- <span data-ttu-id="da5ee-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3027">I card number</span></span> 
- <span data-ttu-id="da5ee-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3028">ID number</span></span> 
- <span data-ttu-id="da5ee-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="da5ee-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="da5ee-3030">Номер внутреннего удостоверения личности гражданина Сингапура (NRIC)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3031">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3031">Format</span></span>

<span data-ttu-id="da5ee-3032">Девять букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3033">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3033">Pattern</span></span>

- <span data-ttu-id="da5ee-3034">Девять букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="da5ee-3035">буква "F", "G", "S" или "T" (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-3036">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3036">Seven digits</span></span> 
- <span data-ttu-id="da5ee-3037">алфавитный проверочный символ.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3038">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3038">Checksum</span></span>

<span data-ttu-id="da5ee-3039">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3040">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3040">Definition</span></span>

<span data-ttu-id="da5ee-3041">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3042">регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3043">находится ключевое слово из Keyword_singapore_nric;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="da5ee-3044">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3044">The checksum passes.</span></span>

<span data-ttu-id="da5ee-3045">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3046">регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3047">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3048">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="da5ee-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="da5ee-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="da5ee-3050">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="da5ee-3051">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3051">Identity Card Number</span></span> 
- <span data-ttu-id="da5ee-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="da5ee-3052">NRIC</span></span> 
- <span data-ttu-id="da5ee-3053">ВНУТРЕННИХ</span><span class="sxs-lookup"><span data-stu-id="da5ee-3053">IC</span></span> 
- <span data-ttu-id="da5ee-3054">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="da5ee-3055">ПРОЦЕНТ</span><span class="sxs-lookup"><span data-stu-id="da5ee-3055">FIN</span></span> 
- <span data-ttu-id="da5ee-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="da5ee-3056">身份证</span></span> 
- <span data-ttu-id="da5ee-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="da5ee-3058">Идентификационный номер для Южной Африки</span><span class="sxs-lookup"><span data-stu-id="da5ee-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3059">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3059">Format</span></span>

<span data-ttu-id="da5ee-3060">13 цифр, которые могут содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3061">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3061">Pattern</span></span>

<span data-ttu-id="da5ee-3062">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3062">13 digits:</span></span>
- <span data-ttu-id="da5ee-3063">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="da5ee-3064">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3064">Four digits</span></span> 
- <span data-ttu-id="da5ee-3065">индикатор гражданства в виде одной цифры;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="da5ee-3066">цифра "8" или "9";</span><span class="sxs-lookup"><span data-stu-id="da5ee-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="da5ee-3067">одна цифра (проверочная).</span><span class="sxs-lookup"><span data-stu-id="da5ee-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3068">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3068">Checksum</span></span>

<span data-ttu-id="da5ee-3069">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3070">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3070">Definition</span></span>

<span data-ttu-id="da5ee-3071">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3072">функция Func_south_africa_identification_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3073">находится ключевое слово из Keyword_south_africa_identification_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="da5ee-3074">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3075">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="da5ee-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="da5ee-3077">Identity card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3077">Identity card</span></span>
- <span data-ttu-id="da5ee-3078">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="da5ee-3078">ID</span></span>
- <span data-ttu-id="da5ee-3079">Процедура</span><span class="sxs-lookup"><span data-stu-id="da5ee-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="da5ee-3080">Регистрационный номер жителя Южной Кореи</span><span class="sxs-lookup"><span data-stu-id="da5ee-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3081">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3081">Format</span></span>

<span data-ttu-id="da5ee-3082">13 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3083">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3083">Pattern</span></span>

<span data-ttu-id="da5ee-3084">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3084">13 digits:</span></span>
- <span data-ttu-id="da5ee-3085">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="da5ee-3086">дефис;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3086">A hyphen</span></span> 
- <span data-ttu-id="da5ee-3087">одна цифра (определяет век и пол);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="da5ee-3088">код региона рождения из четырех цифр;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="da5ee-3089">одна цифра, используемая для разграничения людей, у которых предшествующие цифры совпадают;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="da5ee-3090">проверочная цифра.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3091">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3091">Checksum</span></span>

<span data-ttu-id="da5ee-3092">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3093">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3093">Definition</span></span>

<span data-ttu-id="da5ee-3094">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3095">функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3096">находится ключевое слово из Keyword_south_korea_resident_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="da5ee-3097">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3097">The checksum passes.</span></span>

<span data-ttu-id="da5ee-3098">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3099">функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3100">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3101">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="da5ee-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="da5ee-3103">National ID card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3103">National ID card</span></span> 
- <span data-ttu-id="da5ee-3104">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="da5ee-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="da5ee-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="da5ee-3106">ррн</span><span class="sxs-lookup"><span data-stu-id="da5ee-3106">RRN</span></span> 
- <span data-ttu-id="da5ee-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="da5ee-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="da5ee-3108">Страховой номер для Испании (SSN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3109">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3109">Format</span></span>

<span data-ttu-id="da5ee-3110">11–12 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3111">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3111">Pattern</span></span>

<span data-ttu-id="da5ee-3112">11-12 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3112">11-12 digits:</span></span>
- <span data-ttu-id="da5ee-3113">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3113">Two digits</span></span> 
- <span data-ttu-id="da5ee-3114">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="da5ee-3115">7–8 цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3115">7-8 digits</span></span> 
- <span data-ttu-id="da5ee-3116">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="da5ee-3117">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3118">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3118">Checksum</span></span>

<span data-ttu-id="da5ee-3119">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3120">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3120">Definition</span></span>

<span data-ttu-id="da5ee-3121">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3122">функция Func_spanish_social_security_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3123">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3124">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3124">Keywords</span></span>

<span data-ttu-id="da5ee-3125">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="da5ee-3126">Строка подключения к SQL Server</span><span class="sxs-lookup"><span data-stu-id="da5ee-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3127">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3127">Format</span></span>

<span data-ttu-id="da5ee-3128">Строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId", за которыми следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3129">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3129">Pattern</span></span>

- <span data-ttu-id="da5ee-3130">Строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId"</span><span class="sxs-lookup"><span data-stu-id="da5ee-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="da5ee-3131">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="da5ee-3132">Строка "Password" или "pwd", где "pwd" не предшествует буква нижнего регистра</span><span class="sxs-lookup"><span data-stu-id="da5ee-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="da5ee-3133">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3133">An equal sign (=)</span></span>
- <span data-ttu-id="da5ee-3134">Любой символ, не являющийся знаком доллара ($), символ процента (%), символ "больше" (>), символ "@", "символ" (@), знак кавычек ("), точка с запятой (;), левая фигурная скобка ([) или левая квадратная скобка ({)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="da5ee-3135">Любая комбинация 7-128 символов, не отделяющая точку с запятой (;), косая черта (/) или кавычки (").</span><span class="sxs-lookup"><span data-stu-id="da5ee-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="da5ee-3136">Точка с запятой (;) или кавычки (")</span><span class="sxs-lookup"><span data-stu-id="da5ee-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3137">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3137">Checksum</span></span>

<span data-ttu-id="da5ee-3138">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3139">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3139">Definition</span></span>

<span data-ttu-id="da5ee-3140">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3141">Регулярное выражение CEP_Regex_SQLServerConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3142">**Не** найдено ключевое слово из CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="da5ee-3143">Регулярное выражение CEP_PasswordPlaceHolder не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3144">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3145">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="da5ee-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="da5ee-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="da5ee-3147">Некоторые пароли</span><span class="sxs-lookup"><span data-stu-id="da5ee-3147">some-password</span></span>
- <span data-ttu-id="da5ee-3148">сомепассворд</span><span class="sxs-lookup"><span data-stu-id="da5ee-3148">somepassword</span></span>
- <span data-ttu-id="da5ee-3149">секретпассворд</span><span class="sxs-lookup"><span data-stu-id="da5ee-3149">secretPassword</span></span>
- <span data-ttu-id="da5ee-3150">примером</span><span class="sxs-lookup"><span data-stu-id="da5ee-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="da5ee-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="da5ee-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="da5ee-3152">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-3153">Пароль или pwd, за которым следует 0-2 пробелов, знак равенства (=), 0-2 пробелы и звездочка (\*)--или--</span><span class="sxs-lookup"><span data-stu-id="da5ee-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="da5ee-3154">Пароль или pwd, а затем:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="da5ee-3155">Знак равенства (=)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="da5ee-3156">Символ "меньше" (<)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="da5ee-3157">Любое сочетание 1-200 символов, которые являются буквами верхнего или нижнего регистра, цифрами, звездочкой (\*), дефисом (-), подчеркиванием (_) или символом пробела</span><span class="sxs-lookup"><span data-stu-id="da5ee-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="da5ee-3158">Символ "больше" (>)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="da5ee-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="da5ee-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="da5ee-3160">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="da5ee-3161">компанией</span><span class="sxs-lookup"><span data-stu-id="da5ee-3161">contoso</span></span>
- <span data-ttu-id="da5ee-3162">компании</span><span class="sxs-lookup"><span data-stu-id="da5ee-3162">fabrikam</span></span>
- <span data-ttu-id="da5ee-3163">базу</span><span class="sxs-lookup"><span data-stu-id="da5ee-3163">northwind</span></span>
- <span data-ttu-id="da5ee-3164">песочниц</span><span class="sxs-lookup"><span data-stu-id="da5ee-3164">sandbox</span></span>
- <span data-ttu-id="da5ee-3165">онебокс</span><span class="sxs-lookup"><span data-stu-id="da5ee-3165">onebox</span></span>
- <span data-ttu-id="da5ee-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="da5ee-3166">localhost</span></span>
- <span data-ttu-id="da5ee-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="da5ee-3167">127.0.0.1</span></span>
- <span data-ttu-id="da5ee-3168">тестакс.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-3169">порта</span><span class="sxs-lookup"><span data-stu-id="da5ee-3169">com</span></span>
- <span data-ttu-id="da5ee-3170">s — int.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="da5ee-3171">команде</span><span class="sxs-lookup"><span data-stu-id="da5ee-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="da5ee-3172">Национальный идентификатор для Швеции</span><span class="sxs-lookup"><span data-stu-id="da5ee-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3173">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3173">Format</span></span>

<span data-ttu-id="da5ee-3174">10 или 12 цифр и дополнительный разделитель.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3175">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3175">Pattern</span></span>

<span data-ttu-id="da5ee-3176">10 или 12 цифр с необязательным разделителем</span><span class="sxs-lookup"><span data-stu-id="da5ee-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="da5ee-3177">2–4 цифры (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="da5ee-3178">Шесть цифр в формате даты ГГММДД.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="da5ee-3179">Разделитель - или + (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="da5ee-3180">четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3181">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3181">Checksum</span></span>

<span data-ttu-id="da5ee-3182">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3183">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3183">Definition</span></span>

<span data-ttu-id="da5ee-3184">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3185">функция Func_swedish_national_identifier находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3186">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3187">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3187">Keywords</span></span>

<span data-ttu-id="da5ee-3188">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="da5ee-3189">Номер паспорта гражданина Швеции</span><span class="sxs-lookup"><span data-stu-id="da5ee-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3190">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3190">Format</span></span>

<span data-ttu-id="da5ee-3191">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3192">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3192">Pattern</span></span>

<span data-ttu-id="da5ee-3193">Восемь последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3194">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3194">Checksum</span></span>

<span data-ttu-id="da5ee-3195">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3196">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3196">Definition</span></span>

<span data-ttu-id="da5ee-3197">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3198">Регулярное выражение Regex_sweden_passport_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3199">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3199">One of the following is true:</span></span>
    - <span data-ttu-id="da5ee-3200">найдено ключевое слово из Keyword_passport;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="da5ee-3201">найдено ключевое слово из Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3202">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="da5ee-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="da5ee-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="da5ee-3204">visa requirements</span></span> 
- <span data-ttu-id="da5ee-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="da5ee-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="da5ee-3206">Schengen visas</span></span> 
- <span data-ttu-id="da5ee-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="da5ee-3207">Schengen visa</span></span> 
- <span data-ttu-id="da5ee-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="da5ee-3208">Visa Processing</span></span> 
- <span data-ttu-id="da5ee-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="da5ee-3209">Visa Type</span></span> 
- <span data-ttu-id="da5ee-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="da5ee-3210">Single Entry</span></span> 
- <span data-ttu-id="da5ee-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="da5ee-3211">Multiple Entry</span></span> 
- <span data-ttu-id="da5ee-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="da5ee-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="da5ee-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-3213">Keyword_passport</span></span>

- <span data-ttu-id="da5ee-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3214">Passport Number</span></span> 
- <span data-ttu-id="da5ee-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="da5ee-3215">Passport No</span></span> 
- <span data-ttu-id="da5ee-3216">Passport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3216">Passport #</span></span> 
- <span data-ttu-id="da5ee-3217">Службу #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3217">Passport#</span></span> 
- <span data-ttu-id="da5ee-3218">пасспортид</span><span class="sxs-lookup"><span data-stu-id="da5ee-3218">PassportID</span></span> 
- <span data-ttu-id="da5ee-3219">пасспортно</span><span class="sxs-lookup"><span data-stu-id="da5ee-3219">Passportno</span></span> 
- <span data-ttu-id="da5ee-3220">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-3220">passportnumber</span></span> 
- <span data-ttu-id="da5ee-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="da5ee-3221">パスポート</span></span> 
- <span data-ttu-id="da5ee-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-3222">パスポート番号</span></span> 
- <span data-ttu-id="da5ee-3223">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="da5ee-3223">パスポートのNum</span></span> 
- <span data-ttu-id="da5ee-3224">パスポート #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3224">パスポート＃</span></span> 
- <span data-ttu-id="da5ee-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="da5ee-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="da5ee-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="da5ee-3226">Passeport n °</span></span> 
- <span data-ttu-id="da5ee-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="da5ee-3227">Passeport Non</span></span> 
- <span data-ttu-id="da5ee-3228">Passeport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3228">Passeport #</span></span> 
- <span data-ttu-id="da5ee-3229">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3229">Passeport#</span></span> 
- <span data-ttu-id="da5ee-3230">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3230">PasseportNon</span></span> 
- <span data-ttu-id="da5ee-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="da5ee-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="da5ee-3232">Код SWIFT</span><span class="sxs-lookup"><span data-stu-id="da5ee-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3233">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3233">Format</span></span>

<span data-ttu-id="da5ee-3234">Четыре буквы, за которыми следуют от 5 до 31 буквы или цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3235">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3235">Pattern</span></span>

<span data-ttu-id="da5ee-3236">Четыре буквы, за которыми следуют от 5 до 31 буквы или цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="da5ee-3237">Четырехбуквенный код банка (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-3238">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-3238">An optional space</span></span> 
- <span data-ttu-id="da5ee-3239">4–28 букв или цифр (основной номер банковского счета, BBAN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="da5ee-3240">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-3240">An optional space</span></span> 
- <span data-ttu-id="da5ee-3241">1–3 буквы или цифры (оставшаяся часть BBAN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3242">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3242">Checksum</span></span>

<span data-ttu-id="da5ee-3243">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3244">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3244">Definition</span></span>

<span data-ttu-id="da5ee-3245">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3246">регулярное выражение Regex_swift находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3247">находится ключевое слово из Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3248">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="da5ee-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="da5ee-3249">Keyword_swift</span></span>

- <span data-ttu-id="da5ee-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="da5ee-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="da5ee-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="da5ee-3251">iso 9362</span></span> 
- <span data-ttu-id="da5ee-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="da5ee-3252">iso9362</span></span> 
- <span data-ttu-id="da5ee-3253">SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3253">swift\#</span></span> 
- <span data-ttu-id="da5ee-3254">свифткоде</span><span class="sxs-lookup"><span data-stu-id="da5ee-3254">swiftcode</span></span> 
- <span data-ttu-id="da5ee-3255">свифтнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-3255">swiftnumber</span></span> 
- <span data-ttu-id="da5ee-3256">свифтраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="da5ee-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="da5ee-3257">swift code</span></span> 
- <span data-ttu-id="da5ee-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3258">swift number #</span></span> 
- <span data-ttu-id="da5ee-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3259">swift routing number</span></span> 
- <span data-ttu-id="da5ee-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3260">bic number</span></span> 
- <span data-ttu-id="da5ee-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="da5ee-3261">bic code</span></span> 
- <span data-ttu-id="da5ee-3262">БИК\#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3262">bic \#</span></span> 
- <span data-ttu-id="da5ee-3263">БИК\#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3263">bic\#</span></span> 
- <span data-ttu-id="da5ee-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="da5ee-3264">bank identifier code</span></span> 
- <span data-ttu-id="da5ee-3265">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="da5ee-3265">標準化9362</span></span> 
- <span data-ttu-id="da5ee-3266">迅速 #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3266">迅速＃</span></span> 
- <span data-ttu-id="da5ee-3267">свифтコード</span><span class="sxs-lookup"><span data-stu-id="da5ee-3267">SWIFTコード</span></span> 
- <span data-ttu-id="da5ee-3268">свифт番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-3268">SWIFT番号</span></span> 
- <span data-ttu-id="da5ee-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="da5ee-3270">бик番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-3270">BIC番号</span></span> 
- <span data-ttu-id="da5ee-3271">бикコード</span><span class="sxs-lookup"><span data-stu-id="da5ee-3271">BICコード</span></span> 
- <span data-ttu-id="da5ee-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="da5ee-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="da5ee-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="da5ee-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="da5ee-3274">Быстрая\#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3274">rapide \#</span></span> 
- <span data-ttu-id="da5ee-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="da5ee-3275">code SWIFT</span></span> 
- <span data-ttu-id="da5ee-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="da5ee-3276">le numéro de swift</span></span> 
- <span data-ttu-id="da5ee-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="da5ee-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="da5ee-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="da5ee-3278">le numéro BIC</span></span> 
- <span data-ttu-id="da5ee-3279">\#БИК</span><span class="sxs-lookup"><span data-stu-id="da5ee-3279">\# BIC</span></span> 
- <span data-ttu-id="da5ee-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="da5ee-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="da5ee-3281">Национальный идентификатор, Тайвань</span><span class="sxs-lookup"><span data-stu-id="da5ee-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3282">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3282">Format</span></span>

<span data-ttu-id="da5ee-3283">Одна буква (английская), за которой следуют девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3284">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3284">Pattern</span></span>

<span data-ttu-id="da5ee-3285">Один символ , за которым следуют девять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="da5ee-3286">Один символ (на английском языке, без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-3287">Цифра 1 или 2</span><span class="sxs-lookup"><span data-stu-id="da5ee-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="da5ee-3288">Восемь цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3289">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3289">Checksum</span></span>

<span data-ttu-id="da5ee-3290">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3291">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3291">Definition</span></span>

<span data-ttu-id="da5ee-3292">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3293">функция Func_taiwanese_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3294">находится ключевое слово из Keyword_taiwanese_national_id;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="da5ee-3295">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3296">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="da5ee-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="da5ee-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="da5ee-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="da5ee-3298">身份證字號</span></span> 
- <span data-ttu-id="da5ee-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="da5ee-3299">身份證</span></span> 
- <span data-ttu-id="da5ee-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="da5ee-3300">身份證號碼</span></span> 
- <span data-ttu-id="da5ee-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="da5ee-3301">身份證號</span></span> 
- <span data-ttu-id="da5ee-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="da5ee-3302">身分證字號</span></span> 
- <span data-ttu-id="da5ee-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="da5ee-3303">身分證</span></span> 
- <span data-ttu-id="da5ee-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="da5ee-3304">身分證號碼</span></span> 
- <span data-ttu-id="da5ee-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="da5ee-3305">身份證號</span></span> 
- <span data-ttu-id="da5ee-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="da5ee-3306">身分證統一編號</span></span> 
- <span data-ttu-id="da5ee-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="da5ee-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="da5ee-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="da5ee-3308">簽名</span></span> 
- <span data-ttu-id="da5ee-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="da5ee-3309">蓋章</span></span> 
- <span data-ttu-id="da5ee-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="da5ee-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="da5ee-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="da5ee-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="da5ee-3312">	Номер паспорта гражданина Тайваня</span><span class="sxs-lookup"><span data-stu-id="da5ee-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3313">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3313">Format</span></span>

- <span data-ttu-id="da5ee-3314">Номер биометрического паспорта: девять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="da5ee-3315">Номер биометрической службы Passport: девять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3316">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3316">Pattern</span></span>
<span data-ttu-id="da5ee-3317">Номер биометрического паспорта:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3317">Biometric passport number:</span></span>
- <span data-ttu-id="da5ee-3318">цифра "3";</span><span class="sxs-lookup"><span data-stu-id="da5ee-3318">The digit "3"</span></span> 
- <span data-ttu-id="da5ee-3319">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3319">Eight digits</span></span>

<span data-ttu-id="da5ee-3320">Номер биометрической службы Passport:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="da5ee-3321">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3322">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3322">Checksum</span></span>

<span data-ttu-id="da5ee-3323">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3324">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3324">Definition</span></span>

<span data-ttu-id="da5ee-3325">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3326">регулярное выражение Regex_taiwan_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3327">находится ключевое слово из Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3328">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="da5ee-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="da5ee-3330">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3330">ROC passport number</span></span> 
- <span data-ttu-id="da5ee-3331">Passport number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3331">Passport number</span></span> 
- <span data-ttu-id="da5ee-3332">Passport no</span><span class="sxs-lookup"><span data-stu-id="da5ee-3332">Passport no</span></span> 
- <span data-ttu-id="da5ee-3333">Passport Num</span><span class="sxs-lookup"><span data-stu-id="da5ee-3333">Passport Num</span></span> 
- <span data-ttu-id="da5ee-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3334">Passport #</span></span> 
- <span data-ttu-id="da5ee-3335">护照</span><span class="sxs-lookup"><span data-stu-id="da5ee-3335">护照</span></span> 
- <span data-ttu-id="da5ee-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="da5ee-3336">中華民國護照</span></span> 
- <span data-ttu-id="da5ee-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="da5ee-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="da5ee-3338">Номер удостоверения жителя Тайваня (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3339">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3339">Format</span></span>

<span data-ttu-id="da5ee-3340">10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3341">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3341">Pattern</span></span>

<span data-ttu-id="da5ee-3342">10 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3342">10 letters and digits:</span></span>
- <span data-ttu-id="da5ee-3343">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="da5ee-3344">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3345">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3345">Checksum</span></span>

<span data-ttu-id="da5ee-3346">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3347">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3347">Definition</span></span>

<span data-ttu-id="da5ee-3348">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3349">регулярное выражение Regex_taiwan_resident_certificate находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3350">находится ключевое слово из Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3351">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="da5ee-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="da5ee-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="da5ee-3353">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="da5ee-3353">Resident Certificate</span></span> 
- <span data-ttu-id="da5ee-3354">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="da5ee-3354">Resident Cert</span></span> 
- <span data-ttu-id="da5ee-3355">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3355">Resident Cert.</span></span> 
- <span data-ttu-id="da5ee-3356">Identification card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3356">Identification card</span></span> 
- <span data-ttu-id="da5ee-3357">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="da5ee-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="da5ee-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="da5ee-3358">ARC</span></span> 
- <span data-ttu-id="da5ee-3359">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="da5ee-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="da5ee-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="da5ee-3360">TARC</span></span> 
- <span data-ttu-id="da5ee-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="da5ee-3361">居留證</span></span> 
- <span data-ttu-id="da5ee-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="da5ee-3362">外僑居留證</span></span> 
- <span data-ttu-id="da5ee-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="da5ee-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="da5ee-3364">Код идентификации для тайского заполнения</span><span class="sxs-lookup"><span data-stu-id="da5ee-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3365">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3365">Format</span></span>

<span data-ttu-id="da5ee-3366">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3367">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3367">Pattern</span></span>

<span data-ttu-id="da5ee-3368">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3368">13 digits:</span></span>
- <span data-ttu-id="da5ee-3369">Первая цифра не равна 0 или 9</span><span class="sxs-lookup"><span data-stu-id="da5ee-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="da5ee-3370">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3371">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3371">Checksum</span></span>

<span data-ttu-id="da5ee-3372">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3373">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3373">Definition</span></span>

<span data-ttu-id="da5ee-3374">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3375">Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3376">Найдено ключевое слово из Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="da5ee-3377">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3378">Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3379">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="da5ee-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="da5ee-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="da5ee-3381">ID Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3381">ID Number</span></span>
- <span data-ttu-id="da5ee-3382">Идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="da5ee-3382">Identification Number</span></span>
- <span data-ttu-id="da5ee-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="da5ee-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="da5ee-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="da5ee-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="da5ee-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="da5ee-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="da5ee-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="da5ee-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="da5ee-3387">Турецкий национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="da5ee-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3388">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3388">Format</span></span>

<span data-ttu-id="da5ee-3389">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3390">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3390">Pattern</span></span>

<span data-ttu-id="da5ee-3391">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3392">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3392">Checksum</span></span>

<span data-ttu-id="da5ee-3393">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3394">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3394">Definition</span></span>

<span data-ttu-id="da5ee-3395">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3396">Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3397">Найдено ключевое слово из Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="da5ee-3398">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3399">Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3400">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="da5ee-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="da5ee-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="da5ee-3402">TC Кимлик No</span><span class="sxs-lookup"><span data-stu-id="da5ee-3402">TC Kimlik No</span></span>
- <span data-ttu-id="da5ee-3403">TC Кимлик нумарасı</span><span class="sxs-lookup"><span data-stu-id="da5ee-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="da5ee-3404">Ватандаşлıк нумарасı</span><span class="sxs-lookup"><span data-stu-id="da5ee-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="da5ee-3405">Ватандаşлıк нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="da5ee-p144">Номер водительского удостоверения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="da5ee-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3408">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3408">Format</span></span>

<span data-ttu-id="da5ee-3409">Сочетание 18 букв и цифр в указанном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3410">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3410">Pattern</span></span>

<span data-ttu-id="da5ee-3411">18 букв и цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3411">18 letters and digits:</span></span>
- <span data-ttu-id="da5ee-3412">Пять букв (без учета регистра) или цифра 9 вместо буквы</span><span class="sxs-lookup"><span data-stu-id="da5ee-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="da5ee-3413">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="da5ee-3413">One digit</span></span> 
- <span data-ttu-id="da5ee-3414">Пять цифр в формате даты ММДДИ для даты рождения (седьмой символ увеличивается на 50, если драйвер — гнездо, то есть 51 – 62, а не с 01 – 12)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="da5ee-3415">Две буквы (без учета регистра) или цифра 9 вместо буквы</span><span class="sxs-lookup"><span data-stu-id="da5ee-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="da5ee-3416">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3417">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3417">Checksum</span></span>

<span data-ttu-id="da5ee-3418">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3419">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3419">Definition</span></span>

<span data-ttu-id="da5ee-3420">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3421">функция Func_uk_drivers_license находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3422">находится ключевое слово из Keyword_uk_drivers_license;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="da5ee-3423">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3424">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="da5ee-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="da5ee-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="da5ee-3426">двла</span><span class="sxs-lookup"><span data-stu-id="da5ee-3426">DVLA</span></span> 
- <span data-ttu-id="da5ee-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="da5ee-3427">light vans</span></span> 
- <span data-ttu-id="da5ee-3428">куадбикес</span><span class="sxs-lookup"><span data-stu-id="da5ee-3428">quadbikes</span></span> 
- <span data-ttu-id="da5ee-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="da5ee-3429">motor cars</span></span> 
- <span data-ttu-id="da5ee-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="da5ee-3430">125cc</span></span> 
- <span data-ttu-id="da5ee-3431">сидекар</span><span class="sxs-lookup"><span data-stu-id="da5ee-3431">sidecar</span></span> 
- <span data-ttu-id="da5ee-3432">трициклес</span><span class="sxs-lookup"><span data-stu-id="da5ee-3432">tricycles</span></span> 
- <span data-ttu-id="da5ee-3433">моторциклес</span><span class="sxs-lookup"><span data-stu-id="da5ee-3433">motorcycles</span></span> 
- <span data-ttu-id="da5ee-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-3434">photocard licence</span></span> 
- <span data-ttu-id="da5ee-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="da5ee-3435">learner drivers</span></span> 
- <span data-ttu-id="da5ee-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="da5ee-3436">licence holder</span></span> 
- <span data-ttu-id="da5ee-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="da5ee-3437">licence holders</span></span> 
- <span data-ttu-id="da5ee-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="da5ee-3438">driving licences</span></span> 
- <span data-ttu-id="da5ee-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="da5ee-3439">driving licence</span></span> 
- <span data-ttu-id="da5ee-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="da5ee-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="da5ee-p145">Регистрационный номер избирателя для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="da5ee-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3443">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3443">Format</span></span>

<span data-ttu-id="da5ee-3444">Две буквы, за которыми следуют 1–4 цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3445">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3445">Pattern</span></span>

<span data-ttu-id="da5ee-3446">Две буквы (без учета регистра), за которыми следуют 1–4 цифры.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3447">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3447">Checksum</span></span>

<span data-ttu-id="da5ee-3448">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3449">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3449">Definition</span></span>

<span data-ttu-id="da5ee-3450">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3451">регулярное выражение Regex_uk_electoral находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3452">находится ключевое слово из Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3453">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="da5ee-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="da5ee-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="da5ee-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="da5ee-3455">council nomination</span></span> 
- <span data-ttu-id="da5ee-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="da5ee-3456">nomination form</span></span> 
- <span data-ttu-id="da5ee-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="da5ee-3457">electoral register</span></span> 
- <span data-ttu-id="da5ee-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="da5ee-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="da5ee-p146">Номер национальной службы здравоохранения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="da5ee-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3461">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3461">Format</span></span>

<span data-ttu-id="da5ee-3462">10–17 цифр, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3463">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3463">Pattern</span></span>

<span data-ttu-id="da5ee-3464">10-17 цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3464">10-17 digits:</span></span>
- <span data-ttu-id="da5ee-3465">3 или 10 цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="da5ee-3466">Пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-3466">A space</span></span> 
- <span data-ttu-id="da5ee-3467">Три цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3467">Three digits</span></span> 
- <span data-ttu-id="da5ee-3468">Пробел</span><span class="sxs-lookup"><span data-stu-id="da5ee-3468">A space</span></span> 
- <span data-ttu-id="da5ee-3469">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3470">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3470">Checksum</span></span>

<span data-ttu-id="da5ee-3471">Да</span><span class="sxs-lookup"><span data-stu-id="da5ee-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3472">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3472">Definition</span></span>

<span data-ttu-id="da5ee-3473">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3474">Функция Func_uk_nhs_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3475">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3475">One of the following is true:</span></span>
    - <span data-ttu-id="da5ee-3476">найдено ключевое слово из Keyword_uk_nhs_number;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="da5ee-3477">найдено ключевое слово из Keyword_uk_nhs_number1;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="da5ee-3478">найдено ключевое слово из Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="da5ee-3479">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3480">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="da5ee-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="da5ee-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="da5ee-3482">national health service</span></span> 
- <span data-ttu-id="da5ee-3483">NHS</span><span class="sxs-lookup"><span data-stu-id="da5ee-3483">nhs</span></span> 
- <span data-ttu-id="da5ee-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="da5ee-3484">health services authority</span></span> 
- <span data-ttu-id="da5ee-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="da5ee-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="da5ee-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="da5ee-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="da5ee-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="da5ee-3487">patient id</span></span> 
- <span data-ttu-id="da5ee-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="da5ee-3488">patient identification</span></span> 
- <span data-ttu-id="da5ee-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="da5ee-3489">patient no</span></span> 
- <span data-ttu-id="da5ee-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="da5ee-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="da5ee-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="da5ee-3492">ГРУПП</span><span class="sxs-lookup"><span data-stu-id="da5ee-3492">GP</span></span> 
- <span data-ttu-id="da5ee-3493">доб</span><span class="sxs-lookup"><span data-stu-id="da5ee-3493">DOB</span></span> 
- <span data-ttu-id="da5ee-3494">D. O. B</span><span class="sxs-lookup"><span data-stu-id="da5ee-3494">D.O.B</span></span> 
- <span data-ttu-id="da5ee-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="da5ee-3495">Date of Birth</span></span> 
- <span data-ttu-id="da5ee-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="da5ee-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="da5ee-p147">Номер карты национального страхования для Соединенного Королевства (NINO)</span><span class="sxs-lookup"><span data-stu-id="da5ee-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3499">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3499">Format</span></span>

<span data-ttu-id="da5ee-3500">7 символов или 9 символов, разделенных пробелами или тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3501">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3501">Pattern</span></span>

<span data-ttu-id="da5ee-3502">Два возможных шаблона:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3502">Two possible patterns:</span></span>

- <span data-ttu-id="da5ee-3503">Две буквы (допустимые Нинос используют только определенные символы в этом префиксе, которые пропускаются при проверке этого шаблона; без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="da5ee-3504">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3504">Six digits</span></span>
- <span data-ttu-id="da5ee-3505">"A", "B", "C", или "'D" (например, префикс, в суффиксе допускаются только определенные символы; без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="da5ee-3506">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="da5ee-3506">OR</span></span>

- <span data-ttu-id="da5ee-3507">Две буквы</span><span class="sxs-lookup"><span data-stu-id="da5ee-3507">Two letters</span></span>
- <span data-ttu-id="da5ee-3508">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-3508">A space or dash</span></span>
- <span data-ttu-id="da5ee-3509">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3509">Two digits</span></span>
- <span data-ttu-id="da5ee-3510">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-3510">A space or dash</span></span>
- <span data-ttu-id="da5ee-3511">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3511">Two digits</span></span>
- <span data-ttu-id="da5ee-3512">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-3512">A space or dash</span></span>
- <span data-ttu-id="da5ee-3513">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3513">Two digits</span></span>
- <span data-ttu-id="da5ee-3514">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-3514">A space or dash</span></span>
- <span data-ttu-id="da5ee-3515">Значение "A", "B", "C" или "'D"</span><span class="sxs-lookup"><span data-stu-id="da5ee-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3516">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3516">Checksum</span></span>

<span data-ttu-id="da5ee-3517">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3518">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3518">Definition</span></span>

<span data-ttu-id="da5ee-3519">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3520">функция Func_uk_nino находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3521">находится ключевое слово из Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="da5ee-3522">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3523">функция Func_uk_nino находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3524">ни одно ключевое слово из Keyword_uk_nino не находится.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3525">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="da5ee-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="da5ee-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="da5ee-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3527">national insurance number</span></span> 
- <span data-ttu-id="da5ee-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="da5ee-3528">national insurance contributions</span></span> 
- <span data-ttu-id="da5ee-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="da5ee-3529">protection act</span></span> 
- <span data-ttu-id="da5ee-3530">страхования</span><span class="sxs-lookup"><span data-stu-id="da5ee-3530">insurance</span></span> 
- <span data-ttu-id="da5ee-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3531">social security number</span></span> 
- <span data-ttu-id="da5ee-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="da5ee-3532">insurance application</span></span> 
- <span data-ttu-id="da5ee-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="da5ee-3533">medical application</span></span> 
- <span data-ttu-id="da5ee-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="da5ee-3534">social insurance</span></span> 
- <span data-ttu-id="da5ee-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="da5ee-3535">medical attention</span></span> 
- <span data-ttu-id="da5ee-3536">social security</span><span class="sxs-lookup"><span data-stu-id="da5ee-3536">social security</span></span> 
- <span data-ttu-id="da5ee-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="da5ee-3537">great britain</span></span> 
- <span data-ttu-id="da5ee-3538">страхования</span><span class="sxs-lookup"><span data-stu-id="da5ee-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="da5ee-p148">Номер паспорта гражданина США и/или Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="da5ee-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3541">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3541">Format</span></span>

<span data-ttu-id="da5ee-3542">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3543">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3543">Pattern</span></span>

<span data-ttu-id="da5ee-3544">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3545">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3545">Checksum</span></span>

<span data-ttu-id="da5ee-3546">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3547">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3547">Definition</span></span>

<span data-ttu-id="da5ee-3548">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3549">функция Func_usa_uk_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3550">находится ключевое слово из Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3551">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="da5ee-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="da5ee-3552">Keyword_passport</span></span>

- <span data-ttu-id="da5ee-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3553">Passport Number</span></span> 
- <span data-ttu-id="da5ee-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="da5ee-3554">Passport No</span></span> 
- <span data-ttu-id="da5ee-3555">Passport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3555">Passport #</span></span> 
- <span data-ttu-id="da5ee-3556">Службу #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3556">Passport#</span></span> 
- <span data-ttu-id="da5ee-3557">пасспортид</span><span class="sxs-lookup"><span data-stu-id="da5ee-3557">PassportID</span></span> 
- <span data-ttu-id="da5ee-3558">пасспортно</span><span class="sxs-lookup"><span data-stu-id="da5ee-3558">Passportno</span></span> 
- <span data-ttu-id="da5ee-3559">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="da5ee-3559">passportnumber</span></span> 
- <span data-ttu-id="da5ee-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="da5ee-3560">パスポート</span></span> 
- <span data-ttu-id="da5ee-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="da5ee-3561">パスポート番号</span></span> 
- <span data-ttu-id="da5ee-3562">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="da5ee-3562">パスポートのNum</span></span> 
- <span data-ttu-id="da5ee-3563">パスポート #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3563">パスポート＃</span></span> 
- <span data-ttu-id="da5ee-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="da5ee-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="da5ee-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="da5ee-3565">Passeport n °</span></span> 
- <span data-ttu-id="da5ee-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="da5ee-3566">Passeport Non</span></span> 
- <span data-ttu-id="da5ee-3567">Passeport#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3567">Passeport #</span></span> 
- <span data-ttu-id="da5ee-3568">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3568">Passeport#</span></span> 
- <span data-ttu-id="da5ee-3569">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3569">PasseportNon</span></span> 
- <span data-ttu-id="da5ee-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="da5ee-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="da5ee-3571">Номер банковского счета для США</span><span class="sxs-lookup"><span data-stu-id="da5ee-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3572">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3572">Format</span></span>

<span data-ttu-id="da5ee-3573">8-17 цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3574">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3574">Pattern</span></span>

<span data-ttu-id="da5ee-3575">8–17 последовательных цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3576">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3576">Checksum</span></span>

<span data-ttu-id="da5ee-3577">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3578">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3578">Definition</span></span>

<span data-ttu-id="da5ee-3579">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3580">регулярное выражение Regex_usa_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3581">находится ключевое слово из Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da5ee-3582">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="da5ee-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="da5ee-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3584">Checking Account Number</span></span> 
- <span data-ttu-id="da5ee-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-3585">Checking Account</span></span> 
- <span data-ttu-id="da5ee-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3586">Checking Account #</span></span> 
- <span data-ttu-id="da5ee-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="da5ee-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3588">Checking Acct #</span></span> 
- <span data-ttu-id="da5ee-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="da5ee-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3590">Checking Account No.</span></span> 
- <span data-ttu-id="da5ee-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3591">Bank Account Number</span></span> 
- <span data-ttu-id="da5ee-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3592">Bank Account #</span></span> 
- <span data-ttu-id="da5ee-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="da5ee-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3594">Bank Acct #</span></span> 
- <span data-ttu-id="da5ee-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="da5ee-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3596">Bank Account No.</span></span> 
- <span data-ttu-id="da5ee-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3597">Savings Account Number</span></span> 
- <span data-ttu-id="da5ee-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3598">Savings Account.</span></span> 
- <span data-ttu-id="da5ee-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3599">Savings Account #</span></span> 
- <span data-ttu-id="da5ee-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="da5ee-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3601">Savings Acct #</span></span> 
- <span data-ttu-id="da5ee-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="da5ee-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3603">Savings Account No.</span></span> 
- <span data-ttu-id="da5ee-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3604">Debit Account Number</span></span> 
- <span data-ttu-id="da5ee-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="da5ee-3605">Debit Account</span></span> 
- <span data-ttu-id="da5ee-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3606">Debit Account #</span></span> 
- <span data-ttu-id="da5ee-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="da5ee-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3608">Debit Acct #</span></span> 
- <span data-ttu-id="da5ee-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="da5ee-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="da5ee-3611">Номер водительского удостоверения для США</span><span class="sxs-lookup"><span data-stu-id="da5ee-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3612">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3612">Format</span></span>

<span data-ttu-id="da5ee-3613">Зависит от штата.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3614">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3614">Pattern</span></span>

<span data-ttu-id="da5ee-3615">В зависимости от штата. Например, для Нью-Йорка:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="da5ee-3616">Девять цифр, отформатированных как DDD DDD DDD, будут совпадают.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="da5ee-3617">Не подойдут девять цифр в формате ццццццццц.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3618">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3618">Checksum</span></span>

<span data-ttu-id="da5ee-3619">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3620">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3620">Definition</span></span>

<span data-ttu-id="da5ee-3621">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3622">функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3623">находится ключевое слово из Keyword_[state_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="da5ee-3624">обнаружено ключевое слово из списка Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="da5ee-3625">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3626">функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3627">находится ключевое слово из Keyword_[state_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="da5ee-3628">находится ключевое слово из Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="da5ee-3629">ни одно ключевое слово из Keyword_us_drivers_license не находится.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3630">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="da5ee-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="da5ee-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="da5ee-3632">DL</span><span class="sxs-lookup"><span data-stu-id="da5ee-3632">DL</span></span> 
- <span data-ttu-id="da5ee-3633">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="da5ee-3633">DLS</span></span> 
- <span data-ttu-id="da5ee-3634">кдл</span><span class="sxs-lookup"><span data-stu-id="da5ee-3634">CDL</span></span> 
- <span data-ttu-id="da5ee-3635">кдлс</span><span class="sxs-lookup"><span data-stu-id="da5ee-3635">CDLS</span></span> 
- <span data-ttu-id="da5ee-3636">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="da5ee-3636">ID</span></span> 
- <span data-ttu-id="da5ee-3637">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="da5ee-3637">IDs</span></span> 
- <span data-ttu-id="da5ee-3638">DL #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3638">DL#</span></span> 
- <span data-ttu-id="da5ee-3639">БИБЛИОТЕК #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3639">DLS#</span></span> 
- <span data-ttu-id="da5ee-3640">кдл #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3640">CDL#</span></span> 
- <span data-ttu-id="da5ee-3641">кдлс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3641">CDLS#</span></span> 
- <span data-ttu-id="da5ee-3642">КОДОВ #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3642">ID#</span></span>
- <span data-ttu-id="da5ee-3643">Идентификаторы #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3643">IDs#</span></span> 
- <span data-ttu-id="da5ee-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3644">ID number</span></span> 
- <span data-ttu-id="da5ee-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-3645">ID numbers</span></span> 
- <span data-ttu-id="da5ee-3646">лик</span><span class="sxs-lookup"><span data-stu-id="da5ee-3646">LIC</span></span> 
- <span data-ttu-id="da5ee-3647">лик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="da5ee-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="da5ee-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="da5ee-3649">дриверлик</span><span class="sxs-lookup"><span data-stu-id="da5ee-3649">DriverLic</span></span> 
- <span data-ttu-id="da5ee-3650">дриверликс</span><span class="sxs-lookup"><span data-stu-id="da5ee-3650">DriverLics</span></span> 
- <span data-ttu-id="da5ee-3651">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-3651">DriverLicense</span></span> 
- <span data-ttu-id="da5ee-3652">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-3652">DriverLicenses</span></span> 
- <span data-ttu-id="da5ee-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-3653">Driver Lic</span></span> 
- <span data-ttu-id="da5ee-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-3654">Driver Lics</span></span> 
- <span data-ttu-id="da5ee-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="da5ee-3655">Driver License</span></span> 
- <span data-ttu-id="da5ee-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-3656">Driver Licenses</span></span> 
- <span data-ttu-id="da5ee-3657">дриверслик</span><span class="sxs-lookup"><span data-stu-id="da5ee-3657">DriversLic</span></span> 
- <span data-ttu-id="da5ee-3658">дриверсликс</span><span class="sxs-lookup"><span data-stu-id="da5ee-3658">DriversLics</span></span> 
- <span data-ttu-id="da5ee-3659">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-3659">DriversLicense</span></span> 
- <span data-ttu-id="da5ee-3660">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-3660">DriversLicenses</span></span> 
- <span data-ttu-id="da5ee-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-3661">Drivers Lic</span></span> 
- <span data-ttu-id="da5ee-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-3662">Drivers Lics</span></span> 
- <span data-ttu-id="da5ee-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="da5ee-3663">Drivers License</span></span> 
- <span data-ttu-id="da5ee-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="da5ee-3665">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="da5ee-3665">Driver'Lic</span></span> 
- <span data-ttu-id="da5ee-3666">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="da5ee-3666">Driver'Lics</span></span> 
- <span data-ttu-id="da5ee-3667">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="da5ee-3667">Driver'License</span></span> 
- <span data-ttu-id="da5ee-3668">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="da5ee-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-3669">Driver' Lic</span></span> 
- <span data-ttu-id="da5ee-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-3670">Driver' Lics</span></span> 
- <span data-ttu-id="da5ee-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="da5ee-3671">Driver' License</span></span> 
- <span data-ttu-id="da5ee-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-3672">Driver' Licenses</span></span>
- <span data-ttu-id="da5ee-3673">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="da5ee-3673">Driver'sLic</span></span> 
- <span data-ttu-id="da5ee-3674">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="da5ee-3674">Driver'sLics</span></span> 
- <span data-ttu-id="da5ee-3675">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="da5ee-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="da5ee-3676">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="da5ee-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="da5ee-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="da5ee-3677">Driver's Lic</span></span> 
- <span data-ttu-id="da5ee-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="da5ee-3678">Driver's Lics</span></span> 
- <span data-ttu-id="da5ee-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="da5ee-3679">Driver's License</span></span> 
- <span data-ttu-id="da5ee-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="da5ee-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="da5ee-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="da5ee-3681">identification number</span></span> 
- <span data-ttu-id="da5ee-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="da5ee-3682">identification numbers</span></span> 
- <span data-ttu-id="da5ee-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3683">identification #</span></span> 
- <span data-ttu-id="da5ee-3684">id card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3684">id card</span></span> 
- <span data-ttu-id="da5ee-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-3685">id cards</span></span> 
- <span data-ttu-id="da5ee-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="da5ee-3686">identification card</span></span> 
- <span data-ttu-id="da5ee-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="da5ee-3687">identification cards</span></span> 
- <span data-ttu-id="da5ee-3688">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3688">DriverLic#</span></span> 
- <span data-ttu-id="da5ee-3689">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3689">DriverLics#</span></span> 
- <span data-ttu-id="da5ee-3690">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3690">DriverLicense#</span></span> 
- <span data-ttu-id="da5ee-3691">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="da5ee-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3692">Driver Lic#</span></span> 
- <span data-ttu-id="da5ee-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3693">Driver Lics#</span></span> 
- <span data-ttu-id="da5ee-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3694">Driver License#</span></span> 
- <span data-ttu-id="da5ee-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="da5ee-3696">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3696">DriversLic#</span></span> 
- <span data-ttu-id="da5ee-3697">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3697">DriversLics#</span></span> 
- <span data-ttu-id="da5ee-3698">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3698">DriversLicense#</span></span> 
- <span data-ttu-id="da5ee-3699">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="da5ee-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="da5ee-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="da5ee-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3702">Drivers License#</span></span> 
- <span data-ttu-id="da5ee-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="da5ee-3704">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="da5ee-3705">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="da5ee-3706">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3706">Driver'License#</span></span> 
- <span data-ttu-id="da5ee-3707">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="da5ee-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="da5ee-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="da5ee-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3710">Driver' License#</span></span> 
- <span data-ttu-id="da5ee-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="da5ee-3712">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="da5ee-3713">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="da5ee-3714">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="da5ee-3715">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="da5ee-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="da5ee-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="da5ee-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3718">Driver's License#</span></span> 
- <span data-ttu-id="da5ee-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="da5ee-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3720">id card#</span></span> 
- <span data-ttu-id="da5ee-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3721">id cards#</span></span> 
- <span data-ttu-id="da5ee-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3722">identification card#</span></span> 
- <span data-ttu-id="da5ee-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="da5ee-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="da5ee-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="da5ee-3725">Аббревиатура штата (например, NY)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="da5ee-3726">Название штата (например, New York)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="da5ee-3727">Идентификационный номер налогоплательщика для США (ITIN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3728">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3728">Format</span></span>

<span data-ttu-id="da5ee-3729">Девять цифр, которые начинаются с "9" и содержат "7" или "8" в качестве четвертой цифры, отформатированных с помощью пробелов или тире (необязательно).</span><span class="sxs-lookup"><span data-stu-id="da5ee-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3730">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3730">Pattern</span></span>

<span data-ttu-id="da5ee-3731">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="da5ee-3731">Formatted:</span></span>
- <span data-ttu-id="da5ee-3732">Цифра 9</span><span class="sxs-lookup"><span data-stu-id="da5ee-3732">The digit "9"</span></span> 
- <span data-ttu-id="da5ee-3733">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3733">Two digits</span></span> 
- <span data-ttu-id="da5ee-3734">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-3734">A space or dash</span></span> 
- <span data-ttu-id="da5ee-3735">Цифра 7 или 8</span><span class="sxs-lookup"><span data-stu-id="da5ee-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="da5ee-3736">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="da5ee-3736">A digit</span></span> 
- <span data-ttu-id="da5ee-3737">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="da5ee-3737">A space, or dash</span></span> 
- <span data-ttu-id="da5ee-3738">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3738">Four digits</span></span>

<span data-ttu-id="da5ee-3739">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="da5ee-3739">Unformatted:</span></span>
- <span data-ttu-id="da5ee-3740">Цифра 9</span><span class="sxs-lookup"><span data-stu-id="da5ee-3740">The digit "9"</span></span> 
- <span data-ttu-id="da5ee-3741">Две цифры</span><span class="sxs-lookup"><span data-stu-id="da5ee-3741">Two digits</span></span> 
- <span data-ttu-id="da5ee-3742">Цифра 7 или 8</span><span class="sxs-lookup"><span data-stu-id="da5ee-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="da5ee-3743">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="da5ee-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3744">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3744">Checksum</span></span>

<span data-ttu-id="da5ee-3745">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="da5ee-3746">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3746">Definition</span></span>

<span data-ttu-id="da5ee-3747">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3748">Функция Func_formatted_itin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3749">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="da5ee-3750">найдено ключевое слово из Keyword_itin;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="da5ee-3751">функция Func_us_address находит адрес в правильном формате;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="da5ee-3752">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="da5ee-3753">найдено ключевое слово из Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="da5ee-3754">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3755">Функция Func_unformatted_itin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3756">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="da5ee-3757">найдено ключевое слово из Keyword_itin_collaborative;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="da5ee-3758">функция Func_us_address находит адрес в правильном формате;</span><span class="sxs-lookup"><span data-stu-id="da5ee-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="da5ee-3759">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3760">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="da5ee-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="da5ee-3761">Keyword_itin</span></span>

- <span data-ttu-id="da5ee-3762">дубликат</span><span class="sxs-lookup"><span data-stu-id="da5ee-3762">taxpayer</span></span> 
- <span data-ttu-id="da5ee-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="da5ee-3763">tax id</span></span> 
- <span data-ttu-id="da5ee-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="da5ee-3764">tax identification</span></span> 
- <span data-ttu-id="da5ee-3765">SharePointв</span><span class="sxs-lookup"><span data-stu-id="da5ee-3765">itin</span></span> 
- <span data-ttu-id="da5ee-3766">SSN</span><span class="sxs-lookup"><span data-stu-id="da5ee-3766">ssn</span></span> 
- <span data-ttu-id="da5ee-3767">ИНН</span><span class="sxs-lookup"><span data-stu-id="da5ee-3767">tin</span></span> 
- <span data-ttu-id="da5ee-3768">social security</span><span class="sxs-lookup"><span data-stu-id="da5ee-3768">social security</span></span> 
- <span data-ttu-id="da5ee-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="da5ee-3769">tax payer</span></span> 
- <span data-ttu-id="da5ee-3770">итинс</span><span class="sxs-lookup"><span data-stu-id="da5ee-3770">itins</span></span> 
- <span data-ttu-id="da5ee-3771">такси</span><span class="sxs-lookup"><span data-stu-id="da5ee-3771">taxid</span></span> 
- <span data-ttu-id="da5ee-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="da5ee-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="da5ee-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="da5ee-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="da5ee-3774">Лицензия</span><span class="sxs-lookup"><span data-stu-id="da5ee-3774">License</span></span> 
- <span data-ttu-id="da5ee-3775">DL</span><span class="sxs-lookup"><span data-stu-id="da5ee-3775">DL</span></span> 
- <span data-ttu-id="da5ee-3776">доб</span><span class="sxs-lookup"><span data-stu-id="da5ee-3776">DOB</span></span> 
- <span data-ttu-id="da5ee-3777">Birthdate</span><span class="sxs-lookup"><span data-stu-id="da5ee-3777">Birthdate</span></span> 
- <span data-ttu-id="da5ee-3778">День рождения </span><span class="sxs-lookup"><span data-stu-id="da5ee-3778">Birthday</span></span> 
- <span data-ttu-id="da5ee-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="da5ee-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="da5ee-3780">Страховой номер для США (SSN)</span><span class="sxs-lookup"><span data-stu-id="da5ee-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="da5ee-3781">Format</span><span class="sxs-lookup"><span data-stu-id="da5ee-3781">Format</span></span>

<span data-ttu-id="da5ee-3782">9 цифр в виде форматированного или неформатированного шаблона.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="da5ee-3783">Есть SSN выдан до середины 2011 г., он отличается строгим форматированием, при котором определенные части номера должны входить в указанные диапазоны (при этом нет контрольной суммы).</span><span class="sxs-lookup"><span data-stu-id="da5ee-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="da5ee-3784">Шаблон</span><span class="sxs-lookup"><span data-stu-id="da5ee-3784">Pattern</span></span>

<span data-ttu-id="da5ee-3785">Четыре функции выполняют поиск SSN с использованием четырех разных шаблонов:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="da5ee-3786">Func_ssn находит SSN со строгим форматированием с тире или пробелами, выданные до 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="da5ee-3787">Func_unformatted_ssn находит SSN со строгим форматированием, выданные до 2011 г. (без форматирования в виде девяти последовательных цифр — ццццццццц);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="da5ee-3788">Func_randomized_formatted_ssn находит SSN с тире или пробелами, выданные после 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);</span><span class="sxs-lookup"><span data-stu-id="da5ee-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="da5ee-3789">Func_randomized_unformatted_ssn находит SSN без форматирования в виде девяти последовательных цифр, выданные после 2011 г. (ццццццццц).</span><span class="sxs-lookup"><span data-stu-id="da5ee-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="da5ee-3790">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="da5ee-3790">Checksum</span></span>

<span data-ttu-id="da5ee-3791">Нет</span><span class="sxs-lookup"><span data-stu-id="da5ee-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="da5ee-3792">Определение</span><span class="sxs-lookup"><span data-stu-id="da5ee-3792">Definition</span></span>

<span data-ttu-id="da5ee-3793">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3794">Функция Func_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3795">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3795">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="da5ee-3796">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3796">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-3797">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3797">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="da5ee-3798">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3798">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3799">Функция Func_unformatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3799">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3800">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3800">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="da5ee-3801">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3801">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-3802">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3802">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="da5ee-3803">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3803">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3804">Функция Func_randomized_formatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3804">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3805">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3805">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="da5ee-3806">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3806">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-3807">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3807">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="da5ee-3808">Политика защиты от потери данных с вероятностью в 55 % верно обнаружила этот тип конфиденциальной информации, если в пределах ближайших 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3808">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3809">Функция Func_randomized_unformatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3809">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3810">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3810">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="da5ee-3811">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3811">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="da5ee-3812">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3812">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="da5ee-3813">Политика защиты от потери данных — 40% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах расстояния от 300 символов:</span><span class="sxs-lookup"><span data-stu-id="da5ee-3813">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="da5ee-3814">Функция Func_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3814">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3815">Функция Func_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3815">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3816">Функция Func_randomized_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3816">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3817">Не найдено ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3817">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="da5ee-3818">или</span><span class="sxs-lookup"><span data-stu-id="da5ee-3818">Or</span></span>

- <span data-ttu-id="da5ee-3819">Функция Func_randomized_formatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3819">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3820">Функция Func_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3820">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3821">Функция Func_randomized_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3821">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="da5ee-3822">Не найдено ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="da5ee-3822">A keyword from Keyword_ssn is not found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="da5ee-3823">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="da5ee-3823">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="da5ee-3824">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="da5ee-3824">Keyword_ssn</span></span>

- <span data-ttu-id="da5ee-3825">Social Security</span><span class="sxs-lookup"><span data-stu-id="da5ee-3825">Social Security</span></span> 
- <span data-ttu-id="da5ee-3826">Social Security#</span><span class="sxs-lookup"><span data-stu-id="da5ee-3826">Social Security#</span></span> 
- <span data-ttu-id="da5ee-3827">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="da5ee-3827">Soc Sec</span></span> 
- <span data-ttu-id="da5ee-3828">SSN</span><span class="sxs-lookup"><span data-stu-id="da5ee-3828">SSN</span></span> 
- <span data-ttu-id="da5ee-3829">SSNS</span><span class="sxs-lookup"><span data-stu-id="da5ee-3829">SSNS</span></span> 
- <span data-ttu-id="da5ee-3830">SSN #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3830">SSN#</span></span> 
- <span data-ttu-id="da5ee-3831">НН #</span><span class="sxs-lookup"><span data-stu-id="da5ee-3831">SS#</span></span> 
- <span data-ttu-id="da5ee-3832">SSID</span><span class="sxs-lookup"><span data-stu-id="da5ee-3832">SSID</span></span> 
   

