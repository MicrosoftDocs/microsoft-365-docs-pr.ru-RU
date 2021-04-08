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
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604409"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="71563-103">Введение в типы объяснений</span><span class="sxs-lookup"><span data-stu-id="71563-103">Introduction to explanation types</span></span>

<span data-ttu-id="71563-104">Объяснения помогают определить информацию, которую вы хотите пометить и извлечь в своих моделях осмысления документации в Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="71563-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="71563-105">При создании объяснения следует выбрать тип объяснения.</span><span class="sxs-lookup"><span data-stu-id="71563-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="71563-106">Данная статья поможет вам узнать о разных типах объяснений и о том, как они используются.</span><span class="sxs-lookup"><span data-stu-id="71563-106">This article helps you understand the different explanation types and how they are used.</span></span> 

![Типы объяснений](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="71563-108">Доступны следующие типы объяснений:</span><span class="sxs-lookup"><span data-stu-id="71563-108">These explanation types are available:</span></span>

- <span data-ttu-id="71563-109">**Список фраз**: список слов, фраз, цифр или других символов, которые можно использовать в документе или в извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="71563-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="71563-110">Например, текстовая строка **Направивший врач** находится во всех идентифицируемых документах с медицинскими направлениями.</span><span class="sxs-lookup"><span data-stu-id="71563-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span> <span data-ttu-id="71563-111">Или **номер телефона** направившего врача из идентифицируемого документа с медицинским направлением.</span><span class="sxs-lookup"><span data-stu-id="71563-111">Or the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span>

- <span data-ttu-id="71563-112">**Расстояние**: описывает, насколько близки объяснения.</span><span class="sxs-lookup"><span data-stu-id="71563-112">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="71563-113">Например, список фраз с *номерами домов* идет прямо перед списком фраз с *названиями улиц* без маркеров между ними (больше информации о маркерах приведено в этой статье).</span><span class="sxs-lookup"><span data-stu-id="71563-113">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="71563-114">Для использования типа расстояния необходимо, чтобы в модели было как минимум два объяснения, иначе эта функция будет отключена.</span><span class="sxs-lookup"><span data-stu-id="71563-114">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="71563-115">Список фраз</span><span class="sxs-lookup"><span data-stu-id="71563-115">Phrase list</span></span>

<span data-ttu-id="71563-116">Список фраз — это тип объяснения, который обычно используется, чтобы идентифицировать и классифицировать документ через вашу модель.</span><span class="sxs-lookup"><span data-stu-id="71563-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="71563-117">Как описано в примере с меткой *Направивший врач*, это строка со словами, фразами, номерами или символами, постоянно встречающимися в идентифицируемых документах.</span><span class="sxs-lookup"><span data-stu-id="71563-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="71563-118">Хоть это и не требование, но лучших результатов можно добиться, если считываемая фраза находится во всех документах в одном месте.</span><span class="sxs-lookup"><span data-stu-id="71563-118">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="71563-119">Например, метка *Направивший врач* может находиться в первом абзаце всех документов.</span><span class="sxs-lookup"><span data-stu-id="71563-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="71563-120">Также можно использовать дополнительный параметр **[Настройка расположения фраз в документе](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** для выбора определенных областей, в которых встречается фраза, особенно если существует вероятность ее нахождения в нескольких местах документа.</span><span class="sxs-lookup"><span data-stu-id="71563-120">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there is a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="71563-121">Если при идентификации метки важна точность, при использовании списка фраз вы можете указать это, выбрав флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="71563-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Учет регистра](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="71563-123">Тип фразы особенно полезен при создании объяснения, которое выявляет и извлекает информацию в различных форматах, например даты, номера телефонов и номера кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="71563-123">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="71563-124">Например, значение даты может быть представлено в нескольких различных форматах (1/1/2020, 1-1-2020, 01.01.20, 01.01.2020, 1 января 2020 г. и т. д.).</span><span class="sxs-lookup"><span data-stu-id="71563-124">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="71563-125">Определение списка фраз делает объяснение более эффективным за счет сбора всех возможных вариаций данных, которые вы хотите выявить и извлечь.</span><span class="sxs-lookup"><span data-stu-id="71563-125">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="71563-126">В случае с **номером телефона** извлеките номер телефона каждого направляющего врача из документов с медицинскими направлениями, которые идентифицирует модель.</span><span class="sxs-lookup"><span data-stu-id="71563-126">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="71563-127">При создании объяснения введите различные форматы, в которых номер телефона может отображаться в документе, для сбора возможных вариаций.</span><span class="sxs-lookup"><span data-stu-id="71563-127">When you create the explanation, type the different formats a phone number might display in your document so that you are able to capture possible variations.</span></span> 

![Шаблоны фраз с номерами телефонов](../media/content-understanding/pattern-list.png)

<span data-ttu-id="71563-129">В этом случае в разделе **Дополнительные параметры** установите флажок **Любая цифра от 0 до 9**, чтобы распознавать каждое значение "0", используемое в списке фраз, как любую цифру от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="71563-129">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Любая цифра от 0 до 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="71563-131">Точно так же при создании списка фраз, включающего текстовые символы, установите флажок **Любая буква от a до я**, чтобы распознавать каждый символ "a", используемый в списке фраз, как любую букву от "а" до "я".</span><span class="sxs-lookup"><span data-stu-id="71563-131">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="71563-132">Например, если вы создаете список фраз **Дата** и хотите, чтобы был распознан формат даты типа *1 янв 2020*, нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="71563-132">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="71563-133">Добавьте в список фраз *aaa 0, 0000* и *aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="71563-133">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="71563-134">Убедитесь, что выбран флажок **Любая буква от а до я**.</span><span class="sxs-lookup"><span data-stu-id="71563-134">Make sure that **Any letter from a-z** is also selected.</span></span>

![Любая буква от а до я](../media/content-understanding/any-letter.png)

<span data-ttu-id="71563-136">Кроме того, если ваш список фраз содержит требования по капитализации, вы можете установить флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="71563-136">Additionally, if you have capitalization requirements in your phrase list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="71563-137">В примере с датами, если нужно, чтобы первая буква месяца была заглавной, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="71563-137">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="71563-138">Добавьте в список фраз *Aaa 0, 0000* и *Aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="71563-138">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="71563-139">Убедитесь, что выбран флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="71563-139">Make sure that **Only exact capitalization** is also selected.</span></span>

![Только точная капитализация](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="71563-141">Вместо того, чтобы вручную создавать объяснение для списка фраз, воспользуйтесь [библиотекой объяснений](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) с шаблонами из популярных списков фраз, например *дата*, *номер телефона*, *номер кредитной карты* и т. д.</span><span class="sxs-lookup"><span data-stu-id="71563-141">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="71563-142">Расстояние</span><span class="sxs-lookup"><span data-stu-id="71563-142">Proximity</span></span> 

<span data-ttu-id="71563-143">Тип объяснения по расстоянию позволяет идентифицировать информацию по ее схожести с другим фрагментом данных.</span><span class="sxs-lookup"><span data-stu-id="71563-143">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="71563-144">Например, вы определили в модели два типа объяснений, которые помечают *Улицу и номер дома* и *Номер телефона* клиента.</span><span class="sxs-lookup"><span data-stu-id="71563-144">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="71563-145">Обратите внимание, что номера телефонов клиента всегда идут до номера дома и улицы.</span><span class="sxs-lookup"><span data-stu-id="71563-145">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="71563-146">Алексей Виноградов</span><span class="sxs-lookup"><span data-stu-id="71563-146">Alex Wilburn</span></span><br>
<span data-ttu-id="71563-147">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="71563-147">555-555-5555</span></span><br>
<span data-ttu-id="71563-148">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="71563-148">One Microsoft Way</span></span><br>
<span data-ttu-id="71563-149">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="71563-149">Redmond, WA 98034</span></span><br>

<span data-ttu-id="71563-150">Используйте объяснение по расстоянию, чтобы определить, насколько далеко находится объяснение номера телефона, чтобы лучше идентифицировать адрес в документах.</span><span class="sxs-lookup"><span data-stu-id="71563-150">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Объяснение по расстоянию](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="71563-152">Что такое маркеры?</span><span class="sxs-lookup"><span data-stu-id="71563-152">What are tokens?</span></span>

<span data-ttu-id="71563-153">Чтобы использовать тип объяснения по расстоянию, вам нужно знать, что такое маркер, так как тип объяснения по расстоянию измеряет расстояние в количестве маркеров.</span><span class="sxs-lookup"><span data-stu-id="71563-153">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="71563-154">Маркер — это непрерывный диапазон (без пробелов или пунктуации) букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="71563-154">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="71563-155">В таблице ниже приведены примеры определения количества маркеров в фразе.</span><span class="sxs-lookup"><span data-stu-id="71563-155">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="71563-156">Фраза</span><span class="sxs-lookup"><span data-stu-id="71563-156">Phrase</span></span>|<span data-ttu-id="71563-157">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="71563-157">Number of tokens</span></span>|<span data-ttu-id="71563-158">Объяснение</span><span class="sxs-lookup"><span data-stu-id="71563-158">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="71563-159">1</span><span class="sxs-lookup"><span data-stu-id="71563-159">1</span></span>|<span data-ttu-id="71563-160">Отдельное слово без пунктуации и пробелов.</span><span class="sxs-lookup"><span data-stu-id="71563-160">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="71563-161">1</span><span class="sxs-lookup"><span data-stu-id="71563-161">1</span></span>|<span data-ttu-id="71563-162">Номер локатора записи.</span><span class="sxs-lookup"><span data-stu-id="71563-162">A record locator number.</span></span> <span data-ttu-id="71563-163">Он может включать буквы и цифры, но не знаки пунктуации.</span><span class="sxs-lookup"><span data-stu-id="71563-163">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="71563-164">5</span><span class="sxs-lookup"><span data-stu-id="71563-164">5</span></span>|<span data-ttu-id="71563-165">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="71563-165">A phone number.</span></span> <span data-ttu-id="71563-166">Каждый знак препинания является маркером, поэтому в `425-555-5555` 5 маркеров:</span><span class="sxs-lookup"><span data-stu-id="71563-166">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="71563-167">7</span><span class="sxs-lookup"><span data-stu-id="71563-167">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="71563-168">Настройка типа объяснения по расстоянию</span><span class="sxs-lookup"><span data-stu-id="71563-168">Configure the proximity explanation type</span></span>

<span data-ttu-id="71563-169">В качестве примера настройте расстояние так, чтобы определить диапазон количества маркеров от объяснения *Номер телефона* до объяснения *Номер дома*.</span><span class="sxs-lookup"><span data-stu-id="71563-169">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="71563-170">Обратите внимание, что в качестве минимального диапазона указан «0», потому что между номером телефона и номером дома нет маркеров.</span><span class="sxs-lookup"><span data-stu-id="71563-170">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="71563-171">Однако к некоторым номерам телефонов в примерах документов добавлен *(мобильный)*.</span><span class="sxs-lookup"><span data-stu-id="71563-171">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="71563-172">Николай Белых</span><span class="sxs-lookup"><span data-stu-id="71563-172">Nestor Wilke</span></span><br>
<span data-ttu-id="71563-173">111-111-1111 (мобильный)</span><span class="sxs-lookup"><span data-stu-id="71563-173">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="71563-174">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="71563-174">One Microsoft Way</span></span><br>
<span data-ttu-id="71563-175">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="71563-175">Redmond, WA 98034</span></span><br>

<span data-ttu-id="71563-176">В примере *(мобильный)* три маркера:</span><span class="sxs-lookup"><span data-stu-id="71563-176">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="71563-177">Фраза</span><span class="sxs-lookup"><span data-stu-id="71563-177">Phrase</span></span>|<span data-ttu-id="71563-178">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="71563-178">Token count</span></span>|
|--|--|
|<span data-ttu-id="71563-179">(</span><span class="sxs-lookup"><span data-stu-id="71563-179">(</span></span>|<span data-ttu-id="71563-180">1</span><span class="sxs-lookup"><span data-stu-id="71563-180">1</span></span>|
|<span data-ttu-id="71563-181">мобильный</span><span class="sxs-lookup"><span data-stu-id="71563-181">mobile</span></span>|<span data-ttu-id="71563-182">2</span><span class="sxs-lookup"><span data-stu-id="71563-182">2</span></span>|
|<span data-ttu-id="71563-183">)</span><span class="sxs-lookup"><span data-stu-id="71563-183">)</span></span>|<span data-ttu-id="71563-184">3</span><span class="sxs-lookup"><span data-stu-id="71563-184">3</span></span>|

<span data-ttu-id="71563-185">Настройте параметры расстояния так, чтобы диапазон был от 0 до 3.</span><span class="sxs-lookup"><span data-stu-id="71563-185">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Пример расстояния](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="71563-187">Настройка расположения фраз в документе</span><span class="sxs-lookup"><span data-stu-id="71563-187">Configure where phrases occur in the document</span></span>

<span data-ttu-id="71563-188">Когда вы создаете объяснение, по умолчанию поиск фразы, которую вы пытаетесь извлечь, выполняется по всему документу.</span><span class="sxs-lookup"><span data-stu-id="71563-188">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="71563-189">Однако вы можете использовать дополнительный параметр **Где встречаются эти фразы**, чтобы изолировать определенное место в документе, в котором встречается фраза.</span><span class="sxs-lookup"><span data-stu-id="71563-189">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="71563-190">Это удобно в ситуациях, когда похожие вхождения фразы могут появляться в другом месте документа и вы хотите убедиться в том, что выбран нужный вариант.</span><span class="sxs-lookup"><span data-stu-id="71563-190">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="71563-191">В нашем примере документа с медицинским направлением **Направивший врач** всегда упоминается в первом абзаце документа.</span><span class="sxs-lookup"><span data-stu-id="71563-191">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="71563-192">С помощью параметра **Где встречаются эти фразы** в этом примере вы можете настроить свое объяснение для поиска этой метки только в начальном разделе документа или в любом другом месте, где она может встречаться.</span><span class="sxs-lookup"><span data-stu-id="71563-192">With the \*\*Where these phrases occur setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Параметр "Где встречаются эти фразы"](../media/content-understanding/phrase-location.png)

<span data-ttu-id="71563-194">В этом параметре доступны следующие варианты на выбор.</span><span class="sxs-lookup"><span data-stu-id="71563-194">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="71563-195">В любом месте файла: поиск фразы выполняется во всем документе.</span><span class="sxs-lookup"><span data-stu-id="71563-195">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="71563-196">Начало файла: поиск в документе выполняется с начала до места, где расположена фраза.</span><span class="sxs-lookup"><span data-stu-id="71563-196">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Начало файла](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="71563-198">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="71563-198">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="71563-199">Значение **Конечное положение** обновляется для отображения количества маркеров, содержащихся в выбранной вами области.</span><span class="sxs-lookup"><span data-stu-id="71563-199">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="71563-200">Обратите внимание, что вы можете изменить значение "Конечное положение", а также настроить выбранную область.</span><span class="sxs-lookup"><span data-stu-id="71563-200">Note that you can update the End position value as well to adjust the selected area.</span></span>

   ![Поле положения "Начало файла"](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="71563-202">Конец файла: поиск в документе выполняется с конца до места, где расположена фраза.</span><span class="sxs-lookup"><span data-stu-id="71563-202">End of the file:  The document is searched from the end to the phrase location.</span></span>

   ![Конец файла](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="71563-204">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="71563-204">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="71563-205">Значение **Начальное положение** обновляется для отображения количества маркеров, содержащихся в выбранной вами области.</span><span class="sxs-lookup"><span data-stu-id="71563-205">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="71563-206">Обратите внимание, что вы можете изменить значение "Начальное положение", а также настроить выбранную область.</span><span class="sxs-lookup"><span data-stu-id="71563-206">Note that you can update the Starting position value as well to adjust the selected area.</span></span>

   ![Конечное поле "Конец файла"](../media/content-understanding/end-box.png)

- <span data-ttu-id="71563-208">Произвольный диапазон: поиск расположения фразы в документе выполняется в указанном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="71563-208">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span>

   ![Произвольный диапазон](../media/content-understanding/custom-file.png)

    <span data-ttu-id="71563-210">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="71563-210">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="71563-211">Для этого параметра требуется выбрать положение **Начало** и **Конец**.</span><span class="sxs-lookup"><span data-stu-id="71563-211">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="71563-212">Эти значения отражают количество маркеров с начала документа.</span><span class="sxs-lookup"><span data-stu-id="71563-212">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="71563-213">Хотя вы можете вручную ввести эти значения, проще вручную изменить поле выбора в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="71563-213">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="71563-214">Используйте шаблона объяснений</span><span class="sxs-lookup"><span data-stu-id="71563-214">Use explanation templates</span></span>

<span data-ttu-id="71563-215">Вы можете вручную добавлять значения списка фраз для объяснений, но может быть проще использовать шаблоны из библиотеки объяснений.</span><span class="sxs-lookup"><span data-stu-id="71563-215">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="71563-216">Например, вместо того, чтобы вручную добавлять все варианты *Даты*, вы можете использовать шаблон списка фраз для *Дат*, так как в нем уже есть несколько значений списков фраз:</span><span class="sxs-lookup"><span data-stu-id="71563-216">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span>

![Библиотека объяснений](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="71563-218&quot;>Библиотека объяснений включает часто используемые объяснения списка фраз, включая:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;71563-218&quot;>The explanation library includes commonly used phrase list explanations, including:</span></span>

- <span data-ttu-id=&quot;71563-219&quot;>Дата: даты календаря, все форматы.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;71563-219&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;71563-220&quot;>Содержит текст и числа (например, &quot;9 декабря 2020 г.").</span><span class="sxs-lookup"><span data-stu-id="71563-220">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="71563-221">Дата (численная): даты календаря, все форматы.</span><span class="sxs-lookup"><span data-stu-id="71563-221">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="71563-222">Содержит числа (например, 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="71563-222">Includes numbers (for example 1-11-2020).</span></span>
- <span data-ttu-id="71563-223">Время: 12- и 24-часовой форматы.</span><span class="sxs-lookup"><span data-stu-id="71563-223">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="71563-224">Число: положительные и отрицательные числа с десятичными дробями до двух знаков после запятой.</span><span class="sxs-lookup"><span data-stu-id="71563-224">Number: Positive and negative numbers up to 2 decimals.</span></span> 
- <span data-ttu-id="71563-225">Процент: список шаблонов, представляющих процентные значения.</span><span class="sxs-lookup"><span data-stu-id="71563-225">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="71563-226">Например, 1 %, 11 %, 100 %, 11,11 % и т. д.</span><span class="sxs-lookup"><span data-stu-id="71563-226">For example, 1%, 11%, 100%, 11.11%, etc.</span></span>
- <span data-ttu-id="71563-227">Номер телефона: распространенные форматы, используемые в США и в других странах мира.</span><span class="sxs-lookup"><span data-stu-id="71563-227">Phone number: Common US and International formats.</span></span> <span data-ttu-id="71563-228">Например, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000 и т. д.</span><span class="sxs-lookup"><span data-stu-id="71563-228">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span>
- <span data-ttu-id="71563-229">Почтовый индекс: почтовый индекс в США.</span><span class="sxs-lookup"><span data-stu-id="71563-229">Zip code: US Zip code formats.</span></span> <span data-ttu-id="71563-230">Например, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="71563-230">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="71563-231">Первое слово предложения: общие шаблоны для слов длиной до 9 букв.</span><span class="sxs-lookup"><span data-stu-id="71563-231">First word of sentence: Common patterns for words up to 9 characters.</span></span> 
- <span data-ttu-id="71563-232">Конец предложения: распространенные знаки препинания для конца предложения</span><span class="sxs-lookup"><span data-stu-id="71563-232">End of sentence: Common punctuation for end of a sentence</span></span>
- <span data-ttu-id="71563-233">Кредитная карта: распространенные форматы номеров кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="71563-233">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="71563-234">Например, 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="71563-234">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="71563-235">Номер социального обеспечения: формат номера социального обеспечения США.</span><span class="sxs-lookup"><span data-stu-id="71563-235">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="71563-236">Например, 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="71563-236">For example, 111-11-1111.</span></span> 
- <span data-ttu-id="71563-237">Элемент "Флажок": список фраз, представляющий варианты для заполнения.</span><span class="sxs-lookup"><span data-stu-id="71563-237">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="71563-238">Например, _X_, _ _X_ и т. д.</span><span class="sxs-lookup"><span data-stu-id="71563-238">For example, _X_, _ _X_, etc.</span></span>
- <span data-ttu-id="71563-239">Валюта: основные международные символы валют.</span><span class="sxs-lookup"><span data-stu-id="71563-239">Currency: Major international symbols.</span></span> <span data-ttu-id="71563-240">Пример: $.</span><span class="sxs-lookup"><span data-stu-id="71563-240">For example, $.</span></span> 
- <span data-ttu-id="71563-241">Адрес электронной почты для отправки копий сообщения: список фраз с термином "CC:", который часто находится рядом с именами или адресами электронной почты дополнительных пользователей или групп, на которые было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="71563-241">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span>
- <span data-ttu-id="71563-242">Дата сообщения электронной почты: список фраз с термином "Отправлено:", который часто находится рядом с датой отправки сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="71563-242">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="71563-243">Приветствие в электронном письме: часто встречающиеся строки, которыми открывается тело сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="71563-243">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="71563-244">Адресат электронной почты: список фраз с термином "Кому:", который часто находится рядом с именами или адресами электронной почты пользователей или групп, на которые было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="71563-244">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="71563-245">Отправитель электронной почты: список фраз с термином "От:", который часто находится рядом с именем или адресом электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="71563-245">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="71563-246">Тема сообщения электронной почты: список фраз с термином "Тема:", который часто находится рядом с темой сообщения.</span><span class="sxs-lookup"><span data-stu-id="71563-246">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> 

<span data-ttu-id="71563-247">Библиотека объяснений также содержит три автоматических типа шаблонов для работы с данными, которые вы пометили в файлах примера:</span><span class="sxs-lookup"><span data-stu-id="71563-247">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="71563-248">После метки. Слова и символы, которые встречаются после меток в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="71563-248">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="71563-249">До метки. Слова и символы, которые встречаются до меток в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="71563-249">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="71563-250">Метки. До 10 первых меток из файлов примера.</span><span class="sxs-lookup"><span data-stu-id="71563-250">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="71563-251">В следующем файле примера для демонстрации работы автоматических шаблонов используется шаблон объяснения "До метки", чтобы предоставить модели дополнительные сведения для получения более точного соответствия.</span><span class="sxs-lookup"><span data-stu-id="71563-251">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

![Пример файла](../media/content-understanding/before-label.png)

<span data-ttu-id="71563-253">Если выбрать шаблон объяснения "До метки", он будет искать первый набор слов, которые появляются перед меткой в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="71563-253">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="71563-254">Например, слова, определяемые в первом примере файла: "As of" (Начиная с).</span><span class="sxs-lookup"><span data-stu-id="71563-254">In the example, the words that are identified in the first example file is "As of".</span></span>

![Шаблон "Перед меткой"](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="71563-256">Чтобы создать объяснение из шаблона, вы можете выбрать **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="71563-256">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="71563-257">Когда вы добавляете другие примеры файлов, дополнительные слова определяются и добавляются в список фраз.</span><span class="sxs-lookup"><span data-stu-id="71563-257">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Добавление метки](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="71563-259">Использование шаблонов из библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="71563-259">To use a template from the explanation library</span></span>

1. <span data-ttu-id="71563-260">В разделе **Объяснения** на странице **Обучение** вашей модели, выберите **Новый**, затем выберите **Из шаблона**.</span><span class="sxs-lookup"><span data-stu-id="71563-260">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Добавление перед меткой](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="71563-262">На странице **Шаблоны объяснений** выберите объяснение, которое хотите использовать, и выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="71563-262">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Выбор шаблона](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="71563-264">Информация о выбранном шаблоне отображается на странице **Создание объяснений**.</span><span class="sxs-lookup"><span data-stu-id="71563-264">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="71563-265">При необходимости измените название объяснения, а также добавьте или удалите элементы из списка фраз.</span><span class="sxs-lookup"><span data-stu-id="71563-265">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Изменение шаблона](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="71563-267">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="71563-267">When finished, select **Save**.</span></span>