---
title: Использование общих запросов в microsoft 365 Defender advanced hunting
description: Быстро начинайте охоту на угрозы с помощью готовых и общих запросов. Делитесь своими запросами с людьми или со своей организацией.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, репо github, мои запросы, общие запросы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f153e438465d4cacf5293cd6e834e85783601c89
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069004"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="2321e-105">Использование общих запросов в расширенной охоте</span><span class="sxs-lookup"><span data-stu-id="2321e-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2321e-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2321e-106">**Applies to:**</span></span>
- <span data-ttu-id="2321e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2321e-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="2321e-108">Запросами [расширенной охоты](advanced-hunting-overview.md) можно делиться с пользователями одной организации.</span><span class="sxs-lookup"><span data-stu-id="2321e-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="2321e-109">Вы также можете найти общедоступные запросы в GitHub.</span><span class="sxs-lookup"><span data-stu-id="2321e-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="2321e-110">Эти запросы позволяют быстро реализовывать сценарии охоты на угрозы, не создавая запросы с нуля.</span><span class="sxs-lookup"><span data-stu-id="2321e-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Изображение общих запросов](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="2321e-112">Сохранение и изменение запроса и предоставление к нему общего доступа</span><span class="sxs-lookup"><span data-stu-id="2321e-112">Save, modify, and share a query</span></span>
<span data-ttu-id="2321e-113">Вы можете сохранить новый или существующий запрос, чтобы он был доступен только вам, или поделиться им с пользователями своей организации.</span><span class="sxs-lookup"><span data-stu-id="2321e-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="2321e-114">Создание или изменение запроса</span><span class="sxs-lookup"><span data-stu-id="2321e-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="2321e-115">Нажмите разворачивающуюся кнопку **Сохранить запрос** и выберите параметр **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="2321e-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="2321e-116">Введите имя запроса.</span><span class="sxs-lookup"><span data-stu-id="2321e-116">Enter a name for the query.</span></span> 

   ![Изображение сохранения запроса](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="2321e-118">Выберите папку, в которую нужно сохранить запрос.</span><span class="sxs-lookup"><span data-stu-id="2321e-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="2321e-119">**Общие запросы** — общие для всех пользователей вашей организации</span><span class="sxs-lookup"><span data-stu-id="2321e-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="2321e-120">**Мои запросы** — доступны только для вас</span><span class="sxs-lookup"><span data-stu-id="2321e-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="2321e-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2321e-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="2321e-122">Удаление или переименование запроса</span><span class="sxs-lookup"><span data-stu-id="2321e-122">Delete or rename a query</span></span>
1. <span data-ttu-id="2321e-123">Щелкните правой кнопкой мыши запрос, который нужно переименовать или удалить.</span><span class="sxs-lookup"><span data-stu-id="2321e-123">Right-click on a query you want to rename or delete.</span></span>

    ![Изображение удаления запроса](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="2321e-125">Нажмите кнопку **Удалить** и подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="2321e-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="2321e-126">Или нажмите кнопку **Переименовать** и введите новое имя запроса.</span><span class="sxs-lookup"><span data-stu-id="2321e-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="2321e-127">Создание прямой ссылки на запрос</span><span class="sxs-lookup"><span data-stu-id="2321e-127">Create a direct link to a query</span></span>
<span data-ttu-id="2321e-128">Чтобы создать ссылку, открываемую запрос непосредственно в редакторе предварительного запроса охоты, завершите запрос и выберите **ссылку Share.**</span><span class="sxs-lookup"><span data-stu-id="2321e-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="2321e-129">Доступ к запросам в репозитории GitHub</span><span class="sxs-lookup"><span data-stu-id="2321e-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="2321e-130">Исследователи безопасности Майкрософт часто делятся запросами расширенной охоты в [специальном общедоступном репозитории в GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="2321e-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="2321e-131">Этот репозиторий открыт для участия.</span><span class="sxs-lookup"><span data-stu-id="2321e-131">This repository is open to contributions.</span></span> <span data-ttu-id="2321e-132">Чтобы внести свой вклад, [бесплатно присоединяйтесь к GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="2321e-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="2321e-133">Исследователи безопасности Майкрософт также предоставляют запросы расширенной охоты, которые можно использовать для обнаружения действий и индикаторов, связанных с возникающими угрозами.</span><span class="sxs-lookup"><span data-stu-id="2321e-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="2321e-134">Эти запросы предоставляются в рамках отчетов [аналитики угроз](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) в Центре безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2321e-134">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2321e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2321e-135">Related topics</span></span>
- [<span data-ttu-id="2321e-136">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="2321e-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2321e-137">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="2321e-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2321e-138">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="2321e-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2321e-139">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="2321e-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2321e-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="2321e-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2321e-141">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="2321e-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)