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
ms.openlocfilehash: 3f64b981b60db9f9089af0555e4bf734864913b9
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300385"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="58bca-102">Дополнительные сведения о типах конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-102">Learn about sensitive information types</span></span>

<span data-ttu-id="58bca-103">Определение и классификация конфиденциальных элементов, которые находятся под контролем организаций, является первым шагом в области защиты [информации.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="58bca-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="58bca-104">Microsoft 365 предоставляет три способа определения элементов, чтобы их можно было классифицировать:</span><span class="sxs-lookup"><span data-stu-id="58bca-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="58bca-105">вручную пользователями</span><span class="sxs-lookup"><span data-stu-id="58bca-105">manually by users</span></span>
- <span data-ttu-id="58bca-106">автоматическое распознавание шаблонов, например типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="58bca-107">машинное обучение</span><span class="sxs-lookup"><span data-stu-id="58bca-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="58bca-108">Типы конфиденциальных сведений — классификаторы на основе шаблонов.</span><span class="sxs-lookup"><span data-stu-id="58bca-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="58bca-109">Они обнаруживают конфиденциальную информацию, например номера социального обеспечения, кредитной карты или банковских счетов, чтобы идентифицировать конфиденциальные элементы, см. в статьи Определения объектов типа [конфиденциальной информации.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="58bca-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="58bca-110">Типы конфиденциальной информации используются в</span><span class="sxs-lookup"><span data-stu-id="58bca-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="58bca-111">Политики предотвращения потери данных</span><span class="sxs-lookup"><span data-stu-id="58bca-111">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md) 
- [<span data-ttu-id="58bca-112">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="58bca-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="58bca-113">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="58bca-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="58bca-114">Управление внутренними рисками</span><span class="sxs-lookup"><span data-stu-id="58bca-114">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="58bca-115">Соответствие требованиям к обмену данными</span><span class="sxs-lookup"><span data-stu-id="58bca-115">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="58bca-116">Политики автоматической маркировки</span><span class="sxs-lookup"><span data-stu-id="58bca-116">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="58bca-117">Основные части типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-117">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="58bca-118">Каждая сущность типа конфиденциальной информации определяется этими полями:</span><span class="sxs-lookup"><span data-stu-id="58bca-118">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="58bca-119">имя: как называется тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-119">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="58bca-120">описание: описывает, что ищет тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-120">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="58bca-121">шаблон. Шаблон определяет, что обнаруживает тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="58bca-121">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="58bca-122">Он состоит из следующих компонентов</span><span class="sxs-lookup"><span data-stu-id="58bca-122">It consists of the following components</span></span>
    - <span data-ttu-id="58bca-123">Основной элемент — основной элемент, который ищет тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="58bca-123">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="58bca-124">Это может быть **регулярное** выражение с проверкой проверки или без нее, список ключевых **слов,** словарь ключевых слов **или** **функция.**</span><span class="sxs-lookup"><span data-stu-id="58bca-124">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="58bca-125">Вспомогательный элемент — элементы, которые выступают в качестве подтверждающих доказательств, которые помогают в повышении уверенности в совпадении.</span><span class="sxs-lookup"><span data-stu-id="58bca-125">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="58bca-126">Например, ключевое слово "SSN" в непосредственной близости от номера SSN.</span><span class="sxs-lookup"><span data-stu-id="58bca-126">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="58bca-127">Это может быть регулярное выражение с проверкой или без проверки, списком ключевых слов, словарем ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="58bca-127">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="58bca-128">Уровень доверия . Уровни доверия (высокий, средний, низкий) отражают, сколько подтверждающих данных было обнаружено вместе с основным элементом.</span><span class="sxs-lookup"><span data-stu-id="58bca-128">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="58bca-129">Чем больше подтверждающих данных содержит элемент, тем выше уверенность в том, что соответствие элементу содержит чувствительную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="58bca-129">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="58bca-130">Близость — количество символов между основным и вспомогательным элементом</span><span class="sxs-lookup"><span data-stu-id="58bca-130">Proximity – Number of characters between primary and supporting element</span></span>

![Схема подтверждающего признака и интервала вероятности](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="58bca-132">Дополнительные информацию об уровнях уверенности в этом видео</span><span class="sxs-lookup"><span data-stu-id="58bca-132">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="58bca-133">Пример типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-133">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="58bca-134">Номер национального удостоверения (DNI) Аргентины</span><span class="sxs-lookup"><span data-stu-id="58bca-134">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="58bca-135">Формат</span><span class="sxs-lookup"><span data-stu-id="58bca-135">Format</span></span>

<span data-ttu-id="58bca-136">Восемь цифр, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="58bca-136">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="58bca-137">Шаблон</span><span class="sxs-lookup"><span data-stu-id="58bca-137">Pattern</span></span>

<span data-ttu-id="58bca-138">Восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="58bca-138">Eight digits:</span></span>
- <span data-ttu-id="58bca-139">две цифры</span><span class="sxs-lookup"><span data-stu-id="58bca-139">two digits</span></span>
- <span data-ttu-id="58bca-140">период</span><span class="sxs-lookup"><span data-stu-id="58bca-140">a period</span></span>
- <span data-ttu-id="58bca-141">три цифры</span><span class="sxs-lookup"><span data-stu-id="58bca-141">three digits</span></span>
- <span data-ttu-id="58bca-142">период</span><span class="sxs-lookup"><span data-stu-id="58bca-142">a period</span></span>
- <span data-ttu-id="58bca-143">три цифры</span><span class="sxs-lookup"><span data-stu-id="58bca-143">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="58bca-144">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="58bca-144">Checksum</span></span>

<span data-ttu-id="58bca-145">Нет</span><span class="sxs-lookup"><span data-stu-id="58bca-145">No</span></span>

### <a name="definition"></a><span data-ttu-id="58bca-146">Определение</span><span class="sxs-lookup"><span data-stu-id="58bca-146">Definition</span></span>

<span data-ttu-id="58bca-147">Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:</span><span class="sxs-lookup"><span data-stu-id="58bca-147">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="58bca-148">регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="58bca-148">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="58bca-149">находится ключевое слово из Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="58bca-149">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="58bca-150">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="58bca-150">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="58bca-151">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="58bca-151">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="58bca-152">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="58bca-152">Argentina National Identity number</span></span> 
- <span data-ttu-id="58bca-153">Identity</span><span class="sxs-lookup"><span data-stu-id="58bca-153">Identity</span></span> 
- <span data-ttu-id="58bca-154">Удостоверение национальной идентификации</span><span class="sxs-lookup"><span data-stu-id="58bca-154">Identification National Identity Card</span></span> 
- <span data-ttu-id="58bca-155">DNI</span><span class="sxs-lookup"><span data-stu-id="58bca-155">DNI</span></span> 
- <span data-ttu-id="58bca-156">Национальный реестр лиц NIC</span><span class="sxs-lookup"><span data-stu-id="58bca-156">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="58bca-157">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="58bca-157">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="58bca-158">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="58bca-158">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="58bca-159">Identidad</span><span class="sxs-lookup"><span data-stu-id="58bca-159">Identidad</span></span> 
- <span data-ttu-id="58bca-160">Identificación</span><span class="sxs-lookup"><span data-stu-id="58bca-160">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="58bca-161">More on confidence levels</span><span class="sxs-lookup"><span data-stu-id="58bca-161">More on confidence levels</span></span>

<span data-ttu-id="58bca-162">В определении объекта типа конфиденциальной информации уровень доверия отражает, сколько подтверждающих данных обнаруживается в дополнение к основному элементу. </span><span class="sxs-lookup"><span data-stu-id="58bca-162">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="58bca-163">Чем больше подтверждающих данных содержит элемент, тем выше уверенность в том, что соответствие элементу содержит чувствительную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="58bca-163">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="58bca-164">Например, совпадения с высоким уровнем доверия будут содержать больше подтверждающих данных в непосредственной близости от основного элемента, в то время как совпадения с низким уровнем доверия не содержат практически никаких подтверждающих доказательств в непосредственной близости.</span><span class="sxs-lookup"><span data-stu-id="58bca-164">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="58bca-165">Высокий уровень доверия возвращает меньшее количество ложных срабатывай, но может привести к более ложным отрицательным результатам.</span><span class="sxs-lookup"><span data-stu-id="58bca-165">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="58bca-166">Низкий или средний уровень уверенности возвращает больше ложных срабатывай, но мало к нулю ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="58bca-166">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="58bca-167">**низкая** достоверность: значение 65, совпадают элементы будут содержать меньшее количество ложных негативов, но наиболее ложных срабатывалось.</span><span class="sxs-lookup"><span data-stu-id="58bca-167">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="58bca-168">Низкая достоверность возвращает все совпадения низкой, средней и высокой уверенности.</span><span class="sxs-lookup"><span data-stu-id="58bca-168">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="58bca-169">**средняя уверенность:** значение 75, совпадает элементов будет содержать среднее количество ложных срабатывай и ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="58bca-169">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="58bca-170">Средняя уверенность возвращает все средние и высокие совпадения доверия.</span><span class="sxs-lookup"><span data-stu-id="58bca-170">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="58bca-171">**высокая** уверенность: значение 85, совпадают элементы будут содержать меньшее количество ложных срабатывай, но наиболее ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="58bca-171">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="58bca-172">Высокая уверенность возвращает только матчи высокой уверенности.</span><span class="sxs-lookup"><span data-stu-id="58bca-172">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="58bca-173">Вы должны использовать шаблоны высокого уровня доверия с низким количеством, скажем, от пяти до десяти, и с низким уровнем доверия с более высокими подсчетами, скажем, 20 или более.</span><span class="sxs-lookup"><span data-stu-id="58bca-173">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="58bca-174">Если у вас есть существующие политики или настраиваемые типы конфиденциальной информации (SITs), определяемые с помощью уровней уверенности на основе номеров (также знаю, как точность), они автоматически будут сопопосаться с тремя дискретными уровнями уверенности; низкая уверенность, средняя уверенность и высокая уверенность в пользовательском интерфейсе Центра обеспечения безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="58bca-174">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="58bca-175">Все политики с минимальной точностью или настраиваемые шаблоны SIT с уровнем доверия от 76 до 100 будут иметь высокую степень уверенности.</span><span class="sxs-lookup"><span data-stu-id="58bca-175">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="58bca-176">Все политики с минимальной точностью или настраиваемые шаблоны SIT с уровнем доверия от 66 до 75 будут соедему со средней степенью уверенности.</span><span class="sxs-lookup"><span data-stu-id="58bca-176">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="58bca-177">Все политики с минимальной точностью или настраиваемые шаблоны SIT с уровнем уверенности менее 65 или равными 65, будут иметь низкое доверие.</span><span class="sxs-lookup"><span data-stu-id="58bca-177">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="58bca-178">Создание пользовательских типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-178">Creating custom sensitive information types</span></span>

<span data-ttu-id="58bca-179">Создать пользовательский тип конфиденциальной информации для защиты от потери данных в Центре безопасности и соответствия требованиям можно с помощью нескольких вариантов:</span><span class="sxs-lookup"><span data-stu-id="58bca-179">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="58bca-180">**С помощью пользовательского интерфейса.** Вы можете настроить пользовательский тип конфиденциальной информации, используя пользовательский интерфейс Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="58bca-180">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="58bca-181">В этом методе можно использовать регулярные выражения, ключевые слова и словари ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="58bca-181">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="58bca-182">Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="58bca-182">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="58bca-183">**С помощью EDM.** вы можете настроить пользовательские типы конфиденциальной информации с использованием классификации на основе точного совпадения данных (EDM).</span><span class="sxs-lookup"><span data-stu-id="58bca-183">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="58bca-184">Этот метод позволяет создать динамический тип конфиденциальной информации с помощью защищенной базы данных, которую можно периодически обновлять.</span><span class="sxs-lookup"><span data-stu-id="58bca-184">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="58bca-185">См. статью [Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="58bca-185">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="58bca-186">**С помощью PowerShell.** Вы можете настроить пользовательские типы конфиденциальной информации с использованием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58bca-186">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="58bca-187">Хотя этот метод сложнее, чем использование пользовательского интерфейса, он предоставляет дополнительные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="58bca-187">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="58bca-188">См. статью [Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="58bca-188">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="58bca-189">Улучшенные уровни доверия доступны для немедленного использования в области предотвращения потери данных для Microsoft 365, Microsoft Information Protection для Microsoft 365, соответствия требованиям к коммуникациям, управления информацией и управления записями.</span><span class="sxs-lookup"><span data-stu-id="58bca-189">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="58bca-190">Microsoft 365 Защита информации теперь поддерживает языки набора символов двойного byte для:</span><span class="sxs-lookup"><span data-stu-id="58bca-190">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="58bca-191">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="58bca-191">Chinese (simplified)</span></span>
> - <span data-ttu-id="58bca-192">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="58bca-192">Chinese (traditional)</span></span>
> - <span data-ttu-id="58bca-193">Корейский</span><span class="sxs-lookup"><span data-stu-id="58bca-193">Korean</span></span>
> - <span data-ttu-id="58bca-194">Японский</span><span class="sxs-lookup"><span data-stu-id="58bca-194">Japanese</span></span>
> 
> <span data-ttu-id="58bca-195">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="58bca-195">This support is available for sensitive information types.</span></span> <span data-ttu-id="58bca-196">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="58bca-196">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="58bca-197">Для выявления шаблонов, содержащих символы китайского или японского языков и однобайтовые символы, или шаблонов, содержащих элементы китайского/японского и английского языков, определите два варианта ключевого слова или регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="58bca-197">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="58bca-198">Например, для выявления такого ключевого слова, как "机密的document", используйте два варианта ключевого слова: один с пробелом между японским и английским текстом, а другой без пробела между японским и английским текстом.</span><span class="sxs-lookup"><span data-stu-id="58bca-198">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="58bca-199">Поэтому в SIT следует добавить ключевые слова "机密的 document" и "机密的document".</span><span class="sxs-lookup"><span data-stu-id="58bca-199">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="58bca-200">Аналогично, для выявления фразы "東京オリンピック2020" следует использовать два варианта: "東京オリンピック 2020" и "東京オリンピック2020".</span><span class="sxs-lookup"><span data-stu-id="58bca-200">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="58bca-201">При создании регулярного выражения с использованием двухбайтового дефиса или двухбайтовой точки необходимо исключить оба этих символа точно так же, как из регулярных выражений исключаются дефис и точка.</span><span class="sxs-lookup"><span data-stu-id="58bca-201">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex.</span></span> <span data-ttu-id="58bca-202">Пример регулярного выражения:</span><span class="sxs-lookup"><span data-stu-id="58bca-202">Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="58bca-203">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="58bca-203">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="58bca-204">Рекомендуется использовать строковую спичку вместо слова в списке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="58bca-204">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="58bca-205">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="58bca-205">For further information</span></span>
- [<span data-ttu-id="58bca-206">Определения объектов типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="58bca-206">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="58bca-207">Создание пользовательского типа конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="58bca-207">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="58bca-208">Создание настраиваемого типа конфиденциальной информации в PowerShell</span><span class="sxs-lookup"><span data-stu-id="58bca-208">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="58bca-209">Сведения о том, как использовать типы конфиденциальной информации для соблюдения правил конфиденциальности данных, см. в странице Развертывание защиты информации для правил конфиденциальности данных с [помощью Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="58bca-209">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
