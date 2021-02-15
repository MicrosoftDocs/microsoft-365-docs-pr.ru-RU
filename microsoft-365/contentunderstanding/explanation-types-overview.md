---
title: Типы объяснений
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Дополнительные сведения о типах объяснений в Microsoft SharePoint Syntex
ms.openlocfilehash: caba92b635feaf8f87e2c487559f70be3fab6df9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242627"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="ff1a0-103">Введение в типы объяснений</span><span class="sxs-lookup"><span data-stu-id="ff1a0-103">Introduction to explanation types</span></span>

<span data-ttu-id="ff1a0-104">Объяснения помогают определить информацию, которую вы хотите пометить и извлечь в своих моделях осмысления документации в Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="ff1a0-105">При создании объяснения следует выбрать тип объяснения.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="ff1a0-106">Данная статья поможет вам узнать о разных типах объяснений и о том, как они используются.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Типы объяснений](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="ff1a0-108">Доступны следующие типы объяснений:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-108">These explanation types are available:</span></span>

- <span data-ttu-id="ff1a0-109">**Список фраз**: список слов, фраз, цифр или других символов, которые можно использовать в документе или в извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="ff1a0-110">Например, текстовая строка **Направивший врач** находится во всех идентифицируемых документах с медицинскими направлениями.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="ff1a0-111">**Список шаблонов**: список шаблонов чисел, букв или других символов, которые можно использовать для идентификации извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="ff1a0-112">Например, вы можете извлечь **номер телефона** направившего врача из идентифицируемого документа с медицинским направлением.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="ff1a0-113">**Расстояние**: описывает, насколько близки объяснения.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="ff1a0-114">Например, список шаблонов с *номерами домов* идет прямо перед списком фраз с *названиями улиц* без маркеров между ними (больше информации о маркерах приведено в этой статье).</span><span class="sxs-lookup"><span data-stu-id="ff1a0-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="ff1a0-115">Для использования типа расстояния необходимо, чтобы в модели было как минимум два объяснения, иначе эта функция будет отключена.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="ff1a0-116">Список фраз</span><span class="sxs-lookup"><span data-stu-id="ff1a0-116">Phrase list</span></span>

<span data-ttu-id="ff1a0-117">Список фраз — это тип объяснения, который обычно используется, чтобы идентифицировать и классифицировать документ через вашу модель.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="ff1a0-118">Как описано в примере с меткой *Направивший врач*, это строка со словами, фразами, номерами или символами, постоянно встречающимися в идентифицируемых документах.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="ff1a0-119">Хоть это и не требование, но лучших результатов можно добиться, если считываемая фраза находится во всех документах в одном месте.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="ff1a0-120">Например, метка *Направивший врач* может находиться в первом абзаце всех документов.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="ff1a0-121">Если при идентификации метки важна точность, при использовании списка фраз вы можете указать это, выбрав флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Учет регистра](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="ff1a0-123">Списки шаблонов</span><span class="sxs-lookup"><span data-stu-id="ff1a0-123">Pattern lists</span></span>

<span data-ttu-id="ff1a0-124">Список шаблонов особенно полезен, когда вы создаете объяснение, которое находит и извлекает информацию из документа.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="ff1a0-125">Обычно такая информация представлена в различных форматах, например как даты, номера телефонов и кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="ff1a0-126">Например, значение даты может быть представлено в нескольких различных форматах (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 января 2020 г. и так далее).</span><span class="sxs-lookup"><span data-stu-id="ff1a0-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="ff1a0-127">Определение списка шаблонов делает объяснение более эффективным за счет сбора всех возможных вариаций данных, которые вы хотите выявить и извлечь.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="ff1a0-128">В случае с **номером телефона** извлеките номер телефона каждого направляющего врача из документов с медицинскими направлениями, которые идентифицирует модель.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="ff1a0-129">Создавая объяснение, выберите тип "Список шаблонов", чтобы были возвращены различные возможные форматы.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Список шаблонов с номером телефона](../media/content-understanding/pattern-list.png)

<span data-ttu-id="ff1a0-131">В этом случае установите флажок **Любая цифра от 0 до 9**, чтобы распознавать каждое значение «0», используемое в списке шаблонов, как любую цифру от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Любая цифра от 0 до 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="ff1a0-133">Точно так же, при создании списка шаблонов, включающего текстовые символы, установите флажок **Любая буква от a до я**, чтобы распознавать каждый символ «a», используемый в списке шаблонов, как любую букву от «a» до «я».</span><span class="sxs-lookup"><span data-stu-id="ff1a0-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="ff1a0-134">Например, если вы создаете список шаблонов **Дата** и хотите, чтобы формат даты типа *1 янв 2020* был идентифицирован, то нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="ff1a0-135">Добавьте в список шаблонов *aaa 0, 0000* и *aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="ff1a0-136">Убедитесь, что выбран флажок **Любая буква от а до я**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Любая буква от а до я](../media/content-understanding/any-letter.png)

<span data-ttu-id="ff1a0-138">Кроме того, если в вашем списке шаблонов есть требования по капитализации, вы можете выбрать флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="ff1a0-139">В примере с датами, если нужно, чтобы первая буква месяца была заглавной, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="ff1a0-140">Добавьте в список шаблонов *Aaa 0, 0000* и *Aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="ff1a0-141">Убедитесь, что выбран флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Только точная капитализация](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="ff1a0-143">Вместо того, чтобы вручную создавать объяснение для списка шаблонов, воспользуйтесь [библиотекой объяснений](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) с шаблонами из популярных списков шаблонов, например *даты*, *номера телефонов*, *номера кредитных карт* и так далее.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="ff1a0-144">Расстояние</span><span class="sxs-lookup"><span data-stu-id="ff1a0-144">Proximity</span></span> 

<span data-ttu-id="ff1a0-145">Тип объяснения по расстоянию позволяет идентифицировать информацию по ее схожести с другим фрагментом данных.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="ff1a0-146">Например, вы определили в модели два типа объяснений, которые помечают *Улицу и номер дома* и *Номер телефона* клиента.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="ff1a0-147">Обратите внимание, что номера телефонов клиента всегда идут до номера дома и улицы.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="ff1a0-148">Алексей Виноградов</span><span class="sxs-lookup"><span data-stu-id="ff1a0-148">Alex Wilburn</span></span><br>
<span data-ttu-id="ff1a0-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="ff1a0-149">555-555-5555</span></span><br>
<span data-ttu-id="ff1a0-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="ff1a0-150">One Microsoft Way</span></span><br>
<span data-ttu-id="ff1a0-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="ff1a0-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="ff1a0-152">Используйте объяснение по расстоянию, чтобы определить, насколько далеко находится объяснение номера телефона, чтобы лучше идентифицировать адрес в документах.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Объяснение по расстоянию](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="ff1a0-154">Что такое маркеры?</span><span class="sxs-lookup"><span data-stu-id="ff1a0-154">What are tokens?</span></span>

<span data-ttu-id="ff1a0-155">Чтобы использовать тип объяснения по расстоянию, вам нужно знать, что такое маркер, так как тип объяснения по расстоянию измеряет расстояние в количестве маркеров.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="ff1a0-156">Маркер — это непрерывный диапазон (без пробелов или пунктуации) букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="ff1a0-157">В таблице ниже приведены примеры определения количества маркеров в фразе.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="ff1a0-158">Фраза</span><span class="sxs-lookup"><span data-stu-id="ff1a0-158">Phrase</span></span>|<span data-ttu-id="ff1a0-159">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="ff1a0-159">Number of tokens</span></span>|<span data-ttu-id="ff1a0-160">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ff1a0-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="ff1a0-161">1</span><span class="sxs-lookup"><span data-stu-id="ff1a0-161">1</span></span>|<span data-ttu-id="ff1a0-162">Отдельное слово без пунктуации и пробелов.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="ff1a0-163">1</span><span class="sxs-lookup"><span data-stu-id="ff1a0-163">1</span></span>|<span data-ttu-id="ff1a0-164">Номер локатора записи.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-164">A record locator number.</span></span> <span data-ttu-id="ff1a0-165">Он может включать буквы и цифры, но не знаки пунктуации.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="ff1a0-166">5</span><span class="sxs-lookup"><span data-stu-id="ff1a0-166">5</span></span>|<span data-ttu-id="ff1a0-167">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-167">A phone number.</span></span> <span data-ttu-id="ff1a0-168">Каждый знак препинания является маркером, поэтому в `425-555-5555` 5 маркеров:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="ff1a0-169">7</span><span class="sxs-lookup"><span data-stu-id="ff1a0-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="ff1a0-170">Настройка типа объяснения по расстоянию</span><span class="sxs-lookup"><span data-stu-id="ff1a0-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="ff1a0-171">В качестве примера настройте расстояние так, чтобы определить диапазон количества маркеров от объяснения *Номер телефона* до объяснения *Номер дома*.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="ff1a0-172">Обратите внимание, что в качестве минимального диапазона указан «0», потому что между номером телефона и номером дома нет маркеров.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="ff1a0-173">Однако к некоторым номерам телефонов в примерах документов добавлен *(мобильный)*.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="ff1a0-174">Николай Белых</span><span class="sxs-lookup"><span data-stu-id="ff1a0-174">Nestor Wilke</span></span><br>
<span data-ttu-id="ff1a0-175">111-111-1111 (мобильный)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="ff1a0-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="ff1a0-176">One Microsoft Way</span></span><br>
<span data-ttu-id="ff1a0-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="ff1a0-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="ff1a0-178">В примере *(мобильный)* три маркера:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="ff1a0-179">Фраза</span><span class="sxs-lookup"><span data-stu-id="ff1a0-179">Phrase</span></span>|<span data-ttu-id="ff1a0-180">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="ff1a0-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="ff1a0-181">(</span><span class="sxs-lookup"><span data-stu-id="ff1a0-181">(</span></span>|<span data-ttu-id="ff1a0-182">1</span><span class="sxs-lookup"><span data-stu-id="ff1a0-182">1</span></span>|
|<span data-ttu-id="ff1a0-183">мобильный</span><span class="sxs-lookup"><span data-stu-id="ff1a0-183">mobile</span></span>|<span data-ttu-id="ff1a0-184">2</span><span class="sxs-lookup"><span data-stu-id="ff1a0-184">2</span></span>|
|<span data-ttu-id="ff1a0-185">)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-185">)</span></span>|<span data-ttu-id="ff1a0-186">3</span><span class="sxs-lookup"><span data-stu-id="ff1a0-186">3</span></span>|

<span data-ttu-id="ff1a0-187">Настройте параметры расстояния так, чтобы диапазон был от 0 до 3.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Пример расстояния](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="ff1a0-189">Настройка расположения фраз в документе</span><span class="sxs-lookup"><span data-stu-id="ff1a0-189">Configure where phrases occur in the document</span></span>

<span data-ttu-id="ff1a0-190">Когда вы создаете объяснение, по умолчанию поиск фразы, которую вы пытаетесь извлечь, выполняется по всему документу.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-190">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="ff1a0-191">Однако вы можете использовать дополнительный параметр <b>Где встречаются эти фразы</b>, чтобы изолировать определенное место в документе, в котором встречается фраза.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-191">However, you can use the <b>Where these phrases occur</b> advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="ff1a0-192">Это удобно в ситуациях, когда похожие вхождения фразы могут появляться в другом месте документа и вы хотите убедиться в том, что выбран нужный вариант.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-192">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="ff1a0-193">В нашем примере документа с медицинским направлением **Направивший врач** всегда упоминается в первом абзаце документа.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-193">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="ff1a0-194">С помощью параметра <b>Где встречаются эти фразы</b> в этом примере вы можете настроить свое объяснение для поиска этой метки только в начальном разделе документа или в любом другом месте, где она может встречаться.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-194">With the <b>Where these phrases occur</b> setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

   ![Параметр "Где встречаются эти фразы"](../media/content-understanding/phrase-location.png)</br>

<span data-ttu-id="ff1a0-196">В этом параметре доступны следующие варианты на выбор.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-196">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="ff1a0-197">В любом месте файла: поиск фразы выполняется во всем документе.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-197">Anywhere in the file: The entire document is searched for the phrase.</span></span>
- <span data-ttu-id="ff1a0-198">Начало файла: поиск в документе выполняется с начала до места, где расположена фраза.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-198">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span></br> 
   <span data-ttu-id="ff1a0-199">![Начало файла](../media/content-understanding/beginning-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-199">![Beginning of file](../media/content-understanding/beginning-of-file.png)</span></span></br>
<span data-ttu-id="ff1a0-200">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-200">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="ff1a0-201">Значение <b>Конечное положение</b> обновляется для отображения количества маркеров, содержащихся в выбранной вами области.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-201">The <b>End position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="ff1a0-202">Обратите внимание, что вы можете изменить значение "Конечное положение", а также настроить выбранную область.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-202">Note that you can update the End position value as well to adjust the selected area.</span></span></br>
   <span data-ttu-id="ff1a0-203">![Поле положения "Начало файла"](../media/content-understanding/beginning-box.png)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-203">![Beginning of file position box](../media/content-understanding/beginning-box.png)</span></span></br>

- <span data-ttu-id="ff1a0-204">Конец файла: поиск в документе выполняется с конца до места, где расположена фраза.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-204">End of the file:  The document is searched from the end to the phrase location.</span></span></br> 
   <span data-ttu-id="ff1a0-205">![Конец файла](../media/content-understanding/end-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-205">![End of file](../media/content-understanding/end-of-file.png)</span></span></br>
<span data-ttu-id="ff1a0-206">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-206">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="ff1a0-207">Значение <b>Начальное положение</b> обновляется для отображения количества маркеров, содержащихся в выбранной вами области.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-207">The <b>Starting position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="ff1a0-208">Обратите внимание, что вы можете изменить значение "Начальное положение", а также настроить выбранную область.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-208">Note that you can update the Starting position value as well to adjust the selected area.</span></span></br> 
   <span data-ttu-id="ff1a0-209">![Конечное поле "Конец файла"](../media/content-understanding/end-box.png)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-209">![End of file end box](../media/content-understanding/end-box.png)</span></span></br>
- <span data-ttu-id="ff1a0-210">Произвольный диапазон: поиск расположения фразы выполняется в указанном диапазоне документа.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-210">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span></br> 
   <span data-ttu-id="ff1a0-211">![Произвольный диапазон](../media/content-understanding/custom-file.png)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-211">![Custom range](../media/content-understanding/custom-file.png)</span></span></br>
<span data-ttu-id="ff1a0-212">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-212">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="ff1a0-213">Для этого параметра требуется выбрать положение <b>Начало</b> и <b>Конец</b>.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-213">For this setting, you need to select a <b>Start</b> and an <b>End</b> position.</span></span> <span data-ttu-id="ff1a0-214">Эти значения отражают количество маркеров с начала документа.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-214">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="ff1a0-215">Хотя вы можете вручную ввести эти значения, проще вручную изменить поле выбора в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-215">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span></br> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="ff1a0-216">Используйте шаблона объяснений</span><span class="sxs-lookup"><span data-stu-id="ff1a0-216">Use explanation templates</span></span>

<span data-ttu-id="ff1a0-217">Вы можете вручную добавлять значения списка фраз для объяснений, но может быть проще использовать шаблоны из библиотеки объяснений.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-217">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="ff1a0-218">Например, вместо того, чтобы вручную добавлять все варианты *Даты*, вы можете использовать шаблон списка фраз для *Дат*, так как в нем уже есть несколько значений списков фраз:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-218">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span></br>

   ![Библиотека объяснений](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="ff1a0-220">Библиотека объяснений включает часто используемые объяснения списка фраз, включая:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-220">The explanation library includes commonly used phrase list explanations, including:</span></span></br>

- <span data-ttu-id="ff1a0-221">Дата</span><span class="sxs-lookup"><span data-stu-id="ff1a0-221">Date</span></span></br>
- <span data-ttu-id="ff1a0-222">Дата (числовая)</span><span class="sxs-lookup"><span data-stu-id="ff1a0-222">Date (numeric)</span></span></br>
- <span data-ttu-id="ff1a0-223">Время</span><span class="sxs-lookup"><span data-stu-id="ff1a0-223">Time</span></span></br>
- <span data-ttu-id="ff1a0-224">Числовой</span><span class="sxs-lookup"><span data-stu-id="ff1a0-224">Number</span></span></br>
- <span data-ttu-id="ff1a0-225">Процентный</span><span class="sxs-lookup"><span data-stu-id="ff1a0-225">Percentage</span></span></br>
- <span data-ttu-id="ff1a0-226">Номер телефона</span><span class="sxs-lookup"><span data-stu-id="ff1a0-226">Phone number</span></span></br>
- <span data-ttu-id="ff1a0-227">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="ff1a0-227">Zip code</span></span></br>
- <span data-ttu-id="ff1a0-228">Первое слово предложения</span><span class="sxs-lookup"><span data-stu-id="ff1a0-228">First word of sentence</span></span></br>
- <span data-ttu-id="ff1a0-229">Конец предложения</span><span class="sxs-lookup"><span data-stu-id="ff1a0-229">End of sentence</span></span></br>
- <span data-ttu-id="ff1a0-230">Кредитная карта</span><span class="sxs-lookup"><span data-stu-id="ff1a0-230">Credit card</span></span></br>
- <span data-ttu-id="ff1a0-231">Номер социального страхования</span><span class="sxs-lookup"><span data-stu-id="ff1a0-231">Social security number</span></span></br>
- <span data-ttu-id="ff1a0-232">Флажок</span><span class="sxs-lookup"><span data-stu-id="ff1a0-232">Checkbox</span></span></br>
- <span data-ttu-id="ff1a0-233">Валюта</span><span class="sxs-lookup"><span data-stu-id="ff1a0-233">Currency</span></span></br>
- <span data-ttu-id="ff1a0-234">Копия письма</span><span class="sxs-lookup"><span data-stu-id="ff1a0-234">Email CC</span></span></br>
- <span data-ttu-id="ff1a0-235">Дата письма</span><span class="sxs-lookup"><span data-stu-id="ff1a0-235">Email date</span></span></br>
- <span data-ttu-id="ff1a0-236">Приветствие в письме</span><span class="sxs-lookup"><span data-stu-id="ff1a0-236">Email greeting</span></span></br>
- <span data-ttu-id="ff1a0-237">Получатель письма</span><span class="sxs-lookup"><span data-stu-id="ff1a0-237">Email recipient</span></span></br>
- <span data-ttu-id="ff1a0-238">Отправитель письма</span><span class="sxs-lookup"><span data-stu-id="ff1a0-238">Email sender</span></span></br>
- <span data-ttu-id="ff1a0-239">Тема письма</span><span class="sxs-lookup"><span data-stu-id="ff1a0-239">Email subject</span></span></br>

<span data-ttu-id="ff1a0-240">Библиотека объяснений также содержит три автоматических типа шаблонов для работы с данными, которые вы пометили в файлах примера:</span><span class="sxs-lookup"><span data-stu-id="ff1a0-240">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="ff1a0-241">После метки. Слова и символы, которые встречаются после меток в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-241">After label: The words or characters that occur after the labels in the example files.</span></span></br>
- <span data-ttu-id="ff1a0-242">До метки. Слова и символы, которые встречаются до меток в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-242">Before label: The words or characters that occur before the labels in the example files.</span></span></br>
- <span data-ttu-id="ff1a0-243">Метки. До 10 первых меток из файлов примера.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-243">Labels: Up to the first 10 labels from the example files.</span></span></br>

<span data-ttu-id="ff1a0-244">В следующем файле примера для демонстрации работы автоматических шаблонов используется шаблон объяснения "До метки", чтобы предоставить модели дополнительные сведения для получения более точного соответствия.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-244">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

   ![Пример файла](../media/content-understanding/before-label.png)</br>

<span data-ttu-id="ff1a0-246">Если выбрать шаблон объяснения "До метки", он будет искать первый набор слов, которые появляются перед меткой в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-246">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="ff1a0-247">Например, слова, определяемые в первом примере файла: "As of" (Начиная с).</span><span class="sxs-lookup"><span data-stu-id="ff1a0-247">In the example, the words that are identified in the first example file is "As of".</span></span>

   ![Шаблон "Перед меткой"](../media/content-understanding/before-label-explanation.png)</br>

<span data-ttu-id="ff1a0-249">Чтобы создать объяснение из шаблона, вы можете выбрать <b>Добавить</b>.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-249">You can select <b>Add</b> to create an explanation from the template.</span></span>  <span data-ttu-id="ff1a0-250">Когда вы добавляете другие примеры файлов, дополнительные слова определяются и добавляются в список фраз.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-250">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

   ![Добавление метки](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="ff1a0-252">Использование шаблонов из библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="ff1a0-252">To use a template from the explanation library</span></span>

1. <span data-ttu-id="ff1a0-253">В разделе **Объяснения** на странице **Обучение** вашей модели, выберите **Новый**, затем выберите **Из шаблона**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-253">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Добавление перед меткой](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="ff1a0-255">На странице **Шаблоны объяснений** выберите объяснение, которое хотите использовать, и выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-255">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Выбор шаблона](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="ff1a0-257">Информация о выбранном шаблоне отображается на странице **Создание объяснений**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-257">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="ff1a0-258">При необходимости измените название объяснения, а также добавьте или удалите элементы из списка фраз.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-258">If needed, edit the explanation name and add or remove items from the phrase list.</span></span> </br> 

   ![Изменение шаблона](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="ff1a0-260">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ff1a0-260">When finished, select **Save**.</span></span>