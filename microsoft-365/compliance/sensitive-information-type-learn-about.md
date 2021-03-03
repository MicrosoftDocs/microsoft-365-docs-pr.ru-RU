---
title: Дополнительные сведения о типах конфиденциальной информации
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: e125a6dfb35b7018b5f85100184c842da9231327
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407329"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="058c9-102">Дополнительные сведения о типах конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-102">Learn about sensitive information types</span></span>

<span data-ttu-id="058c9-103">Определение и классификация конфиденциальных элементов, которые находятся под контролем организаций, является первым шагом в области защиты [информации.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="058c9-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="058c9-104">Microsoft 365 предоставляет три способа идентификации элементов, чтобы их можно было классифицировать:</span><span class="sxs-lookup"><span data-stu-id="058c9-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="058c9-105">вручную пользователями</span><span class="sxs-lookup"><span data-stu-id="058c9-105">manually by users</span></span>
- <span data-ttu-id="058c9-106">автоматическое распознавание шаблонов, например типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="058c9-107">машинное обучение</span><span class="sxs-lookup"><span data-stu-id="058c9-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="058c9-108">Типы конфиденциальных сведений — классификаторы на основе шаблонов.</span><span class="sxs-lookup"><span data-stu-id="058c9-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="058c9-109">Они обнаруживают конфиденциальную информацию, например номера социального обеспечения, кредитной карты или банковских счетов, чтобы идентифицировать конфиденциальные элементы, см. в статьи Определения объектов типа [конфиденциальной информации.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="058c9-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="058c9-110">Типы конфиденциальной информации используются в</span><span class="sxs-lookup"><span data-stu-id="058c9-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="058c9-111">Политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="058c9-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="058c9-112">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="058c9-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="058c9-113">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="058c9-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="058c9-114">Соответствие требованиям к обмену данными</span><span class="sxs-lookup"><span data-stu-id="058c9-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="058c9-115">Политики автоматической маркировки</span><span class="sxs-lookup"><span data-stu-id="058c9-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="058c9-116">Основные части типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="058c9-117">Каждая сущность типа конфиденциальной информации определяется этими полями:</span><span class="sxs-lookup"><span data-stu-id="058c9-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="058c9-118">имя: как называется тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="058c9-119">описание: описывает, что ищет тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="058c9-120">шаблон. Шаблон определяет, что обнаруживает тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="058c9-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="058c9-121">Он состоит из следующих компонентов</span><span class="sxs-lookup"><span data-stu-id="058c9-121">It consists of the following components</span></span>
    - <span data-ttu-id="058c9-122">Основной элемент — основной элемент, который ищет тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="058c9-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="058c9-123">Это может быть **регулярное** выражение с проверкой проверки или без нее, список ключевых **слов,** словарь ключевых слов **или** **функция.**</span><span class="sxs-lookup"><span data-stu-id="058c9-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="058c9-124">Вспомогательный элемент — элементы, которые выступают в качестве подтверждающих доказательств, которые помогают в повышении уверенности в совпадении.</span><span class="sxs-lookup"><span data-stu-id="058c9-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="058c9-125">Например, ключевое слово "SSN" в непосредственной близости от номера SSN.</span><span class="sxs-lookup"><span data-stu-id="058c9-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="058c9-126">Это может быть регулярное выражение с проверкой или без проверки, списком ключевых слов, словарем ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="058c9-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="058c9-127">Уровень доверия . Уровни доверия (высокий, средний, низкий) отражают, сколько подтверждающих данных было обнаружено вместе с основным элементом.</span><span class="sxs-lookup"><span data-stu-id="058c9-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="058c9-128">Чем больше подтверждающих данных содержит элемент, тем выше уверенность в том, что соответствие элементу содержит чувствительную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="058c9-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="058c9-129">Близость — количество символов между основным и вспомогательным элементом</span><span class="sxs-lookup"><span data-stu-id="058c9-129">Proximity – Number of characters between primary and supporting element</span></span>

![Схема подтверждающего признака и интервала вероятности](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="058c9-131">Дополнительные информацию об уровнях уверенности в этом видео</span><span class="sxs-lookup"><span data-stu-id="058c9-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="058c9-132">Пример типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="058c9-133">Номер национального удостоверения (DNI) Аргентины</span><span class="sxs-lookup"><span data-stu-id="058c9-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="058c9-134">Format</span><span class="sxs-lookup"><span data-stu-id="058c9-134">Format</span></span>

<span data-ttu-id="058c9-135">Восемь цифр, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="058c9-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="058c9-136">Шаблон</span><span class="sxs-lookup"><span data-stu-id="058c9-136">Pattern</span></span>

<span data-ttu-id="058c9-137">Восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="058c9-137">Eight digits:</span></span>
- <span data-ttu-id="058c9-138">две цифры</span><span class="sxs-lookup"><span data-stu-id="058c9-138">two digits</span></span>
- <span data-ttu-id="058c9-139">период</span><span class="sxs-lookup"><span data-stu-id="058c9-139">a period</span></span>
- <span data-ttu-id="058c9-140">три цифры</span><span class="sxs-lookup"><span data-stu-id="058c9-140">three digits</span></span>
- <span data-ttu-id="058c9-141">период</span><span class="sxs-lookup"><span data-stu-id="058c9-141">a period</span></span>
- <span data-ttu-id="058c9-142">три цифры</span><span class="sxs-lookup"><span data-stu-id="058c9-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="058c9-143">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="058c9-143">Checksum</span></span>

<span data-ttu-id="058c9-144">Нет</span><span class="sxs-lookup"><span data-stu-id="058c9-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="058c9-145">Определение</span><span class="sxs-lookup"><span data-stu-id="058c9-145">Definition</span></span>

<span data-ttu-id="058c9-146">Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:</span><span class="sxs-lookup"><span data-stu-id="058c9-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="058c9-147">регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="058c9-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="058c9-148">находится ключевое слово из Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="058c9-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="058c9-149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="058c9-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="058c9-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="058c9-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="058c9-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="058c9-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="058c9-152">Identity</span><span class="sxs-lookup"><span data-stu-id="058c9-152">Identity</span></span> 
- <span data-ttu-id="058c9-153">Удостоверение национальной идентификации</span><span class="sxs-lookup"><span data-stu-id="058c9-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="058c9-154">DNI</span><span class="sxs-lookup"><span data-stu-id="058c9-154">DNI</span></span> 
- <span data-ttu-id="058c9-155">Национальный реестр лиц NIC</span><span class="sxs-lookup"><span data-stu-id="058c9-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="058c9-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="058c9-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="058c9-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="058c9-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="058c9-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="058c9-158">Identidad</span></span> 
- <span data-ttu-id="058c9-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="058c9-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="058c9-160">More on confidence levels</span><span class="sxs-lookup"><span data-stu-id="058c9-160">More on confidence levels</span></span>

<span data-ttu-id="058c9-161">В определении объекта типа конфиденциальной информации уровень доверия отражает, сколько подтверждающих данных обнаруживается в дополнение к основному элементу. </span><span class="sxs-lookup"><span data-stu-id="058c9-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="058c9-162">Чем больше подтверждающих данных содержит элемент, тем выше уверенность в том, что соответствие элементу содержит чувствительную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="058c9-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="058c9-163">Например, совпадения с высоким уровнем доверия будут содержать больше подтверждающих данных в непосредственной близости от основного элемента, в то время как совпадения с низким уровнем доверия не содержат практически никаких подтверждающих доказательств в непосредственной близости.</span><span class="sxs-lookup"><span data-stu-id="058c9-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="058c9-164">Высокий уровень доверия возвращает меньшее количество ложных срабатывай, но может привести к более ложным отрицательным результатам.</span><span class="sxs-lookup"><span data-stu-id="058c9-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="058c9-165">Низкий или средний уровень уверенности возвращает больше ложных срабатывай, но мало к нулю ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="058c9-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="058c9-166">**низкая** достоверность: значение 65, совпадают элементы будут содержать меньшее количество ложных негативов, но наиболее ложных срабатывалось.</span><span class="sxs-lookup"><span data-stu-id="058c9-166">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="058c9-167">Низкая достоверность возвращает все совпадения низкой, средней и высокой уверенности.</span><span class="sxs-lookup"><span data-stu-id="058c9-167">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="058c9-168">**средняя уверенность:** значение 75, совпадает элементов будет содержать среднее количество ложных срабатывай и ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="058c9-168">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="058c9-169">Средняя уверенность возвращает все средние и высокие совпадения доверия.</span><span class="sxs-lookup"><span data-stu-id="058c9-169">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="058c9-170">**высокая** уверенность: значение 85, совпадают элементы будут содержать меньшее количество ложных срабатывай, но наиболее ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="058c9-170">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="058c9-171">Высокая уверенность возвращает только матчи высокой уверенности.</span><span class="sxs-lookup"><span data-stu-id="058c9-171">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="058c9-172">Вы должны использовать шаблоны высокого уровня доверия с низким количеством, скажем, от пяти до десяти, и с низким уровнем доверия с более высокими подсчетами, скажем, 20 или более.</span><span class="sxs-lookup"><span data-stu-id="058c9-172">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="058c9-173">Создание пользовательских типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-173">Creating custom sensitive information types</span></span>

<span data-ttu-id="058c9-174">Создать пользовательский тип конфиденциальной информации для защиты от потери данных в Центре безопасности и соответствия требованиям можно с помощью нескольких вариантов:</span><span class="sxs-lookup"><span data-stu-id="058c9-174">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="058c9-175">**С помощью пользовательского интерфейса.** Вы можете настроить пользовательский тип конфиденциальной информации, используя пользовательский интерфейс Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="058c9-175">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="058c9-176">В этом методе можно использовать регулярные выражения, ключевые слова и словари ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="058c9-176">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="058c9-177">Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="058c9-177">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="058c9-178">**С помощью EDM.** вы можете настроить пользовательские типы конфиденциальной информации с использованием классификации на основе точного совпадения данных (EDM).</span><span class="sxs-lookup"><span data-stu-id="058c9-178">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="058c9-179">Этот метод позволяет создать динамический тип конфиденциальной информации с помощью защищенной базы данных, которую можно периодически обновлять.</span><span class="sxs-lookup"><span data-stu-id="058c9-179">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="058c9-180">См. статью [Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="058c9-180">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="058c9-181">**С помощью PowerShell.** Вы можете настроить пользовательские типы конфиденциальной информации с использованием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="058c9-181">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="058c9-182">Хотя этот метод сложнее, чем использование пользовательского интерфейса, он предоставляет дополнительные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="058c9-182">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="058c9-183">См. статью [Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="058c9-183">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="058c9-184">Улучшенные уровни доверия доступны для немедленного использования в службах по предотвращению потери данных для служб Microsoft 365, Microsoft Information Protection для служб Microsoft 365, соответствия требованиям к коммуникациям, управлению информацией и управлению записями.</span><span class="sxs-lookup"><span data-stu-id="058c9-184">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="058c9-185">Служба защиты информации Microsoft 365 теперь поддерживает в предварительный версии языки с  	набором двухбайтовых символов:</span><span class="sxs-lookup"><span data-stu-id="058c9-185">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="058c9-186">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="058c9-186">Chinese (simplified)</span></span>
> - <span data-ttu-id="058c9-187">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="058c9-187">Chinese (traditional)</span></span>
> - <span data-ttu-id="058c9-188">Корейский</span><span class="sxs-lookup"><span data-stu-id="058c9-188">Korean</span></span>
> - <span data-ttu-id="058c9-189">Японский</span><span class="sxs-lookup"><span data-stu-id="058c9-189">Japanese</span></span>

><span data-ttu-id="058c9-190">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="058c9-190">This support is available for sensitive information types.</span></span> <span data-ttu-id="058c9-191">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="058c9-191">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="058c9-192">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="058c9-192">For further information</span></span>
- [<span data-ttu-id="058c9-193">Определения объектов типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="058c9-193">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="058c9-194">Создание пользовательского типа конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="058c9-194">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="058c9-195">Создание настраиваемого типа конфиденциальной информации в PowerShell</span><span class="sxs-lookup"><span data-stu-id="058c9-195">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
