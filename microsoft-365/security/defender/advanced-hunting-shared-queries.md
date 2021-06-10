---
title: Использование общих запросов в Microsoft 365 defender advanced hunting
description: Быстро начинайте охоту на угрозы с помощью готовых и общих запросов. Делитесь своими запросами с людьми или со своей организацией.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, пользовательские обнаружения, схема, кусто, github repo, мои запросы, общие запросы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952588"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="8625d-105">Использование общих запросов в расширенной охоте</span><span class="sxs-lookup"><span data-stu-id="8625d-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8625d-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8625d-106">**Applies to:**</span></span>
- <span data-ttu-id="8625d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8625d-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="8625d-108">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8625d-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="8625d-109">Запросами [расширенной охоты](advanced-hunting-overview.md) можно делиться с пользователями одной организации.</span><span class="sxs-lookup"><span data-stu-id="8625d-109">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="8625d-110">Вы также можете найти общедоступные запросы в GitHub.</span><span class="sxs-lookup"><span data-stu-id="8625d-110">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="8625d-111">Эти запросы позволяют быстро реализовывать сценарии охоты на угрозы, не создавая запросы с нуля.</span><span class="sxs-lookup"><span data-stu-id="8625d-111">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Изображение общих запросов](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="8625d-113">Сохранение и изменение запроса и предоставление к нему общего доступа</span><span class="sxs-lookup"><span data-stu-id="8625d-113">Save, modify, and share a query</span></span>
<span data-ttu-id="8625d-114">Вы можете сохранить новый или существующий запрос, чтобы он был доступен только вам, или поделиться им с пользователями своей организации.</span><span class="sxs-lookup"><span data-stu-id="8625d-114">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="8625d-115">Создание или изменение запроса</span><span class="sxs-lookup"><span data-stu-id="8625d-115">Create or modify a query.</span></span> 

2. <span data-ttu-id="8625d-116">Нажмите разворачивающуюся кнопку **Сохранить запрос** и выберите параметр **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="8625d-116">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="8625d-117">Введите имя запроса.</span><span class="sxs-lookup"><span data-stu-id="8625d-117">Enter a name for the query.</span></span> 

   ![Изображение сохранения запроса](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="8625d-119">Выберите папку, в которую нужно сохранить запрос.</span><span class="sxs-lookup"><span data-stu-id="8625d-119">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="8625d-120">**Общие запросы** — общие для всех пользователей вашей организации</span><span class="sxs-lookup"><span data-stu-id="8625d-120">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="8625d-121">**Мои запросы** — доступны только для вас</span><span class="sxs-lookup"><span data-stu-id="8625d-121">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="8625d-122">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8625d-122">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="8625d-123">Удаление или переименование запроса</span><span class="sxs-lookup"><span data-stu-id="8625d-123">Delete or rename a query</span></span>
1. <span data-ttu-id="8625d-124">Щелкните правой кнопкой мыши запрос, который нужно переименовать или удалить.</span><span class="sxs-lookup"><span data-stu-id="8625d-124">Right-click on a query you want to rename or delete.</span></span>

    ![Изображение удаления запроса](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="8625d-126">Нажмите кнопку **Удалить** и подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="8625d-126">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="8625d-127">Или нажмите кнопку **Переименовать** и введите новое имя запроса.</span><span class="sxs-lookup"><span data-stu-id="8625d-127">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="8625d-128">Создание прямой ссылки на запрос</span><span class="sxs-lookup"><span data-stu-id="8625d-128">Create a direct link to a query</span></span>
<span data-ttu-id="8625d-129">Чтобы создать ссылку, открываемую запрос непосредственно в редакторе предварительного запроса охоты, завершите запрос и выберите **ссылку Share.**</span><span class="sxs-lookup"><span data-stu-id="8625d-129">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="8625d-130">Доступ к запросам в репозитории GitHub</span><span class="sxs-lookup"><span data-stu-id="8625d-130">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="8625d-131">Исследователи безопасности Майкрософт часто делятся запросами расширенной охоты в [специальном общедоступном репозитории в GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="8625d-131">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="8625d-132">Этот репозиторий открыт для участия.</span><span class="sxs-lookup"><span data-stu-id="8625d-132">This repository is open to contributions.</span></span> <span data-ttu-id="8625d-133">Чтобы внести свой вклад, [бесплатно присоединяйтесь к GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="8625d-133">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="8625d-134">Исследователи безопасности Майкрософт также предоставляют запросы расширенной охоты, которые можно использовать для обнаружения действий и индикаторов, связанных с возникающими угрозами.</span><span class="sxs-lookup"><span data-stu-id="8625d-134">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="8625d-135">Эти запросы предоставляются в рамках отчетов [аналитики угроз](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) в Центре безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8625d-135">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

>[!NOTE]
><span data-ttu-id="8625d-136">Некоторые таблицы в этой статье могут быть недоступны в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8625d-136">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8625d-137">[Включи Microsoft 365 Defender,](m365d-enable.md) чтобы искать угрозы с помощью дополнительных источников данных.</span><span class="sxs-lookup"><span data-stu-id="8625d-137">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="8625d-138">Вы можете переместить расширенные процессы охоты из Microsoft Defender для endpoint в Microsoft 365 Defender, следуя шагам в миграции расширенных запросов охоты из [Microsoft Defender для конечной точки](advanced-hunting-migrate-from-mde.md).</span><span class="sxs-lookup"><span data-stu-id="8625d-138">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8625d-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8625d-139">Related topics</span></span>
- [<span data-ttu-id="8625d-140">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="8625d-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8625d-141">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="8625d-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8625d-142">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="8625d-142">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8625d-143">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="8625d-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8625d-144">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="8625d-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8625d-145">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="8625d-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)