---
title: Типы объяснений в Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Подробнее о типах объяснений в Microsoft SharePoint Syntex
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706580"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="32eba-103">Типы объяснений в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="32eba-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="32eba-104">Объяснения помогают определить информацию, которую вы хотите пометить и извлечь в своих моделях осмысления документации в Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="32eba-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="32eba-105">При создании объяснения следует выбрать тип объяснения.</span><span class="sxs-lookup"><span data-stu-id="32eba-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="32eba-106">Эта статья поможет вам узнать о разных типах объяснений и о том, как они используются.</span><span class="sxs-lookup"><span data-stu-id="32eba-106">This article helps you understand the different explanation types and how they're used.</span></span>

![Снимок экрана: панель "Создание объяснения" с тремя типами объяснений.](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="32eba-108">Существуют следующие типы объяснений:</span><span class="sxs-lookup"><span data-stu-id="32eba-108">These explanation types are available:</span></span>

- <span data-ttu-id="32eba-109">[**Список фраз**](#phrase-list): список слов, фраз, цифр или других символов, которые можно использовать в документе или в извлекаемой информации.</span><span class="sxs-lookup"><span data-stu-id="32eba-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="32eba-110">Например, текстовая строка *Направивший врач* находится во всех идентифицируемых документах с медицинскими направлениями.</span><span class="sxs-lookup"><span data-stu-id="32eba-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="32eba-111">Или *Номер телефона* направившего врача из идентифицируемого документа с медицинским направлением.</span><span class="sxs-lookup"><span data-stu-id="32eba-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="32eba-112">[**Регулярное выражение**](#regular-expression): использует нотацию сопоставления с шаблоном для поиска определенных сочетаний символов.</span><span class="sxs-lookup"><span data-stu-id="32eba-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="32eba-113">Например, с помощью регулярного выражения можно найти все *адреса электронной почты* в наборе документов.</span><span class="sxs-lookup"><span data-stu-id="32eba-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="32eba-114">[**Расстояние**](#proximity): описывает, насколько близки объяснения друг к другу.</span><span class="sxs-lookup"><span data-stu-id="32eba-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="32eba-115">Например, список фраз с *номерами домов* идет прямо перед списком фраз с *названиями улиц* без маркеров между ними (больше информации о маркерах приведено в этой статье).</span><span class="sxs-lookup"><span data-stu-id="32eba-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="32eba-116">Для использования типа расстояния необходимо, чтобы в модели было как минимум два объяснения, иначе эта функция будет отключена.</span><span class="sxs-lookup"><span data-stu-id="32eba-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="32eba-117">Список фраз</span><span class="sxs-lookup"><span data-stu-id="32eba-117">Phrase list</span></span>

<span data-ttu-id="32eba-118">Список фраз — это тип объяснения, который обычно используется, чтобы идентифицировать и классифицировать документ через вашу модель.</span><span class="sxs-lookup"><span data-stu-id="32eba-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="32eba-119">Как описано в примере с меткой *Направивший врач*, это строка со словами, фразами, номерами или символами, постоянно встречающимися в идентифицируемых документах.</span><span class="sxs-lookup"><span data-stu-id="32eba-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="32eba-120">Хоть это и не обязательно, но если считываемая фраза находится в одном и том же месте во всех документах, это позволяет добиться наилучших результатов.</span><span class="sxs-lookup"><span data-stu-id="32eba-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="32eba-121">Например, метка *Направивший врач* может находиться в первом абзаце всех документов.</span><span class="sxs-lookup"><span data-stu-id="32eba-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="32eba-122">Также можно использовать дополнительный параметр **[Настройка расположения фраз в документе](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** для выбора определенных областей, в которых встречается фраза, особенно если существует вероятность ее нахождения в нескольких местах документа.</span><span class="sxs-lookup"><span data-stu-id="32eba-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="32eba-123">Если при идентификации метки важна точность, при использовании списка фраз вы можете указать это, выбрав флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="32eba-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Учет регистра](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="32eba-125">Тип фразы особенно полезен при создании объяснения, которое выявляет и извлекает информацию в различных форматах, например даты, номера телефонов и номера кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="32eba-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="32eba-126">Например, дата может быть представлена в нескольких различных форматах (1/1/2020, 1-1-2020, 01.01.20, 01.01.2020, 1 января 2020 г. и т. д.).</span><span class="sxs-lookup"><span data-stu-id="32eba-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="32eba-127">Определение списка фраз делает объяснение более эффективным, так как оно будет содержать все возможные вариации данных, которые вы хотите выявить и извлечь.</span><span class="sxs-lookup"><span data-stu-id="32eba-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="32eba-128">В случае с *номером телефона* извлеките номер телефона каждого направляющего врача из документов с медицинскими направлениями, которые идентифицирует модель.</span><span class="sxs-lookup"><span data-stu-id="32eba-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="32eba-129">При создании объяснения введите различные форматы, в которых номер телефона может отображаться в документе, для сбора возможных вариаций.</span><span class="sxs-lookup"><span data-stu-id="32eba-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![Шаблоны фраз с номерами телефонов](../media/content-understanding/pattern-list.png)

<span data-ttu-id="32eba-131">В этом случае в разделе **Дополнительные параметры** установите флажок **Любая цифра от 0 до 9**, чтобы распознавать каждое значение "0", используемое в списке фраз, как любую цифру от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="32eba-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Любая цифра от 0 до 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="32eba-133">Точно так же при создании списка фраз, включающего текстовые символы, установите флажок **Любая буква от a до я**, чтобы распознавать каждый символ "a", используемый в списке фраз, как любую букву от "а" до "я".</span><span class="sxs-lookup"><span data-stu-id="32eba-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="32eba-134">Например, если вы создаете список фраз **Дата** и хотите, чтобы был распознан формат даты типа *1 янв 2020*, нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="32eba-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="32eba-135">Добавьте в список фраз *aaa 0, 0000* и *aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="32eba-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="32eba-136">Убедитесь, что выбран флажок **Любая буква от а до я**.</span><span class="sxs-lookup"><span data-stu-id="32eba-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![Любая буква от а до я](../media/content-understanding/any-letter.png)

<span data-ttu-id="32eba-138">Кроме того, если ваш список фраз содержит требования относительно заглавных букв, вы можете установить флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="32eba-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="32eba-139">В примере с датами, если нужно, чтобы первая буква месяца была заглавной, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="32eba-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="32eba-140">Добавьте в список фраз *Aaa 0, 0000* и *Aaa 00, 0000*.</span><span class="sxs-lookup"><span data-stu-id="32eba-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="32eba-141">Убедитесь, что выбран флажок **Только точная капитализация**.</span><span class="sxs-lookup"><span data-stu-id="32eba-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![Только точная капитализация](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="32eba-143">Вместо того, чтобы вручную создавать объяснение для списка фраз, воспользуйтесь [библиотекой объяснений](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) с шаблонами популярных списков фраз, например *дата*, *номер телефона*, *номер кредитной карты* и т. д.</span><span class="sxs-lookup"><span data-stu-id="32eba-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="32eba-144">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="32eba-144">Regular expression</span></span>

<span data-ttu-id="32eba-145">Тип объяснения регулярного выражения позволяет создавать шаблоны, помогающие находить и выявлять определенные текстовые строки в документах.</span><span class="sxs-lookup"><span data-stu-id="32eba-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="32eba-146">С помощью регулярных выражений можно быстро анализировать большие объемы текста, чтобы:</span><span class="sxs-lookup"><span data-stu-id="32eba-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="32eba-147">Находить сочетания символов, соответствующие определенным шаблонам.</span><span class="sxs-lookup"><span data-stu-id="32eba-147">Find specific character patterns.</span></span>
- <span data-ttu-id="32eba-148">Проверять текст на соответствие заданному шаблону (например, адресу электронной почты).</span><span class="sxs-lookup"><span data-stu-id="32eba-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="32eba-149">Извлекать, изменять, заменять и удалять подстроки текста.</span><span class="sxs-lookup"><span data-stu-id="32eba-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="32eba-150">Тип регулярного выражения особенно полезен при создании объяснения, которое выявляет и извлекает информацию в различных форматах, например даты, номера телефонов и номера кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="32eba-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="32eba-151">Например, адрес электронной почты, такой как olga@contoso.com, отображается в определенном шаблоне ("olga" — первая часть, а "com" — последняя часть).</span><span class="sxs-lookup"><span data-stu-id="32eba-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="32eba-152">Регулярное выражение для адреса электронной почты: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span><span class="sxs-lookup"><span data-stu-id="32eba-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="32eba-153">Это выражение состоит из пяти частей в таком порядке:</span><span class="sxs-lookup"><span data-stu-id="32eba-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="32eba-154">Следующие символы в любом количестве: </span><span class="sxs-lookup"><span data-stu-id="32eba-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="32eba-155">а.</span><span class="sxs-lookup"><span data-stu-id="32eba-155">a.</span></span> <span data-ttu-id="32eba-156">буквы от a до z</span><span class="sxs-lookup"><span data-stu-id="32eba-156">Letters from a to z</span></span>

   <span data-ttu-id="32eba-157">б.</span><span class="sxs-lookup"><span data-stu-id="32eba-157">b.</span></span> <span data-ttu-id="32eba-158">цифры от 0 до 9</span><span class="sxs-lookup"><span data-stu-id="32eba-158">Numbers from 0-9</span></span>

   <span data-ttu-id="32eba-159">в.</span><span class="sxs-lookup"><span data-stu-id="32eba-159">c.</span></span> <span data-ttu-id="32eba-160">точка, символ подчеркивания, знак процент или дефис</span><span class="sxs-lookup"><span data-stu-id="32eba-160">Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="32eba-161">Знак @</span><span class="sxs-lookup"><span data-stu-id="32eba-161">The @ symbol</span></span>

3. <span data-ttu-id="32eba-162">любое количество тех же символов, что и в первой части адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="32eba-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="32eba-163">точка</span><span class="sxs-lookup"><span data-stu-id="32eba-163">A period</span></span>

5. <span data-ttu-id="32eba-164">от двух до шести букв</span><span class="sxs-lookup"><span data-stu-id="32eba-164">Two to six letters</span></span>

<span data-ttu-id="32eba-165">Чтобы добавить тип объяснения регулярного выражения, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="32eba-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="32eba-166">На панели **Создание объяснения** в элементе **Тип объяснения** выберите **Регулярное выражение**.</span><span class="sxs-lookup"><span data-stu-id="32eba-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![Снимок экрана: панель "Создание объяснения" с выбранным регулярным выражением.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="32eba-168">Вы можете ввести выражение вручную в поле **Регулярное выражение** или выбрать **Добавить регулярное выражение из шаблона**.</span><span class="sxs-lookup"><span data-stu-id="32eba-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="32eba-169">При добавлении регулярного выражения с помощью шаблона в текстовое поле автоматически добавляются имя и регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="32eba-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="32eba-170">Например, если вы выберете **адрес электронной почты**, будет заполнена панель **Создание объяснения**.</span><span class="sxs-lookup"><span data-stu-id="32eba-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![Снимок экрана: панель "Создание объяснения" с выбранным регулярным выражением "Адрес электронной почты".](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="32eba-172">Расстояние</span><span class="sxs-lookup"><span data-stu-id="32eba-172">Proximity</span></span> 

<span data-ttu-id="32eba-173">Тип объяснения по расстоянию позволяет идентифицировать информацию по ее схожести с другим фрагментом данных.</span><span class="sxs-lookup"><span data-stu-id="32eba-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="32eba-174">Например, вы определили в модели два типа объяснений, которые помечают *Улицу и номер дома* и *Номер телефона* клиента.</span><span class="sxs-lookup"><span data-stu-id="32eba-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="32eba-175">Обратите внимание, что номера телефонов клиента всегда идут до номера дома и улицы.</span><span class="sxs-lookup"><span data-stu-id="32eba-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="32eba-176">Алексей Виноградов</span><span class="sxs-lookup"><span data-stu-id="32eba-176">Alex Wilburn</span></span><br>
<span data-ttu-id="32eba-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="32eba-177">555-555-5555</span></span><br>
<span data-ttu-id="32eba-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="32eba-178">One Microsoft Way</span></span><br>
<span data-ttu-id="32eba-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="32eba-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="32eba-180">Используйте объяснение по расстоянию, чтобы определить, насколько далеко находится объяснение номера телефона, чтобы лучше идентифицировать адрес в документах.</span><span class="sxs-lookup"><span data-stu-id="32eba-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Объяснение по расстоянию](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="32eba-182">Что такое маркеры?</span><span class="sxs-lookup"><span data-stu-id="32eba-182">What are tokens?</span></span>

<span data-ttu-id="32eba-183">Чтобы использовать тип объяснения по расстоянию, необходимо понять, что такое маркер.</span><span class="sxs-lookup"><span data-stu-id="32eba-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="32eba-184">Тип объяснения по расстоянию измеряет расстояние в маркерах.</span><span class="sxs-lookup"><span data-stu-id="32eba-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="32eba-185">Маркер — это непрерывный диапазон (без пробелов или пунктуации) букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="32eba-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="32eba-186">В таблице ниже приведены примеры определения количества маркеров в фразе.</span><span class="sxs-lookup"><span data-stu-id="32eba-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="32eba-187">Фраза</span><span class="sxs-lookup"><span data-stu-id="32eba-187">Phrase</span></span>|<span data-ttu-id="32eba-188">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="32eba-188">Number of tokens</span></span>|<span data-ttu-id="32eba-189">Объяснение</span><span class="sxs-lookup"><span data-stu-id="32eba-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="32eba-190">1</span><span class="sxs-lookup"><span data-stu-id="32eba-190">1</span></span>|<span data-ttu-id="32eba-191">Отдельное слово без пунктуации и пробелов.</span><span class="sxs-lookup"><span data-stu-id="32eba-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="32eba-192">1</span><span class="sxs-lookup"><span data-stu-id="32eba-192">1</span></span>|<span data-ttu-id="32eba-193">Номер локатора записи.</span><span class="sxs-lookup"><span data-stu-id="32eba-193">A record locator number.</span></span> <span data-ttu-id="32eba-194">Он может содержать буквы и цифры, но не знаки пунктуации.</span><span class="sxs-lookup"><span data-stu-id="32eba-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="32eba-195">5</span><span class="sxs-lookup"><span data-stu-id="32eba-195">5</span></span>|<span data-ttu-id="32eba-196">Номер телефона.</span><span class="sxs-lookup"><span data-stu-id="32eba-196">A phone number.</span></span> <span data-ttu-id="32eba-197">Каждый знак препинания является маркером, поэтому в `425-555-5555` 5 маркеров:</span><span class="sxs-lookup"><span data-stu-id="32eba-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="32eba-198">7</span><span class="sxs-lookup"><span data-stu-id="32eba-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="32eba-199">Настройка типа объяснения по расстоянию</span><span class="sxs-lookup"><span data-stu-id="32eba-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="32eba-200">В качестве примера настройте расстояние так, чтобы определить диапазон количества маркеров от объяснения *Номер телефона* до объяснения *Номер дома*.</span><span class="sxs-lookup"><span data-stu-id="32eba-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="32eba-201">Обратите внимание, что в качестве минимального диапазона указан «0», потому что между номером телефона и номером дома нет маркеров.</span><span class="sxs-lookup"><span data-stu-id="32eba-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="32eba-202">Однако к некоторым номерам телефонов в примерах документов добавлен *(мобильный)*.</span><span class="sxs-lookup"><span data-stu-id="32eba-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="32eba-203">Николай Белых</span><span class="sxs-lookup"><span data-stu-id="32eba-203">Nestor Wilke</span></span><br>
<span data-ttu-id="32eba-204">111-111-1111 (мобильный)</span><span class="sxs-lookup"><span data-stu-id="32eba-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="32eba-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="32eba-205">One Microsoft Way</span></span><br>
<span data-ttu-id="32eba-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="32eba-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="32eba-207">В примере *(мобильный)* три маркера:</span><span class="sxs-lookup"><span data-stu-id="32eba-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="32eba-208">Фраза</span><span class="sxs-lookup"><span data-stu-id="32eba-208">Phrase</span></span>|<span data-ttu-id="32eba-209">Количество маркеров</span><span class="sxs-lookup"><span data-stu-id="32eba-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="32eba-210">(</span><span class="sxs-lookup"><span data-stu-id="32eba-210">(</span></span>|<span data-ttu-id="32eba-211">1</span><span class="sxs-lookup"><span data-stu-id="32eba-211">1</span></span>|
|<span data-ttu-id="32eba-212">мобильный</span><span class="sxs-lookup"><span data-stu-id="32eba-212">mobile</span></span>|<span data-ttu-id="32eba-213">2</span><span class="sxs-lookup"><span data-stu-id="32eba-213">2</span></span>|
|<span data-ttu-id="32eba-214">)</span><span class="sxs-lookup"><span data-stu-id="32eba-214">)</span></span>|<span data-ttu-id="32eba-215">3</span><span class="sxs-lookup"><span data-stu-id="32eba-215">3</span></span>|

<span data-ttu-id="32eba-216">Настройте параметры расстояния так, чтобы диапазон был от 0 до 3.</span><span class="sxs-lookup"><span data-stu-id="32eba-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Пример расстояния](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="32eba-218">Настройка расположения фраз в документе</span><span class="sxs-lookup"><span data-stu-id="32eba-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="32eba-219">Когда вы создаете объяснение, по умолчанию поиск фразы, которую вы пытаетесь извлечь, выполняется по всему документу.</span><span class="sxs-lookup"><span data-stu-id="32eba-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="32eba-220">Однако вы можете использовать дополнительный параметр **Где встречаются эти фразы**, чтобы изолировать определенное место в документе, в котором встречается фраза.</span><span class="sxs-lookup"><span data-stu-id="32eba-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="32eba-221">Это удобно в ситуациях, когда похожие вхождения фразы могут появляться в другом месте документа и вы хотите убедиться в том, что выбран нужный вариант.</span><span class="sxs-lookup"><span data-stu-id="32eba-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="32eba-222">В нашем примере, когда документ представляет собой медицинское направление, *Направивший врач* всегда упоминается в первом абзаце документа.</span><span class="sxs-lookup"><span data-stu-id="32eba-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="32eba-223">С помощью параметра **Где встречаются эти фразы** в этом примере вы можете настроить свое объяснение для поиска этой метки только в начальном разделе документа или в любом другом месте, где она может встречаться.</span><span class="sxs-lookup"><span data-stu-id="32eba-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Параметр "Где встречаются эти фразы"](../media/content-understanding/phrase-location.png)

<span data-ttu-id="32eba-225">В этом параметре доступны следующие варианты на выбор.</span><span class="sxs-lookup"><span data-stu-id="32eba-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="32eba-226">В любом месте файла: поиск фразы выполняется во всем документе.</span><span class="sxs-lookup"><span data-stu-id="32eba-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="32eba-227">Начало файла: поиск в документе выполняется с начала до места, где расположена фраза.</span><span class="sxs-lookup"><span data-stu-id="32eba-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Начало файла](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="32eba-229">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="32eba-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="32eba-230">Значение **Конечное положение** обновляется для отображения количества маркеров, содержащихся в выбранной вами области.</span><span class="sxs-lookup"><span data-stu-id="32eba-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="32eba-231">Обратите внимание, что вы можете изменить значение **Конечное положение**, а также настроить выбранную область.</span><span class="sxs-lookup"><span data-stu-id="32eba-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![Поле положения "Начало файла"](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="32eba-233">Конец файла: поиск в документе выполняется с конца до места, где расположена фраза.</span><span class="sxs-lookup"><span data-stu-id="32eba-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![Конец файла](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="32eba-235">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="32eba-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="32eba-236">Значение **Начальное положение** обновляется для отображения количества маркеров, содержащихся в выбранной вами области.</span><span class="sxs-lookup"><span data-stu-id="32eba-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="32eba-237">Обратите внимание, что вы можете изменить значение "Начальное положение", а также настроить выбранную область.</span><span class="sxs-lookup"><span data-stu-id="32eba-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![Конечное поле "Конец файла"](../media/content-understanding/end-box.png)

- <span data-ttu-id="32eba-239">Произвольный диапазон: поиск расположения фразы в документе выполняется в указанном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="32eba-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![Произвольный диапазон](../media/content-understanding/custom-file.png)

    <span data-ttu-id="32eba-241">В средстве просмотра вы можете вручную изменить поле выбора, чтобы включить расположение фразы.</span><span class="sxs-lookup"><span data-stu-id="32eba-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="32eba-242">Для этого параметра требуется выбрать положение **Начало** и **Конец**.</span><span class="sxs-lookup"><span data-stu-id="32eba-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="32eba-243">Эти значения отражают количество маркеров с начала документа.</span><span class="sxs-lookup"><span data-stu-id="32eba-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="32eba-244">Хотя вы можете вручную ввести эти значения, проще вручную изменить поле выбора в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="32eba-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="32eba-245">Используйте шаблона объяснений</span><span class="sxs-lookup"><span data-stu-id="32eba-245">Use explanation templates</span></span>

<span data-ttu-id="32eba-246">Вы можете вручную добавлять значения списка фраз для объяснений, но может быть проще использовать шаблоны из библиотеки объяснений.</span><span class="sxs-lookup"><span data-stu-id="32eba-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="32eba-247">Например, вместо того, чтобы вручную добавлять все варианты *Даты*, вы можете использовать шаблон списка фраз для *Дат*, так как в нем уже есть несколько значений списков фраз:</span><span class="sxs-lookup"><span data-stu-id="32eba-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![Библиотека объяснений](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="32eba-249&quot;>Библиотека объяснений содержит часто используемые объяснения *списка фраз*, в том числе:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;32eba-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;32eba-250&quot;>Дата: даты календаря, все форматы.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;32eba-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;32eba-251&quot;>Содержит текст и числа (например, &quot;9 декабря 2020 г.").</span><span class="sxs-lookup"><span data-stu-id="32eba-251">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="32eba-252">Дата (численная): даты календаря, все форматы.</span><span class="sxs-lookup"><span data-stu-id="32eba-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="32eba-253">Числа (например, 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="32eba-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="32eba-254">Время: 12- и 24-часовой форматы.</span><span class="sxs-lookup"><span data-stu-id="32eba-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="32eba-255">Число: положительные и отрицательные числа с десятичными дробями до двух знаков после запятой.</span><span class="sxs-lookup"><span data-stu-id="32eba-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="32eba-256">Процент: список шаблонов, представляющих процентные значения.</span><span class="sxs-lookup"><span data-stu-id="32eba-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="32eba-257">Например, 1%, 11%, 100% или 11.11%.</span><span class="sxs-lookup"><span data-stu-id="32eba-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="32eba-258">Номер телефона: распространенные форматы, используемые в США и в других странах мира.</span><span class="sxs-lookup"><span data-stu-id="32eba-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="32eba-259">Например, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000 и т. д.</span><span class="sxs-lookup"><span data-stu-id="32eba-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="32eba-260">Почтовый индекс: почтовый индекс в США.</span><span class="sxs-lookup"><span data-stu-id="32eba-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="32eba-261">Например, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="32eba-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="32eba-262">Первое слово предложения: общие шаблоны для слов длиной до 9 букв.</span><span class="sxs-lookup"><span data-stu-id="32eba-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="32eba-263">Конец предложения: распространенные знаки препинания для конца предложения</span><span class="sxs-lookup"><span data-stu-id="32eba-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="32eba-264">Кредитная карта: распространенные форматы номеров кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="32eba-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="32eba-265">Например, 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="32eba-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="32eba-p132">Номер социального обеспечения: формат номера социального обеспечения США. Например, 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="32eba-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="32eba-268">Элемент "Флажок": список фраз, представляющий варианты проставленного флажка.</span><span class="sxs-lookup"><span data-stu-id="32eba-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="32eba-269">Например, _X_, _ _X_ и т. д.</span><span class="sxs-lookup"><span data-stu-id="32eba-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="32eba-270">Валюта: основные международные символы валют.</span><span class="sxs-lookup"><span data-stu-id="32eba-270">Currency: Major international symbols.</span></span> <span data-ttu-id="32eba-271">Пример: $.</span><span class="sxs-lookup"><span data-stu-id="32eba-271">For example, $.</span></span> 
- <span data-ttu-id="32eba-272">Адрес электронной почты для отправки копий сообщения: список фраз с термином "CC:", который часто находится рядом с именами или адресами электронной почты дополнительных пользователей или групп - адресатов сообщения.</span><span class="sxs-lookup"><span data-stu-id="32eba-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="32eba-273">Дата сообщения электронной почты: список фраз с термином "Отправлено:", который часто находится рядом с датой отправки сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="32eba-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="32eba-274">Приветствие в электронном письме: часто встречающиеся строки, которыми открывается тело сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="32eba-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="32eba-275">Адресат электронной почты: список фраз с термином "Кому:", который часто находится рядом с именами или адресами электронной почты пользователей или групп, на которые было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="32eba-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="32eba-276">Отправитель электронной почты: список фраз с термином "От:", который часто находится рядом с именем или адресом электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="32eba-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="32eba-277">Тема сообщения электронной почты: список фраз с термином "Тема:", который часто находится рядом с темой сообщения.</span><span class="sxs-lookup"><span data-stu-id="32eba-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="32eba-278">Библиотека объяснений содержит часто используемые объяснения в формате *регулярных выражений*, в том числе:</span><span class="sxs-lookup"><span data-stu-id="32eba-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="32eba-279">От 6 до 17 цифр: соответствует любому числу длиной от 6 до 17 цифр.</span><span class="sxs-lookup"><span data-stu-id="32eba-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="32eba-280">Номера банковских счетов в США соответствуют этому шаблону.</span><span class="sxs-lookup"><span data-stu-id="32eba-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="32eba-281">Адрес электронной почты: соответствует общему типу адреса электронной почты, например olgaa@contoso.com</span><span class="sxs-lookup"><span data-stu-id="32eba-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="32eba-282">Идентификационный номер налогоплательщика США: 3-значный номер, начинающийся с 9, за которым следует 6-значный номер, начинающийся с 7 или 8.</span><span class="sxs-lookup"><span data-stu-id="32eba-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="32eba-283">Веб-адрес (URL-адрес): соответствует формату веб-адреса, то есть начинается с http:// или https://</span><span class="sxs-lookup"><span data-stu-id="32eba-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="32eba-284">Библиотека объяснений также содержит три автоматических типа шаблонов для работы с данными, которые вы пометили в файлах примера:</span><span class="sxs-lookup"><span data-stu-id="32eba-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="32eba-285">После метки. Слова и символы, которые встречаются после меток в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="32eba-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="32eba-286">До метки. Слова и символы, которые встречаются до меток в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="32eba-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="32eba-287">Метки. До 10 первых меток из файлов примера.</span><span class="sxs-lookup"><span data-stu-id="32eba-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="32eba-288">В следующем примере мы рассмотрим для демонстрации работы автоматических шаблонов шаблон объяснения "До метки", предоставляющий модели дополнительные сведения для получения более точного соответствия.</span><span class="sxs-lookup"><span data-stu-id="32eba-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![Пример файла](../media/content-understanding/before-label.png)

<span data-ttu-id="32eba-290">Если выбрать шаблон объяснения "До метки", он будет искать первый набор слов, которые появляются перед меткой в файлах примера.</span><span class="sxs-lookup"><span data-stu-id="32eba-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="32eba-291">Например, слова, определяемые в первом примере файла: "As of" (Начиная с).</span><span class="sxs-lookup"><span data-stu-id="32eba-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![Шаблон "Перед меткой"](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="32eba-293">Чтобы создать объяснение из шаблона, вы можете выбрать **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="32eba-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="32eba-294">Когда вы добавляете другие примеры файлов, дополнительные слова определяются и добавляются в список фраз.</span><span class="sxs-lookup"><span data-stu-id="32eba-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Добавление метки](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="32eba-296">Использование шаблонов из библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="32eba-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="32eba-297">В разделе **Объяснения** на странице **Обучение** вашей модели, выберите **Новый**, затем выберите **Из шаблона**.</span><span class="sxs-lookup"><span data-stu-id="32eba-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Добавление перед меткой](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="32eba-299">На странице **Шаблоны объяснений** выберите объяснение, которое хотите использовать, и выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="32eba-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Выбор шаблона](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="32eba-301">Информация о выбранном шаблоне отображается на странице **Создание объяснений**.</span><span class="sxs-lookup"><span data-stu-id="32eba-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="32eba-302">При необходимости измените название объяснения, а также добавьте или удалите элементы из списка фраз.</span><span class="sxs-lookup"><span data-stu-id="32eba-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Изменение шаблона](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="32eba-304">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="32eba-304">When finished, select **Save**.</span></span>