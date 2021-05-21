---
title: Управление инцидентами в Microsoft 365 Defender
description: Узнайте, как назначать, обновлять статус,
keywords: инциденты, инциденты, анализ, ответ, оповещения, сопоставленные оповещения, назначение, обновление, состояние, управление, классификация, Microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594158"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="ae03b-104">Управление инцидентами в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae03b-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ae03b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ae03b-105">**Applies to:**</span></span>
- <span data-ttu-id="ae03b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae03b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ae03b-107">Управление инцидентами имеет решающее значение для обеспечения сдерживания и решения угроз.</span><span class="sxs-lookup"><span data-stu-id="ae03b-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="ae03b-108">Вы управляете инцидентами из & оповещений > **инцидентов** при быстром запуске центра Microsoft 365 безопасности [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ae03b-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="ae03b-109">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="ae03b-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Пример очереди инцидента":::

<span data-ttu-id="ae03b-111">Вот способы, которыми можно управлять своими инцидентами:</span><span class="sxs-lookup"><span data-stu-id="ae03b-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="ae03b-112">Изменение имени инцидента</span><span class="sxs-lookup"><span data-stu-id="ae03b-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="ae03b-113">Добавление тегов инцидента</span><span class="sxs-lookup"><span data-stu-id="ae03b-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="ae03b-114">Назначьте инцидент самому себе</span><span class="sxs-lookup"><span data-stu-id="ae03b-114">Assign the incident to yourself</span></span>](#assign-incidents)
- [<span data-ttu-id="ae03b-115">Их устранение</span><span class="sxs-lookup"><span data-stu-id="ae03b-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="ae03b-116">Настройка классификации и определения</span><span class="sxs-lookup"><span data-stu-id="ae03b-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="ae03b-117">Добавление примечаний</span><span class="sxs-lookup"><span data-stu-id="ae03b-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="ae03b-118">Вы можете управлять инцидентами из области **Управление** инцидентами для инцидента.</span><span class="sxs-lookup"><span data-stu-id="ae03b-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="ae03b-119">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="ae03b-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Пример области управления инцидентом инцидента":::

<span data-ttu-id="ae03b-121">Эту области можно отобразить в ссылке **Управление инцидентами** по ссылке:</span><span class="sxs-lookup"><span data-stu-id="ae03b-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="ae03b-122">Области свойств инцидента в очереди инцидента.</span><span class="sxs-lookup"><span data-stu-id="ae03b-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="ae03b-123">**Сводная** страница инцидента.</span><span class="sxs-lookup"><span data-stu-id="ae03b-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="ae03b-124">В случаях, когда необходимо переместить оповещения из одного инцидента в другой, вы также можете сделать это со вкладки **Alerts,** создав таким образом больший или меньший инцидент, который включает все соответствующие оповещения.</span><span class="sxs-lookup"><span data-stu-id="ae03b-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="ae03b-125">Изменение имени инцидента</span><span class="sxs-lookup"><span data-stu-id="ae03b-125">Edit the incident name</span></span>

<span data-ttu-id="ae03b-126">Microsoft 365 Defender автоматически назначает имя на основе атрибутов оповещений, таких как количество затронутых конечных точек, затронутых пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="ae03b-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="ae03b-127">Это позволяет быстро понять масштаб инцидента.</span><span class="sxs-lookup"><span data-stu-id="ae03b-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="ae03b-128">Например: *многоэтапный инцидент на нескольких конечных точках, сообщаемой несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="ae03b-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="ae03b-129">Имя инцидента можно изменить в поле **Имя** инцидента на области **Управление инцидентами.**</span><span class="sxs-lookup"><span data-stu-id="ae03b-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="ae03b-130">Инциденты, существовающие до выкатки функции автоматического именования инцидентов, сохраняют свое имя.</span><span class="sxs-lookup"><span data-stu-id="ae03b-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="ae03b-131">Добавление тегов инцидента</span><span class="sxs-lookup"><span data-stu-id="ae03b-131">Add incident tags</span></span>

<span data-ttu-id="ae03b-132">К инциденту можно добавить настраиваемые теги, например для флага группы инцидентов с общей характеристикой.</span><span class="sxs-lookup"><span data-stu-id="ae03b-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="ae03b-133">Позже можно отфильтровать очередь инцидентов для всех инцидентов, содержащих определенный тег.</span><span class="sxs-lookup"><span data-stu-id="ae03b-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="ae03b-134">Когда вы начинаете печатать, у вас есть возможность выбрать из списка выбранных тегов.</span><span class="sxs-lookup"><span data-stu-id="ae03b-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="ae03b-135">Назначение инцидентов</span><span class="sxs-lookup"><span data-stu-id="ae03b-135">Assign incidents</span></span>

<span data-ttu-id="ae03b-136">Чтобы назначить инцидент, выберите **Назначение для меня**.</span><span class="sxs-lookup"><span data-stu-id="ae03b-136">To assign an incident, select **Assign to me**.</span></span> <span data-ttu-id="ae03b-137">При этом назначается право собственности на инцидент и все оповещения, связанные с ним, на учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae03b-137">Doing so assigns ownership of the incident and all the alerts associated with it to your user account.</span></span>

<span data-ttu-id="ae03b-138">Вы можете получить список инцидентов, назначенного вам, фильтруя очередь инцидента.</span><span class="sxs-lookup"><span data-stu-id="ae03b-138">You can get a list of incidents assigned to you by filtering the incident queue.</span></span> 

1. <span data-ttu-id="ae03b-139">Из очереди инцидента выберите **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="ae03b-139">From the incident queue, select **Filters**.</span></span>
2. <span data-ttu-id="ae03b-140">в разделе **Назначение инцидента,** очистить **Выберите все** и выберите **назначенное мне**.</span><span class="sxs-lookup"><span data-stu-id="ae03b-140">in the **Incident assignment** section, clear **Select all** and select **Assigned to me**.</span></span>
3. <span data-ttu-id="ae03b-141">Выберите **Применить,** а затем закрыть области **Фильтры.**</span><span class="sxs-lookup"><span data-stu-id="ae03b-141">Select **Apply**, and then close the **Filters** pane.</span></span>

<span data-ttu-id="ae03b-142">Затем вы можете сохранить в браузере в качестве закладки соответствующий URL-адрес, чтобы быстро увидеть список инцидентов, назначенного вам.</span><span class="sxs-lookup"><span data-stu-id="ae03b-142">You can then save the resulting URL in your browser as a bookmark to quickly see the list of incidents assigned to you.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="ae03b-143">Устранение инцидента</span><span class="sxs-lookup"><span data-stu-id="ae03b-143">Resolve an incident</span></span>

<span data-ttu-id="ae03b-144">Если инцидент был исправлен, выберите  разрешить инцидент, чтобы переместить перегной вправо.</span><span class="sxs-lookup"><span data-stu-id="ae03b-144">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="ae03b-145">Обратите внимание, что устранение инцидента также устраняет все связанные и активные оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="ae03b-145">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="ae03b-146">Инцидент, который не разрешен, отображается как **Active**.</span><span class="sxs-lookup"><span data-stu-id="ae03b-146">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="ae03b-147">Настройка классификации и определения</span><span class="sxs-lookup"><span data-stu-id="ae03b-147">Set the classification and determination</span></span>

<span data-ttu-id="ae03b-148">Классификация инцидентов — это истинное оповещение или ложное оповещение, которое настраивается из поля **Классификация.**</span><span class="sxs-lookup"><span data-stu-id="ae03b-148">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="ae03b-149">Если это было настоящее оповещение, необходимо также указать тип угрозы с **полем Определения.**</span><span class="sxs-lookup"><span data-stu-id="ae03b-149">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="ae03b-150">Указание типа угрозы помогает группе безопасности видеть шаблоны угроз и защищать организацию от них.</span><span class="sxs-lookup"><span data-stu-id="ae03b-150">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="ae03b-151">Добавление примечаний</span><span class="sxs-lookup"><span data-stu-id="ae03b-151">Add comments</span></span>

<span data-ttu-id="ae03b-152">Вы можете добавить несколько комментариев к инциденту с **полем Комментарий.**</span><span class="sxs-lookup"><span data-stu-id="ae03b-152">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="ae03b-153">Каждый комментарий добавляется к историческим событиям инцидента.</span><span class="sxs-lookup"><span data-stu-id="ae03b-153">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="ae03b-154">Комментарии и история инцидента см. в разделе **Комментарии** и история на странице **Сводка.**</span><span class="sxs-lookup"><span data-stu-id="ae03b-154">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae03b-155">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ae03b-155">Next steps</span></span>

<span data-ttu-id="ae03b-156">Для новых инцидентов, начните [свое расследование](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="ae03b-156">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="ae03b-157">В случае инцидентов в процессе продолжайте [расследование.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="ae03b-157">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="ae03b-158">Для разрешения инцидентов выполните [проверку после инцидента.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="ae03b-158">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae03b-159">См. также</span><span class="sxs-lookup"><span data-stu-id="ae03b-159">See also</span></span>

- [<span data-ttu-id="ae03b-160">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="ae03b-160">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ae03b-161">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="ae03b-161">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ae03b-162">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="ae03b-162">Investigate incidents</span></span>](investigate-incidents.md)
