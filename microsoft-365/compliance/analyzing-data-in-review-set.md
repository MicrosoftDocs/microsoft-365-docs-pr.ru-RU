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
ms.openlocfilehash: fbc2ad99433e2bf296e2891b6f3e85e22b6af6df
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079936"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="6839a-102">Анализ данных в наборе анализа в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6839a-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="6839a-103">При большом количестве собранных документов может быть трудно Просмотреть все.</span><span class="sxs-lookup"><span data-stu-id="6839a-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="6839a-104">Расширенное обнаружение электронных данных предоставляет ряд средств для анализа документов, чтобы сократить объем документов, проверяемых без потерь данных, и помочь организовать документы единообразно.</span><span class="sxs-lookup"><span data-stu-id="6839a-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="6839a-105">Чтобы узнать больше об этих возможностях, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="6839a-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="6839a-106">Обнаружение схожих документов (почти дубликатов)</span><span class="sxs-lookup"><span data-stu-id="6839a-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="6839a-107">Потоки почты</span><span class="sxs-lookup"><span data-stu-id="6839a-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="6839a-108">Темы</span><span class="sxs-lookup"><span data-stu-id="6839a-108">Themes</span></span>](themes.md)

<span data-ttu-id="6839a-109">Анализ данных в наборе проверки:</span><span class="sxs-lookup"><span data-stu-id="6839a-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="6839a-110">Настройте параметры аналитики для своего случая.</span><span class="sxs-lookup"><span data-stu-id="6839a-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="6839a-111">Дополнительную информацию можно узнать в статье [Настройка параметров поиска и аналитики](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6839a-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="6839a-112">Откройте набор проверок, который необходимо проанализировать.</span><span class="sxs-lookup"><span data-stu-id="6839a-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="6839a-113">Щелкните **Управление набором проверки**.</span><span class="sxs-lookup"><span data-stu-id="6839a-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="6839a-114">Щелкните **запустить аналитику для набора проверки**.</span><span class="sxs-lookup"><span data-stu-id="6839a-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="6839a-115">На вкладке **задания** можно проверить ход выполнения анализа.</span><span class="sxs-lookup"><span data-stu-id="6839a-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="6839a-116">После завершения анализа можно просмотреть аналитический отчет, запустить запросы в наборе рецензирования для результатов анализа (см. [запрос в наборе проверки](review-set-search.md)), а также связанные документы определенного документа (см. [Обзор данных в наборе проверки](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="6839a-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="6839a-117">Аналитический отчет</span><span class="sxs-lookup"><span data-stu-id="6839a-117">Analytics report</span></span>

<span data-ttu-id="6839a-118">Чтобы просмотреть аналитический отчет для набора проверки:</span><span class="sxs-lookup"><span data-stu-id="6839a-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="6839a-119">Откройте набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="6839a-119">Open the review set.</span></span>

2. <span data-ttu-id="6839a-120">Щелкните **Управление набором проверки**.</span><span class="sxs-lookup"><span data-stu-id="6839a-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="6839a-121">Нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="6839a-121">Click **View report**.</span></span>

<span data-ttu-id="6839a-122">Отчет содержит четыре компонента из анализа:</span><span class="sxs-lookup"><span data-stu-id="6839a-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="6839a-123">**Разбивка** — количество сообщений электронной почты, вложений и свободных документов, обнаруженных в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="6839a-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="6839a-124">**Документы (за исключением вложений)** — сколько свободных документов было сведено, уникально возле дубликатов сводной таблицы или точной копии другого документа.</span><span class="sxs-lookup"><span data-stu-id="6839a-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="6839a-125">**Сообщения** электронной почты — сколько сообщений электронной почты было инклюзивным, включительно — включительно или ни один из вышеперечисленных элементов.</span><span class="sxs-lookup"><span data-stu-id="6839a-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="6839a-126">**Вложения** — сколько вложений электронной почты было уникальным или дублировать другое вложение в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="6839a-126">**Attachments** - How many email attachments were unique or duplicates of another email attachment in the review set.</span></span>
