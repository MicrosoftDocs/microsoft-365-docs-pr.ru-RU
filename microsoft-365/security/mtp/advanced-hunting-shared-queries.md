---
title: Использование общих запросов в расширенной охоте службы защиты от угроз (Майкрософт)
description: Быстро начинайте охоту на угрозы с помощью готовых и общих запросов. Делитесь своими запросами с людьми или со своей организацией.
keywords: расширенная охота, охота на угрозы, охота на киберугрозы, поиск, запрос, телеметрия, пользовательские обнаружения, схема, kusto, репозиторий github, мои запросы, общие запросы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bd92bde39f56180a79490a24b78ee3824cc262e7
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911516"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="26ba7-105">Использование общих запросов в расширенной охоте</span><span class="sxs-lookup"><span data-stu-id="26ba7-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="26ba7-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="26ba7-106">**Applies to:**</span></span>
- <span data-ttu-id="26ba7-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="26ba7-107">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="26ba7-108">Запросами [расширенной охоты](advanced-hunting-overview.md) можно делиться с пользователями одной организации.</span><span class="sxs-lookup"><span data-stu-id="26ba7-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="26ba7-109">Вы также можете найти общедоступные запросы в GitHub.</span><span class="sxs-lookup"><span data-stu-id="26ba7-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="26ba7-110">Эти запросы позволяют быстро реализовывать сценарии охоты на угрозы, не создавая запросы с нуля.</span><span class="sxs-lookup"><span data-stu-id="26ba7-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Изображение общих запросов](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="26ba7-112">Сохранение и изменение запроса и предоставление к нему общего доступа</span><span class="sxs-lookup"><span data-stu-id="26ba7-112">Save, modify, and share a query</span></span>
<span data-ttu-id="26ba7-113">Вы можете сохранить новый или существующий запрос, чтобы он был доступен только вам, или поделиться им с пользователями своей организации.</span><span class="sxs-lookup"><span data-stu-id="26ba7-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="26ba7-114">Создание или изменение запроса</span><span class="sxs-lookup"><span data-stu-id="26ba7-114">Create or modify a lookup table</span></span> 

2. <span data-ttu-id="26ba7-115">Нажмите разворачивающуюся кнопку **Сохранить запрос** и выберите параметр **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="26ba7-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="26ba7-116">Введите имя запроса.</span><span class="sxs-lookup"><span data-stu-id="26ba7-116">Enter a name for the title.</span></span> 

   ![Изображение сохранения запроса](../images/advanced-hunting-save-query.png)

4. <span data-ttu-id="26ba7-118">Выберите папку, в которую нужно сохранить запрос.</span><span class="sxs-lookup"><span data-stu-id="26ba7-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="26ba7-119">**Общие запросы** — общие для всех пользователей вашей организации</span><span class="sxs-lookup"><span data-stu-id="26ba7-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="26ba7-120">**Мои запросы** — доступны только для вас</span><span class="sxs-lookup"><span data-stu-id="26ba7-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="26ba7-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="26ba7-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="26ba7-122">Удаление или переименование запроса</span><span class="sxs-lookup"><span data-stu-id="26ba7-122">Delete or rename a query</span></span>
1. <span data-ttu-id="26ba7-123">Щелкните правой кнопкой мыши запрос, который нужно переименовать или удалить.</span><span class="sxs-lookup"><span data-stu-id="26ba7-123">Right-click on a query you want to rename or delete.</span></span>

    ![Изображение удаления запроса](../images/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="26ba7-125">Нажмите кнопку **Удалить** и подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="26ba7-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="26ba7-126">Или нажмите кнопку **Переименовать** и введите новое имя запроса.</span><span class="sxs-lookup"><span data-stu-id="26ba7-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="26ba7-127">Доступ к запросам в репозитории GitHub</span><span class="sxs-lookup"><span data-stu-id="26ba7-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="26ba7-128">Исследователи безопасности Майкрософт часто делятся запросами расширенной охоты в [специальном общедоступном репозитории в GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="26ba7-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="26ba7-129">Этот репозиторий открыт для участия.</span><span class="sxs-lookup"><span data-stu-id="26ba7-129">This repository is open to contributions.</span></span> <span data-ttu-id="26ba7-130">Чтобы внести свой вклад, [бесплатно присоединяйтесь к GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="26ba7-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="26ba7-131">Исследователи безопасности Майкрософт также предоставляют запросы расширенной охоты, которые можно использовать для обнаружения действий и индикаторов, связанных с возникающими угрозами.</span><span class="sxs-lookup"><span data-stu-id="26ba7-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="26ba7-132">Эти запросы предоставляются в рамках отчетов [аналитики угроз](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) в Центре безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="26ba7-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26ba7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="26ba7-133">Related topics</span></span>
- [<span data-ttu-id="26ba7-134">Профилактическая охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="26ba7-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="26ba7-135">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="26ba7-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="26ba7-136">Охота на угрозы в электронной почте и устройствах</span><span class="sxs-lookup"><span data-stu-id="26ba7-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="26ba7-137">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="26ba7-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="26ba7-138">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="26ba7-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)