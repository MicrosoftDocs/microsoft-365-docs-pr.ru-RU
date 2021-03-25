---
title: Использование общих запросов в расширенной охоте
description: Быстро начинайте охоту на угрозы с помощью готовых и общих запросов. Делитесь своими запросами с людьми или со своей организацией.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, microsoft defender atp, поиск wdatp, запрос, телеметрия, пользовательские обнаружения, схема, kusto, github repo, мои запросы, общие запросы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075469"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="193c5-105">Использование общих запросов в расширенной охоте</span><span class="sxs-lookup"><span data-stu-id="193c5-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="193c5-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="193c5-106">**Applies to:**</span></span>
- [<span data-ttu-id="193c5-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="193c5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="193c5-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="193c5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="193c5-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="193c5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="193c5-110">Запросами [расширенной охоты](advanced-hunting-overview.md) можно делиться с пользователями одной организации.</span><span class="sxs-lookup"><span data-stu-id="193c5-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="193c5-111">Вы также можете найти общедоступные запросы в GitHub.</span><span class="sxs-lookup"><span data-stu-id="193c5-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="193c5-112">Эти запросы позволяют быстро реализовывать сценарии охоты на угрозы, не создавая запросы с нуля.</span><span class="sxs-lookup"><span data-stu-id="193c5-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Изображение общих запросов](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="193c5-114">Сохранение и изменение запроса и предоставление к нему общего доступа</span><span class="sxs-lookup"><span data-stu-id="193c5-114">Save, modify, and share a query</span></span>
<span data-ttu-id="193c5-115">Вы можете сохранить новый или существующий запрос, чтобы он был доступен только вам, или поделиться им с пользователями своей организации.</span><span class="sxs-lookup"><span data-stu-id="193c5-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="193c5-116">Введите новый запрос или загрузим существующий из **разделов Общие запросы** или **Мои запросы.**</span><span class="sxs-lookup"><span data-stu-id="193c5-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="193c5-117">Выберите **сохранить** **или сохранить как** из параметров сохранения.</span><span class="sxs-lookup"><span data-stu-id="193c5-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="193c5-118">Чтобы не переписать существующий запрос, выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="193c5-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="193c5-119">Введите имя запроса.</span><span class="sxs-lookup"><span data-stu-id="193c5-119">Enter a name for the query.</span></span>

   ![Изображение сохранения запроса](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="193c5-121">Выберите папку, в которую нужно сохранить запрос.</span><span class="sxs-lookup"><span data-stu-id="193c5-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="193c5-122">**Общие запросы** — общие для всех пользователей в вашей организации</span><span class="sxs-lookup"><span data-stu-id="193c5-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="193c5-123">**Мои запросы** — доступны только для вас</span><span class="sxs-lookup"><span data-stu-id="193c5-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="193c5-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="193c5-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="193c5-125">Удаление или переименование запроса</span><span class="sxs-lookup"><span data-stu-id="193c5-125">Delete or rename a query</span></span>
1. <span data-ttu-id="193c5-126">Щелкните правой кнопкой мыши запрос, который нужно переименовать или удалить.</span><span class="sxs-lookup"><span data-stu-id="193c5-126">Right-click on a query you want to rename or delete.</span></span>

    ![Изображение удаления запроса](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="193c5-128">Нажмите кнопку **Удалить** и подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="193c5-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="193c5-129">Или нажмите кнопку **Переименовать** и введите новое имя запроса.</span><span class="sxs-lookup"><span data-stu-id="193c5-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="193c5-130">Создание прямой ссылки на запрос</span><span class="sxs-lookup"><span data-stu-id="193c5-130">Create a direct link to a query</span></span>
<span data-ttu-id="193c5-131">Чтобы создать ссылку, открываемую запрос непосредственно в редакторе предварительного запроса охоты, завершите запрос и выберите **ссылку Share.**</span><span class="sxs-lookup"><span data-stu-id="193c5-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="193c5-132">Доступ к запросам в репозитории GitHub</span><span class="sxs-lookup"><span data-stu-id="193c5-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="193c5-133">Исследователи безопасности Майкрософт часто делятся запросами расширенной охоты в [специальном общедоступном репозитории в GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span><span class="sxs-lookup"><span data-stu-id="193c5-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="193c5-134">Этот репозиторий открыт для участия.</span><span class="sxs-lookup"><span data-stu-id="193c5-134">This repository is open to contributions.</span></span> <span data-ttu-id="193c5-135">Чтобы внести свой вклад, [бесплатно присоединяйтесь к GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="193c5-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="193c5-136">Исследователи безопасности Майкрософт также предоставляют запросы расширенной охоты, которые можно использовать для обнаружения действий и индикаторов, связанных с возникающими угрозами.</span><span class="sxs-lookup"><span data-stu-id="193c5-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="193c5-137">Эти запросы предоставляются в рамках отчетов [аналитики угроз](threat-analytics.md) в Центре безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="193c5-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="193c5-138">См. также</span><span class="sxs-lookup"><span data-stu-id="193c5-138">Related topics</span></span>
- [<span data-ttu-id="193c5-139">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="193c5-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="193c5-140">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="193c5-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="193c5-141">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="193c5-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="193c5-142">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="193c5-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="193c5-143">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="193c5-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="193c5-144">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="193c5-144">Custom detections overview</span></span>](overview-custom-detections.md)
