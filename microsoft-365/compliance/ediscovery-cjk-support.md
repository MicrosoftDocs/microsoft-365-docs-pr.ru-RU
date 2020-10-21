---
title: Поддержка CJK/Double Byte для расширенного обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как Расширенное обнаружение электронных данных в Microsoft 365 поддерживает языки китайского, японского и корейского языков (CJK), использующие набор двухбайтовых символов.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626943"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="2f4fa-103">Поддержка CJK языка для расширенного обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="2f4fa-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="2f4fa-104">Advanced eDiscovery поддерживает языки набора двухбайтовых символов (например, упрощенное китайское письмо, традиционное письмо, японский и *корейский язык)* для следующих сложных сценариев в наборе проверки:</span><span class="sxs-lookup"><span data-stu-id="2f4fa-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="2f4fa-105">При [запросе данных в наборе рецензирования](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="2f4fa-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="2f4fa-106">При [разметке документов в наборе рецензирования](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="2f4fa-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="2f4fa-107">При [анализе данных о делах в наборе](analyzing-data-in-review-set.md) анализа с использованием почти повторяющихся данных, почтовых потоков и анализа тем.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="2f4fa-108">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="2f4fa-108">Frequently asked questions</span></span>

<span data-ttu-id="2f4fa-109">**Как создать поиск для сбора элементов, содержащих знаки CJK?**</span><span class="sxs-lookup"><span data-stu-id="2f4fa-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="2f4fa-110">При поиске контента в Advanced eDiscovery можно использовать символы CJK для [поиска по ключевым словам](building-search-queries.md#keyword-searches), [запросов ключевых слов и условий поиска](keyword-queries-and-search-conditions.md) .</span><span class="sxs-lookup"><span data-stu-id="2f4fa-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="2f4fa-111">Поиск символов CJK также поддерживается при поиске контента в основном eDiscovery и поиске контента.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="2f4fa-112">Мы предоставляем поддержку CJK для всех [операторов поиска](keyword-queries-and-search-conditions.md#search-operators) и [условий поиска](keyword-queries-and-search-conditions.md#search-conditions), в том числе логических операторов **and**, **or**, **Not**и **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="2f4fa-113">Если вы уверены, что расположения или элементы контента содержат знаки CJK, но поиск не возвращает результаты, щелкните значок язык запроса — страна/регион</span><span class="sxs-lookup"><span data-stu-id="2f4fa-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Язык запросов — значок страны или региона в поиске контента](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="2f4fa-115">и выберите соответствующее значение кода языка и региональных параметров страны для поиска.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="2f4fa-116">По умолчанию используется нейтральный язык и регион.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-116">The default language/region is neutral.</span></span>

<span data-ttu-id="2f4fa-117">**Можно ли сразу выполнить поиск на нескольких языках?**</span><span class="sxs-lookup"><span data-stu-id="2f4fa-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="2f4fa-118">Это зависит от используемого сценария поиска.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="2f4fa-119">При [запросе данных в наборе анализа](review-set-search.md) в Advanced eDiscovery можно выполнять поиск на нескольких языках.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="2f4fa-120">При [создании поиска для сбора данных](create-search-to-collect-data.md)создайте отдельный поиск для каждого целевого языка.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="2f4fa-121">Например, если вы ищете документ, который содержит как китайский, так и корейский, выберите Китайский для первого запроса и выберите корейский для второго запроса.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="2f4fa-122">**Не отображается значок запроса языка и страны/региона, чтобы выбрать язык для запросов в наборе рецензирования. Как указать язык запроса в поиске набора проверки?**</span><span class="sxs-lookup"><span data-stu-id="2f4fa-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="2f4fa-123">Чтобы просмотреть запросы Set, вам не нужно указывать язык документа.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="2f4fa-124">Расширенное обнаружение электронных данных автоматически обнаруживает Языки документов при добавлении контента в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="2f4fa-125">Это позволяет оптимизировать результаты запроса в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="2f4fa-126">**Можно ли увидеть обнаруженные языки в [метаданных файлов](view-documents-in-review-set.md#file-metadata)?**</span><span class="sxs-lookup"><span data-stu-id="2f4fa-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="2f4fa-127">Нет, обнаруженные языки в метаданных файлов отображаться не будут.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="2f4fa-128">**Можно ли фильтровать по языкам документов в наборе проверки**?</span><span class="sxs-lookup"><span data-stu-id="2f4fa-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="2f4fa-129">Нет, вы не можете фильтровать, сортировать и искать по языкам документов в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="2f4fa-130">**Будет ли этот выпуск CJK выпустить сценарии набора исправлений, которые влияют на любые существующие запросы на поисковые запросы и на рецензирование?**</span><span class="sxs-lookup"><span data-stu-id="2f4fa-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="2f4fa-131">Нет, не изменится ни один из существующих наборов результатов поиска и рецензирования.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="2f4fa-132">Нет необходимости переиндексации существующих данных, и результаты поиска для английского текста будут одинаковы.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="2f4fa-133">**Как изменить язык отображения на китайский, японский или корейский?**</span><span class="sxs-lookup"><span data-stu-id="2f4fa-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="2f4fa-134">Сведения о том, как изменить язык отображения и часовой пояс, приведены [в статье Настройка языковых и региональных параметров для Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="2f4fa-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="2f4fa-135">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="2f4fa-135">Known issues</span></span>

- <span data-ttu-id="2f4fa-136">Программа оптического распознавания текста не поддерживает ККЯ символов из файлов изображений</span><span class="sxs-lookup"><span data-stu-id="2f4fa-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="2f4fa-137">Файлы электронной почты (например, \*. EML и \*. MSG) в [представлении "Примечания](view-documents-in-review-set.md#annotate-view) " не поддерживаются для языков CJK.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="2f4fa-138">Выделение совпадений поиска в [текстовом представлении](view-documents-in-review-set.md#text-view) не поддерживается для языков CJK.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="2f4fa-139">[Модуль релевантности](using-relevance.md) , используемый для анализа данных, не поддерживает языки CJK.</span><span class="sxs-lookup"><span data-stu-id="2f4fa-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="2f4fa-140">Для языков CJK не поддерживаются [удержания на основе запросов](managing-holds.md#manage-non-custodial-holds) .</span><span class="sxs-lookup"><span data-stu-id="2f4fa-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
