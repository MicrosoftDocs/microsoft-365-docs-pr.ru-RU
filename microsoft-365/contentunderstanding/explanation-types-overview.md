---
title: Типы объяснения
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Дополнительные сведения о типах объяснений в Microsoft SharePoint Синтекс
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295991"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="428bd-103">Общие сведения о типах объяснения</span><span class="sxs-lookup"><span data-stu-id="428bd-103">Introduction to explanation types</span></span>

<span data-ttu-id="428bd-104">Используйте объяснения, чтобы определить сведения, которые необходимо обозначить, и извлеките в документ общие сведения о моделях для Microsoft SharePoint Синтекс.</span><span class="sxs-lookup"><span data-stu-id="428bd-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="428bd-105">При создании объяснения обязательно Выбирайте тип объяснения.</span><span class="sxs-lookup"><span data-stu-id="428bd-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="428bd-106">В этой статье рассказывается о различных типах объяснений и способах их использования.</span><span class="sxs-lookup"><span data-stu-id="428bd-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![Типы объяснения](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="428bd-108">Эти типы объяснения доступны:</span><span class="sxs-lookup"><span data-stu-id="428bd-108">These explanation types are available:</span></span>

- <span data-ttu-id="428bd-109">**Список фраз**: список слов, фраз, цифр и других знаков, которые можно использовать в документе или извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="428bd-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="428bd-110">Например, Текстовая строка, **ссылающаяся на Doctor** , относится ко всем идентифицирующим документам медицинских ссылок, которые вы идентифицируете.</span><span class="sxs-lookup"><span data-stu-id="428bd-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="428bd-111">**Список "шаблон**": шаблоны списка чисел, букв или других символов, которые можно использовать для определения извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="428bd-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="428bd-112">Например, вы можете извлечь **номер телефона** ссылающегося врача из всех идентифицирующих документов, которые вы идентифицируете.</span><span class="sxs-lookup"><span data-stu-id="428bd-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="428bd-113">**Близость**: сведения о том, как близкие объяснения относятся друг к другу.</span><span class="sxs-lookup"><span data-stu-id="428bd-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="428bd-114">Например, список "шаблон *номера дома* " отправляется сразу перед списком " *название улицы* ", но без маркеров между ними (вы узнаете о маркерах далее в этой статье).</span><span class="sxs-lookup"><span data-stu-id="428bd-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="428bd-115">Список фраз</span><span class="sxs-lookup"><span data-stu-id="428bd-115">Phrase list</span></span>

<span data-ttu-id="428bd-116">Тип объяснения списка фразы обычно используется для идентификации и классификации документа с помощью модели.</span><span class="sxs-lookup"><span data-stu-id="428bd-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="428bd-117">Как описано в примере кода с именем *Doctor* , это строка слов, фраз, чисел или символов, которые постоянно используются в документах, которые вы идентифицируете.</span><span class="sxs-lookup"><span data-stu-id="428bd-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="428bd-118">В то же время вы можете добиться лучшей успеха с объяснением, если заданная вами фраза находится в согласованном расположении в документе.</span><span class="sxs-lookup"><span data-stu-id="428bd-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="428bd-119">Например, *ссылающаяся на врач* метку может быть постоянно расположена в первом абзаце документа.</span><span class="sxs-lookup"><span data-stu-id="428bd-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="428bd-120">Если для определения метки требуется чувствительность к регистру, то с помощью типа список фраз вы можете указать его в объяснении, выбрав только флажок **точный регистр** .</span><span class="sxs-lookup"><span data-stu-id="428bd-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Учет регистра](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="428bd-122">Списки шаблонов</span><span class="sxs-lookup"><span data-stu-id="428bd-122">Pattern lists</span></span>

<span data-ttu-id="428bd-123">Тип списка "шаблон" особенно полезен при создании объяснения, идентифицирующего и извлекающее сведения из документа.</span><span class="sxs-lookup"><span data-stu-id="428bd-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="428bd-124">Как правило, они представлены в разных форматах, таких как даты, Номера телефонов или номера кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="428bd-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="428bd-125">Например, дата может отображаться в различных форматах (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 января, 2020 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="428bd-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="428bd-126">Определение шаблона позволяет повысить эффективность объяснений, записывая все возможные варианты в данных, которые вы пытаетесь идентифицировать и извлечь.</span><span class="sxs-lookup"><span data-stu-id="428bd-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="428bd-127">В качестве примера **номера телефона** извлеките номер телефона для каждой ссылки врача из всех документов медицинских ссылок, которые идентифицирует модель.</span><span class="sxs-lookup"><span data-stu-id="428bd-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="428bd-128">При создании объяснения выберите тип списка шаблон, чтобы разрешить возвращение различных форматов.</span><span class="sxs-lookup"><span data-stu-id="428bd-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Список шаблонов телефонных номеров](../media/content-understanding/pattern-list.png)

<span data-ttu-id="428bd-130">В этом примере установите флажок **любая цифра из 0-9** .</span><span class="sxs-lookup"><span data-stu-id="428bd-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="428bd-131">При выборе этого значения каждое значение "0" в списке шаблонов распознается как любая цифра в диапазоне от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="428bd-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Любая цифра из 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="428bd-133">Аналогичным образом, если вы создаете список шаблонов, включающий текстовые символы, установите флажок **любая буква от a до z** .</span><span class="sxs-lookup"><span data-stu-id="428bd-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="428bd-134">При выборе этого параметра каждый символ "a", используемый в списке шаблонов, распознается как любой символ из "a" в "z".</span><span class="sxs-lookup"><span data-stu-id="428bd-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="428bd-135">Например, если вы создадите список шаблонов **дат** и хотите убедиться в том, что формат даты, такой как *1 января, 2020* , то необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="428bd-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="428bd-136">Добавьте *AAA 0, 0000* и *AAA 00, 0000* в свой список шаблонов.</span><span class="sxs-lookup"><span data-stu-id="428bd-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="428bd-137">Убедитесь, что также выбрана **любая буква от a до z** .</span><span class="sxs-lookup"><span data-stu-id="428bd-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Любая буква a – z](../media/content-understanding/any-letter.png)

<span data-ttu-id="428bd-139">Кроме того, если в вашем списке есть требования к капитализации, можно выбрать **только флажок точное заглавные прописные буквы** .</span><span class="sxs-lookup"><span data-stu-id="428bd-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="428bd-140">Например, если для первой буквы месяца требуется использовать прописные буквы, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="428bd-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="428bd-141">Добавьте *AAA 0, 0000* и *AAA 00, 0000* в свой список шаблонов.</span><span class="sxs-lookup"><span data-stu-id="428bd-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="428bd-142">Убедитесь, что выбраны **только точные прописные и строчные буквы** .</span><span class="sxs-lookup"><span data-stu-id="428bd-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Только точный регистр](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="428bd-144">Вместо того чтобы поступать со списками шаблонов вручную, используйте [библиотеку объяснений]() для использования готовых шаблонов списка шаблонов для общего списка, например *даты*, *номера телефона*, *номера кредитной карты*и т. д.</span><span class="sxs-lookup"><span data-stu-id="428bd-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="428bd-145">Компонент ранжирования с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="428bd-145">Proximity</span></span> 

<span data-ttu-id="428bd-146">Тип объяснения близлежащих элементов помогает модели определять данные с помощью определения способа закрытия другой части данных.</span><span class="sxs-lookup"><span data-stu-id="428bd-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="428bd-147">Например, в вашей модели вы определили два объяснения, которые помечают как *номер почтового адреса* клиента, так и *номер телефона*.</span><span class="sxs-lookup"><span data-stu-id="428bd-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="428bd-148">Кроме того, обратите внимание на то, что номера телефонов клиентов всегда отображаются перед номером почтового адреса.</span><span class="sxs-lookup"><span data-stu-id="428bd-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="428bd-149">Алекс Вилбурн</span><span class="sxs-lookup"><span data-stu-id="428bd-149">Alex Wilburn</span></span><br>
<span data-ttu-id="428bd-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="428bd-150">555-555-5555</span></span><br>
<span data-ttu-id="428bd-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="428bd-151">One Microsoft Way</span></span><br>
<span data-ttu-id="428bd-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="428bd-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="428bd-153">Используйте описание близости, чтобы определить, насколько далеко из объяснения номера телефона лучше определить номер почтового адреса в документах.</span><span class="sxs-lookup"><span data-stu-id="428bd-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Объяснение близости](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="428bd-155">Что такое маркеры?</span><span class="sxs-lookup"><span data-stu-id="428bd-155">What are tokens?</span></span>

<span data-ttu-id="428bd-156">Чтобы использовать тип объяснения близости, Узнайте, что такое маркер, так как количество маркеров определяет расстояние от одного объяснения до другого.</span><span class="sxs-lookup"><span data-stu-id="428bd-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="428bd-157">Маркер — это непрерывный диапазон (без пробелов и знаков препинания) букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="428bd-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="428bd-158">Пробел не является маркером.</span><span class="sxs-lookup"><span data-stu-id="428bd-158">A space is NOT a token.</span></span> <span data-ttu-id="428bd-159">Каждый знак пунктуации является маркером.</span><span class="sxs-lookup"><span data-stu-id="428bd-159">Each punctuation character is a token.</span></span> <span data-ttu-id="428bd-160">В следующей таблице приведено несколько примеров того, как определить количество маркеров в фразе.</span><span class="sxs-lookup"><span data-stu-id="428bd-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="428bd-161">Программа</span><span class="sxs-lookup"><span data-stu-id="428bd-161">Phrase</span></span>|<span data-ttu-id="428bd-162">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="428bd-162">Number of tokens</span></span>|<span data-ttu-id="428bd-163">Объяснение</span><span class="sxs-lookup"><span data-stu-id="428bd-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="428bd-164">1 </span><span class="sxs-lookup"><span data-stu-id="428bd-164">1</span></span>|<span data-ttu-id="428bd-165">Одно слово без знаков препинания и пробелов.</span><span class="sxs-lookup"><span data-stu-id="428bd-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="428bd-166">1 </span><span class="sxs-lookup"><span data-stu-id="428bd-166">1</span></span>|<span data-ttu-id="428bd-167">Номер локатора записи.</span><span class="sxs-lookup"><span data-stu-id="428bd-167">A record locator number.</span></span> <span data-ttu-id="428bd-168">Он может иметь цифры и буквы, но не имеет знаков препинания.</span><span class="sxs-lookup"><span data-stu-id="428bd-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="428bd-169">5 </span><span class="sxs-lookup"><span data-stu-id="428bd-169">5</span></span>|<span data-ttu-id="428bd-170">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="428bd-170">A phone number.</span></span> <span data-ttu-id="428bd-171">Каждый знак пунктуации является одним маркером, поэтому он будет  `425-555-5555` иметь 5 маркеров:</span><span class="sxs-lookup"><span data-stu-id="428bd-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="428bd-172">7 </span><span class="sxs-lookup"><span data-stu-id="428bd-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="428bd-173">Настройка типа объяснения близости</span><span class="sxs-lookup"><span data-stu-id="428bd-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="428bd-174">В этом примере настраивается параметр близости, чтобы можно было определить диапазон количества маркеров, на которые объясняется номер *телефона* , из объяснения *номера улицы* .</span><span class="sxs-lookup"><span data-stu-id="428bd-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="428bd-175">Необходимо убедиться, что в качестве минимального диапазона задано значение 0, поскольку между номером телефона и номером улицы нет маркеров.</span><span class="sxs-lookup"><span data-stu-id="428bd-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="428bd-176">Однако некоторые номера телефонов в примерах документов добавляются вместе с *(Mobile)*.</span><span class="sxs-lookup"><span data-stu-id="428bd-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="428bd-177">Пользователя Nestor вилке</span><span class="sxs-lookup"><span data-stu-id="428bd-177">Nestor Wilke</span></span><br>
<span data-ttu-id="428bd-178">111-111-1111 (мобильный телефон)</span><span class="sxs-lookup"><span data-stu-id="428bd-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="428bd-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="428bd-179">One Microsoft Way</span></span><br>
<span data-ttu-id="428bd-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="428bd-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="428bd-181">В *(Mobile)* есть три токена:</span><span class="sxs-lookup"><span data-stu-id="428bd-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="428bd-182">Программа</span><span class="sxs-lookup"><span data-stu-id="428bd-182">Phrase</span></span>|<span data-ttu-id="428bd-183">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="428bd-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="428bd-184">(</span><span class="sxs-lookup"><span data-stu-id="428bd-184">(</span></span>|<span data-ttu-id="428bd-185">1 </span><span class="sxs-lookup"><span data-stu-id="428bd-185">1</span></span>|
|<span data-ttu-id="428bd-186">связь</span><span class="sxs-lookup"><span data-stu-id="428bd-186">mobile</span></span>|<span data-ttu-id="428bd-187">2 </span><span class="sxs-lookup"><span data-stu-id="428bd-187">2</span></span>|
|<span data-ttu-id="428bd-188">)</span><span class="sxs-lookup"><span data-stu-id="428bd-188">)</span></span>|<span data-ttu-id="428bd-189">3 </span><span class="sxs-lookup"><span data-stu-id="428bd-189">3</span></span>|

<span data-ttu-id="428bd-190">Настройте параметр близости от 0 до 3.</span><span class="sxs-lookup"><span data-stu-id="428bd-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Пример сходства](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="428bd-192">Использование библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="428bd-192">Use the explanation library</span></span>

<span data-ttu-id="428bd-193">Несмотря на то, что вы можете вручную добавлять различные значения списка шаблонов для вашего объяснения, значительно упрощается использование готовых шаблонов, предоставленных в библиотеке объяснений.</span><span class="sxs-lookup"><span data-stu-id="428bd-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="428bd-194">Например, вместо того чтобы вручную добавлять все варианты для *Date*, используйте шаблон списка шаблон для параметра *Дата*, который уже включает ряд значений шаблона:</span><span class="sxs-lookup"><span data-stu-id="428bd-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Библиотека объяснений](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="428bd-196">Библиотека объяснений содержит ряд часто используемых объяснений в списке шаблонов, в том числе:</span><span class="sxs-lookup"><span data-stu-id="428bd-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="428bd-197">Date</span><span class="sxs-lookup"><span data-stu-id="428bd-197">Date</span></span></br>
- <span data-ttu-id="428bd-198">Дата (число)</span><span class="sxs-lookup"><span data-stu-id="428bd-198">Date (numeric)</span></span></br>
- <span data-ttu-id="428bd-199">Time</span><span class="sxs-lookup"><span data-stu-id="428bd-199">Time</span></span></br>
- <span data-ttu-id="428bd-200">Числовой</span><span class="sxs-lookup"><span data-stu-id="428bd-200">Number</span></span></br>
- <span data-ttu-id="428bd-201">Номер телефона</span><span class="sxs-lookup"><span data-stu-id="428bd-201">Phone number</span></span></br>
- <span data-ttu-id="428bd-202">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="428bd-202">Zip code</span></span></br>
- <span data-ttu-id="428bd-203">Первое слово предложения</span><span class="sxs-lookup"><span data-stu-id="428bd-203">First word of sentence</span></span></br>
- <span data-ttu-id="428bd-204">Кредитная карта</span><span class="sxs-lookup"><span data-stu-id="428bd-204">Credit card</span></span></br>
- <span data-ttu-id="428bd-205">Номер социального страхования</span><span class="sxs-lookup"><span data-stu-id="428bd-205">Social security number</span></span></br>

<span data-ttu-id="428bd-206">Обратите внимание, что библиотека объяснений также включает шаблоны для объяснений со списками фраз, в том числе:</span><span class="sxs-lookup"><span data-stu-id="428bd-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="428bd-207">Конец предложения</span><span class="sxs-lookup"><span data-stu-id="428bd-207">End of sentence</span></span>
- <span data-ttu-id="428bd-208">Денежный</span><span class="sxs-lookup"><span data-stu-id="428bd-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="428bd-209">Использование шаблона из библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="428bd-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="428bd-210">В разделе **объяснения** на странице **обучение** модели выберите **создать**, а затем выберите **из шаблона**.</span><span class="sxs-lookup"><span data-stu-id="428bd-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Создание из шаблона](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="428bd-212">На странице " **объяснения шаблонов** " выберите объяснение, которое необходимо использовать, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="428bd-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Выбор шаблона](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="428bd-214">Сведения о выбранном шаблоне будут отображаться на странице **Создание объяснения** .</span><span class="sxs-lookup"><span data-stu-id="428bd-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="428bd-215">При необходимости измените имя объяснения и добавьте или удалите элементы из списка шаблон.</span><span class="sxs-lookup"><span data-stu-id="428bd-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Изменение шаблона](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="428bd-217">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="428bd-217">When finished, select **Save**.</span></span>
