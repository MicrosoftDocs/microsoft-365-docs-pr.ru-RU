---
title: 'Управление темами в центре тем в разделе "Опыт работы с разделами" (предварительная версия) '
description: Управление темами в Центре тем.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 832067d157ed9ffcba1ed9ad514c375cbbdd752b
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699031"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="d05f2-103">Управление темами в Центре тем (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="d05f2-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d05f2-104">Содержимое этой статьи для Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="d05f2-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d05f2-105">[Узнайте больше о работе с Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="d05f2-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="d05f2-106">В Центре знаний менеджер по  анализу может просмотреть страницу "Управление темами", чтобы просмотреть разделы, выявленные в расположениях источников SharePoint, указанные вашим администратором знаний.</span><span class="sxs-lookup"><span data-stu-id="d05f2-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Центр тем](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="d05f2-108">Менеджеры по знаниям помогают направлять обнаруженные темы по жизненному циклу тем, в которых данная тема:</span><span class="sxs-lookup"><span data-stu-id="d05f2-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="d05f2-109">Рекомендуемый: тема определена ИИ и имеет достаточно вспомогательных ресурсов, подключений и свойств для удовлетворения порогового значения темы.</span><span class="sxs-lookup"><span data-stu-id="d05f2-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="d05f2-110">Подтверждено: проверена тема, предложенная ИИ.</span><span class="sxs-lookup"><span data-stu-id="d05f2-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="d05f2-111">Проверка делается путем подтверждения от администратора знаний. Кроме того, раздел может быть подтвержден, если хотя бы два пользователя дают положительный отзыв о том, что этот раздел является допустимым.</span><span class="sxs-lookup"><span data-stu-id="d05f2-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="d05f2-112">Удалено: тема отклоняется администратором знаний и больше не будет видна для посетителей.</span><span class="sxs-lookup"><span data-stu-id="d05f2-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="d05f2-113">Тема может быть в любом состоянии при удалении (предлагается или подтверждается).</span><span class="sxs-lookup"><span data-stu-id="d05f2-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="d05f2-114">Опубликовано: подтвержденный раздел, который был обновлен вручную.</span><span class="sxs-lookup"><span data-stu-id="d05f2-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Диаграмма жизненного цикла темы](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="d05f2-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d05f2-116">Requirements</span></span>

<span data-ttu-id="d05f2-117">Для управления темами в Центре тем необходимо:</span><span class="sxs-lookup"><span data-stu-id="d05f2-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="d05f2-118">Лицензия "Опыт работы с разделами".</span><span class="sxs-lookup"><span data-stu-id="d05f2-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="d05f2-119">У вас есть разрешения на [**управление темами.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)</span><span class="sxs-lookup"><span data-stu-id="d05f2-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="d05f2-120">Администраторы знаний могут предоставить пользователям это разрешение в параметрах разрешений раздела "Сеть знаний".</span><span class="sxs-lookup"><span data-stu-id="d05f2-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="d05f2-121">Вы не сможете просмотреть страницу "Управление разделами" в Центре тем, если у вас нет разрешения "Кто **может управлять темами".**</span><span class="sxs-lookup"><span data-stu-id="d05f2-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="d05f2-122">В центре тем менеджер по анализу может просмотреть разделы, указанные в указанных вами источниках SharePoint, и подтвердить или отклонить их.</span><span class="sxs-lookup"><span data-stu-id="d05f2-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="d05f2-123">Менеджер по знаниям также может создавать и публиковать новые страницы тем, если они не найдены в обнаружении тем, или редактировать существующие, если их нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="d05f2-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="d05f2-124">Обзор рекомендуемых разделов</span><span class="sxs-lookup"><span data-stu-id="d05f2-124">Review suggested topics</span></span>

<span data-ttu-id="d05f2-125">На странице "Управление разделами в центре тем" разделы, обнаруженные в указанных исходных расположениях SharePoint, будут перечислены на вкладке **"Рекомендуемые".** Менеджер по анализу может просмотреть неподтвержденные темы и подтвердить или отклонить их.</span><span class="sxs-lookup"><span data-stu-id="d05f2-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="d05f2-126">Чтобы просмотреть рекомендуемый раздел:</span><span class="sxs-lookup"><span data-stu-id="d05f2-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="d05f2-127">На странице **"Управление темами"** выберите **вкладку** "Предлагаемые", выберите раздел, чтобы открыть страницу темы.</span><span class="sxs-lookup"><span data-stu-id="d05f2-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="d05f2-128">На странице темы просмотрите страницу  темы и выберите "Изменить", если необходимо внести какие-либо изменения в страницу.</span><span class="sxs-lookup"><span data-stu-id="d05f2-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="d05f2-129">После просмотра этой темы снова перейдите на страницу "Управление темами".</span><span class="sxs-lookup"><span data-stu-id="d05f2-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="d05f2-130">Для выбранного раздела вы можете:</span><span class="sxs-lookup"><span data-stu-id="d05f2-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="d05f2-131">Чтобы подтвердить раздел, выберите этот контрольный знак.</span><span class="sxs-lookup"><span data-stu-id="d05f2-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="d05f2-132">Выберите **x,** если нужно отклонить раздел.</span><span class="sxs-lookup"><span data-stu-id="d05f2-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="d05f2-133">Подтвержденные разделы будут удалены из списка **"Предложенные"** и теперь отображаются в списке **"Подтверждено".**</span><span class="sxs-lookup"><span data-stu-id="d05f2-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="d05f2-134">Отклоненные темы будут удалены из списка **"Рекомендуемые"** и теперь отображаются на вкладке **"Удалено".**</span><span class="sxs-lookup"><span data-stu-id="d05f2-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="d05f2-135">Подтвержденные разделы</span><span class="sxs-lookup"><span data-stu-id="d05f2-135">Confirmed topics</span></span>

<span data-ttu-id="d05f2-136">На странице "Управление темами" на вкладке "Подтверждение" будут перечислены разделы, обнаруженные в указанных источниках SharePoint и подтвержденные менеджером по  знаниям или "крауд-источником", которые были подтверждены двумя или более людьми с помощью механизма обратной связи с карточкой. При необходимости пользователь с разрешениями на управление темами может просмотреть подтвержденные темы и отклонить их.</span><span class="sxs-lookup"><span data-stu-id="d05f2-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="d05f2-137">Чтобы просмотреть подтвержденный раздел:</span><span class="sxs-lookup"><span data-stu-id="d05f2-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="d05f2-138">На **вкладке "Подтверждено"** выберите раздел, чтобы открыть страницу темы.</span><span class="sxs-lookup"><span data-stu-id="d05f2-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="d05f2-139">На странице темы просмотрите страницу  темы и выберите "Изменить", если необходимо внести какие-либо изменения в страницу.</span><span class="sxs-lookup"><span data-stu-id="d05f2-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="d05f2-140">Обратите внимание, что вы по-прежнему можете отклонить подтвержденную тему.</span><span class="sxs-lookup"><span data-stu-id="d05f2-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="d05f2-141">Для этого перейдите к выбранному разделу в списке "Подтверждено" и выберите **x,** если нужно отклонить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="d05f2-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="d05f2-142">Опубликованные разделы</span><span class="sxs-lookup"><span data-stu-id="d05f2-142">Published topics</span></span>
<span data-ttu-id="d05f2-143">Опубликованные разделы были изменены таким образом, чтобы определенная информация всегда появлялась на странице.</span><span class="sxs-lookup"><span data-stu-id="d05f2-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="d05f2-144">Здесь перечислены разделы, созданные вручную.</span><span class="sxs-lookup"><span data-stu-id="d05f2-144">Manually created topics are listed here.</span></span>




