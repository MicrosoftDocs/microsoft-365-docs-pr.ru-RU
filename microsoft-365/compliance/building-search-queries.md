---
title: Создание поисковых запросов
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Использование ключевых слов и условий для сужения области поиска при поиске данных с помощью расширенного обнаружения электронных данных в Microsoft 365.
ms.openlocfilehash: c704b338600c715193829e442e1bd6ba7c780455
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079046"
---
# <a name="build-search-queries"></a><span data-ttu-id="32c15-103">Создание поисковых запросов</span><span class="sxs-lookup"><span data-stu-id="32c15-103">Build search queries</span></span>

<span data-ttu-id="32c15-104">При создании поисковых запросов можно использовать ключевые слова для поиска определенного содержимого и условий, чтобы сузить область поиска для возврата элементов, наиболее релевантных для вашего судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="32c15-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![Использование ключевых слов и условий для сужения результатов поиска](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="32c15-106">Поиск по ключевым словам</span><span class="sxs-lookup"><span data-stu-id="32c15-106">Keyword searches</span></span>

<span data-ttu-id="32c15-107">Введите запрос ключевого слова в поле **Ключевые слова** в запросе поиска.</span><span class="sxs-lookup"><span data-stu-id="32c15-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="32c15-108">Можно указать ключевые слова, свойства сообщений электронной почты, такие как даты отправки и получения, а также свойства документа, такие как имена файлов или Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="32c15-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="32c15-109">Можно создавать более сложные запросы, включающие логические операторы, например **AND**, **OR**, **NOT** и **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="32c15-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="32c15-110">Кроме того, можно искать конфиденциальные сведения (например, номера социального страхования) в документах SharePoint и OneDrive (не в сообщениях электронной почты) или искать документы, к которым предоставлен доступ извне.</span><span class="sxs-lookup"><span data-stu-id="32c15-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="32c15-111">Если оставить поле **Ключевые слова** пустым, то весь контент, расположенный в указанных расположениях контента, будет находиться в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="32c15-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>
    
<span data-ttu-id="32c15-112">Кроме того, можно установить флажок **Показать список ключевых слов** и ввести ключевое слово или ключевое слово ключевое слово в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="32c15-112">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="32c15-113">В этом случае ключевые слова в каждой строке соединяются логическим оператором (который представляется как *к:с* в синтаксисе поискового запроса), который аналогичен оператору **or** в созданном запросе поиска.</span><span class="sxs-lookup"><span data-stu-id="32c15-113">If you do this, the keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="32c15-114">Это означает, что элементы, содержащие любое ключевое слово в любой строке, находятся в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="32c15-114">This means items that contain any keyword in any row are in the search results.</span></span>

![Использование списка ключевых слов для получения статистики по всем ключевым словам в запросе](../media/KeywordListSearch.png)

<span data-ttu-id="32c15-116">Зачем использовать список ключевых слов?</span><span class="sxs-lookup"><span data-stu-id="32c15-116">Why use the keyword list?</span></span> <span data-ttu-id="32c15-117">Вы можете получить статистику по количеству элементов, которые совпадают с каждым ключевым словом в списке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="32c15-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="32c15-118">Это поможет быстро определить наиболее эффективные (и наименее) Ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="32c15-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="32c15-119">Кроме того, можно использовать ключевую фразу (заключенную в круглые скобки) в строке в списке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="32c15-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="32c15-120">Дополнительные сведения о статистике поиска можно найти в статье [Статистика поиска](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="32c15-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="32c15-121">Для сокращения проблем, вызванных списками с большими ключевыми словами, в списке ключевых слов можно ограничить до 20 строк.</span><span class="sxs-lookup"><span data-stu-id="32c15-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="32c15-122">Условия</span><span class="sxs-lookup"><span data-stu-id="32c15-122">Conditions</span></span>
    
<span data-ttu-id="32c15-123">Вы можете добавить условия поиска, чтобы сузить область поиска и возвратить более уточненный набор результатов.</span><span class="sxs-lookup"><span data-stu-id="32c15-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="32c15-124">Каждое условие добавляет предложение к поисковому запросу, которое создается и запускается в начале поиска.</span><span class="sxs-lookup"><span data-stu-id="32c15-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="32c15-125">Условие логически подключается к запросу ключевого слова, указанному в поле ключевое слово логическим оператором (который представляется как *к:к* в синтаксисе поискового запроса), который похож на функциональность оператора **and** .</span><span class="sxs-lookup"><span data-stu-id="32c15-125">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="32c15-126">Это означает, что элементы должны удовлетворять как запрос ключевого слова, так и одно или несколько условий, включаемых в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="32c15-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="32c15-127">Таким образом условия помогают сузить область результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="32c15-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="32c15-128">Список и описание условий, которые можно использовать в поисковых запросах, представлены в разделе "условия поиска" в разделе [запросы и условия поиска ключевых слов](keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="32c15-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
