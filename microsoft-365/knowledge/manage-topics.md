---
title: Управление темами в центре тем в Microsoft Viva Topics
description: Управление темами в центре тем.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: ba8f27c90f9c84729a10f461e85b2e1441b49549
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625405"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="410bc-103">Управление темами в центре тем в Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="410bc-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="410bc-104">В центре тем Viva Topics диспетчер знаний может просмотреть страницу Управление темами, чтобы просмотреть темы, которые были определены в исходных расположениях, указанные администратором знаний. </span><span class="sxs-lookup"><span data-stu-id="410bc-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Центр тем](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="410bc-106">Этапы темы</span><span class="sxs-lookup"><span data-stu-id="410bc-106">Topic stages</span></span>

<span data-ttu-id="410bc-107">Менеджеры знаний помогают направлять обнаруженные темы на различных этапах жизненного цикла тем: **Предложенные,** **Подтвержденные,** **Опубликованные** и **Удалены**.</span><span class="sxs-lookup"><span data-stu-id="410bc-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Диаграмма жизненного цикла темы](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="410bc-109">**Рекомендуемые**. Тема определена с помощью ИИ и содержит достаточно вспомогательных ресурсов, связей и свойств.</span><span class="sxs-lookup"><span data-stu-id="410bc-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="410bc-110">(Они помечены как **рекомендуемая тема** в пользовательском интерфейсе.)</span><span class="sxs-lookup"><span data-stu-id="410bc-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="410bc-111">**Подтверждено.** Тема, обнаруженная ИИ и проверенная.</span><span class="sxs-lookup"><span data-stu-id="410bc-111">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="410bc-112">Проверка темы возникает, когда либо:</span><span class="sxs-lookup"><span data-stu-id="410bc-112">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="410bc-113">Руководитель знаний подтверждает тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-113">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="410bc-114">Руководитель знаний [подтверждает тему на](manage-topics.md#confirmed-topics) странице Управление **темами.**</span><span class="sxs-lookup"><span data-stu-id="410bc-114">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="410bc-115">Несколько пользователей подтверждают тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-115">Multiple users confirm a topic.</span></span> <span data-ttu-id="410bc-116">Должна быть сеть из двух положительных голосов, полученных от пользователей, голосовавших с помощью механизма обратной связи на карточке темы.</span><span class="sxs-lookup"><span data-stu-id="410bc-116">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="410bc-117">Например, если один пользователь голосовал положительно, а один — отрицательный для определенной темы, для подтверждения этой темы по-прежнему потребуется еще два положительных голоса.</span><span class="sxs-lookup"><span data-stu-id="410bc-117">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="410bc-118">**Опубликовано.** Тема, которая была куратором.</span><span class="sxs-lookup"><span data-stu-id="410bc-118">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="410bc-119">Вручную были сделаны изменения, чтобы улучшить его качество, или он был создан пользователем.</span><span class="sxs-lookup"><span data-stu-id="410bc-119">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="410bc-120">**Удалено.** Тема, которая была отклонена и больше не будет видна для зрителей.</span><span class="sxs-lookup"><span data-stu-id="410bc-120">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="410bc-121">Тема может быть удалена в любом состоянии (предложено, подтверждено или опубликовано).</span><span class="sxs-lookup"><span data-stu-id="410bc-121">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="410bc-122">Удаление темы происходит, когда либо:</span><span class="sxs-lookup"><span data-stu-id="410bc-122">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="410bc-123">Менеджер знаний удаляет тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-123">A knowledge manager removes a topic.</span></span> <span data-ttu-id="410bc-124">Менеджер знаний удаляет тему на странице **Управление темами.**</span><span class="sxs-lookup"><span data-stu-id="410bc-124">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="410bc-125">Несколько пользователей отдали отрицательные голоса с помощью механизма обратной связи на карточке темы.</span><span class="sxs-lookup"><span data-stu-id="410bc-125">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="410bc-126">Для удаления темы должна быть сеть из двух отрицательных голосов, полученных от пользователей.</span><span class="sxs-lookup"><span data-stu-id="410bc-126">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="410bc-127">Например, если один пользователь голосовал отрицательно, а один — положительно для определенной темы, для удаления темы по-прежнему потребуется еще два отрицательных голоса.</span><span class="sxs-lookup"><span data-stu-id="410bc-127">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="410bc-128">После удаления опубликованной темы страницу с кураторами необходимо удалять вручную через Библиотеку страниц центра темы.</span><span class="sxs-lookup"><span data-stu-id="410bc-128">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="410bc-129">На странице **Управление темами** каждый менеджер знаний сможет видеть только те темы, в которых у них есть доступ к файлам и страницам, связанным с этой темой.</span><span class="sxs-lookup"><span data-stu-id="410bc-129">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="410bc-130">Это обрезка разрешений будет отражена в списке тем, которые отображаются в предлагаемых, подтвержденных,  **опубликованных** и **удаленных вкладок.**</span><span class="sxs-lookup"><span data-stu-id="410bc-130">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="410bc-131">Тем не менее в этой теме учитываются общие числа в организации независимо от разрешений.</span><span class="sxs-lookup"><span data-stu-id="410bc-131">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="410bc-132">Requirements</span><span class="sxs-lookup"><span data-stu-id="410bc-132">Requirements</span></span>

<span data-ttu-id="410bc-133">Чтобы управлять темами в центре тем, необходимо:</span><span class="sxs-lookup"><span data-stu-id="410bc-133">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="410bc-134">лицензия на Viva Темы;</span><span class="sxs-lookup"><span data-stu-id="410bc-134">Have a Viva Topics license.</span></span>

- <span data-ttu-id="410bc-135">Чтобы Кто [**можно управлять разрешениями на темы.**](./topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="410bc-135">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="410bc-136">Администраторы баз знаний могут предоставлять пользователям такие разрешения в разделе параметров разрешений Viva Темы.</span><span class="sxs-lookup"><span data-stu-id="410bc-136">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="410bc-137">Вы не сможете просматривать страницу **Управление** темами в центре тем, если у вас нет Кто для управления **темами.**</span><span class="sxs-lookup"><span data-stu-id="410bc-137">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="410bc-138">В центре тем руководитель знаний может просмотреть темы, которые были определены в указанных вами исходных расположениях, и подтвердить или удалить их.</span><span class="sxs-lookup"><span data-stu-id="410bc-138">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="410bc-139">Менеджер знаний также может создавать и публиковать новые страницы темы, если они не были найдены в обнаружении темы, или изменить существующие, если они нуждаются в обновлении.</span><span class="sxs-lookup"><span data-stu-id="410bc-139">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="410bc-140">Обзор предложенных тем</span><span class="sxs-lookup"><span data-stu-id="410bc-140">Review suggested topics</span></span>

<span data-ttu-id="410bc-141">На странице **Управление темами** на вкладке Рекомендуемые будут перечислены темы, обнаруженные в указанных SharePoint **исходных расположениях.** При необходимости руководитель знаний может просмотреть неподтвержденные темы и выбрать, чтобы подтвердить или удалить их.</span><span class="sxs-lookup"><span data-stu-id="410bc-141">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Предлагаемые темы](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="410bc-143">Чтобы просмотреть предложенную тему:</span><span class="sxs-lookup"><span data-stu-id="410bc-143">To review a suggested topic:</span></span>

1. <span data-ttu-id="410bc-144">На странице **Управление темами** выберите вкладку **Рекомендуемые,** а затем выберите тему, чтобы открыть страницу темы.</span><span class="sxs-lookup"><span data-stu-id="410bc-144">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="410bc-145">На странице темы просмотрите страницу темы и выберите **Изменить,** если необходимо внести какие-либо изменения на страницу.</span><span class="sxs-lookup"><span data-stu-id="410bc-145">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="410bc-146">Публикация любых изменений переместит эту тему на вкладку **Published.**</span><span class="sxs-lookup"><span data-stu-id="410bc-146">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="410bc-147">После просмотра темы перейдите на страницу **Управление темами.**</span><span class="sxs-lookup"><span data-stu-id="410bc-147">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="410bc-148">Для выбранной темы можно:</span><span class="sxs-lookup"><span data-stu-id="410bc-148">For the selected topic, you can:</span></span>

   - <span data-ttu-id="410bc-149">Выберите контрольный знак, чтобы подтвердить тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-149">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="410bc-150">Выберите **x,** если вы хотите удалить тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-150">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="410bc-151">Подтвержденные темы будут удалены из списка **Рекомендуемые** и теперь будут отображаться в **списке Подтвержденный.**</span><span class="sxs-lookup"><span data-stu-id="410bc-151">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="410bc-152">Удаляемые темы будут удалены из списка **Рекомендуемые** и теперь будут отображаться на вкладке **Removed.**</span><span class="sxs-lookup"><span data-stu-id="410bc-152">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="410bc-153">Оценка качества</span><span class="sxs-lookup"><span data-stu-id="410bc-153">Quality score</span></span>

<span data-ttu-id="410bc-154">Каждая тема, которая отображается на странице **Предлагаемые** темы, имеет оценку качества, назначенную ему.</span><span class="sxs-lookup"><span data-stu-id="410bc-154">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="410bc-155">Оценка качества отражает объем сведений, которые средний пользователь увидит для сведений по этой теме, с учетом того, что каждый пользователь может видеть более или менее сведения из-за разрешений, которые они могут иметь или не иметь на информацию в этой теме.</span><span class="sxs-lookup"><span data-stu-id="410bc-155">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="410bc-156">Оценка качества может помочь получить представление о темах с наибольшей информацией и может быть полезна для поиска тем, которые могут быть изменены вручную.</span><span class="sxs-lookup"><span data-stu-id="410bc-156">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="410bc-157">Например, тема с более низким показателем качества может быть результатом того, что некоторые пользователи не SharePoint разрешений на доступ к файлам или сайтам, включенным ВИ в эту тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-157">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="410bc-158">После этого участник может изменить тему, включив в нее сведения (при необходимости), доступные для просмотра всем пользователям, которые могут видеть эту тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-158">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="410bc-159">Просмотры</span><span class="sxs-lookup"><span data-stu-id="410bc-159">Impressions</span></span>

<span data-ttu-id="410bc-160">Столбец **Impressions** отображает количество раз, когда тема отображается конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="410bc-160">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="410bc-161">Это включает представления через карточки ответов на темы в поиске и через основные темы.</span><span class="sxs-lookup"><span data-stu-id="410bc-161">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="410bc-162">Это не отражает щелчок по этим темам, но что тема была отображна.</span><span class="sxs-lookup"><span data-stu-id="410bc-162">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="410bc-163">Столбец **"Впечатления"** будет показываться для тем на странице  "Рекомендуемые, подтвержденные, опубликованные и удалены" на странице Управление **темами.** </span><span class="sxs-lookup"><span data-stu-id="410bc-163">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="410bc-164">Подтвержденные темы</span><span class="sxs-lookup"><span data-stu-id="410bc-164">Confirmed topics</span></span>

<span data-ttu-id="410bc-165">На  странице Управление темами темы, обнаруженные в заданных SharePoint исходных расположениях и подтвержденные менеджером знаний или "crowdsourced", подтвержденные чистыми двумя или более людьми (балансировки отрицательных голосов пользователей с положительными голосами пользователей) с помощью механизма обратной связи с картами, будут перечислены на вкладке **Confirmed.** При необходимости пользователь с разрешениями на управление темами может просмотреть подтвержденные темы и отклонить их.</span><span class="sxs-lookup"><span data-stu-id="410bc-165">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="410bc-166">Чтобы просмотреть подтвержденную тему:</span><span class="sxs-lookup"><span data-stu-id="410bc-166">To review a confirmed topic:</span></span>

1. <span data-ttu-id="410bc-167">На вкладке **Подтверждено** выберите тему, чтобы открыть ее страницу.</span><span class="sxs-lookup"><span data-stu-id="410bc-167">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="410bc-168">На странице темы просмотрите страницу темы и выберите **Изменить,** если необходимо внести какие-либо изменения на страницу.</span><span class="sxs-lookup"><span data-stu-id="410bc-168">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="410bc-169">Обратите внимание, что вы по-прежнему можете отказаться от подтвержденной темы.</span><span class="sxs-lookup"><span data-stu-id="410bc-169">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="410bc-170">Для этого перейдите к выбранной теме на вкладке **Подтвержденный** и выберите **x,** если вы хотите отклонить эту тему.</span><span class="sxs-lookup"><span data-stu-id="410bc-170">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="410bc-171">Опубликованные темы</span><span class="sxs-lookup"><span data-stu-id="410bc-171">Published topics</span></span>

<span data-ttu-id="410bc-172">Опубликованные темы были отредактированы таким образом, чтобы конкретные сведения всегда появлялись у тех, кто сталкивается со страницей.</span><span class="sxs-lookup"><span data-stu-id="410bc-172">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="410bc-173">Здесь также перечислены темы, созданные вручную.</span><span class="sxs-lookup"><span data-stu-id="410bc-173">Manually created topics are listed here as well.</span></span>

   ![Управление темами](../media/knowledge-management/manage-topics-new.png)
