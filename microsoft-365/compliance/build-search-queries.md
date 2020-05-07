---
title: Создание поисковых запросов — расследования данных
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
ms.custom: seo-marvel-mar2020
description: Использование ключевых слов и условий для сужения области поиска при поиске данных с помощью расследования данных в Microsoft 365.
ms.openlocfilehash: 95466d0e7c7109001fef001cc0d5bca5b6d658ed
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034117"
---
# <a name="build-search-queries"></a><span data-ttu-id="946d1-103">Создание поисковых запросов</span><span class="sxs-lookup"><span data-stu-id="946d1-103">Build search queries</span></span>

<span data-ttu-id="946d1-104">При создании поисковых запросов можно использовать ключевые слова для поиска определенного содержимого и условий, чтобы сузить область поиска для возврата элементов, наиболее релевантных для вашего расследования.</span><span class="sxs-lookup"><span data-stu-id="946d1-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your investigation.</span></span>

![Использование ключевых слов и условий для сужения результатов поиска](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="946d1-106">Поиск по ключевым словам</span><span class="sxs-lookup"><span data-stu-id="946d1-106">Keyword searches</span></span>

<span data-ttu-id="946d1-107">Введите запрос ключевого слова в поле **Ключевые слова** в запросе поиска.</span><span class="sxs-lookup"><span data-stu-id="946d1-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="946d1-108">Можно указать ключевые слова, свойства сообщений электронной почты, такие как даты отправки и получения, а также свойства документа, такие как имена файлов или Дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="946d1-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="946d1-109">Можно создавать более сложные запросы, включающие логические операторы, например **AND**, **OR**, **NOT** и **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="946d1-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="946d1-110">Кроме того, можно искать конфиденциальные сведения, например номера социального страхования, в документах SharePoint и OneDrive (не в сообщениях электронной почты) или искать документы, к которым предоставлен доступ извне.</span><span class="sxs-lookup"><span data-stu-id="946d1-110">You can also search for sensitive information, such as social security numbers, in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="946d1-111">Если оставить поле **Ключевые слова** пустым, весь контент, расположенный в указанных расположениях контента, будет включен в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="946d1-111">If you leave the **Keywords** box empty, all content located in the specified content locations is included in the search results.</span></span>
    
<span data-ttu-id="946d1-112">Кроме того, можно установить флажок **Показать список ключевых слов** , а затем ввести ключевое слово или ключевое слово ключевое слово в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="946d1-112">Alternatively, you can select the **Show keyword list** check box and then type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="946d1-113">В этом случае ключевые слова в каждой строке соединяются логическим оператором (представленным как *к:с*), который аналогичен оператору **or** в созданном запросе поиска.</span><span class="sxs-lookup"><span data-stu-id="946d1-113">If you do this, the keywords in each row are connected by a logical operator (represented as *c:s*) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="946d1-114">Это означает, что элементы, содержащие любое ключевое слово в любой строке, включаются в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="946d1-114">This means that items that contain any keyword in any row are included in the search results.</span></span>

![Использование списка ключевых слов для получения статистики по всем ключевым словам в запросе](../media/KeywordListSearch.png)

<span data-ttu-id="946d1-116">Зачем использовать список ключевых слов?</span><span class="sxs-lookup"><span data-stu-id="946d1-116">Why use the keyword list?</span></span> <span data-ttu-id="946d1-117">Вы можете получить статистику по количеству элементов, которые совпадают с каждым ключевым словом в списке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="946d1-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="946d1-118">Это поможет быстро определить наиболее эффективные (и наименее) Ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="946d1-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="946d1-119">Кроме того, можно использовать ключевую фразу (заключенную в круглые скобки) в строке в списке ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="946d1-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="946d1-120">Дополнительные сведения о статистике поиска можно найти в статье [Статистика поиска](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="946d1-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="946d1-121">Для сокращения проблем, вызванных списками с большими ключевыми словами, в списке ключевых слов можно ограничить до 20 строк.</span><span class="sxs-lookup"><span data-stu-id="946d1-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="946d1-122">Условия</span><span class="sxs-lookup"><span data-stu-id="946d1-122">Conditions</span></span>
    
<span data-ttu-id="946d1-123">Вы можете добавить условия поиска, чтобы сузить область поиска и возвратить более уточненный набор результатов.</span><span class="sxs-lookup"><span data-stu-id="946d1-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="946d1-124">Каждое условие добавляет предложение к поисковому запросу, которое создается и запускается в начале поиска.</span><span class="sxs-lookup"><span data-stu-id="946d1-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="946d1-125">Условие логически подключается к запросу ключевого слова (заданному в поле ключевое слово) логическим оператором (представленным как *к:к*), который аналогичен оператору **and** .</span><span class="sxs-lookup"><span data-stu-id="946d1-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c*) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="946d1-126">Это означает, что элементы должны удовлетворять как запрос ключевого слова, так и одно или несколько условий, включаемых в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="946d1-126">This means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="946d1-127">Таким образом условия помогают сузить область результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="946d1-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="946d1-128">Список и описание условий, которые можно использовать в поисковых запросах, представлены в разделе "условия поиска" в разделе [запросы и условия поиска ключевых слов](keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="946d1-128">For a list and description of conditions you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
