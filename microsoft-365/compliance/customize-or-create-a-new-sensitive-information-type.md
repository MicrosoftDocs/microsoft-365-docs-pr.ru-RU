---
title: Настройка и создание типа конфиденциальной информации
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: ''
description: Узнайте, как изменить или создать типы конфиденциальной информации в Office 365 для соблюдения Общего регламента по защите данных (GDPR).
ms.openlocfilehash: 3eca04fcf949a19615dc574c90d8dbeea0894a23
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166070"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a><span data-ttu-id="34d28-103">Настройка и создание типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="34d28-103">Customize or create a new sensitive information type</span></span>

<span data-ttu-id="34d28-104">В этой статье приведены три примера того, как изменить или создать типы конфиденциальной информации для соблюдения регламента GDPR.</span><span class="sxs-lookup"><span data-stu-id="34d28-104">This article provides three examples to demonstrate how to modify or create new sensitive information types for GDPR.</span></span>

- <span data-ttu-id="34d28-105">Изменение имеющегося типа конфиденциальной информации — номер банковской карты для ЕС</span><span class="sxs-lookup"><span data-stu-id="34d28-105">Modify an existing sensitive information type — EU Debit Card Number</span></span>

- <span data-ttu-id="34d28-106">Создание типа конфиденциальной информации — адрес электронной почты</span><span class="sxs-lookup"><span data-stu-id="34d28-106">Create a new sensitive information type — email address</span></span>

- <span data-ttu-id="34d28-107">Создание типа конфиденциальной информации с примером XML-файла — номер клиента Contoso</span><span class="sxs-lookup"><span data-stu-id="34d28-107">Create a new sensitive information type with example XML file — Contoso customer number</span></span>

<span data-ttu-id="34d28-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="34d28-108">Also see:</span></span>

- [<span data-ttu-id="34d28-109">Создание пользовательского типа конфиденциальной информации с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="34d28-109">Create a custom sensitive information type using PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [<span data-ttu-id="34d28-110">Настройка встроенных типов конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="34d28-110">Customize a built-in sensitive information type</span></span>](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a><span data-ttu-id="34d28-111">Изменение типа конфиденциальной информации для повышения точности данных</span><span class="sxs-lookup"><span data-stu-id="34d28-111">Modify a sensitive information type to improve accuracy</span></span>

<span data-ttu-id="34d28-112">Если вы используете веб-часть "Поиск контента" для поиска персональных данных по типами конфиденциальной информации, но при этом не получаете ожидаемых результатов либо запрос возвращает слишком много ложноположительных результатов, вы можете изменить тип конфиденциальной информации в соответствии с особенностями своей среды.</span><span class="sxs-lookup"><span data-stu-id="34d28-112">If you're using Content Search to search for personal data using sensitive information types and you're not returning the expected results, or the query returns too many false positives, consider modifying the sensitive information type to work better with your environment.</span></span>

<span data-ttu-id="34d28-p101">Тип конфиденциальной информации рекомендуется создавать или настраивать на основе имеющегося типа, присвоив ему уникальное имя и идентификаторы. Например, если вы хотите настроить параметры типа конфиденциальной информации "Номер банковской карты для ЕС", копию соответствующего правила можно назвать "Номер банковской карты для ЕС (улучшенная версия)", чтобы отличать этот тип от исходного.</span><span class="sxs-lookup"><span data-stu-id="34d28-p101">The best practice when creating or customizing a sensitive information type is to create a new sensitive information type based on an existing one, giving it a unique name and identifiers. For example, if you wish to adjust the parameters of the "EU Debit Card Number" sensitive information type, you could name your copy of that rule "EU Debit Card Enhanced" to distinguish it from the original.</span></span>

<span data-ttu-id="34d28-p102">В новом типе конфиденциальной информации просто измените необходимые значения, чтобы повысить точность данных. После завершения отправьте новый тип конфиденциальной информации и создайте новое правило защиты от потери данных (или измените имеющееся), чтобы использовать новый тип конфиденциальной информации, который вы только что добавили. Изменение точности типов конфиденциальной информации выполняется методом проб и ошибок, поэтому рекомендуется сохранить копию исходного типа, к которому вы можете при необходимости вернуться в будущем.</span><span class="sxs-lookup"><span data-stu-id="34d28-p102">In your new sensitive information type, simply modify the values you wish to change to improve its accuracy. Once complete, upload your new sensitive information type and create a new DLP rule (or modify an existing one) to use the new sensitive information type you just added. Modifying the accuracy of sensitive information types might require some trial and error, so maintaining a copy of the original type allows you to fall back to it if required in the future.</span></span>

<span data-ttu-id="34d28-118">Вот как настроить тип конфиденциальной информации:</span><span class="sxs-lookup"><span data-stu-id="34d28-118">To customize a sensitive information type:</span></span>

1.  <span data-ttu-id="34d28-119">Экспортируйте имеющийся пакет правил Майкрософт со встроенными типами конфиденциальной информации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="34d28-119">Export the existing Microsoft Rule Package of built in sensitive information types in Office 365.</span></span>

2.  <span data-ttu-id="34d28-120">Переименуйте этот XML-файл и откройте его в своем любимом редакторе XML.</span><span class="sxs-lookup"><span data-stu-id="34d28-120">Rename this XML file and open it in your favorite XML editor.</span></span>

3.  <span data-ttu-id="34d28-121">Изолируйте нужный тип конфиденциальной информации и удалите все остальные.</span><span class="sxs-lookup"><span data-stu-id="34d28-121">Isolate the sensitive information type and remove all others.</span></span>

4.  <span data-ttu-id="34d28-122">С помощью PowerShell создайте два GUID для типа конфиденциальной информации, который вы изменяете.</span><span class="sxs-lookup"><span data-stu-id="34d28-122">Use PowerShell to generate two new GUIDs for the sensitive information type you are modifying.</span></span>

5.  <span data-ttu-id="34d28-123">Измените идентификатор и другие основные элементы, чтобы сделать тип конфиденциальной информации уникальным (в том числе замените два GUID только что созданными).</span><span class="sxs-lookup"><span data-stu-id="34d28-123">Modify the ID and other basic elements so the sensitive information type is unique (this includes replacing two GUIDs with the new ones you generated).</span></span>

6.  <span data-ttu-id="34d28-124">Настройте требования к соответствию для повышения точности.</span><span class="sxs-lookup"><span data-stu-id="34d28-124">Tune the match requirements to improve accuracy.</span></span>

    1.  <span data-ttu-id="34d28-125">Изменения в расположении слов и знаков: измените расположение слов и знаков, чтобы расширить или сжать окно, в котором тип конфиденциальной информации должны окружать ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="34d28-125">Proximity modifications — Modify the character pattern proximity to expand or shrink the window in which keywords must be found around the sensitive information type.</span></span>

    2.  <span data-ttu-id="34d28-p103">Изменения в ключевых словах: добавьте ключевые слова в один из элементов \<Ключевые слова\>, чтобы предоставить более конкретные подкрепляющие доказательства для типа конфиденциальной информации с целью обнаружения соответствия этому правилу. Вы также можете удалить ключевые слова, которые приводят к ложным срабатываниям.</span><span class="sxs-lookup"><span data-stu-id="34d28-p103">Keyword modifications — Add keywords to one of the \<Keywords\> element in order to provide our sensitive information type more specific corroborative evidence to search for in order to signal a match on this rule. Or remove keywords that are causing false positives.</span></span>

    3.  <span data-ttu-id="34d28-128">Изменения в доверии: измените доверие, при котором тип конфиденциальной информации должен соответствовать условиям, заданным в его определении, для нахождения совпадения и сообщения о нем.</span><span class="sxs-lookup"><span data-stu-id="34d28-128">Confidence modifications — Modify the confidence with which the sensitive information type must match the criteria specified in its definition before a match is signaled and reported.</span></span>

7.  <span data-ttu-id="34d28-129">Передайте новый тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="34d28-129">Upload the new sensitive information type.</span></span>

8.  <span data-ttu-id="34d28-p104">Выполните повторный обход контента, чтобы идентифицировать конфиденциальную информацию. См. статью [Ручной запрос обхода контента и переиндексации сайта](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="34d28-p104">Recrawl your content to identify the sensitive information. See [Manually request crawling and re-indexing of a site](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a><span data-ttu-id="34d28-132">Пример: изменение типа конфиденциальной информации "Номер банковской карты для ЕС"</span><span class="sxs-lookup"><span data-stu-id="34d28-132">Example: modify the 'EU Debit Card Number' sensitive information type</span></span>

<span data-ttu-id="34d28-p105">Для повышения точности правил защиты от потери данных в любой системе их необходимо проверить, используя тестовый набор данных. Кроме того, может потребоваться точная настройка путем многократных изменений и проверок. В этом примере приведены изменения, внесенные в тип конфиденциальной информации "Номер банковской карты для ЕС" для повышения его точности.</span><span class="sxs-lookup"><span data-stu-id="34d28-p105">Improving the accuracy of DLP rules in any system requires testing against a sample data set, and may require fine tuning through repetitive modifications and tests. This example demonstrates modifications to the 'EU Debit Card Number' sensitive information type to improve its accuracy.</span></span>

<span data-ttu-id="34d28-p106">При поиске номера банковской карты для ЕС в нашем примере определение соответствующего номера строго ограничено 16 знаками с использованием сложного шаблона. Кроме того, применяется проверка контрольной суммы. Мы не можем изменить этот шаблон из-за определения строки для этого типа конфиденциальной информации. Тем не менее мы можем внести перечисленные ниже изменения, чтобы повысить точность поиска этого типа конфиденциальной информации в среде Office 365 с помощью защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="34d28-p106">When searching for an EU Debit Card Number in our example, the definition of that number is strictly defined as 16 digits using a complex pattern, and being subject to the validation of a checksum. We cannot alter this pattern due to the string definition of this sensitive information type. However, we can make the following adjustments to improve the accuracy of how DLP finds this sensitive information type within Office 365.</span></span>

### <a name="proximity-modification"></a><span data-ttu-id="34d28-138">Изменение расположения слов и знаков</span><span class="sxs-lookup"><span data-stu-id="34d28-138">Proximity modification</span></span>

<span data-ttu-id="34d28-p107">Окно будет сжато путем изменения значения patternProximity в элементе \<Entity\> с 300 на 150 символов. Это значит, что подкрепляющие доказательства, или ключевые слова, должны в большей мере соответствовать нашему типу конфиденциальной информации для обнаружения соответствия этому правилу.</span><span class="sxs-lookup"><span data-stu-id="34d28-p107">We'll shrink the window by modifying the patternProximity value in our \<Entity\> element from 300 to 150 characters. This means that our corroborative evidence, or our keywords, must be closer to our sensitive information type in order to signal a match on this rule.</span></span>

<span data-ttu-id="34d28-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="34d28-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

### <a name="keyword-modifications"></a><span data-ttu-id="34d28-142">Изменения ключевых слов</span><span class="sxs-lookup"><span data-stu-id="34d28-142">Keyword modifications</span></span>

<span data-ttu-id="34d28-p108">Некоторые ключевые слова могут приводить к ложным срабатываниям, поэтому их может потребоваться удалить. Вот ключевые слова в этом примере:</span><span class="sxs-lookup"><span data-stu-id="34d28-p108">Some keywords might cause false positives to occur. As a result you might want to remove keywords. Here are the keywords for this example::</span></span>

<span data-ttu-id="34d28-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span><span class="sxs-lookup"><span data-stu-id="34d28-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span></span>

<span data-ttu-id="34d28-147">\<Group\></span><span class="sxs-lookup"><span data-stu-id="34d28-147">\<Group\></span></span>

<span data-ttu-id="34d28-148">\<Term\>корпоративная карта\</Term\></span><span class="sxs-lookup"><span data-stu-id="34d28-148">\<Term\>corporate card\</Term\></span></span>

<span data-ttu-id="34d28-149">\<Term\>карта организации\</Term\></span><span class="sxs-lookup"><span data-stu-id="34d28-149">\<Term\>organization card\</Term\></span></span>

<span data-ttu-id="34d28-150">\<Term\>acct nbr\</Term\></span><span class="sxs-lookup"><span data-stu-id="34d28-150">\<Term\>acct nbr\</Term\></span></span>

<span data-ttu-id="34d28-151">\<Term\>acct num\</Term\></span><span class="sxs-lookup"><span data-stu-id="34d28-151">\<Term\>acct num\</Term\></span></span>

<span data-ttu-id="34d28-152">\<Term\>acct no\</Term\></span><span class="sxs-lookup"><span data-stu-id="34d28-152">\<Term\>acct no\</Term\></span></span>

<span data-ttu-id="34d28-153">...</span><span class="sxs-lookup"><span data-stu-id="34d28-153">…</span></span>

<span data-ttu-id="34d28-154">\</Group\></span><span class="sxs-lookup"><span data-stu-id="34d28-154">\</Group\></span></span>

<span data-ttu-id="34d28-155">\</Keyword\></span><span class="sxs-lookup"><span data-stu-id="34d28-155">\</Keyword\></span></span>

### <a name="confidence-modifications"></a><span data-ttu-id="34d28-156">Изменения в доверии</span><span class="sxs-lookup"><span data-stu-id="34d28-156">Confidence modifications</span></span>

<span data-ttu-id="34d28-p109">Удаляя ключевые слова из определения, вы, как правило, хотите настроить вероятность нахождения этого типа конфиденциальной информации путем сокращения этого значения. Стандартный уровень для типа "Номер банковской карты для ЕС" — 85.</span><span class="sxs-lookup"><span data-stu-id="34d28-p109">If you remove keywords from the definition, you would typically want to adjust how confident you are that this sensitive information type was found by lowering this value. The default level for EU Debit Card Number type is 85.</span></span>

<span data-ttu-id="34d28-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="34d28-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

<span data-ttu-id="34d28-160">\<Pattern confidenceLevel="85"\></span><span class="sxs-lookup"><span data-stu-id="34d28-160">\<Pattern confidenceLevel="85"\></span></span>

<span data-ttu-id="34d28-161">...</span><span class="sxs-lookup"><span data-stu-id="34d28-161">…</span></span>

<span data-ttu-id="34d28-162">\</Pattern\></span><span class="sxs-lookup"><span data-stu-id="34d28-162">\</Pattern\></span></span>

<span data-ttu-id="34d28-163">\</Entity\></span><span class="sxs-lookup"><span data-stu-id="34d28-163">\</Entity\></span></span>

## <a name="create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="34d28-164">Создание пользовательского типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="34d28-164">Create a new custom sensitive information type</span></span>

<span data-ttu-id="34d28-165">Чтобы создать пользовательский тип конфиденциальной информации, сначала воспользуйтесь веб-частью "Поиск контента" для:</span><span class="sxs-lookup"><span data-stu-id="34d28-165">To create a new custom sensitive information type, start by using Content Search to:</span></span>

-   <span data-ttu-id="34d28-166">оптимизации запроса KQL;</span><span class="sxs-lookup"><span data-stu-id="34d28-166">Optimize a KQL query</span></span>

-   <span data-ttu-id="34d28-167">определения наиболее полезных ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="34d28-167">See which keywords are most useful</span></span>

<span data-ttu-id="34d28-p110">Используйте эти результаты, чтобы создать тип конфиденциальной информации. Затем оптимизируйте новый тип конфиденциальной информации для своей среды.</span><span class="sxs-lookup"><span data-stu-id="34d28-p110">Use these results to create a new sensitive information type. Then optimize the new sensitive information type for your environment.</span></span>

<span data-ttu-id="34d28-p111">Примечание. В ближайшее время будет представлен ряд новых типов конфиденциальной информации для персональных данных в странах ЕС. Если вам нужно создать типы конфиденциальной информации, сначала определите данные, характерные для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="34d28-p111">Note: Many new sensitive information types are coming soon for personal data in EU countries. If you need to create new sensitive information types, begin by targeting data that is custom to your environment.</span></span>

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a><span data-ttu-id="34d28-172">Шаг 1. Использование запросов KQL и ключевых слов для поиска дополнительных данных в среде</span><span class="sxs-lookup"><span data-stu-id="34d28-172">Step 1 — Use KQL queries and key words to find additional data in your environment</span></span>

<span data-ttu-id="34d28-p112">Возможно, вам потребуется создать дополнительные запросы для поиска персональных данных, на которые распространяется действие регламента GDPR. Для поиска данных в веб-части "Поиск контента" используется язык запросов Keyword Query Language (KQL). Точное обнаружение большинства конфиденциальных данных невозможно при использовании только языка KQL (без применения типов конфиденциальной информации). Поэтому наша цель — проверить и оптимизировать строки KQL с помощью веб-части "Поиск контента", а затем использовать их для создания и настройки новых типов конфиденциальной информации, чтобы повысить точность данных.</span><span class="sxs-lookup"><span data-stu-id="34d28-p112">You might need to create additional queries to find personal data that is subject to GDPR. Content Search uses Keyword Query Language (KQL) to find data. Most sensitive data can't be accurately detected using just KQL without sensitive information types. So the goal is to test and optimize KQL strings using Content Search and then use these to create and tune new sensitive information types where you can achieve even greater accuracy.</span></span>

<span data-ttu-id="34d28-177">Для формулирования и оптимизации запросов с помощью KQL используйте эти ресурсы:</span><span class="sxs-lookup"><span data-stu-id="34d28-177">Use these resources to formulate and optimize queries using KQL:</span></span>

- [<span data-ttu-id="34d28-178">Руководство по синтаксису языка запросов по ключевым словам (KQL)</span><span class="sxs-lookup"><span data-stu-id="34d28-178">Keyword Query Language (KQL) syntax reference (DMC)</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [<span data-ttu-id="34d28-179">Выполнение поиска контента</span><span class="sxs-lookup"><span data-stu-id="34d28-179">Run a Content Search</span></span>](content-search.md)

<span data-ttu-id="34d28-p113">Поиск контента предоставляет еще один ресурс, который помогает создавать запросы KQL и типы конфиденциальной информации, — ключевые слова. Зачем использовать список ключевых слов? Вы можете получить статистические данные о том, сколько элементов соответствуют каждому ключевому слову. Это поможет быстро определить наиболее (и наименее) эффективные ключевые слова. Дополнительные сведения о статистике поиска см. в статье [Просмотр статистики ключевых слов для результатов поиска контента](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).</span><span class="sxs-lookup"><span data-stu-id="34d28-p113">Content Search provides another resource to help you develop KQL queries and sensitive information types — keywords. Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. For more information about search statistics, see [View keyword statistics for Content Search results](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).</span></span>

<span data-ttu-id="34d28-p114">Ключевые слова в каждой строке соединяются с помощью оператора OR в созданном поисковом запросе. В строке также можно использовать ключевую фразу (которая заключается в скобки).</span><span class="sxs-lookup"><span data-stu-id="34d28-p114">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span>

<span data-ttu-id="34d28-187">Подробнее см. в статье [Запросы ключевых слов и условия поиска контента](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions).</span><span class="sxs-lookup"><span data-stu-id="34d28-187">For more information, see [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions).</span></span>

### <a name="exampleusing-content-search-to-identify-email-addresses"></a><span data-ttu-id="34d28-188">Пример: использование веб-части "Поиск контента" для определения адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="34d28-188">Example—Using Content Search to identify email addresses</span></span>

<span data-ttu-id="34d28-p115">Адреса электронной почты считаются конфиденциальной информацией, связанной с субъектами данных. В этом простом примере показано, как использовать Поиск контента.</span><span class="sxs-lookup"><span data-stu-id="34d28-p115">Email addresses are considered sensitive information related to data subjects. This is a simple example to demonstrate how Content Search can help.</span></span>

<span data-ttu-id="34d28-p116">Запросы KQL и ключевые слова невозможно использовать одновременно. Применяйте эти средства по отдельности, чтобы уточнить запрос и определить ключевые слова, которые могут понадобиться в типах конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="34d28-p116">KQL and keywords can't be used together. Use these tools separately to hone your query and determine keywords that might be useful in sensitive information types.</span></span>

### <a name="kql-query"></a><span data-ttu-id="34d28-193">Запрос KQL</span><span class="sxs-lookup"><span data-stu-id="34d28-193">KQL query</span></span>

<span data-ttu-id="34d28-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span><span class="sxs-lookup"><span data-stu-id="34d28-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span></span>

<span data-ttu-id="34d28-195">Примечания.</span><span class="sxs-lookup"><span data-stu-id="34d28-195">Notes:</span></span>

-   <span data-ttu-id="34d28-196">Для поиска с учетом расположения можно использовать операторы NEAR и ONEAR.</span><span class="sxs-lookup"><span data-stu-id="34d28-196">You can use NEAR and ONEAR for proximity searches.</span></span>

-   <span data-ttu-id="34d28-197">К сожалению, язык KQL не поддерживает запросы с классом Regex (например, IdRef="адрес\_электронной_почты\_Regex")</span><span class="sxs-lookup"><span data-stu-id="34d28-197">Unfortunately, KQL doesn't support queries with the Regex Class (ex: IdRef="Regex\_email\_address")</span></span>

### <a name="keywords"></a><span data-ttu-id="34d28-198">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="34d28-198">Keywords</span></span>

<span data-ttu-id="34d28-p117">Введите каждое ключевое слово в отдельной строке. Примеры ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="34d28-p117">Enter each keyword on a separate line. Example keywords:</span></span>

-   <span data-ttu-id="34d28-201">адрес электронной почты;</span><span class="sxs-lookup"><span data-stu-id="34d28-201">email address</span></span>

-   <span data-ttu-id="34d28-202">почта;</span><span class="sxs-lookup"><span data-stu-id="34d28-202">mail</span></span>

-   <span data-ttu-id="34d28-203">контакт;</span><span class="sxs-lookup"><span data-stu-id="34d28-203">contact</span></span>

-   <span data-ttu-id="34d28-204">отправитель;</span><span class="sxs-lookup"><span data-stu-id="34d28-204">sender</span></span>

-   <span data-ttu-id="34d28-205">получатель;</span><span class="sxs-lookup"><span data-stu-id="34d28-205">recipient</span></span>

-   <span data-ttu-id="34d28-206">копия;</span><span class="sxs-lookup"><span data-stu-id="34d28-206">cc</span></span>

-   <span data-ttu-id="34d28-207">СК.</span><span class="sxs-lookup"><span data-stu-id="34d28-207">bcc</span></span>

<span data-ttu-id="34d28-208">В этом примере вы можете узнать, что ключевые слова использовать необязательно, так как они приводят к большому количеству ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="34d28-208">In this example, you might learn the keywords are not necessary and produce a lot of false positive results.</span></span>

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="34d28-209">Шаг 2. Создание пользовательского типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="34d28-209">Step 2 — Create a new custom sensitive information type</span></span>

<span data-ttu-id="34d28-p118">После того как вы используете запросы KQL и ключевые слова для определения конфиденциальной информации, создайте с их помощью пользовательские типы конфиденциальной информации. Во многих случаях вам потребуется усложнить типы конфиденциальной информации, чтобы обеспечить нужный уровень точности. Затем эти пользовательские типы конфиденциальной информации можно использовать в веб-части "Поиск контента", в политиках защиты от потери данных и других инструментах, а также в других запросах KQL.</span><span class="sxs-lookup"><span data-stu-id="34d28-p118">After using KQL queries and keywords to identify sensitive information, use these to create new custom sensitive information types. In many cases, you'll require the sophistication of sensitive information types to achieve the right level of accuracy. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span>

<span data-ttu-id="34d28-p119">Тип конфиденциальной информации рекомендуется создавать на основе имеющегося типа. Выполните действия, описанные выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="34d28-p119">The best practice is to create a new sensitive information type based on an existing one. Use the same process described earlier in this article.</span></span>

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a><span data-ttu-id="34d28-215">Пример: создание типа конфиденциальной информации для адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="34d28-215">Example — Create a new sensitive information for email addresses</span></span> 

<span data-ttu-id="34d28-p120">Мы продолжим использовать адрес электронной почты для примера ввиду его простоты. В приведенной ниже таблице описаны изменения, которые рекомендуется внести в новый тип конфиденциальной информации для электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34d28-p120">We'll continue with the email address as an example because it's simple. The following table details the modifications recommended for a new email sensitive information type.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="34d28-218"><strong>Этап</strong></span><span class="sxs-lookup"><span data-stu-id="34d28-218"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="34d28-219"><strong>Изменение</strong></span><span class="sxs-lookup"><span data-stu-id="34d28-219"><strong>Modification </strong></span></span></th>
<th align="left"><span data-ttu-id="34d28-220"><strong>Пример синтаксиса XML</strong></span><span class="sxs-lookup"><span data-stu-id="34d28-220"><strong>Example XML syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="34d28-221">1</span><span class="sxs-lookup"><span data-stu-id="34d28-221">1</span></span></td>
<td align="left"><span data-ttu-id="34d28-222">Установка свойства IdRef</span><span class="sxs-lookup"><span data-stu-id="34d28-222">Set the IdRef property</span></span>
<p><span data-ttu-id="34d28-p121">В элементе &lt;Entity&gt; измените элемент &lt;IdMatch&gt; таким образом, чтобы его свойство idRef равнялось уникальному значению. Это значение будет указывать на элемент, определяющий наше регулярное выражение для адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34d28-p121">Within the &lt;Entity&gt; element, modify the &lt;IdMatch&gt; element so that its idRef property is = to a unique value. This value will point to an element that defines our regular expression to find email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="34d28-225">IdRef=&quot;Regex_email_address&quot;</span><span class="sxs-lookup"><span data-stu-id="34d28-225">IdRef=&quot;Regex_email_address&quot;</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="34d28-226">2</span><span class="sxs-lookup"><span data-stu-id="34d28-226">2</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-227">Атрибут расстояния</span><span class="sxs-lookup"><span data-stu-id="34d28-227">Proximity attribute</span></span></p>
<p><span data-ttu-id="34d28-228">Мы начнем со значения patternProximity в элементе &lt;Entity&gt;, равного 300.</span><span class="sxs-lookup"><span data-stu-id="34d28-228">We'll start with a patternProximity value in our &lt;Entity&gt; element of 300.</span></span></p></td>
<td align="left"><span data-ttu-id="34d28-229">patternsProximity=&quot;300&quot;</span><span class="sxs-lookup"><span data-stu-id="34d28-229">patternsProximity=&quot;300&quot;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="34d28-230">3</span><span class="sxs-lookup"><span data-stu-id="34d28-230">3</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-231">Уровень вероятности</span><span class="sxs-lookup"><span data-stu-id="34d28-231">Confidence level</span></span></p>
<p><span data-ttu-id="34d28-p122">Установите для свойства recommendedConfidence значение, которое, по вашему мнению, соответствует вероятности нахождения точного совпадения. Скорее всего, для получения точного результата потребуется проверка с использованием репрезентативного набора данных. В качестве начального параметра задайте значение 75.</span><span class="sxs-lookup"><span data-stu-id="34d28-p122">Set the recommendedConfidence property to a value you feel will represent the confidence of finding an accurate match. This will likely require testing with a representative data set to get an accurate result. As an initial setting, set this value to 75.</span></span></p></td>
<td align="left"><p><span data-ttu-id="34d28-235">recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-235">recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="34d28-236">Полученный в результате код XML для первых трех элементов выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="34d28-236">The resulting XML for these first three elements combined looks like this:</span></span></p>
<p><span data-ttu-id="34d28-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="34d28-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="34d28-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span></span></p>
<p><span data-ttu-id="34d28-240">&lt;Any minMatches=&quot;1&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-240">&lt;Any minMatches=&quot;1&quot;&gt;</span></span></p>
<p><span data-ttu-id="34d28-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span></span></p>
<p><span data-ttu-id="34d28-242">&lt;/Any&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-242">&lt;/Any&gt;</span></span></p>
<p><span data-ttu-id="34d28-243">&lt;/Pattern&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-243">&lt;/Pattern&gt;</span></span></p>
<p><span data-ttu-id="34d28-244">&lt;/Entity&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-244">&lt;/Entity&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="34d28-245">4</span><span class="sxs-lookup"><span data-stu-id="34d28-245">4</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-246">Элемент Regex</span><span class="sxs-lookup"><span data-stu-id="34d28-246">Regex element</span></span></p>
<p><span data-ttu-id="34d28-247">Сразу после элементов &lt;Entity&gt; добавьте новый элемент &lt;Regex&gt;, определяющий регулярное выражение, которое используется для определения адресов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34d28-247">Add a new &lt;Regex&gt; element immediately be below the &lt;Entity&gt; elements that defines the regular expression used to identify email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="34d28-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="34d28-249">5</span><span class="sxs-lookup"><span data-stu-id="34d28-249">5</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-250">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="34d28-250">Keywords</span></span></p>
<p><span data-ttu-id="34d28-p123">После элемента &lt;Regex&gt; добавьте новый элемент &lt;Keyword&gt;, который определяет список ключевых слов, связанных с адресами электронной почты. Убедитесь, что значение идентификатора для элемента &lt;Keyword&gt; соответствует значению &lt;Match idRef&gt; в элементе &lt;Entity&gt;&lt;Pattern&gt;. При необходимости вы можете добавить собственные ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="34d28-p123">Add a new &lt;Keyword&gt; element below the &lt;Regex&gt; element that defines list of email address related keywords. Ensure that the id value for the &lt;Keyword&gt; element matches the &lt;Match idRef&gt; value in the &lt;Entity&gt;&lt;Pattern&gt; element. You may continue to add your own keywords if needed.</span></span></p>
<p><span data-ttu-id="34d28-p124">Ключевые слова необязательно включать в тип конфиденциальной информации, связанный с электронной почтой. Эти ключевые слова приведены для примера.</span><span class="sxs-lookup"><span data-stu-id="34d28-p124">Keywords are likely not necessary to include in an email sensitive information type. These are provided as an example.</span></span></p></td>
<td align="left"><p><span data-ttu-id="34d28-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span></span></p>
<p><span data-ttu-id="34d28-257">&lt;Group&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-257">&lt;Group&gt;</span></span></p>
<p><span data-ttu-id="34d28-258">&lt;Term&gt;электронная почта&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-258">&lt;Term&gt;email&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="34d28-259">&lt;Term&gt;адрес электронной почты&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-259">&lt;Term&gt;email address&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="34d28-260">&lt;Term&gt;контакт&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-260">&lt;Term&gt;contact&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="34d28-261">&lt;/Group&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-261">&lt;/Group&gt;</span></span></p>
<p><span data-ttu-id="34d28-262">&lt;/Keyword&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-262">&lt;/Keyword&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="34d28-263">6</span><span class="sxs-lookup"><span data-stu-id="34d28-263">6</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-264">Элемент LocalizedStrings</span><span class="sxs-lookup"><span data-stu-id="34d28-264">LocalizedStrings element</span></span></p>
<p><span data-ttu-id="34d28-265">Убедитесь, что элемент &lt;LocalizedStrings&gt;&lt;Resource&gt; включает уникальное имя, определяющее ваш тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="34d28-265">In the &lt;LocalizedStrings&gt;&lt;Resource&gt; element ensure that you have a unique name that identifies your sensitive information type.</span></span></p></td>
<td align="left"><p><span data-ttu-id="34d28-266">&lt;LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-266">&lt;LocalizedStrings&gt;</span></span></p>
<p><span data-ttu-id="34d28-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span></span></p>
<p><span data-ttu-id="34d28-268">&lt;Name default=&quot;true&quot; langcode=&quot;ru-ru&quot;&gt;Адрес электронной почты&lt;/Name&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span></span></p>
<p><span data-ttu-id="34d28-269">&lt;Description default=&quot;true&quot; langcode=&quot;ru-ru&quot;&gt;Обнаружение адресов электронной почты.&lt;/Description&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span></span></p>
<p><span data-ttu-id="34d28-270">&lt;/Resource&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-270">&lt;/Resource&gt;</span></span></p>
<p><span data-ttu-id="34d28-271">&lt;/LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="34d28-271">&lt;/LocalizedStrings&gt;</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a><span data-ttu-id="34d28-272">Создание типа конфиденциальной информации с примером XML-файла с помощью PowerShell — номер клиента Contoso</span><span class="sxs-lookup"><span data-stu-id="34d28-272">Create a new sensitive information type with example PowerShell and XML file — Contoso customer number</span></span>

<span data-ttu-id="34d28-p125">Организация Contoso использует номер клиента Contoso (CCN — Contoso Customer Number) для идентификации каждого клиента в базе данных. Вот из каких компонентов состоит номер CCN.</span><span class="sxs-lookup"><span data-stu-id="34d28-p125">Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following taxonomy:</span></span>

-   <span data-ttu-id="34d28-p126">Две цифры представляют собой год создания записи. Организацию Contoso основали в 2002 году, поэтому самое раннее возможное значение составляет 02.</span><span class="sxs-lookup"><span data-stu-id="34d28-p126">Two digits to represent the year that the record was created. Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>

-   <span data-ttu-id="34d28-p127">Три цифры представляют собой партнерское агентство, создавшее запись. Возможные значения — от 000 до 999.</span><span class="sxs-lookup"><span data-stu-id="34d28-p127">Three digits to represent the partner agency that created the record. Possible agency values range from 000 to 999.</span></span>

-   <span data-ttu-id="34d28-p128">Символ "альфа" представляет собой сферу деятельности. Возможные значения: a–z без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="34d28-p128">An alpha character to represent the line of business. Possible values are a-z and should be case insensitive.</span></span>

-   <span data-ttu-id="34d28-p129">Четырехзначный серийный номер. Возможные значения — от 0000 до 9999.</span><span class="sxs-lookup"><span data-stu-id="34d28-p129">A four-digit serial number. Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="34d28-283">Примеры номеров CCN:</span><span class="sxs-lookup"><span data-stu-id="34d28-283">Example CCNs:</span></span>

> <span data-ttu-id="34d28-284">15080P9562;</span><span class="sxs-lookup"><span data-stu-id="34d28-284">15080P9562</span></span>
>
> <span data-ttu-id="34d28-285">14040O1119;</span><span class="sxs-lookup"><span data-stu-id="34d28-285">14040O1119</span></span>
>
> <span data-ttu-id="34d28-286">15020J8317;</span><span class="sxs-lookup"><span data-stu-id="34d28-286">15020J8317</span></span>
>
> <span data-ttu-id="34d28-287">14050E2330;</span><span class="sxs-lookup"><span data-stu-id="34d28-287">14050E2330</span></span>
>
> <span data-ttu-id="34d28-288">16050E2166;</span><span class="sxs-lookup"><span data-stu-id="34d28-288">16050E2166</span></span>
>
> <span data-ttu-id="34d28-289">17040O1118.</span><span class="sxs-lookup"><span data-stu-id="34d28-289">17040O1118</span></span>

<span data-ttu-id="34d28-290">Организация Contoso всегда ссылается на клиентов, используя номер CCN во внутренних и внешних сообщениях, документах и т. д. Ей требуется создать тип конфиденциальной информации для обнаружения использования номеров CCN, чтобы получить возможность применить защиту к использованию этой разновидности персональных данных.</span><span class="sxs-lookup"><span data-stu-id="34d28-290">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, etc. They would like to create a custom sensitive information type to detect the use of CCN so that they may apply protection to the use of this form of personal data.</span></span>

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a><span data-ttu-id="34d28-291">Создание типа конфиденциальной информации для номера клиента Contoso</span><span class="sxs-lookup"><span data-stu-id="34d28-291">Create a new sensitive information type for Contoso customer number</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="34d28-292"><strong>Шаг</strong></span><span class="sxs-lookup"><span data-stu-id="34d28-292"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="34d28-293"><strong>Действие </strong></span><span class="sxs-lookup"><span data-stu-id="34d28-293"><strong>Action </strong></span></span></th>
<th align="left"><span data-ttu-id="34d28-294"><strong>Результат</strong></span><span class="sxs-lookup"><span data-stu-id="34d28-294"><strong>Result</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="34d28-295">1</span><span class="sxs-lookup"><span data-stu-id="34d28-295">1</span></span></td>
<td align="left"><span data-ttu-id="34d28-296">Contoso использует PowerShell и Поиск контента для поиска документов, которые соответствуют примеру набора номеров CCN.</span><span class="sxs-lookup"><span data-stu-id="34d28-296">Contoso uses PowerShell and Content Search to find documents that match an example set of CCNs.</span></span></td>
<td align="left">

<p><span data-ttu-id="34d28-297">#Подключитесь к Центру безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="34d28-297">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="34d28-298">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="34d28-298">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="34d28-299">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="34d28-299">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="34d28-300">#Create &amp; start search for sample data</span><span class="sxs-lookup"><span data-stu-id="34d28-300">#Create &amp; start search for sample data</span></span></p>
<p><span data-ttu-id="34d28-301">$searchName = &quot;Sample Customer Information Search&quot;</span><span class="sxs-lookup"><span data-stu-id="34d28-301">$searchName = &quot;Sample Customer Information Search&quot;</span></span></p>
<p><span data-ttu-id="34d28-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span><span class="sxs-lookup"><span data-stu-id="34d28-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span></span></p>
<p><span data-ttu-id="34d28-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span><span class="sxs-lookup"><span data-stu-id="34d28-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span></span></p>
<p><span data-ttu-id="34d28-304">Start-ComplianceSearch -Identity $searchName</span><span class="sxs-lookup"><span data-stu-id="34d28-304">Start-ComplianceSearch -Identity $searchName</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="34d28-305">2</span><span class="sxs-lookup"><span data-stu-id="34d28-305">2</span></span></td>
<td align="left"><span data-ttu-id="34d28-p130">Организация Contoso анализирует результаты. При каждом применении номера CCN использовалась дата в формате, принятом в ЕС, а также одно из приведенных справа ключевых слов с параметром близости в 300 символов.</span><span class="sxs-lookup"><span data-stu-id="34d28-p130">Contoso analyzes the results. Every time the CCN was used, an EU formatted date was used and one of these keywords were also used within a proximity of 300 characters.</span></span></td>
<td align="left"><span data-ttu-id="34d28-308">номер клиента, н-р клиента, № клиента, №клиента, клиент Contoso</span><span class="sxs-lookup"><span data-stu-id="34d28-308">customer number, customer no, customer #, customer#, Contoso customer</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="34d28-309">3</span><span class="sxs-lookup"><span data-stu-id="34d28-309">3</span></span></td>
<td align="left"><span data-ttu-id="34d28-310">Организация Contoso разработала приведенный справа шаблон регулярного выражения (RegEx) для определения своих номеров CCN.</span><span class="sxs-lookup"><span data-stu-id="34d28-310">Contoso developed the following Regular Expression (RegEx) pattern to identify their CCN.</span></span></td>
<td align="left"><span data-ttu-id="34d28-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="34d28-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="34d28-312">4</span><span class="sxs-lookup"><span data-stu-id="34d28-312">4</span></span></td>
<td align="left"><span data-ttu-id="34d28-313">Организация Contoso разработала приведенный справа шаблон регулярного выражения (RegEx) для определения дат в форматах, которые приняты в ЕС и используются в ее различных дочерних подразделениях.</span><span class="sxs-lookup"><span data-stu-id="34d28-313">Contoso developed the following Regular Expression (RegEx) pattern to identify EU dates in the formats used by their various subsidiaries.</span></span></td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="34d28-314">5</span><span class="sxs-lookup"><span data-stu-id="34d28-314">5</span></span></td>
<td align="left"><span data-ttu-id="34d28-315">Организация Contoso создала три уникальных GUID с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34d28-315">Contoso uses PowerShell to generate three unique GUIDs.</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-316">#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</span><span class="sxs-lookup"><span data-stu-id="34d28-316">#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</span></span></p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="34d28-317">6</span><span class="sxs-lookup"><span data-stu-id="34d28-317">6</span></span></td>
<td align="left"><span data-ttu-id="34d28-318">Организация Contoso определяет приведенные справа параметры для соответствующего правила в отношении типа конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="34d28-318">Contoso defines the following parameters for their sensitive item type rule.</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-319">Имя: номер клиента Contoso (CCN)</span><span class="sxs-lookup"><span data-stu-id="34d28-319">Name: Contoso Customer Number (CCN)</span></span></p>
<p><span data-ttu-id="34d28-320">Описание: номер клиента Contoso (CCN), который используется для поиска дополнительных ключевых слов и даты в формате, принятом в ЕС</span><span class="sxs-lookup"><span data-stu-id="34d28-320">Description: Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="34d28-321">7</span><span class="sxs-lookup"><span data-stu-id="34d28-321">7</span></span></td>
<td align="left"><span data-ttu-id="34d28-322">Организация Contoso создает XML-файл для нового типа конфиденциальной информации с целью обнаружения номера клиента Contoso (CCN) и сохраняет его в локальной файловой системе как C:\Scripts\ContosoCCN.xml в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="34d28-322">Contoso creates an XML file for a new sensitive information type to detect a Contoso Customer Number (CCN) and saves this to a local file system as C:\Scripts\ContosoCCN.xml in with UTF-8 encoding.</span></span></td>
<td align="left"><span data-ttu-id="34d28-323">См. XML-файл под этой таблицей.</span><span class="sxs-lookup"><span data-stu-id="34d28-323">See the XML file below this table.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="34d28-324">8</span><span class="sxs-lookup"><span data-stu-id="34d28-324">8</span></span></td>
<td align="left"><span data-ttu-id="34d28-325">Организация Contoso создает пользовательский тип конфиденциальной информации с помощью PowerShell, как показано справа.</span><span class="sxs-lookup"><span data-stu-id="34d28-325">Contoso creates the custom sensitive information type with the following PowerShell.</span></span></td>
<td align="left"><p><span data-ttu-id="34d28-326">#Подключитесь к Центру безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="34d28-326">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="34d28-327">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="34d28-327">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="34d28-328">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="34d28-328">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="34d28-329">#Create new Sensitive Information Type</span><span class="sxs-lookup"><span data-stu-id="34d28-329">#Create new Sensitive Information Type</span></span></p>
<p><span data-ttu-id="34d28-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span><span class="sxs-lookup"><span data-stu-id="34d28-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a><span data-ttu-id="34d28-331">Пример XML-файла для нового типа конфиденциальной информации (шаг 7)</span><span class="sxs-lookup"><span data-stu-id="34d28-331">Example XML file for the new sensitive information type (step 7)</span></span>
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
