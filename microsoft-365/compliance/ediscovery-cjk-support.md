---
title: Поддержка CJK/Double Byte для advanced eDiscovery
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
description: Узнайте, как advanced eDiscovery в Microsoft 365 поддерживает китайский, японский и корейский (CJK) языки, в которых используется набор символов с двойным байтом.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926605"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="fcc41-103">Языковая поддержка CJK для advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fcc41-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="fcc41-104">Advanced eDiscovery поддерживает языки набора символов с двойным байтом (к ним относятся упрощенный китайский, традиционный китайский, японский и корейский языки, которые в совокупности называют языками *CJK)* для следующих расширенных сценариев в наборе обзоров:</span><span class="sxs-lookup"><span data-stu-id="fcc41-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="fcc41-105">При [запросе данных в наборе отзывов](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="fcc41-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="fcc41-106">При [теге документов в наборе отзывов](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="fcc41-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="fcc41-107">При [анализе данных случаев в наборе обзоров](analyzing-data-in-review-set.md) с помощью почти дубликатов обнаружения, потоковой обработки электронной почты и аналитики тем.</span><span class="sxs-lookup"><span data-stu-id="fcc41-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="fcc41-108">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="fcc41-108">Frequently asked questions</span></span>

<span data-ttu-id="fcc41-109">**Как создать поиск для сбора элементов с символами CJK?**</span><span class="sxs-lookup"><span data-stu-id="fcc41-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="fcc41-110">При поиске контента в advanced eDiscovery можно использовать символы CJK для поиска по ключевым [словам,](building-search-queries.md#keyword-searches)запросов по ключевым словам и условий поиска. [](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="fcc41-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="fcc41-111">Поиск символов CJK также поддерживается при поиске контента в core eDiscovery и Content Search.</span><span class="sxs-lookup"><span data-stu-id="fcc41-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="fcc41-112">Мы предоставляем поддержку CJK для всех операторов поиска и условий [поиска,](keyword-queries-and-search-conditions.md#search-conditions)в том числе операторов boolean **и**, **ИЛИ**, **НЕ**, и **БЛИЗКО**. [](keyword-queries-and-search-conditions.md#search-operators)</span><span class="sxs-lookup"><span data-stu-id="fcc41-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="fcc41-113">Если вы уверены, что расположения контента или элементы содержат символы CJK, но поиски не возвращают результатов, щелкните значок язык-страна запроса или региона.</span><span class="sxs-lookup"><span data-stu-id="fcc41-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Значок языковой страны и региона в поиске контента](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="fcc41-115">и выберите соответствующее значение кода культурного кода языковой страны для поиска.</span><span class="sxs-lookup"><span data-stu-id="fcc41-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="fcc41-116">По умолчанию используется нейтральный язык и регион.</span><span class="sxs-lookup"><span data-stu-id="fcc41-116">The default language/region is neutral.</span></span>

<span data-ttu-id="fcc41-117">**Можно ли одновременно искать несколько языков?**</span><span class="sxs-lookup"><span data-stu-id="fcc41-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="fcc41-118">Это зависит от сценария поиска.</span><span class="sxs-lookup"><span data-stu-id="fcc41-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="fcc41-119">При [запросе данных в наборе обзоров](review-set-search.md) в advanced eDiscovery можно искать несколько языков.</span><span class="sxs-lookup"><span data-stu-id="fcc41-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="fcc41-120">При создании [поиска для сбора данных](create-search-to-collect-data.md)создайте отдельный поиск для каждого языка, на который вы нацелены.</span><span class="sxs-lookup"><span data-stu-id="fcc41-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="fcc41-121">Например, если вы ищете документ, содержащий как китайский, так и корейский, выберите китайский для первого запроса и выберите корейский для второго запроса.</span><span class="sxs-lookup"><span data-stu-id="fcc41-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="fcc41-122">**Я не вижу значок язык-страна запроса или региона, чтобы выбрать язык для запросов в наборе отзывов. Как указать язык запроса в поиске набора отзывов?**</span><span class="sxs-lookup"><span data-stu-id="fcc41-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="fcc41-123">Для запросов набора обзоров не требуется указывать язык документов.</span><span class="sxs-lookup"><span data-stu-id="fcc41-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="fcc41-124">Advanced eDiscovery автоматически обнаруживает языки документов при добавлении контента в набор отзывов.</span><span class="sxs-lookup"><span data-stu-id="fcc41-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="fcc41-125">Это поможет оптимизировать результаты запроса в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="fcc41-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="fcc41-126">**Можно ли увидеть обнаруженные языки в [метаданных файлов?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="fcc41-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="fcc41-127">Нет, вы не можете видеть обнаруженные языки в метаданных файлов.</span><span class="sxs-lookup"><span data-stu-id="fcc41-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="fcc41-128">**Можно ли фильтровать языки документов в наборе отзывов?**</span><span class="sxs-lookup"><span data-stu-id="fcc41-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="fcc41-129">Нет, вы не можете фильтровать, сортировать или искать на языках документов в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="fcc41-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="fcc41-130">**Повлияет ли этот выпуск CJK для сценариев набора обзоров на любой из существующих наборов запросов и обзоров?**</span><span class="sxs-lookup"><span data-stu-id="fcc41-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="fcc41-131">Нет, ни один из существующих наборов поисков и обзоров не изменится.</span><span class="sxs-lookup"><span data-stu-id="fcc41-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="fcc41-132">Нет необходимости реиндексовать существующие данные, и результаты поиска по английскому тексту будут одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="fcc41-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="fcc41-133">**Как изменить язык отображения на китайский, японский или корейский?**</span><span class="sxs-lookup"><span data-stu-id="fcc41-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="fcc41-134">Сведения о том, как изменить язык отображения и часовой пояс, см. в руб. Как установить параметры языка и региона [для Office 365.](/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="fcc41-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="fcc41-135">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="fcc41-135">Known issues</span></span>

- <span data-ttu-id="fcc41-136">OCR не поддерживает символы CJK из файлов изображений</span><span class="sxs-lookup"><span data-stu-id="fcc41-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="fcc41-137">Файлы электронной почты (например, \*.eml и \*.msg) в представлении [Аннотации](view-documents-in-review-set.md#annotate-view) не поддерживаются для языков CJK.</span><span class="sxs-lookup"><span data-stu-id="fcc41-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="fcc41-138">Выделение хита поиска в [текстовом представлении](view-documents-in-review-set.md#text-view) не поддерживается для языков CJK.</span><span class="sxs-lookup"><span data-stu-id="fcc41-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="fcc41-139">Модуль [Релевантность,](using-relevance.md) используемый для анализа данных, не поддерживает языки CJK.</span><span class="sxs-lookup"><span data-stu-id="fcc41-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="fcc41-140">[Для языков](managing-holds.md#manage-non-custodial-holds) CJK не поддерживаются ведерки на основе запросов.</span><span class="sxs-lookup"><span data-stu-id="fcc41-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>