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
description: В этой статье представлен обзор типов конфиденциальной информации и их обнаружения конфиденциальных сведений, таких как номера социального обеспечения, кредитных карт или банковских счетов для идентификации конфиденциальных элементов.
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453625"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="85586-103">Дополнительные сведения о типах конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-103">Learn about sensitive information types</span></span>

<span data-ttu-id="85586-104">Определение и классификация конфиденциальных элементов, которые находятся под контролем организаций, является первым шагом в области защиты [информации.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="85586-104">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="85586-105">Microsoft 365 предоставляет три способа определения элементов, чтобы их можно было классифицировать:</span><span class="sxs-lookup"><span data-stu-id="85586-105">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="85586-106">вручную пользователями</span><span class="sxs-lookup"><span data-stu-id="85586-106">manually by users</span></span>
- <span data-ttu-id="85586-107">автоматическое распознавание шаблонов, например типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-107">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="85586-108">машинное обучение</span><span class="sxs-lookup"><span data-stu-id="85586-108">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="85586-109">Типы конфиденциальных сведений — классификаторы на основе шаблонов.</span><span class="sxs-lookup"><span data-stu-id="85586-109">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="85586-110">Они обнаруживают конфиденциальную информацию, например номера социального обеспечения, кредитной карты или банковских счетов, чтобы идентифицировать конфиденциальные элементы, см. в статьи Определения объектов типа [конфиденциальной информации.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="85586-110">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="85586-111">Типы конфиденциальной информации используются в</span><span class="sxs-lookup"><span data-stu-id="85586-111">Sensitive information types are used in</span></span>

- [<span data-ttu-id="85586-112">Политики предотвращения потери данных</span><span class="sxs-lookup"><span data-stu-id="85586-112">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="85586-113">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="85586-113">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="85586-114">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="85586-114">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="85586-115">Управление рисками, связанными с инсайдерами</span><span class="sxs-lookup"><span data-stu-id="85586-115">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="85586-116">Соответствие требованиям к обмену данными</span><span class="sxs-lookup"><span data-stu-id="85586-116">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="85586-117">Политики автоматической маркировки</span><span class="sxs-lookup"><span data-stu-id="85586-117">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [<span data-ttu-id="85586-118">Управление конфиденциальностью (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="85586-118">Privacy management (preview)</span></span>](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="85586-119">Основные части типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-119">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="85586-120">Каждая сущность типа конфиденциальной информации определяется этими полями:</span><span class="sxs-lookup"><span data-stu-id="85586-120">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="85586-121">имя: как называется тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-121">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="85586-122">описание: описывает, что ищет тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-122">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="85586-123">шаблон. Шаблон определяет, что обнаруживает тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="85586-123">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="85586-124">Он состоит из следующих компонентов</span><span class="sxs-lookup"><span data-stu-id="85586-124">It consists of the following components</span></span>
    - <span data-ttu-id="85586-125">Основной элемент — основной элемент, который ищет тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="85586-125">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="85586-126">Это может быть **регулярное** выражение с проверкой проверки или без нее, список ключевых **слов,** словарь ключевых слов **или** **функция.**</span><span class="sxs-lookup"><span data-stu-id="85586-126">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="85586-127">Вспомогательный элемент — элементы, которые выступают в качестве подтверждающих доказательств, которые помогают в повышении уверенности в совпадении.</span><span class="sxs-lookup"><span data-stu-id="85586-127">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="85586-128">Например, ключевое слово "SSN" в непосредственной близости от номера SSN.</span><span class="sxs-lookup"><span data-stu-id="85586-128">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="85586-129">Это может быть регулярное выражение с проверкой или без проверки, списком ключевых слов, словарем ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="85586-129">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="85586-130">Уровень доверия . Уровни доверия (высокий, средний, низкий) отражают, сколько подтверждающих данных было обнаружено вместе с основным элементом.</span><span class="sxs-lookup"><span data-stu-id="85586-130">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="85586-131">Чем больше подтверждающих данных содержит элемент, тем выше уверенность в том, что соответствие элементу содержит чувствительную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="85586-131">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="85586-132">Близость — количество символов между основным и вспомогательным элементом</span><span class="sxs-lookup"><span data-stu-id="85586-132">Proximity – Number of characters between primary and supporting element</span></span>

![Схема подтверждающего признака и интервала вероятности](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="85586-134">Дополнительные информацию об уровнях уверенности в этом видео</span><span class="sxs-lookup"><span data-stu-id="85586-134">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="85586-135">Пример типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-135">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="85586-136">Номер национального удостоверения (DNI) Аргентины</span><span class="sxs-lookup"><span data-stu-id="85586-136">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="85586-137">Формат</span><span class="sxs-lookup"><span data-stu-id="85586-137">Format</span></span>

<span data-ttu-id="85586-138">Восемь цифр, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="85586-138">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="85586-139">Шаблон</span><span class="sxs-lookup"><span data-stu-id="85586-139">Pattern</span></span>

<span data-ttu-id="85586-140">Восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="85586-140">Eight digits:</span></span>
- <span data-ttu-id="85586-141">две цифры</span><span class="sxs-lookup"><span data-stu-id="85586-141">two digits</span></span>
- <span data-ttu-id="85586-142">период</span><span class="sxs-lookup"><span data-stu-id="85586-142">a period</span></span>
- <span data-ttu-id="85586-143">три цифры</span><span class="sxs-lookup"><span data-stu-id="85586-143">three digits</span></span>
- <span data-ttu-id="85586-144">период</span><span class="sxs-lookup"><span data-stu-id="85586-144">a period</span></span>
- <span data-ttu-id="85586-145">три цифры</span><span class="sxs-lookup"><span data-stu-id="85586-145">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="85586-146">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="85586-146">Checksum</span></span>

<span data-ttu-id="85586-147">Нет</span><span class="sxs-lookup"><span data-stu-id="85586-147">No</span></span>

### <a name="definition"></a><span data-ttu-id="85586-148">Определение</span><span class="sxs-lookup"><span data-stu-id="85586-148">Definition</span></span>

<span data-ttu-id="85586-149">Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:</span><span class="sxs-lookup"><span data-stu-id="85586-149">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="85586-150">регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="85586-150">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="85586-151">находится ключевое слово из Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="85586-151">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85586-152">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="85586-152">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="85586-153">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="85586-153">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="85586-154">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="85586-154">Argentina National Identity number</span></span> 
- <span data-ttu-id="85586-155">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="85586-155">Identity</span></span> 
- <span data-ttu-id="85586-156">Удостоверение национальной идентификации</span><span class="sxs-lookup"><span data-stu-id="85586-156">Identification National Identity Card</span></span> 
- <span data-ttu-id="85586-157">DNI</span><span class="sxs-lookup"><span data-stu-id="85586-157">DNI</span></span> 
- <span data-ttu-id="85586-158">Национальный реестр лиц NIC</span><span class="sxs-lookup"><span data-stu-id="85586-158">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="85586-159">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="85586-159">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="85586-160">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="85586-160">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="85586-161">Identidad</span><span class="sxs-lookup"><span data-stu-id="85586-161">Identidad</span></span> 
- <span data-ttu-id="85586-162">Identificación</span><span class="sxs-lookup"><span data-stu-id="85586-162">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="85586-163">More on confidence levels</span><span class="sxs-lookup"><span data-stu-id="85586-163">More on confidence levels</span></span>

<span data-ttu-id="85586-164">В определении объекта типа конфиденциальной информации уровень доверия отражает, сколько подтверждающих данных обнаруживается в дополнение к основному элементу. </span><span class="sxs-lookup"><span data-stu-id="85586-164">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="85586-165">Чем больше подтверждающих данных содержит элемент, тем выше уверенность в том, что соответствие элементу содержит чувствительную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="85586-165">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="85586-166">Например, совпадения с высоким уровнем доверия будут содержать больше подтверждающих данных в непосредственной близости от основного элемента, в то время как совпадения с низким уровнем доверия не содержат практически никаких подтверждающих доказательств в непосредственной близости.</span><span class="sxs-lookup"><span data-stu-id="85586-166">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="85586-167">Высокий уровень доверия возвращает меньшее количество ложных срабатывай, но может привести к более ложным отрицательным результатам.</span><span class="sxs-lookup"><span data-stu-id="85586-167">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="85586-168">Низкий или средний уровень уверенности возвращает больше ложных срабатывай, но мало к нулю ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="85586-168">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="85586-169">**низкая** достоверность: значение 65, совпадают элементы будут содержать меньшее количество ложных негативов, но наиболее ложных срабатывалось.</span><span class="sxs-lookup"><span data-stu-id="85586-169">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="85586-170">Низкая достоверность возвращает все совпадения низкой, средней и высокой уверенности.</span><span class="sxs-lookup"><span data-stu-id="85586-170">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="85586-171">**средняя уверенность:** значение 75, совпадает элементов будет содержать среднее количество ложных срабатывай и ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="85586-171">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="85586-172">Средняя уверенность возвращает все средние и высокие совпадения доверия.</span><span class="sxs-lookup"><span data-stu-id="85586-172">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="85586-173">**высокая** уверенность: значение 85, совпадают элементы будут содержать меньшее количество ложных срабатывай, но наиболее ложных негативов.</span><span class="sxs-lookup"><span data-stu-id="85586-173">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="85586-174">Высокая уверенность возвращает только матчи высокой уверенности.</span><span class="sxs-lookup"><span data-stu-id="85586-174">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="85586-175">Вы должны использовать шаблоны высокого уровня доверия с низким количеством, скажем, от пяти до десяти, и с низким уровнем доверия с более высокими подсчетами, скажем, 20 или более.</span><span class="sxs-lookup"><span data-stu-id="85586-175">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="85586-176">Если у вас есть существующие политики или настраиваемые типы конфиденциальной информации (SITs), определяемые с помощью уровней уверенности на основе номеров (также знаю, как точность), они автоматически будут сопопосаться с тремя дискретными уровнями уверенности; низкая уверенность, средняя уверенность и высокая уверенность в пользовательском интерфейсе Центра обеспечения безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="85586-176">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="85586-177">Все политики с минимальной точностью или настраиваемые шаблоны SIT с уровнем доверия от 76 до 100 будут иметь высокую степень уверенности.</span><span class="sxs-lookup"><span data-stu-id="85586-177">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="85586-178">Все политики с минимальной точностью или настраиваемые шаблоны SIT с уровнем доверия от 66 до 75 будут соедему со средней степенью уверенности.</span><span class="sxs-lookup"><span data-stu-id="85586-178">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="85586-179">Все политики с минимальной точностью или настраиваемые шаблоны SIT с уровнем уверенности менее 65 или равными 65, будут иметь низкое доверие.</span><span class="sxs-lookup"><span data-stu-id="85586-179">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="85586-180">Создание пользовательских типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-180">Creating custom sensitive information types</span></span>

<span data-ttu-id="85586-181">Создать пользовательский тип конфиденциальной информации для защиты от потери данных в Центре безопасности и соответствия требованиям можно с помощью нескольких вариантов:</span><span class="sxs-lookup"><span data-stu-id="85586-181">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="85586-182">**С помощью пользовательского интерфейса.** Вы можете настроить пользовательский тип конфиденциальной информации, используя пользовательский интерфейс Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="85586-182">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="85586-183">В этом методе можно использовать регулярные выражения, ключевые слова и словари ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="85586-183">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="85586-184">Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="85586-184">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="85586-185">**С помощью EDM.** вы можете настроить пользовательские типы конфиденциальной информации с использованием классификации на основе точного совпадения данных (EDM).</span><span class="sxs-lookup"><span data-stu-id="85586-185">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="85586-186">Этот метод позволяет создать динамический тип конфиденциальной информации с помощью защищенной базы данных, которую можно периодически обновлять.</span><span class="sxs-lookup"><span data-stu-id="85586-186">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="85586-187">См. статью [Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="85586-187">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="85586-188">**С помощью PowerShell.** Вы можете настроить пользовательские типы конфиденциальной информации с использованием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85586-188">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="85586-189">Хотя этот метод сложнее, чем использование пользовательского интерфейса, он предоставляет дополнительные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="85586-189">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="85586-190">См. статью [Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="85586-190">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="85586-191">Улучшенные уровни доверия доступны для немедленного использования в области предотвращения потери данных для Microsoft 365, Microsoft Information Protection для Microsoft 365, соответствия требованиям к коммуникациям, управления информацией и управления записями.</span><span class="sxs-lookup"><span data-stu-id="85586-191">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="85586-192">Microsoft 365 Защита информации теперь поддерживает языки набора символов двойного byte для:</span><span class="sxs-lookup"><span data-stu-id="85586-192">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="85586-193">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="85586-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="85586-194">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="85586-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="85586-195">Korean</span><span class="sxs-lookup"><span data-stu-id="85586-195">Korean</span></span>
> - <span data-ttu-id="85586-196">Японский</span><span class="sxs-lookup"><span data-stu-id="85586-196">Japanese</span></span>
> 
> <span data-ttu-id="85586-197">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="85586-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="85586-198">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="85586-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="85586-199">Для выявления шаблонов, содержащих символы китайского или японского языков и однобайтовые символы, или шаблонов, содержащих элементы китайского/японского и английского языков, определите два варианта ключевого слова или регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="85586-199">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="85586-200">Например, для выявления такого ключевого слова, как "机密的document", используйте два варианта ключевого слова: один с пробелом между японским и английским текстом, а другой без пробела между японским и английским текстом.</span><span class="sxs-lookup"><span data-stu-id="85586-200">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="85586-201">Поэтому в SIT следует добавить ключевые слова "机密的 document" и "机密的document".</span><span class="sxs-lookup"><span data-stu-id="85586-201">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="85586-202">Аналогично, для выявления фразы "東京オリンピック2020" следует использовать два варианта: "東京オリンピック 2020" и "東京オリンピック2020".</span><span class="sxs-lookup"><span data-stu-id="85586-202">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="85586-p118">При создании регулярного выражения с использованием двухбайтового дефиса или двухбайтовой точки необходимо исключить оба этих символа точно так же, как из регулярных выражений исключаются дефис и точка. Пример регулярного выражения:</span><span class="sxs-lookup"><span data-stu-id="85586-p118">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="85586-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="85586-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="85586-206">Рекомендуется использовать строковую спичку вместо слова в списке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="85586-206">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="85586-207">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="85586-207">For further information</span></span>
- [<span data-ttu-id="85586-208">Определения объектов типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="85586-208">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="85586-209">Создание пользовательского типа конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="85586-209">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="85586-210">Создание настраиваемого типа конфиденциальной информации в PowerShell</span><span class="sxs-lookup"><span data-stu-id="85586-210">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="85586-211">Сведения о том, как использовать типы конфиденциальной информации для соблюдения правил конфиденциальности данных, см. в странице Развертывание защиты информации для правил конфиденциальности данных с [помощью Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="85586-211">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
