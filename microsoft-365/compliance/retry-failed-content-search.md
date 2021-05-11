---
title: Повторное поиск контента для устранения ошибки расположения контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Во время расследования можно использовать кнопку Retry для разрешения поиска контента с ошибками расположения контента.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311824"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="c858c-103">Повторное поиск контента для устранения ошибки расположения контента</span><span class="sxs-lookup"><span data-stu-id="c858c-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="c858c-104">При использовании поиска контента в центре безопасности и соответствия требованиям для поиска большого количества почтовых ящиков могут возникнуть ошибки поиска, аналогичные ошибке:</span><span class="sxs-lookup"><span data-stu-id="c858c-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="c858c-105">Эти ошибки (с кодами ошибок CS001-002, CS003-002, CS008-009, CS012-002 и другими ошибками формы CS0XX-0XX) указывают на то, что поиск контента не удалось найти определенные расположения контента; В этом примере два почтовых ящика не были отправлены в поиск.</span><span class="sxs-lookup"><span data-stu-id="c858c-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="c858c-106">Эти ошибки отображаются на странице сведений о состоянии на странице поиска контента.</span><span class="sxs-lookup"><span data-stu-id="c858c-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="c858c-107">Причина ошибок расположения контента</span><span class="sxs-lookup"><span data-stu-id="c858c-107">Cause of content location errors</span></span>

<span data-ttu-id="c858c-108">При поиске большого количества почтовых ящиков поиск распространяется на тысячи серверов центра обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c858c-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="c858c-109">В любое время определенные серверы могут быть в состоянии перезагрузки или в процессе отказа от избыточных копий.</span><span class="sxs-lookup"><span data-stu-id="c858c-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="c858c-110">В любом из этих случаев запрос поиска контента на извлечение данных будет отстает. В предыдущем примере ошибки для сбоя почтовых ящиков были результатом времени поиска.</span><span class="sxs-lookup"><span data-stu-id="c858c-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="c858c-111">Устранение ошибок расположения контента</span><span class="sxs-lookup"><span data-stu-id="c858c-111">Resolving content location errors</span></span>

<span data-ttu-id="c858c-112">Перезапуск поиска часто приводит к аналогичным ошибкам на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="c858c-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="c858c-113">Вместо перезапуска поиска нажмите кнопку **Retry,** отображаемую в верхней части страницы результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="c858c-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Нажмите кнопку Retry для устранения ошибок расположения контента](../media/retrycontentsearch3.png)

<span data-ttu-id="c858c-115">Это приведет к повторному поиску только для сбоя почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="c858c-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="c858c-116">При повторном поиске сохраняются другие успешно возвращенные результаты.</span><span class="sxs-lookup"><span data-stu-id="c858c-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="c858c-117">Советы, чтобы избежать ошибок расположения контента</span><span class="sxs-lookup"><span data-stu-id="c858c-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="c858c-118">Вот некоторые дополнительные причины ошибок расположения контента и советы, которые помогут избежать их при поиске большого количества почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="c858c-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="c858c-119">Поиск почтового ящика может быть занят из-за активности пользователя.</span><span class="sxs-lookup"><span data-stu-id="c858c-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="c858c-120">В этом случае служба поиска может затормошать себя, чтобы не допустить недоступности почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c858c-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="c858c-121">Чтобы избежать этого, попробуйте запускать поиск в не-бизнес-часы.</span><span class="sxs-lookup"><span data-stu-id="c858c-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="c858c-122">Запрос поиска может быть поиск слишком содержимого из почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c858c-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="c858c-123">По возможности попробуйте сузить область поиска с помощью ключевых слов, диапазонов дат и условий поиска.</span><span class="sxs-lookup"><span data-stu-id="c858c-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="c858c-124">Слишком много ключевых слов или фраз ключевых слов при создании поискового запроса с помощью списка [ключевых слов](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="c858c-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span> <span data-ttu-id="c858c-125">При запуске поискового запроса, использующего список ключевых слов, служба по сути выполняет отдельный поиск для каждой строки в списке ключевых слов, чтобы можно было получить статистику.</span><span class="sxs-lookup"><span data-stu-id="c858c-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="c858c-126">Если вы используете список ключевых слов в поисковых запросах, свести к минимуму количество строк в списке ключевых слов или разделить число ключевых слов на более мелкие списки и создать другой поиск для каждого списка ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="c858c-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c858c-127">Чтобы уменьшить проблемы, вызванные большими списками ключевых слов, теперь в списке ключевых слов поискового запроса ограничено не более 20 строк.</span><span class="sxs-lookup"><span data-stu-id="c858c-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="c858c-128">В одном почтовом ящике одновременно выполняется слишком много поисков.</span><span class="sxs-lookup"><span data-stu-id="c858c-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="c858c-129">По возможности попробуйте выполнить один поиск одновременно на любом почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="c858c-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="c858c-130">Поиск слишком много почтовых ящиков в одном поиске.</span><span class="sxs-lookup"><span data-stu-id="c858c-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="c858c-131">Вероятность ошибок расположения контента увеличивается при поиске большого количества почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="c858c-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="c858c-132">По возможности попробуйте выполнить несколько поисков, чтобы каждый поиск включал подмножество почтовых ящиков в организации.</span><span class="sxs-lookup"><span data-stu-id="c858c-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="c858c-133">В почтовом ящике выполняется обязательное обслуживание.</span><span class="sxs-lookup"><span data-stu-id="c858c-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="c858c-134">Хотя эта причина, вероятно, происходит нечасто, подождите некоторое время после получения ошибки расположения контента, а затем повторного поиска.</span><span class="sxs-lookup"><span data-stu-id="c858c-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
