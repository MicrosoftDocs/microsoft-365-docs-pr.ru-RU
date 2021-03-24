---
title: Управление инцидентами ATP защитника Майкрософт
description: Управление инцидентами путем назначения, обновления состояния или настройки классификации.
keywords: инциденты, управление, назначение, состояние, классификация, истинное оповещение, ложное оповещение
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 412938e506895aaabfa0796cb1d46ea892876435
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070190"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="f3b87-104">Управление microsoft Defender для инцидентов конечной точки</span><span class="sxs-lookup"><span data-stu-id="f3b87-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f3b87-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f3b87-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3b87-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f3b87-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f3b87-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3b87-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f3b87-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f3b87-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3b87-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f3b87-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f3b87-110">Управление инцидентами является важной частью каждой операции по кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="f3b87-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="f3b87-111">Вы можете управлять инцидентами, выбрав инцидент из очереди **Инциденты** или области управления **инцидентами.**</span><span class="sxs-lookup"><span data-stu-id="f3b87-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="f3b87-112">Выбор инцидента из очереди **Инциденты**  приводит к области управления инцидентами, где можно открыть страницу инцидента для дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="f3b87-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Изображение области управления инцидентами](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="f3b87-114">Вы можете назначить инциденты себе, изменить состояние и классификацию, переименовать или прокомментировать их, чтобы отслеживать их ход.</span><span class="sxs-lookup"><span data-stu-id="f3b87-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="f3b87-115">Для дополнительной видимости с первого взгляда имена инцидентов автоматически создаются на основе атрибутов оповещений, таких как количество затронутых конечных точек, пострадавших пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="f3b87-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="f3b87-116">Это позволяет быстро понять масштаб инцидента.</span><span class="sxs-lookup"><span data-stu-id="f3b87-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="f3b87-117">Например: *многоэтапный инцидент на нескольких конечных точках, сообщаемой несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="f3b87-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="f3b87-118">Инциденты, существовающие до начала автоматического именования инцидентов, будут сохранять их имена.</span><span class="sxs-lookup"><span data-stu-id="f3b87-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Изображение страницы с подробными данными об инциденте](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="f3b87-120">Назначение инцидентов</span><span class="sxs-lookup"><span data-stu-id="f3b87-120">Assign incidents</span></span>
<span data-ttu-id="f3b87-121">Если инцидент еще не назначен, вы  можете назначить мне назначение инцидента самому.</span><span class="sxs-lookup"><span data-stu-id="f3b87-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="f3b87-122">При этом передается не только владение инцидентом, но и все связанные с ним оповещения.</span><span class="sxs-lookup"><span data-stu-id="f3b87-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="f3b87-123">Установка статуса и классификации</span><span class="sxs-lookup"><span data-stu-id="f3b87-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="f3b87-124">Статус инцидента</span><span class="sxs-lookup"><span data-stu-id="f3b87-124">Incident status</span></span>
<span data-ttu-id="f3b87-125">Инциденты можно распределять по категориям (например, **Активно** или **Устранено**), изменяя его статус в ходе расследования.</span><span class="sxs-lookup"><span data-stu-id="f3b87-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="f3b87-126">Это помогает организовать обработку инцидентов вашей группой и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="f3b87-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="f3b87-127">Например, аналитик SoC может просмотреть срочные инциденты **Active** за день и назначить их себе для расследования.</span><span class="sxs-lookup"><span data-stu-id="f3b87-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="f3b87-128">Кроме того, аналитик SoC может установить, что инцидент **устранен,** если инцидент был исправлен.</span><span class="sxs-lookup"><span data-stu-id="f3b87-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="f3b87-129">Классификация</span><span class="sxs-lookup"><span data-stu-id="f3b87-129">Classification</span></span>
<span data-ttu-id="f3b87-130">Можно не задавать классификацию, а также указать, будет ли инцидент истинным или ложным.</span><span class="sxs-lookup"><span data-stu-id="f3b87-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="f3b87-131">Это поможет заметить закономерности в инцидентах и изучить их.</span><span class="sxs-lookup"><span data-stu-id="f3b87-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="f3b87-132">Добавление примечаний</span><span class="sxs-lookup"><span data-stu-id="f3b87-132">Add comments</span></span>
<span data-ttu-id="f3b87-133">К инциденту можно добавить комментарии, а также просмотреть историю связанных с ним событий, чтобы узнать об изменениях, ранее внесенных в него.</span><span class="sxs-lookup"><span data-stu-id="f3b87-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="f3b87-134">Каждое изменение или комментарий к оповещению записывается в раздел комментариев и журнал.</span><span class="sxs-lookup"><span data-stu-id="f3b87-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="f3b87-135">Добавленные комментарии сразу же появляются в соответствующей области.</span><span class="sxs-lookup"><span data-stu-id="f3b87-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="f3b87-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f3b87-136">Related topics</span></span>
- [<span data-ttu-id="f3b87-137">Очередь инцидентов</span><span class="sxs-lookup"><span data-stu-id="f3b87-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="f3b87-138">Просмотр и организация очереди Инциденты</span><span class="sxs-lookup"><span data-stu-id="f3b87-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="f3b87-139">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="f3b87-139">Investigate incidents</span></span>](investigate-incidents.md)
