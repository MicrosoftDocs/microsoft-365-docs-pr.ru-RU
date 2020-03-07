---
title: Анализ данных в наборе анализа в Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 0f9cb386ce57d6581ade5caa05e029511100d9b3
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42556787"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="3cc73-102">Анализ данных в наборе анализа в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3cc73-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="3cc73-103">При большом количестве собранных документов может быть трудно Просмотреть все.</span><span class="sxs-lookup"><span data-stu-id="3cc73-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="3cc73-104">Расширенное обнаружение электронных данных предоставляет ряд средств для анализа документов, чтобы сократить объем документов, проверяемых без потерь данных, и помочь организовать документы единообразно.</span><span class="sxs-lookup"><span data-stu-id="3cc73-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="3cc73-105">Чтобы узнать больше об этих возможностях, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="3cc73-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="3cc73-106">Обнаружение схожих документов (почти дубликатов)</span><span class="sxs-lookup"><span data-stu-id="3cc73-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="3cc73-107">Потоки почты</span><span class="sxs-lookup"><span data-stu-id="3cc73-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="3cc73-108">Темы</span><span class="sxs-lookup"><span data-stu-id="3cc73-108">Themes</span></span>](themes.md)

<span data-ttu-id="3cc73-109">Анализ данных в наборе проверки:</span><span class="sxs-lookup"><span data-stu-id="3cc73-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="3cc73-110">Настройте параметры аналитики для своего случая.</span><span class="sxs-lookup"><span data-stu-id="3cc73-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="3cc73-111">Дополнительную информацию можно узнать в статье [Настройка параметров поиска и аналитики](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3cc73-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="3cc73-112">Откройте набор проверок, который необходимо проанализировать.</span><span class="sxs-lookup"><span data-stu-id="3cc73-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="3cc73-113">Щелкните **Управление набором проверки**.</span><span class="sxs-lookup"><span data-stu-id="3cc73-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="3cc73-114">Щелкните **запустить аналитику для набора проверки**.</span><span class="sxs-lookup"><span data-stu-id="3cc73-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="3cc73-115">На вкладке **задания** можно проверить ход выполнения анализа.</span><span class="sxs-lookup"><span data-stu-id="3cc73-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="3cc73-116">После завершения анализа можно просмотреть аналитический отчет, запустить запросы в наборе рецензирования для результатов анализа (см. [запрос в наборе проверки](review-set-search.md)), а также связанные документы определенного документа (см. [Обзор данных в наборе проверки](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="3cc73-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="3cc73-117">Аналитический отчет</span><span class="sxs-lookup"><span data-stu-id="3cc73-117">Analytics report</span></span>

<span data-ttu-id="3cc73-118">Чтобы просмотреть аналитический отчет для набора проверки:</span><span class="sxs-lookup"><span data-stu-id="3cc73-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="3cc73-119">Откройте набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="3cc73-119">Open the review set.</span></span>

2. <span data-ttu-id="3cc73-120">Щелкните **Управление набором проверки**.</span><span class="sxs-lookup"><span data-stu-id="3cc73-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="3cc73-121">Нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="3cc73-121">Click **View report**.</span></span>

<span data-ttu-id="3cc73-122">В отчете есть семь компонентов из анализа:</span><span class="sxs-lookup"><span data-stu-id="3cc73-122">The report has seven components from analysis:</span></span>

- <span data-ttu-id="3cc73-123">**Целевое заполнение:** Количество сообщений электронной почты, вложений и свободных документов, найденных в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="3cc73-123">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="3cc73-124">**Документы (кроме вложений):** Количество свободных документов, которые являются сводными, уникальными рядом с дубликатами сводной таблицы или точной копией другого документа.</span><span class="sxs-lookup"><span data-stu-id="3cc73-124">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="3cc73-125">**Сообщения электронной почты:** Количество включенных в список сообщений электронной почты включительно, включительные копии, включительно, или ни один из указанных выше вариантов.</span><span class="sxs-lookup"><span data-stu-id="3cc73-125">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="3cc73-126">**Вложения:** Количество вложений электронной почты, которые уникальны или дублируют другое вложение электронной почты в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="3cc73-126">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="3cc73-127">**Количество файлов по типу:** Количество файлов, определяемое по расширению файла.</span><span class="sxs-lookup"><span data-stu-id="3cc73-127">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="3cc73-128">**Документы по источнику:** Сводка контента по исходному источнику данных.</span><span class="sxs-lookup"><span data-stu-id="3cc73-128">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="3cc73-129">**Документы, собранные по процессу:** Сводка по контенту с помощью процедуры Set.</span><span class="sxs-lookup"><span data-stu-id="3cc73-129">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
