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
ms.openlocfilehash: 91366e8f255d277d4d40de4c4cd3330283da718c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166454"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="40ee6-102">Дополнительные сведения о типах конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-102">Learn about sensitive information types</span></span>

<span data-ttu-id="40ee6-103">Определение и классификация конфиденциальных элементов, которые находятся под контролем вашей организации, — это первый шаг в области [защиты информации.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="40ee6-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="40ee6-104">Microsoft 365 предоставляет три способа определения элементов, чтобы их можно было классифицировать:</span><span class="sxs-lookup"><span data-stu-id="40ee6-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="40ee6-105">вручную пользователями</span><span class="sxs-lookup"><span data-stu-id="40ee6-105">manually by users</span></span>
- <span data-ttu-id="40ee6-106">автоматическое распознавание шаблонов, например типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="40ee6-107">машинное обучение</span><span class="sxs-lookup"><span data-stu-id="40ee6-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="40ee6-108">Типы конфиденциальной информации — это классификаторы на основе шаблонов.</span><span class="sxs-lookup"><span data-stu-id="40ee6-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="40ee6-109">Они обнаруживают конфиденциальную информацию, например номера социального страхования, кредитной карты или банковского счета, для идентификации конфиденциальных элементов. См. определения объектов типов [конфиденциальной информации](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="40ee6-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="40ee6-110">Типы конфиденциальной информации используются в</span><span class="sxs-lookup"><span data-stu-id="40ee6-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="40ee6-111">Политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="40ee6-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="40ee6-112">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="40ee6-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="40ee6-113">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="40ee6-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="40ee6-114">Соответствие требованиям к обмену данными</span><span class="sxs-lookup"><span data-stu-id="40ee6-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="40ee6-115">Политики автоматической маркировки</span><span class="sxs-lookup"><span data-stu-id="40ee6-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="40ee6-116">Основные части типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="40ee6-117">Каждая сущность типа конфиденциальной информации определяется этими полями:</span><span class="sxs-lookup"><span data-stu-id="40ee6-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="40ee6-118">name: как ссылается тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="40ee6-119">description: описывает, что ищет тип конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="40ee6-120">шаблон: шаблон определяет, что обнаруживает тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="40ee6-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="40ee6-121">Он состоит из следующих компонентов</span><span class="sxs-lookup"><span data-stu-id="40ee6-121">It consists of the following components</span></span>
    - <span data-ttu-id="40ee6-122">Основной элемент — основной элемент, который ищет тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="40ee6-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="40ee6-123">Это может быть **регулярное** выражение с проверкой контрольнойum или без нее, список ключевых **слов,** словарь ключевых слов **или** **функция.**</span><span class="sxs-lookup"><span data-stu-id="40ee6-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="40ee6-124">Вспомогательный элемент — элементы, которые выступают в качестве вспомогательного свидетельства, которые помогают увеличить достоверность совпадения.</span><span class="sxs-lookup"><span data-stu-id="40ee6-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="40ee6-125">Например, ключевое слово "SSN" находится рядом с номером SSN.</span><span class="sxs-lookup"><span data-stu-id="40ee6-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="40ee6-126">Это может быть регулярное выражение с проверкой контрольных объемов, списком ключевых слов и словарем ключевых слов или без него.</span><span class="sxs-lookup"><span data-stu-id="40ee6-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="40ee6-127">Уровень уверенности — уровни уверенности (высокий, средний, низкий) отражают, сколько вспомогательных признаков было обнаружено вместе с основным элементом.</span><span class="sxs-lookup"><span data-stu-id="40ee6-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="40ee6-128">Чем больше подтверждающих признаков содержит элемент, тем выше уверенность в том, что совпадение содержит конфиденциальную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="40ee6-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="40ee6-129">Бесконтактность — количество символов между основным и вспомогательным элементом</span><span class="sxs-lookup"><span data-stu-id="40ee6-129">Proximity – Number of characters between primary and supporting element</span></span>

![Схема подтверждающего признака и интервала вероятности](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="40ee6-131">Узнайте больше об уровнях уверенности в этом видео</span><span class="sxs-lookup"><span data-stu-id="40ee6-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="40ee6-132">Пример типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="40ee6-133">Номер удостоверения личности для Аргентины</span><span class="sxs-lookup"><span data-stu-id="40ee6-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="40ee6-134">Format</span><span class="sxs-lookup"><span data-stu-id="40ee6-134">Format</span></span>

<span data-ttu-id="40ee6-135">Восемь цифр, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="40ee6-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="40ee6-136">Шаблон</span><span class="sxs-lookup"><span data-stu-id="40ee6-136">Pattern</span></span>

<span data-ttu-id="40ee6-137">Восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="40ee6-137">Eight digits:</span></span>
- <span data-ttu-id="40ee6-138">две цифры</span><span class="sxs-lookup"><span data-stu-id="40ee6-138">two digits</span></span>
- <span data-ttu-id="40ee6-139">точка</span><span class="sxs-lookup"><span data-stu-id="40ee6-139">a period</span></span>
- <span data-ttu-id="40ee6-140">три цифры</span><span class="sxs-lookup"><span data-stu-id="40ee6-140">three digits</span></span>
- <span data-ttu-id="40ee6-141">точка</span><span class="sxs-lookup"><span data-stu-id="40ee6-141">a period</span></span>
- <span data-ttu-id="40ee6-142">три цифры</span><span class="sxs-lookup"><span data-stu-id="40ee6-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="40ee6-143">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="40ee6-143">Checksum</span></span>

<span data-ttu-id="40ee6-144">Нет</span><span class="sxs-lookup"><span data-stu-id="40ee6-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="40ee6-145">Определение</span><span class="sxs-lookup"><span data-stu-id="40ee6-145">Definition</span></span>

<span data-ttu-id="40ee6-146">Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:</span><span class="sxs-lookup"><span data-stu-id="40ee6-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="40ee6-147">регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="40ee6-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="40ee6-148">находится ключевое слово из Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="40ee6-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="40ee6-149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="40ee6-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="40ee6-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="40ee6-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="40ee6-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="40ee6-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="40ee6-152">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="40ee6-152">Identity</span></span> 
- <span data-ttu-id="40ee6-153">Идентификация национального удостоверения личности</span><span class="sxs-lookup"><span data-stu-id="40ee6-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="40ee6-154">DNI</span><span class="sxs-lookup"><span data-stu-id="40ee6-154">DNI</span></span> 
- <span data-ttu-id="40ee6-155">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="40ee6-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="40ee6-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="40ee6-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="40ee6-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="40ee6-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="40ee6-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="40ee6-158">Identidad</span></span> 
- <span data-ttu-id="40ee6-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="40ee6-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="40ee6-160">Подробнее об уровнях уверенности</span><span class="sxs-lookup"><span data-stu-id="40ee6-160">More on confidence levels</span></span>

<span data-ttu-id="40ee6-161">В определении сущности типа конфиденциальной информации уровень достоверности отражает, сколько вспомогательного свидетельства обнаруживается в дополнение к основному элементу. </span><span class="sxs-lookup"><span data-stu-id="40ee6-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="40ee6-162">Чем больше подтверждающих признаков содержит элемент, тем выше уверенность в том, что совпадение содержит конфиденциальную информацию, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="40ee6-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="40ee6-163">Например, совпадения с высоким уровнем достоверности будут содержать больше вспомогательных свидетельств в непосредственной близости от основного элемента, а совпадения с низким уровнем достоверности будут содержать практически отсутствие вспомогательных признаков в непосредственной близости.</span><span class="sxs-lookup"><span data-stu-id="40ee6-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="40ee6-164">Высокий уровень уверенности возвращает меньшее количество ложных срабатывай, но может привести к более ложным отрицательным результатам.</span><span class="sxs-lookup"><span data-stu-id="40ee6-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="40ee6-165">Низкий или средний уровень уверенности возвращает больше ложных срабатывай, но меньшее количество до нуля ложных отрицательных результатов.</span><span class="sxs-lookup"><span data-stu-id="40ee6-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="40ee6-166">**низкая достоверность:** значение 65, совместимые элементы будут содержать меньшее количество ложных отрицательных результатов, но больше всего ложных срабатывай.</span><span class="sxs-lookup"><span data-stu-id="40ee6-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="40ee6-167">**средняя достоверность:** значение 75, совпадение элементов будет содержать среднее количество ложных срабатывай и ложных отрицательных результатов.</span><span class="sxs-lookup"><span data-stu-id="40ee6-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="40ee6-168">**высокая достоверность:** значение 85, совместимые элементы будут содержать меньшее количество ложных срабатывай, но больше всего ложных отрицательных результатов.</span><span class="sxs-lookup"><span data-stu-id="40ee6-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="40ee6-169">Следует использовать шаблоны высокого уровня достоверности с низким количеством, скажем, от пяти до десяти, и шаблонами низкой достоверности с более высокими, скажем, 20 или более.</span><span class="sxs-lookup"><span data-stu-id="40ee6-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="40ee6-170">Создание пользовательских типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="40ee6-171">Создать пользовательский тип конфиденциальной информации для защиты от потери данных в Центре безопасности и соответствия требованиям можно с помощью нескольких вариантов:</span><span class="sxs-lookup"><span data-stu-id="40ee6-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="40ee6-172">**С помощью пользовательского интерфейса.** Вы можете настроить пользовательский тип конфиденциальной информации, используя пользовательский интерфейс Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="40ee6-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="40ee6-173">В этом методе можно использовать регулярные выражения, ключевые слова и словари ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="40ee6-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="40ee6-174">Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="40ee6-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="40ee6-175">**С помощью EDM.** вы можете настроить пользовательские типы конфиденциальной информации с использованием классификации на основе точного совпадения данных (EDM).</span><span class="sxs-lookup"><span data-stu-id="40ee6-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="40ee6-176">Этот метод позволяет создать динамический тип конфиденциальной информации с помощью защищенной базы данных, которую можно периодически обновлять.</span><span class="sxs-lookup"><span data-stu-id="40ee6-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="40ee6-177">См. статью [Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="40ee6-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="40ee6-178">**С помощью PowerShell.** Вы можете настроить пользовательские типы конфиденциальной информации с использованием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40ee6-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="40ee6-179">Хотя этот метод сложнее, чем использование пользовательского интерфейса, он предоставляет дополнительные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40ee6-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="40ee6-180">См. статью [Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="40ee6-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="40ee6-181">Улучшенные уровни уверенности доступны для немедленного использования в службах Защиты от потери данных для служб Microsoft 365, Microsoft Information Protection для служб Microsoft 365, соответствия коммуникациям, управлении информацией и управлении записями.</span><span class="sxs-lookup"><span data-stu-id="40ee6-181">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="40ee6-182">Служба защиты информации Microsoft 365 теперь поддерживает в предварительный версии языки с  	набором двухбайтовых символов:</span><span class="sxs-lookup"><span data-stu-id="40ee6-182">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="40ee6-183">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="40ee6-183">Chinese (simplified)</span></span>
> - <span data-ttu-id="40ee6-184">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="40ee6-184">Chinese (traditional)</span></span>
> - <span data-ttu-id="40ee6-185">Корейский</span><span class="sxs-lookup"><span data-stu-id="40ee6-185">Korean</span></span>
> - <span data-ttu-id="40ee6-186">Японский</span><span class="sxs-lookup"><span data-stu-id="40ee6-186">Japanese</span></span>

><span data-ttu-id="40ee6-187">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="40ee6-187">This support is available for sensitive information types.</span></span> <span data-ttu-id="40ee6-188">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="40ee6-188">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="40ee6-189">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="40ee6-189">For further information</span></span>
- [<span data-ttu-id="40ee6-190">Определения объектов типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="40ee6-190">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="40ee6-191">Создание пользовательского типа конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="40ee6-191">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="40ee6-192">Создание пользовательского типа конфиденциальной информации в PowerShell</span><span class="sxs-lookup"><span data-stu-id="40ee6-192">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
