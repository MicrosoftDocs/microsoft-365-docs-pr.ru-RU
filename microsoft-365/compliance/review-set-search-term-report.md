---
title: Создание отчета о терминах поиска для набора проверки
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: bb65745f92d1f77e6cc3224832c0a9871e567ca5
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558476"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="d3647-102">Создание отчета о терминах поиска для набора проверки</span><span class="sxs-lookup"><span data-stu-id="d3647-102">Generate search term report for a review set</span></span>

<span data-ttu-id="d3647-103">В случае обнаружения электронных данных одно из наиболее часто используемых условий для запросов к документам заключается в использовании ключевых слов для поиска ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="d3647-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="d3647-104">Определяя документы, содержащие определенные ключевые слова (также называемые *терминами*), которые важны для случая, проверяющие могут начать получать высокоуровневое понимание того, что они размещаются.</span><span class="sxs-lookup"><span data-stu-id="d3647-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="d3647-105">В приложении Advanced eDiscovery в Microsoft 365 это можно сделать, создав отчеты о терминах поиска для сохраненных запросов в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="d3647-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="d3647-106">Шаг 1: Создание сохраненного запроса в наборе рецензирования</span><span class="sxs-lookup"><span data-stu-id="d3647-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="d3647-107">Чтобы создать осмысленный отчет по условиям поиска, создайте сохраненный запрос, который определяет набор документов в наборе проверки, для которых необходимо создать отчет о терминах поиска.</span><span class="sxs-lookup"><span data-stu-id="d3647-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="d3647-108">Например, можно использовать диапазон дат или фактический набор терминов поиска (с помощью карточки условия ключевых слов), чтобы создать запрос.</span><span class="sxs-lookup"><span data-stu-id="d3647-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="d3647-109">Чтобы узнать больше о наборах проверок, ознакомьтесь [со статьей запрос данных в наборе рецензирования](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="d3647-110">Шаг 2: создание отчета по условиям поиска</span><span class="sxs-lookup"><span data-stu-id="d3647-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="d3647-111">Создать отчет термина поиска можно двумя разными способами: через контекстное меню сохраненного запроса, созданного на шаге 1, или с помощью консоли управления отчетным термином поиска.</span><span class="sxs-lookup"><span data-stu-id="d3647-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="d3647-112">Чтобы использовать контекстное меню, откройте контекстное меню сохраненного запроса, созданного на шаге 1, и щелкните **создать отчет термина поиска**.</span><span class="sxs-lookup"><span data-stu-id="d3647-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="d3647-113">Чтобы использовать консоль управления, перейдите к разделу **Управление обзором > Просмотр отчетов терминов поиска**, нажмите кнопку **создать**, а затем выберите сохраненный запрос, созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d3647-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="d3647-114">Затем введите термины, которые необходимо включить в отчет, отделяя их символами новой строки. Если сохраненный запрос, созданный на шаге 1, использовался в карточке условия с ключевыми словами, всплывающая страница будет предварительно заполнена терминами из первой карточки условия ключевых слов, используемой в сохраненном запросе.</span><span class="sxs-lookup"><span data-stu-id="d3647-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="d3647-115">Затем выберите перед тремя сводными сообщениями, которые необходимо включить в отчет, и нажмите кнопку **создать**, в котором будет запущено задание создания отчета о терминах поиска.</span><span class="sxs-lookup"><span data-stu-id="d3647-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="d3647-116">Что такое сводная таблица?</span><span class="sxs-lookup"><span data-stu-id="d3647-116">What is a pivot?</span></span>

<span data-ttu-id="d3647-117">Сводные сведения о том, как будет организован отчет.</span><span class="sxs-lookup"><span data-stu-id="d3647-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="d3647-118">Рассмотрим приведенный ниже пример.</span><span class="sxs-lookup"><span data-stu-id="d3647-118">Consider the following example.</span></span>

- <span data-ttu-id="d3647-119">Сохраненный запрос получает 10 документов: doc1 до doc10.</span><span class="sxs-lookup"><span data-stu-id="d3647-119">The saved query retrieves 10 documents: doc1 through doc10.</span></span>

- <span data-ttu-id="d3647-120">doc1, doc2, doc3, doc4, doc5, doc6 и DOC7 содержат термин "обнаружение электронных данных".</span><span class="sxs-lookup"><span data-stu-id="d3647-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="d3647-121">doc6, DOC7, doc8, doc9 и doc10 содержат термин "исследование".</span><span class="sxs-lookup"><span data-stu-id="d3647-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="d3647-122">doc1, doc3, doc5, DOC7, doc9 — от хранитель A.</span><span class="sxs-lookup"><span data-stu-id="d3647-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="d3647-123">doc2, doc4, doc6, doc8, doc10 — из хранитель B.</span><span class="sxs-lookup"><span data-stu-id="d3647-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="d3647-124">В этом случае, если вы создавали отчет термина поиска на терминах "обнаружение электронных данных" и "исследование" и сведение по custodians, отчет по условиям поиска будет организован следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3647-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="d3647-125">"обнаружение электронных данных" — Хранитель A: 4 документа</span><span class="sxs-lookup"><span data-stu-id="d3647-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="d3647-126">"обнаружение электронных данных" — Хранитель б: 3 документа</span><span class="sxs-lookup"><span data-stu-id="d3647-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="d3647-127">"Исследование" — Хранитель A: 2 документы</span><span class="sxs-lookup"><span data-stu-id="d3647-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="d3647-128">"Исследование" — Хранитель б: 3 документа</span><span class="sxs-lookup"><span data-stu-id="d3647-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="d3647-129">Шаг 3: Загрузка отчета</span><span class="sxs-lookup"><span data-stu-id="d3647-129">Step 3: Download report</span></span>

<span data-ttu-id="d3647-130">В консоли управления поиском терминов можно отслеживать состояние ранее созданного задания отчета о поиске терминов.</span><span class="sxs-lookup"><span data-stu-id="d3647-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="d3647-131">После завершения задания щелкните строку отчета Поиск терминов и нажмите кнопку "Скачать", чтобы скачать отчет термина поиска в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="d3647-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="d3647-132">Одна строка для каждого кортежа (термин поиска, сводка) и каждая строка будет содержать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d3647-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="d3647-133">Сколько документов было получено?</span><span class="sxs-lookup"><span data-stu-id="d3647-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="d3647-134">Сколько раз было найдено условие поиска в документах?</span><span class="sxs-lookup"><span data-stu-id="d3647-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="d3647-135">Каков общий объем извлеченных документов?</span><span class="sxs-lookup"><span data-stu-id="d3647-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="d3647-136">Сколько семейств было получено?</span><span class="sxs-lookup"><span data-stu-id="d3647-136">How many families were retrieved?</span></span>

- <span data-ttu-id="d3647-137">Каково общее количество документов для этих семейств, включая документы, для которых не задано условие поиска?</span><span class="sxs-lookup"><span data-stu-id="d3647-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="d3647-138">Каков общий объем указанного выше?</span><span class="sxs-lookup"><span data-stu-id="d3647-138">What is the total volume of the above?</span></span>