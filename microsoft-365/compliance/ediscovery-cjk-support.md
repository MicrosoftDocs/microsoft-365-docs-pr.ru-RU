---
title: Поддержка CJK/Double Byte для Advanced eDiscovery
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
description: Узнайте, как Advanced eDiscovery в Microsoft 365 поддерживает китайский, японский и корейский языки (CJK), которые используют двухбайтовой набор символов.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626943"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="f756f-103">Поддержка языка CJK для Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f756f-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="f756f-104">Advanced eDiscovery поддерживает двухбайтовые языки набора символов (например, китайский (упрощенный китайский, традиционное китайский, японский и корейский языки, которые совместно называются языками *CJK)* для следующих расширенных сценариев в наборе для проверки:</span><span class="sxs-lookup"><span data-stu-id="f756f-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="f756f-105">При [запросе данных в наборе для проверки.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="f756f-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="f756f-106">При [пометке документов в наборе для проверки.](tagging-documents.md)</span><span class="sxs-lookup"><span data-stu-id="f756f-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="f756f-107">При [анализе данных дела](analyzing-data-in-review-set.md) в наборе для проверки с помощью обнаружения практически дублирующихся сообщений, потоков электронной почты и аналитики тем.</span><span class="sxs-lookup"><span data-stu-id="f756f-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f756f-108">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="f756f-108">Frequently asked questions</span></span>

<span data-ttu-id="f756f-109">**Как создать поиск для сбора элементов, которые содержат символы CJK?**</span><span class="sxs-lookup"><span data-stu-id="f756f-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="f756f-110">При поиске контента в Advanced eDiscovery можно использовать символы CJK для поиска по ключевым [словам,](building-search-queries.md#keyword-searches)запросов по ключевым словам и условий поиска. [](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="f756f-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="f756f-111">Поиск символов CJK также поддерживается при поиске контента в основных eDiscovery и поиске контента.</span><span class="sxs-lookup"><span data-stu-id="f756f-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="f756f-112">Мы предоставляем поддержку CJK для всех операторов поиска и условий [поиска,](keyword-queries-and-search-conditions.md#search-conditions)включая boolean operators [](keyword-queries-and-search-conditions.md#search-operators) **AND**, OR , **NOT**, and **NEAR**. </span><span class="sxs-lookup"><span data-stu-id="f756f-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="f756f-113">Если вы уверены, что расположения контента или элементы содержат символы CJK, но поиск не возвращает результатов, щелкните значок языка или региона запроса</span><span class="sxs-lookup"><span data-stu-id="f756f-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Значок страны или региона запроса в поиске контента](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="f756f-115">и выберите соответствующее значение кода языка и страны для поиска.</span><span class="sxs-lookup"><span data-stu-id="f756f-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="f756f-116">По умолчанию используется нейтральный язык и регион.</span><span class="sxs-lookup"><span data-stu-id="f756f-116">The default language/region is neutral.</span></span>

<span data-ttu-id="f756f-117">**Можно ли искать несколько языков одновременно?**</span><span class="sxs-lookup"><span data-stu-id="f756f-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="f756f-118">Это зависит от сценария поиска.</span><span class="sxs-lookup"><span data-stu-id="f756f-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="f756f-119">При [запросе данных в наборе для проверки](review-set-search.md) в Advanced eDiscovery можно искать несколько языков.</span><span class="sxs-lookup"><span data-stu-id="f756f-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="f756f-120">При создании [поиска для сбора данных](create-search-to-collect-data.md)создайте отдельный поиск для каждого языка, на который вы нацелены.</span><span class="sxs-lookup"><span data-stu-id="f756f-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="f756f-121">Например, если вы ищете документ, который содержит китайский и корейский, выберите китайский для первого запроса и выберите корейский для второго запроса.</span><span class="sxs-lookup"><span data-stu-id="f756f-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="f756f-122">**Я не вижу значок страны или региона запроса для выбора языка запросов в наборе для проверки. Как задать язык запроса в поисковом наборе для проверки?**</span><span class="sxs-lookup"><span data-stu-id="f756f-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="f756f-123">Для запросов набора для проверки не нужно указывать язык документа.</span><span class="sxs-lookup"><span data-stu-id="f756f-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="f756f-124">Advanced eDiscovery автоматически обнаруживает языки документов при добавлении контента в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="f756f-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="f756f-125">Это помогает оптимизировать результаты запроса в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="f756f-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="f756f-126">**Можно ли увидеть обнаруженные языки в [метаданных файла?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="f756f-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="f756f-127">Нет, в метаданных файла не могут быть обнаружены языки.</span><span class="sxs-lookup"><span data-stu-id="f756f-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="f756f-128">**Можно ли фильтровать языки документов в наборе для проверки?**</span><span class="sxs-lookup"><span data-stu-id="f756f-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="f756f-129">Нет, в наборе для проверки нельзя фильтровать, сортировать или искать языки документов.</span><span class="sxs-lookup"><span data-stu-id="f756f-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="f756f-130">**Повлияет ли этот выпуск CJK на какие-либо из существующих наборов поиска и проверки?**</span><span class="sxs-lookup"><span data-stu-id="f756f-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="f756f-131">Нет, ни один из существующих наборов поиска и проверки не изменится.</span><span class="sxs-lookup"><span data-stu-id="f756f-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="f756f-132">Переиндексовать существующие данные не требуется, и результаты поиска текста на английском языке будут одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="f756f-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="f756f-133">**Как изменить язык отображения на китайский, японский или корейский?**</span><span class="sxs-lookup"><span data-stu-id="f756f-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="f756f-134">Сведения об изменении языка и часового пояса см. в сведениях о настройке языка и региона [для Office 365.](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="f756f-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="f756f-135">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f756f-135">Known issues</span></span>

- <span data-ttu-id="f756f-136">OCR не поддерживает символы CJK из файлов изображений</span><span class="sxs-lookup"><span data-stu-id="f756f-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="f756f-137">Файлы электронной почты (например, \*.eml и \*.msg) в представлении [Annotate](view-documents-in-review-set.md#annotate-view) не поддерживаются для языков CJK.</span><span class="sxs-lookup"><span data-stu-id="f756f-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="f756f-138">Выделение результатов поиска в [текстовом представлении](view-documents-in-review-set.md#text-view) не поддерживается для языков CJK.</span><span class="sxs-lookup"><span data-stu-id="f756f-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="f756f-139">Модуль [релевантности,](using-relevance.md) используемый для анализа данных, не поддерживает языки CJK.</span><span class="sxs-lookup"><span data-stu-id="f756f-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="f756f-140">[Запросы не](managing-holds.md#manage-non-custodial-holds) поддерживаются для языков CJK.</span><span class="sxs-lookup"><span data-stu-id="f756f-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
