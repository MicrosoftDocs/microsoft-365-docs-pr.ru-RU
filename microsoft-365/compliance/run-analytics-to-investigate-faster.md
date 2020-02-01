---
title: Запуск аналитики для ускорения исследования
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
ms.openlocfilehash: 0631754fc7003f0c562b4551649b9622030ac45a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601586"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="f5eca-102">Запуск аналитики для ускорения исследования</span><span class="sxs-lookup"><span data-stu-id="f5eca-102">Run analytics to investigate faster</span></span>

<span data-ttu-id="f5eca-103">Если коллекция свидетельств велика, ее может быть трудно Просмотреть все.</span><span class="sxs-lookup"><span data-stu-id="f5eca-103">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="f5eca-104">Набор свидетельств часто включает несколько копий одинаковых или похожих сообщений электронной почты или документов.</span><span class="sxs-lookup"><span data-stu-id="f5eca-104">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="f5eca-105">Анализ данных (Предварительная версия) предоставляет ряд средств анализа, которые помогут вам уменьшить объем документов, которые необходимо проанализировать без потери данных.</span><span class="sxs-lookup"><span data-stu-id="f5eca-105">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="f5eca-106">Чтобы узнать больше об этих возможностях, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="f5eca-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="f5eca-107">Обнаружение схожих документов (почти дубликатов)</span><span class="sxs-lookup"><span data-stu-id="f5eca-107">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="f5eca-108">Потоки почты</span><span class="sxs-lookup"><span data-stu-id="f5eca-108">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="f5eca-109">Темы</span><span class="sxs-lookup"><span data-stu-id="f5eca-109">Themes</span></span>](themes.md)

<span data-ttu-id="f5eca-110">Анализ данных в наборе свидетельств:</span><span class="sxs-lookup"><span data-stu-id="f5eca-110">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="f5eca-111">Настройка параметров аналитики для расследования.</span><span class="sxs-lookup"><span data-stu-id="f5eca-111">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="f5eca-112">Дополнительную информацию можно узнать в статье [Настройка параметров поиска и аналитики](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f5eca-112">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="f5eca-113">Откройте набор свидетельств.</span><span class="sxs-lookup"><span data-stu-id="f5eca-113">Open the evidence set.</span></span>

3. <span data-ttu-id="f5eca-114">Щелкните **Управление доказательством**.</span><span class="sxs-lookup"><span data-stu-id="f5eca-114">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="f5eca-115">В разделе **аналитика**щелкните **анализ**.</span><span class="sxs-lookup"><span data-stu-id="f5eca-115">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="f5eca-116">Вы можете проверить ход выполнения анализа на вкладке **задания** в расследовании.</span><span class="sxs-lookup"><span data-stu-id="f5eca-116">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="f5eca-117">Активируемый тип задания называется " **выполнение аналитики**".</span><span class="sxs-lookup"><span data-stu-id="f5eca-117">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="f5eca-118">После завершения анализа можно просмотреть список точных дубликатов или почти дубликатов документа, который вы просматриваете на панели справа.</span><span class="sxs-lookup"><span data-stu-id="f5eca-118">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="f5eca-119">Чтобы выбрать все дубликаты просматриваемого документа, это можно сделать с помощью этой панели.</span><span class="sxs-lookup"><span data-stu-id="f5eca-119">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="f5eca-120">Чтобы узнать больше о других возможностях на этой панели, ознакомьтесь со статьей [Просмотр данных в доказательстве](review-data-in-evidence.md).</span><span class="sxs-lookup"><span data-stu-id="f5eca-120">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="f5eca-121">Кроме того, вы можете выполнять дополнительные запросы в пределах доказательств, используя выходные данные анализа, такие как темы.</span><span class="sxs-lookup"><span data-stu-id="f5eca-121">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="f5eca-122">Дополнительные сведения см. [в статье Query Data в доказательстве](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="f5eca-122">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="f5eca-123">Аналитический отчет</span><span class="sxs-lookup"><span data-stu-id="f5eca-123">Analytics report</span></span>

<span data-ttu-id="f5eca-124">Чтобы просмотреть отчет аналитики для вашего доказательства:</span><span class="sxs-lookup"><span data-stu-id="f5eca-124">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="f5eca-125">Откройте набор свидетельств.</span><span class="sxs-lookup"><span data-stu-id="f5eca-125">Open the evidence set.</span></span>

2. <span data-ttu-id="f5eca-126">Щелкните **Управление доказательством**.</span><span class="sxs-lookup"><span data-stu-id="f5eca-126">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="f5eca-127">В разделе **аналитика**щелкните **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="f5eca-127">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="f5eca-128">Отчет содержит четыре компонента из анализа:</span><span class="sxs-lookup"><span data-stu-id="f5eca-128">The report has four components from analysis:</span></span>

- <span data-ttu-id="f5eca-129">**Подразделение** — количество необработанных электронных писем, вложений и документов, найденных в наборе свидетельств.</span><span class="sxs-lookup"><span data-stu-id="f5eca-129">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="f5eca-130">**Сообщения электронной почты** — количество включенных в еамил сообщений, включая минусы, включительные копии или ни один из вышеперечисленных элементов.</span><span class="sxs-lookup"><span data-stu-id="f5eca-130">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="f5eca-131">Включительно: Последнее сообщение в цепочке сообщений электронной почты, содержащее все предыдущие истории и требующее проверки.</span><span class="sxs-lookup"><span data-stu-id="f5eca-131">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="f5eca-132">Инклюзивные минусы: сообщение в потоке, содержащее одно или несколько вложений, требующих проверки.</span><span class="sxs-lookup"><span data-stu-id="f5eca-132">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="f5eca-133">Инклюзивные копии: сообщение, которое является копией другого инклюзивного или инклюзивного сообщения минуса (тема и текст).</span><span class="sxs-lookup"><span data-stu-id="f5eca-133">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="f5eca-134">**Вложения** — количество вложений электронной почты, которые уникальны или дублируют другое вложение электронной почты в одном и том же свидетельстве.</span><span class="sxs-lookup"><span data-stu-id="f5eca-134">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="f5eca-135">**Документы (за исключением вложений электронной почты)** — количество уникальных документов, для которых требуется проверка, например наиболее репрезентативный документ из почти-повторяющегося набора или точный дубликат другого документа).</span><span class="sxs-lookup"><span data-stu-id="f5eca-135">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>