---
title: Типы объяснений
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Дополнительные сведения о типах объяснений в Microsoft SharePoint Syntex
ms.openlocfilehash: 7d78337fd91bc7e5a71bccd4867f019ae663417a
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321801"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="a18dd-103">Введение в типы объяснений</span><span class="sxs-lookup"><span data-stu-id="a18dd-103">Introduction to explanation types</span></span>

<span data-ttu-id="a18dd-104">Объяснения помогают определить информацию, которую вы хотите пометить и извлечь в своих моделях осмысления документации в Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="a18dd-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="a18dd-105">При создании объяснения следует выбрать тип объяснения.</span><span class="sxs-lookup"><span data-stu-id="a18dd-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="a18dd-106">Данная статья поможет вам узнать подробности о разных типах объяснений и о том, как они используются.</span><span class="sxs-lookup"><span data-stu-id="a18dd-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![Типы объяснений](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="a18dd-108">Доступны следующие типы объяснений:</span><span class="sxs-lookup"><span data-stu-id="a18dd-108">These explanation types are available:</span></span>

- <span data-ttu-id="a18dd-109">**Список фраз**: список слов, фраз, цифр или других символов, которые можно использовать в документе или в извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="a18dd-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="a18dd-110">Например, текстовая строка **Направивший врач** находится во всех идентифицируемых документах с медицинскими направлениями.</span><span class="sxs-lookup"><span data-stu-id="a18dd-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="a18dd-111">**Список шаблонов**: список шаблонов чисел, букв или других символов, которые можно использовать для идентификации извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="a18dd-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="a18dd-112">Например, вы можете извлечь **номер телефона** направившего врача из идентифицируемого документа с медицинским направлением.</span><span class="sxs-lookup"><span data-stu-id="a18dd-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="a18dd-113">**Расстояние**: описывает, насколько близки объяснения.</span><span class="sxs-lookup"><span data-stu-id="a18dd-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="a18dd-114">Например, список шаблонов с *номерами домов* идет прямо перед списком фраз с *названиями улиц* без маркеров между ними (больше информации о маркерах приведено в этой статье).</span><span class="sxs-lookup"><span data-stu-id="a18dd-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="a18dd-115">Для использования типа расстояния требуется, чтобы в вашей модели было как минимум два объяснения, иначе эта функция будет отключена.</span><span class="sxs-lookup"><span data-stu-id="a18dd-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="a18dd-116">Список фраз</span><span class="sxs-lookup"><span data-stu-id="a18dd-116">Phrase list</span></span>

<span data-ttu-id="a18dd-117">Список фраз — это тип объяснения, который обычно используется, чтобы идентифицировать и классифицировать документ через вашу модель.</span><span class="sxs-lookup"><span data-stu-id="a18dd-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="a18dd-118">Как описано в примере с меткой *Направивший врач*, это строка со словами, фразами, номерами или символами, которые постоянно встречаются в идентифицируемых документах.</span><span class="sxs-lookup"><span data-stu-id="a18dd-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="a18dd-119">Хоть это и не требования, но лучших результатов можно добиться, если считываемая фраза находится во всех документах в одном месте.</span><span class="sxs-lookup"><span data-stu-id="a18dd-119">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="a18dd-120">Например, метка *Направивший врач* может находиться в первом абзаце всех документов.</span><span class="sxs-lookup"><span data-stu-id="a18dd-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="a18dd-121">Если при идентификации метки важна точность, при использовании списка фраз вы можете указать это, выбрав флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Учет регистра](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="a18dd-123">Списки шаблонов</span><span class="sxs-lookup"><span data-stu-id="a18dd-123">Pattern lists</span></span>

<span data-ttu-id="a18dd-124">Список шаблонов особенно полезен, когда вы создаете объяснение, которое находит и извлекает информацию из документа.</span><span class="sxs-lookup"><span data-stu-id="a18dd-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="a18dd-125">Обычно такая информация представлена определенным форматом, например даты, номера телефонов или кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="a18dd-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="a18dd-126">Например, значение даты может быть представлено в нескольких различных форматах (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 января 2020 г. и так далее).</span><span class="sxs-lookup"><span data-stu-id="a18dd-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="a18dd-127">Определение списка шаблонов делает объяснение более эффективным за счет сбора всех возможных вариаций данных, которые вы хотите выявить и извлечь.</span><span class="sxs-lookup"><span data-stu-id="a18dd-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="a18dd-128">В случае с **номером телефона** извлеките номер телефона каждого направивишего врача из документов с медицинскими направлениями, которые идентифицирует модель.</span><span class="sxs-lookup"><span data-stu-id="a18dd-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="a18dd-129">Создавая объяснение, выберите тип "Список шаблонов", чтобы были возвращены различные возможные форматы.</span><span class="sxs-lookup"><span data-stu-id="a18dd-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Список шаблонов с номером телефона](../media/content-understanding/pattern-list.png)

<span data-ttu-id="a18dd-131">В этом примере выберите флажок **Любая цифра от 0 до 9**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="a18dd-132">При выборе этого пункта каждое значение "0" в шаблоне будет любой цифрой от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="a18dd-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Любая цифра от 0 до 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="a18dd-134">Походим образом, если вы создаете список шаблонов с текстовыми символами, выберите флажок **Любая буква от а до я**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="a18dd-135">При данном выборе каждый символ "а" в списке шаблоном будет буквой от "а" до "я".</span><span class="sxs-lookup"><span data-stu-id="a18dd-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="a18dd-136">Например, если вы создаете список шаблонов **Дата** и хотите, чтобы формат даты типа *1 янв 2020* был идентифицирован, то нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="a18dd-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="a18dd-137">Добавьте в список шаблонов *aaa 0, 0000* и *aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="a18dd-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="a18dd-138">Убедитесь, что выбран флажок **Любая буква от а до я**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Любая буква от а до я](../media/content-understanding/any-letter.png)

<span data-ttu-id="a18dd-140">Кроме того, если в вашем списке шаблонов есть требования по капитализации, вы можете выбрать флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="a18dd-141">В примере с датами, если нужно, чтобы первая буква месяца была заглавной, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="a18dd-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="a18dd-142">Добавьте в список шаблонов *Aaa 0, 0000* и *Aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="a18dd-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="a18dd-143">Убедитесь, что выбран флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Только точная капитализация](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="a18dd-145">Вместо того, чтобы вручную создавать объяснение для списка шаблонов, воспользуйтесь [библиотекой объяснений]() с готовыми шаблонами из популярных списков шаблонов, например *даты*, *номера телефонов*, *номера кредитных карт* и так далее.</span><span class="sxs-lookup"><span data-stu-id="a18dd-145">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="a18dd-146">Расстояние</span><span class="sxs-lookup"><span data-stu-id="a18dd-146">Proximity</span></span> 

<span data-ttu-id="a18dd-147">Тип объяснения по расстоянию позволяет идентифицировать информацию по ее схожести с другим фрагментов данных.</span><span class="sxs-lookup"><span data-stu-id="a18dd-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="a18dd-148">Например, в своей модели вы определили два типа объяснений, которые отмечают *Улицу и номер дома* и *Номер телефона* клиента.</span><span class="sxs-lookup"><span data-stu-id="a18dd-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="a18dd-149">Вы также обратили внимание, что номер телефона клиента всегда идет до номера дома и улицы.</span><span class="sxs-lookup"><span data-stu-id="a18dd-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="a18dd-150">Алексей Виноградов</span><span class="sxs-lookup"><span data-stu-id="a18dd-150">Alex Wilburn</span></span><br>
<span data-ttu-id="a18dd-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="a18dd-151">555-555-5555</span></span><br>
<span data-ttu-id="a18dd-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="a18dd-152">One Microsoft Way</span></span><br>
<span data-ttu-id="a18dd-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="a18dd-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="a18dd-154">Используйте объяснение по расстоянию, чтобы определить, насколько далеко находится объяснение номера телефона, чтобы лучше идентифицировать адрес в документах.</span><span class="sxs-lookup"><span data-stu-id="a18dd-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Объяснение по расстоянию](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="a18dd-156">Что такое маркеры?</span><span class="sxs-lookup"><span data-stu-id="a18dd-156">What are tokens?</span></span>

<span data-ttu-id="a18dd-157">Чтобы использовать тип объяснения по расстоянию, нужно знать, что такое маркер, поскольку тип объяснения по расстоянию измеряет расстояние в маркерах.</span><span class="sxs-lookup"><span data-stu-id="a18dd-157">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="a18dd-158">Маркер — это непрерывный диапазон (без пробелов или пунктуации) букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="a18dd-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="a18dd-159">Пробел не является маркером.</span><span class="sxs-lookup"><span data-stu-id="a18dd-159">A space is NOT a token.</span></span> <span data-ttu-id="a18dd-160">Каждый знак препинания является маркером.</span><span class="sxs-lookup"><span data-stu-id="a18dd-160">Each punctuation character is a token.</span></span> <span data-ttu-id="a18dd-161">В таблице ниже приведены примеры определения количества маркеров в фразе.</span><span class="sxs-lookup"><span data-stu-id="a18dd-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="a18dd-162">Фраза</span><span class="sxs-lookup"><span data-stu-id="a18dd-162">Phrase</span></span>|<span data-ttu-id="a18dd-163">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="a18dd-163">Number of tokens</span></span>|<span data-ttu-id="a18dd-164">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a18dd-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="a18dd-165">1</span><span class="sxs-lookup"><span data-stu-id="a18dd-165">1</span></span>|<span data-ttu-id="a18dd-166">Отдельное слово без пунктуации и пробелов.</span><span class="sxs-lookup"><span data-stu-id="a18dd-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="a18dd-167">1</span><span class="sxs-lookup"><span data-stu-id="a18dd-167">1</span></span>|<span data-ttu-id="a18dd-168">Номер локатора записи.</span><span class="sxs-lookup"><span data-stu-id="a18dd-168">A record locator number.</span></span> <span data-ttu-id="a18dd-169">В нем могут быть буквы и цифры, но не знаки пунктуации.</span><span class="sxs-lookup"><span data-stu-id="a18dd-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="a18dd-170">5</span><span class="sxs-lookup"><span data-stu-id="a18dd-170">5</span></span>|<span data-ttu-id="a18dd-171">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="a18dd-171">A phone number.</span></span> <span data-ttu-id="a18dd-172">Каждый знак препинания является маркером, поэтому в `425-555-5555` 5 маркеров:</span><span class="sxs-lookup"><span data-stu-id="a18dd-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="a18dd-173">7</span><span class="sxs-lookup"><span data-stu-id="a18dd-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="a18dd-174">Настройка типа объяснения по расстоянию</span><span class="sxs-lookup"><span data-stu-id="a18dd-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="a18dd-175">В качестве примера настройте расстояние так, чтобы определить диапазон количества маркеров от объяснения *Номер телефона* до объяснения *Номер дома*.</span><span class="sxs-lookup"><span data-stu-id="a18dd-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="a18dd-176">В качестве минимального диапазона указан "0", потому что между номером телефона и номером дома нет маркеров.</span><span class="sxs-lookup"><span data-stu-id="a18dd-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="a18dd-177">Однако некоторые номера телефонов в примерах имеют добавление, например *(мобильный)*.</span><span class="sxs-lookup"><span data-stu-id="a18dd-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="a18dd-178">Николай Белых</span><span class="sxs-lookup"><span data-stu-id="a18dd-178">Nestor Wilke</span></span><br>
<span data-ttu-id="a18dd-179">111-111-1111 (мобильный)</span><span class="sxs-lookup"><span data-stu-id="a18dd-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="a18dd-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="a18dd-180">One Microsoft Way</span></span><br>
<span data-ttu-id="a18dd-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="a18dd-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="a18dd-182">В примере *(мобильный)* три маркера:</span><span class="sxs-lookup"><span data-stu-id="a18dd-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="a18dd-183">Фраза</span><span class="sxs-lookup"><span data-stu-id="a18dd-183">Phrase</span></span>|<span data-ttu-id="a18dd-184">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="a18dd-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="a18dd-185">(</span><span class="sxs-lookup"><span data-stu-id="a18dd-185">(</span></span>|<span data-ttu-id="a18dd-186">1</span><span class="sxs-lookup"><span data-stu-id="a18dd-186">1</span></span>|
|<span data-ttu-id="a18dd-187">мобильный</span><span class="sxs-lookup"><span data-stu-id="a18dd-187">mobile</span></span>|<span data-ttu-id="a18dd-188">2</span><span class="sxs-lookup"><span data-stu-id="a18dd-188">2</span></span>|
|<span data-ttu-id="a18dd-189">)</span><span class="sxs-lookup"><span data-stu-id="a18dd-189">)</span></span>|<span data-ttu-id="a18dd-190">3</span><span class="sxs-lookup"><span data-stu-id="a18dd-190">3</span></span>|

<span data-ttu-id="a18dd-191">Настройте параметры расстояния так, чтобы диапазон был от 0 до 3.</span><span class="sxs-lookup"><span data-stu-id="a18dd-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Пример расстояния](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="a18dd-193">Используйте шаблона объяснений</span><span class="sxs-lookup"><span data-stu-id="a18dd-193">Use explanation templates</span></span>

<span data-ttu-id="a18dd-194">Вы можете вручную добавлять значения списка шаблонов для объяснений, но может быть проще использовать уже созданные шаблоны из библиотеки объяснений.</span><span class="sxs-lookup"><span data-stu-id="a18dd-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="a18dd-195">Например, вместо того, чтобы вручную добавлять все вариации *Даты*, вы можете использовать шаблон *Дат*, в котором уже есть несколько значений для списка шаблонов:</span><span class="sxs-lookup"><span data-stu-id="a18dd-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Библиотека объяснений](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="a18dd-197">В библиотеке объяснений включает часто используемые объяснений в виде списка шаблонов, включая:</span><span class="sxs-lookup"><span data-stu-id="a18dd-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="a18dd-198">Дата</span><span class="sxs-lookup"><span data-stu-id="a18dd-198">Date</span></span></br>
- <span data-ttu-id="a18dd-199">Дата (числовая)</span><span class="sxs-lookup"><span data-stu-id="a18dd-199">Date (numeric)</span></span></br>
- <span data-ttu-id="a18dd-200">Время</span><span class="sxs-lookup"><span data-stu-id="a18dd-200">Time</span></span></br>
- <span data-ttu-id="a18dd-201">Числовой</span><span class="sxs-lookup"><span data-stu-id="a18dd-201">Number</span></span></br>
- <span data-ttu-id="a18dd-202">Номер телефона</span><span class="sxs-lookup"><span data-stu-id="a18dd-202">Phone number</span></span></br>
- <span data-ttu-id="a18dd-203">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="a18dd-203">Zip code</span></span></br>
- <span data-ttu-id="a18dd-204">Первое слово предложения</span><span class="sxs-lookup"><span data-stu-id="a18dd-204">First word of sentence</span></span></br>
- <span data-ttu-id="a18dd-205">Кредитная карта</span><span class="sxs-lookup"><span data-stu-id="a18dd-205">Credit card</span></span></br>
- <span data-ttu-id="a18dd-206">Номер социального страхования</span><span class="sxs-lookup"><span data-stu-id="a18dd-206">Social security number</span></span></br>

<span data-ttu-id="a18dd-207">Обратите внимание, что библиотека объяснений также включает в себя шаблоны для списков фраз, в том числе:</span><span class="sxs-lookup"><span data-stu-id="a18dd-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="a18dd-208">Конец предложения</span><span class="sxs-lookup"><span data-stu-id="a18dd-208">End of sentence</span></span>
- <span data-ttu-id="a18dd-209">Валюта</span><span class="sxs-lookup"><span data-stu-id="a18dd-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="a18dd-210">Использование шаблонов из библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="a18dd-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="a18dd-211">В разделе **Объяснения** на странице **Обучение** вашей модели, выберите **Новый**, затем выберите **Из шаблона**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Создание из шаблона](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="a18dd-213">На странице **Шаблоны объяснений** выберите объяснение, которое хотите использовать, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Выбор шаблона](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="a18dd-215">Информация о шаблоне, который вы выбрали, отобразится на странице **Создание объяснений**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="a18dd-216">При необходимости измените название объяснения, а также добавьте или удалите элементы из списка шаблонов.</span><span class="sxs-lookup"><span data-stu-id="a18dd-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Изменение шаблона](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="a18dd-218">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a18dd-218">When finished, select **Save**.</span></span>
