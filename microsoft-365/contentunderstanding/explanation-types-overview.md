---
title: Типы объяснений
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Дополнительные сведения о типах объяснений в Microsoft SharePoint Syntex
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087647"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="b47d5-103">Введение в типы объяснений</span><span class="sxs-lookup"><span data-stu-id="b47d5-103">Introduction to explanation types</span></span>

<span data-ttu-id="b47d5-p101">Объяснения помогают определить информацию, которую вы хотите пометить и извлечь в своих моделях осмысления документации в Microsoft SharePoint Syntex. При создании объяснения следует выбрать тип объяснения. Данная статья поможет вам узнать о разных типах объяснений и о том, как они используются.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p101">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex. When creating an explanation, you need to select an explanation type. This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Типы объяснений](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="b47d5-108">Доступны следующие типы объяснений:</span><span class="sxs-lookup"><span data-stu-id="b47d5-108">These explanation types are available:</span></span>

- <span data-ttu-id="b47d5-p102">**Список фраз**: список слов, фраз, цифр или других символов, которые можно использовать в документе или в извлекаемой информации. Например, текстовая строка **Направляющий врач** содержится во всех документах с медицинскими направлениями, которые вы идентифицируете.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p102">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting. For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="b47d5-p103">**Список шаблонов**: список шаблонов цифр, букв или других символов, которые можно использовать для идентификации извлекаемой информации. Например, можно извлечь **Номер телефона** направляющего врача из всех документов с медицинскими направлениями, которые вы идентифицируете.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p103">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting. For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="b47d5-p104">**Расстояние**: описывает, насколько близки объяснения. Например, список шаблонов *номер дома* идет непосредственно перед списком фраз *название улицы*, без каких-либо маркеров между ними (сведения о маркерах приводятся далее в этой статье). Для использования типа расстояния необходимо, чтобы в модели было как минимум два объяснения, иначе эта функция будет отключена.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p104">**Proximity**: Describes how close explanations are to each other. For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article). Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="b47d5-116">Список фраз</span><span class="sxs-lookup"><span data-stu-id="b47d5-116">Phrase list</span></span>

<span data-ttu-id="b47d5-p105">Список фраз — это тип объяснения, который обычно используется, чтобы идентифицировать и классифицировать документ через вашу модель. Как показано в примере с меткой *Направляющий врач*, это строка, состоящая из слов, фраз, цифр или символов, которая постоянно встречается в идентифицируемых документах.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p105">A phrase list explanation type is typically used to identify and classify a document through your model. As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="b47d5-p106">Лучших результатов можно добиться, если считываемая фраза находится в одном месте во всех документах, хотя это и не является требованием. Например, метка *Направляющий врач* может находиться в первом абзаце всех документов.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p106">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document. For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="b47d5-121">Если при идентификации метки необходимо учитывать регистр, при использовании списка фраз вы можете указать это в объяснении, выбрав флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="b47d5-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Учет регистра](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="b47d5-123">Списки шаблонов</span><span class="sxs-lookup"><span data-stu-id="b47d5-123">Pattern lists</span></span>

<span data-ttu-id="b47d5-p107">Список шаблонов особенно полезен, когда вы создаете объяснение, которое находит и извлекает информацию из документа. Обычно такая информация представлена в различных форматах, например как даты, номера телефонов и кредитных карт. Например, значение даты может быть представлено в нескольких различных форматах (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 января 2020 г. и так далее). Определение списка шаблонов делает объяснение более эффективным за счет сбора всех возможных вариаций данных, которые вы хотите выявить и извлечь.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p107">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document. It is typically presented in different formats, such as dates, phone numbers, and credit card numbers. For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.). Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="b47d5-p108">В случае с **номером телефона** извлеките номер телефона каждого направляющего врача из документов с медицинскими направлениями, которые идентифицирует модель. Создавая объяснение, выберите тип "Список шаблонов", чтобы были возвращены различные возможные форматы.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p108">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies. When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Список шаблонов с номером телефона](../media/content-understanding/pattern-list.png)

<span data-ttu-id="b47d5-131">В этом случае установите флажок **Любая цифра от 0 до 9**, чтобы распознавать каждое значение «0», используемое в списке шаблонов, как любую цифру от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="b47d5-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Любая цифра от 0 до 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="b47d5-133">Точно так же, при создании списка шаблонов, включающего текстовые символы, установите флажок **Любая буква от a до я**, чтобы распознавать каждый символ «a», используемый в списке шаблонов, как любую букву от «a» до «я».</span><span class="sxs-lookup"><span data-stu-id="b47d5-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="b47d5-134">Например, если вы создаете список шаблонов **Дата** и хотите, чтобы формат даты типа *1 янв. 2020* был идентифицирован, то нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="b47d5-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="b47d5-135">Добавьте в список шаблонов *aaa 0, 0000* и *aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="b47d5-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="b47d5-136">Убедитесь, что выбран флажок **Любая буква от а до я**.</span><span class="sxs-lookup"><span data-stu-id="b47d5-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Любая буква от а до я](../media/content-understanding/any-letter.png)

<span data-ttu-id="b47d5-p109">Кроме того, если в вашем списке шаблонов есть требования по капитализации, вы можете выбрать флажок **Только точная капитализация**. В примере с датами, если нужно, чтобы первая буква месяца была заглавной, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b47d5-p109">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox. For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="b47d5-140">Добавьте в список шаблонов *Aaa 0, 0000* и *Aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="b47d5-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="b47d5-141">Убедитесь, что выбран флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="b47d5-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Только точная капитализация](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="b47d5-143">Вместо того, чтобы вручную создавать объяснение для списка шаблонов, воспользуйтесь [библиотекой объяснений](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) с шаблонами из популярных списков шаблонов, например *даты*, *номера телефонов*, *номера кредитных карт* и так далее.</span><span class="sxs-lookup"><span data-stu-id="b47d5-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="b47d5-144">Расстояние</span><span class="sxs-lookup"><span data-stu-id="b47d5-144">Proximity</span></span> 

<span data-ttu-id="b47d5-p110">Тип объяснения по расстоянию позволяет идентифицировать информацию по ее схожести с другим фрагментом данных. Например, вы определили в модели два типа объяснений, которые помечают *Улицу и номер дома* и *Номер телефона* клиента.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p110">The proximity explanation type helps your model identify data by defining how close another piece of data is to it. For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="b47d5-147">Обратите внимание, что номера телефонов клиентов всегда идут перед номером дома и улицей.</span><span class="sxs-lookup"><span data-stu-id="b47d5-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="b47d5-148">Алексей Виноградов</span><span class="sxs-lookup"><span data-stu-id="b47d5-148">Alex Wilburn</span></span><br>
<span data-ttu-id="b47d5-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="b47d5-149">555-555-5555</span></span><br>
<span data-ttu-id="b47d5-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="b47d5-150">One Microsoft Way</span></span><br>
<span data-ttu-id="b47d5-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="b47d5-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="b47d5-152">Используйте объяснение по расстоянию, чтобы определить, насколько далеко находится объяснение номера телефона, чтобы лучше идентифицировать адрес в документах.</span><span class="sxs-lookup"><span data-stu-id="b47d5-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Объяснение по расстоянию](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="b47d5-154">Что такое маркеры?</span><span class="sxs-lookup"><span data-stu-id="b47d5-154">What are tokens?</span></span>

<span data-ttu-id="b47d5-p111">Чтобы использовать тип объяснения по расстоянию, нужно знать, что такое маркер, так как тип объяснения по расстоянию измеряет расстояние в количестве маркеров. Маркер — это непрерывный диапазон букв и цифр (без пробелов или знаков препинания).</span><span class="sxs-lookup"><span data-stu-id="b47d5-p111">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another. A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="b47d5-157">В таблице ниже приведены примеры определения количества маркеров в фразе.</span><span class="sxs-lookup"><span data-stu-id="b47d5-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="b47d5-158">Фраза</span><span class="sxs-lookup"><span data-stu-id="b47d5-158">Phrase</span></span>|<span data-ttu-id="b47d5-159">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="b47d5-159">Number of tokens</span></span>|<span data-ttu-id="b47d5-160">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b47d5-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="b47d5-161">1</span><span class="sxs-lookup"><span data-stu-id="b47d5-161">1</span></span>|<span data-ttu-id="b47d5-162">Отдельное слово без пунктуации и пробелов.</span><span class="sxs-lookup"><span data-stu-id="b47d5-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="b47d5-163">1</span><span class="sxs-lookup"><span data-stu-id="b47d5-163">1</span></span>|<span data-ttu-id="b47d5-p112">Номер локатора записи. Он может включать буквы и цифры, но не знаки препинания.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p112">A record locator number. It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="b47d5-166">5</span><span class="sxs-lookup"><span data-stu-id="b47d5-166">5</span></span>|<span data-ttu-id="b47d5-p113">Номер телефона. Каждый знак препинания является маркером, поэтому в `425-555-5555` 5 маркеров:</span><span class="sxs-lookup"><span data-stu-id="b47d5-p113">A phone number. Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="b47d5-169">7</span><span class="sxs-lookup"><span data-stu-id="b47d5-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="b47d5-170">Настройка типа объяснения по расстоянию</span><span class="sxs-lookup"><span data-stu-id="b47d5-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="b47d5-p114">В качестве примера настройте расстояние так, чтобы определить диапазон количества маркеров от объяснения *Номер телефона* до объяснения *Улица и номер дома*. Обратите внимание, что в качестве минимального диапазона указан "0", потому что между номером телефона и улицей и номером дома нет маркеров.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p114">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation. Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="b47d5-173">Однако к некоторым номерам телефонов в примерах документов добавлен *(мобильный)*.</span><span class="sxs-lookup"><span data-stu-id="b47d5-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="b47d5-174">Николай Белых</span><span class="sxs-lookup"><span data-stu-id="b47d5-174">Nestor Wilke</span></span><br>
<span data-ttu-id="b47d5-175">111-111-1111 (мобильный)</span><span class="sxs-lookup"><span data-stu-id="b47d5-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="b47d5-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="b47d5-176">One Microsoft Way</span></span><br>
<span data-ttu-id="b47d5-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="b47d5-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="b47d5-178">В примере *(мобильный)* три маркера:</span><span class="sxs-lookup"><span data-stu-id="b47d5-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="b47d5-179">Фраза</span><span class="sxs-lookup"><span data-stu-id="b47d5-179">Phrase</span></span>|<span data-ttu-id="b47d5-180">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="b47d5-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="b47d5-181">(</span><span class="sxs-lookup"><span data-stu-id="b47d5-181">(</span></span>|<span data-ttu-id="b47d5-182">1</span><span class="sxs-lookup"><span data-stu-id="b47d5-182">1</span></span>|
|<span data-ttu-id="b47d5-183">мобильный</span><span class="sxs-lookup"><span data-stu-id="b47d5-183">mobile</span></span>|<span data-ttu-id="b47d5-184">2</span><span class="sxs-lookup"><span data-stu-id="b47d5-184">2</span></span>|
|<span data-ttu-id="b47d5-185">)</span><span class="sxs-lookup"><span data-stu-id="b47d5-185">)</span></span>|<span data-ttu-id="b47d5-186">3</span><span class="sxs-lookup"><span data-stu-id="b47d5-186">3</span></span>|

<span data-ttu-id="b47d5-187">Настройте параметры расстояния так, чтобы диапазон был от 0 до 3.</span><span class="sxs-lookup"><span data-stu-id="b47d5-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Пример расстояния](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="b47d5-189">Использование шаблонов объяснений</span><span class="sxs-lookup"><span data-stu-id="b47d5-189">Use explanation templates</span></span>

<span data-ttu-id="b47d5-190">Вы можете вручную добавлять значения списка шаблонов для объяснений, но может быть проще использовать шаблоны из библиотеки объяснений.</span><span class="sxs-lookup"><span data-stu-id="b47d5-190">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="b47d5-191">Например, вместо того, чтобы вручную добавлять все вариации *Даты*, вы можете использовать шаблон *Дат*, так как в нем уже есть несколько значений для списка шаблонов:</span><span class="sxs-lookup"><span data-stu-id="b47d5-191">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![Библиотека объяснений](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="b47d5-193">Библиотека объяснений включает часто используемые объяснения списка шаблонов, включая:</span><span class="sxs-lookup"><span data-stu-id="b47d5-193">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="b47d5-194">Дата</span><span class="sxs-lookup"><span data-stu-id="b47d5-194">Date</span></span></br>
- <span data-ttu-id="b47d5-195">Дата (числовая)</span><span class="sxs-lookup"><span data-stu-id="b47d5-195">Date (numeric)</span></span></br>
- <span data-ttu-id="b47d5-196">Время</span><span class="sxs-lookup"><span data-stu-id="b47d5-196">Time</span></span></br>
- <span data-ttu-id="b47d5-197">Числовой</span><span class="sxs-lookup"><span data-stu-id="b47d5-197">Number</span></span></br>
- <span data-ttu-id="b47d5-198">Номер телефона</span><span class="sxs-lookup"><span data-stu-id="b47d5-198">Phone number</span></span></br>
- <span data-ttu-id="b47d5-199">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="b47d5-199">Zip code</span></span></br>
- <span data-ttu-id="b47d5-200">Первое слово предложения</span><span class="sxs-lookup"><span data-stu-id="b47d5-200">First word of sentence</span></span></br>
- <span data-ttu-id="b47d5-201">Кредитная карта</span><span class="sxs-lookup"><span data-stu-id="b47d5-201">Credit card</span></span></br>
- <span data-ttu-id="b47d5-202">Номер социального страхования</span><span class="sxs-lookup"><span data-stu-id="b47d5-202">Social security number</span></span></br>

<span data-ttu-id="b47d5-203">Обратите внимание, что библиотека объяснений также включает шаблоны для объяснений списков фраз:</span><span class="sxs-lookup"><span data-stu-id="b47d5-203">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="b47d5-204">Конец предложения</span><span class="sxs-lookup"><span data-stu-id="b47d5-204">End of sentence</span></span>
- <span data-ttu-id="b47d5-205">Валюта</span><span class="sxs-lookup"><span data-stu-id="b47d5-205">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="b47d5-206">Использование шаблонов из библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="b47d5-206">To use a template from the explanation library</span></span>

1. <span data-ttu-id="b47d5-207">В разделе **Объяснения** на странице **Обучение** вашей модели, выберите **Новый**, затем выберите **Из шаблона**.</span><span class="sxs-lookup"><span data-stu-id="b47d5-207">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Создание из шаблона](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="b47d5-209">На странице **Шаблоны объяснений** выберите объяснение, которое хотите использовать, и выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b47d5-209">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Выбор шаблона](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="b47d5-p115">Информация о выбранном шаблоне отображается на странице **Создание объяснений**. При необходимости измените название объяснения, а также добавьте или удалите элементы из списка шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b47d5-p115">The information for the template you selected displays on the **Create an explanation** page. If needed, edit the explanation name and add or remove items from the pattern list. </span></span></br> 

   ![Изменение шаблона](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="b47d5-214">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b47d5-214">When finished, select **Save**.</span></span>
