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
ms.openlocfilehash: 5705edcc4015460a8c6c5a2edc6ebf922dabbb2f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596156"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="c4820-102">Анализ данных в наборе анализа в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c4820-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="c4820-103">При большом количестве собранных документов может быть трудно Просмотреть все.</span><span class="sxs-lookup"><span data-stu-id="c4820-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="c4820-104">Расширенное обнаружение электронных данных предоставляет ряд средств для анализа документов, чтобы сократить объем документов, проверяемых без потерь данных, и помочь организовать документы единообразно.</span><span class="sxs-lookup"><span data-stu-id="c4820-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="c4820-105">Чтобы узнать больше об этих возможностях, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="c4820-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="c4820-106">Обнаружение схожих документов (почти дубликатов)</span><span class="sxs-lookup"><span data-stu-id="c4820-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="c4820-107">Потоки почты</span><span class="sxs-lookup"><span data-stu-id="c4820-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="c4820-108">Темы</span><span class="sxs-lookup"><span data-stu-id="c4820-108">Themes</span></span>](themes.md)

<span data-ttu-id="c4820-109">Анализ данных в наборе проверки:</span><span class="sxs-lookup"><span data-stu-id="c4820-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="c4820-110">Настройте параметры аналитики для своего случая.</span><span class="sxs-lookup"><span data-stu-id="c4820-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="c4820-111">Дополнительную информацию можно узнать в статье [Настройка параметров поиска и аналитики](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c4820-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="c4820-112">Откройте набор проверок, который необходимо проанализировать.</span><span class="sxs-lookup"><span data-stu-id="c4820-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="c4820-113">Щелкните **Управление набором проверки**.</span><span class="sxs-lookup"><span data-stu-id="c4820-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="c4820-114">Щелкните **запустить аналитику для набора проверки**.</span><span class="sxs-lookup"><span data-stu-id="c4820-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="c4820-115">На вкладке **задания** можно проверить ход выполнения анализа.</span><span class="sxs-lookup"><span data-stu-id="c4820-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="c4820-116">После завершения анализа можно просмотреть аналитический отчет, запустить запросы в наборе рецензирования для результатов анализа (см. [запрос в наборе проверки](review-set-search.md)), а также связанные документы определенного документа (см. [Обзор данных в наборе проверки](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="c4820-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="c4820-117">Аналитический отчет</span><span class="sxs-lookup"><span data-stu-id="c4820-117">Analytics report</span></span>

<span data-ttu-id="c4820-118">Чтобы просмотреть аналитический отчет для набора проверки:</span><span class="sxs-lookup"><span data-stu-id="c4820-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="c4820-119">Откройте набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="c4820-119">Open the review set.</span></span>

2. <span data-ttu-id="c4820-120">Щелкните **Управление набором проверки**.</span><span class="sxs-lookup"><span data-stu-id="c4820-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="c4820-121">Нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="c4820-121">Click **View report**.</span></span>

<span data-ttu-id="c4820-122">Отчет содержит четыре компонента из анализа:</span><span class="sxs-lookup"><span data-stu-id="c4820-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="c4820-123">**Разбивка** — количество сообщений электронной почты, вложений и свободных документов, обнаруженных в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="c4820-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="c4820-124">**Документы (за исключением вложений)** — сколько свободных документов было сведено, уникально возле дубликатов сводной таблицы или точной копии другого документа.</span><span class="sxs-lookup"><span data-stu-id="c4820-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="c4820-125">**Сообщения** электронной почты — сколько сообщений электронной почты было инклюзивным, включительно — включительно или ни один из вышеперечисленных элементов.</span><span class="sxs-lookup"><span data-stu-id="c4820-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="c4820-126">**Вложения** — сколько вложений электронной почты было уникальным или дублировать другое вложение в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="c4820-126">**Attachments** - How many email attachments were unique or duplicates of another email attachment in the review set.</span></span>