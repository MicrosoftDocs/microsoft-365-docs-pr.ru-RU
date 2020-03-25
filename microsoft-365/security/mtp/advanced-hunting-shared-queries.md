---
title: Использование общих запросов в расширенной охоте службы защиты от угроз (Майкрософт)
description: Быстро начинайте охоту на угрозы с помощью готовых и общих запросов. Делитесь своими запросами с людьми или со своей организацией.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, репозиторий GitHub, мои запросы, общие запросы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 38eb3c39c5473d0a729b12771b61e965dbc81931
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929484"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="ab8ca-105">Использование общих запросов в расширенной охоте</span><span class="sxs-lookup"><span data-stu-id="ab8ca-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="ab8ca-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ab8ca-106">**Applies to:**</span></span>
- <span data-ttu-id="ab8ca-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ab8ca-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="ab8ca-108">Запросами [расширенной охоты](advanced-hunting-overview.md) можно делиться с пользователями одной организации.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="ab8ca-109">Вы также можете найти общедоступные запросы в GitHub.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="ab8ca-110">Эти запросы позволяют быстро реализовывать сценарии охоты на угрозы, не создавая запросы с нуля.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Изображение общих запросов](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="ab8ca-112">Сохранение и изменение запроса и предоставление к нему общего доступа</span><span class="sxs-lookup"><span data-stu-id="ab8ca-112">Save, modify, and share a query</span></span>
<span data-ttu-id="ab8ca-113">Вы можете сохранить новый или существующий запрос, чтобы он был доступен только вам, или поделиться им с пользователями своей организации.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="ab8ca-114">Создание или изменение запроса</span><span class="sxs-lookup"><span data-stu-id="ab8ca-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="ab8ca-115">Нажмите разворачивающуюся кнопку **Сохранить запрос** и выберите параметр **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="ab8ca-116">Введите имя запроса.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-116">Enter a name for the query.</span></span> 

   ![Изображение сохранения запроса](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="ab8ca-118">Выберите папку, в которую нужно сохранить запрос.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="ab8ca-119">**Общие запросы** — общие для всех пользователей вашей организации</span><span class="sxs-lookup"><span data-stu-id="ab8ca-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="ab8ca-120">**Мои запросы** — доступны только для вас</span><span class="sxs-lookup"><span data-stu-id="ab8ca-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="ab8ca-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="ab8ca-122">Удаление или переименование запроса</span><span class="sxs-lookup"><span data-stu-id="ab8ca-122">Delete or rename a query</span></span>
1. <span data-ttu-id="ab8ca-123">Щелкните правой кнопкой мыши запрос, который нужно переименовать или удалить.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-123">Right-click on a query you want to rename or delete.</span></span>

    ![Изображение удаления запроса](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="ab8ca-125">Нажмите кнопку **Удалить** и подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="ab8ca-126">Или нажмите кнопку **Переименовать** и введите новое имя запроса.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="ab8ca-127">Доступ к запросам в репозитории GitHub</span><span class="sxs-lookup"><span data-stu-id="ab8ca-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="ab8ca-128">Исследователи безопасности Майкрософт часто делятся запросами расширенной охоты в [специальном общедоступном репозитории в GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="ab8ca-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="ab8ca-129">Этот репозиторий открыт для участия.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-129">This repository is open to contributions.</span></span> <span data-ttu-id="ab8ca-130">Чтобы внести свой вклад, [бесплатно присоединяйтесь к GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="ab8ca-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="ab8ca-131">Исследователи безопасности Майкрософт также предоставляют запросы расширенной охоты, которые можно использовать для обнаружения действий и индикаторов, связанных с возникающими угрозами.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="ab8ca-132">Эти запросы предоставляются в рамках отчетов [аналитики угроз](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) в Центре безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ab8ca-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab8ca-133">См. также</span><span class="sxs-lookup"><span data-stu-id="ab8ca-133">Related topics</span></span>
- [<span data-ttu-id="ab8ca-134">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ab8ca-134">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ab8ca-135">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="ab8ca-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ab8ca-136">Работать с результатами запроса</span><span class="sxs-lookup"><span data-stu-id="ab8ca-136">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ab8ca-137">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="ab8ca-137">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ab8ca-138">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ab8ca-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ab8ca-139">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="ab8ca-139">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
