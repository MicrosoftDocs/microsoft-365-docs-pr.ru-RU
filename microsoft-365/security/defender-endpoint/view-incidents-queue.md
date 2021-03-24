---
title: Просмотр и организация очереди Инциденты
ms.reviewer: ''
description: См. список инцидентов и узнайте, как применять фильтры для ограничения списка и получения более сфокусированного представления.
keywords: просмотр, организация, инциденты, совокупность, расследования, очередь, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f25189ac6550d9c3349e08f7e7ac685d4b8031fc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071773"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="7bbf3-104">Просмотр и организация очереди Microsoft Defender для инцидентов конечной точки</span><span class="sxs-lookup"><span data-stu-id="7bbf3-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7bbf3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7bbf3-105">**Applies to:**</span></span>
- [<span data-ttu-id="7bbf3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7bbf3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7bbf3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bbf3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7bbf3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7bbf3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7bbf3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="7bbf3-110">Очередь **Инциденты показывает** коллекцию инцидентов, которые были помечены с устройств в сети.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="7bbf3-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="7bbf3-112">По умолчанию в очереди отображаются инциденты, замеченные за последние 30 дней, а последний инцидент отображается в верхней части списка, что помогает сначала увидеть последние инциденты.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="7bbf3-113">Существует несколько вариантов настройки представления очереди Incidents.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="7bbf3-114">В верхней части навигации можно:</span><span class="sxs-lookup"><span data-stu-id="7bbf3-114">On the top navigation you can:</span></span>
- <span data-ttu-id="7bbf3-115">Настройка столбцов для добавления или удаления столбцов</span><span class="sxs-lookup"><span data-stu-id="7bbf3-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="7bbf3-116">Изменение количества элементов для просмотра на странице</span><span class="sxs-lookup"><span data-stu-id="7bbf3-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="7bbf3-117">Выберите элементы, которые будут показываться на странице</span><span class="sxs-lookup"><span data-stu-id="7bbf3-117">Select the items to show per page</span></span>
- <span data-ttu-id="7bbf3-118">Пакетный выбор инцидентов для назначения</span><span class="sxs-lookup"><span data-stu-id="7bbf3-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="7bbf3-119">Перемещение между страницами</span><span class="sxs-lookup"><span data-stu-id="7bbf3-119">Navigate between pages</span></span>
- <span data-ttu-id="7bbf3-120">Применение фильтров</span><span class="sxs-lookup"><span data-stu-id="7bbf3-120">Apply filters</span></span>

![Изображение очереди инцидентов](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="7bbf3-122">Сортировка и фильтрация очереди инцидентов</span><span class="sxs-lookup"><span data-stu-id="7bbf3-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="7bbf3-123">Вы можете применить следующие фильтры, чтобы ограничить список инцидентов и получить более целенаправленное представление.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="7bbf3-124">Severity</span><span class="sxs-lookup"><span data-stu-id="7bbf3-124">Severity</span></span>

<span data-ttu-id="7bbf3-125">Серьезность инцидента</span><span class="sxs-lookup"><span data-stu-id="7bbf3-125">Incident severity</span></span> | <span data-ttu-id="7bbf3-126">Описание</span><span class="sxs-lookup"><span data-stu-id="7bbf3-126">Description</span></span>
:---|:---
<span data-ttu-id="7bbf3-127">Высокий</span><span class="sxs-lookup"><span data-stu-id="7bbf3-127">High</span></span> </br><span data-ttu-id="7bbf3-128">(Красный)</span><span class="sxs-lookup"><span data-stu-id="7bbf3-128">(Red)</span></span> | <span data-ttu-id="7bbf3-129">Угрозы, часто связанные с расширенными постоянными угрозами (APT).</span><span class="sxs-lookup"><span data-stu-id="7bbf3-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="7bbf3-130">Эти инциденты указывают на высокий риск из-за серьезности ущерба, который они могут нанести устройствам.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="7bbf3-131">Средний</span><span class="sxs-lookup"><span data-stu-id="7bbf3-131">Medium</span></span> </br><span data-ttu-id="7bbf3-132">(Оранжевый)</span><span class="sxs-lookup"><span data-stu-id="7bbf3-132">(Orange)</span></span> | <span data-ttu-id="7bbf3-133">В организации редко наблюдаются угрозы, такие как аномальное изменение реестра, выполнение подозрительных файлов и наблюдаемые действия, характерные для стадий атаки.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="7bbf3-134">Низкий</span><span class="sxs-lookup"><span data-stu-id="7bbf3-134">Low</span></span> </br><span data-ttu-id="7bbf3-135">(Желтый)</span><span class="sxs-lookup"><span data-stu-id="7bbf3-135">(Yellow)</span></span> | <span data-ttu-id="7bbf3-136">Угрозы, связанные с распространенными вредоносными программами и средствами взлома, которые не обязательно указывают на передовую угрозу, направленную на организацию.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="7bbf3-137">Информационная</span><span class="sxs-lookup"><span data-stu-id="7bbf3-137">Informational</span></span> </br><span data-ttu-id="7bbf3-138">(Серый)</span><span class="sxs-lookup"><span data-stu-id="7bbf3-138">(Grey)</span></span> | <span data-ttu-id="7bbf3-139">Информационные инциденты не могут считаться вредными для сети, но могут быть хорошими для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="7bbf3-140">Кому назначено</span><span class="sxs-lookup"><span data-stu-id="7bbf3-140">Assigned to</span></span>
<span data-ttu-id="7bbf3-141">Вы можете отфильтровать список, выбрав по назначению кому-либо или выбрав те, которые назначены вам.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="7bbf3-142">Category</span><span class="sxs-lookup"><span data-stu-id="7bbf3-142">Category</span></span>
<span data-ttu-id="7bbf3-143">Инциденты классифицируются в зависимости от описания стадии, на которой находится цепочка убийств в области кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="7bbf3-144">Это представление помогает аналитику угроз определить приоритет, срочность и соответствующую стратегию реагирования для развертывания на основе контекста.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="7bbf3-145">Состояние</span><span class="sxs-lookup"><span data-stu-id="7bbf3-145">Status</span></span>
<span data-ttu-id="7bbf3-146">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="7bbf3-147">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="7bbf3-147">Data sensitivity</span></span>
<span data-ttu-id="7bbf3-148">Этот фильтр используется для демонстрации инцидентов, содержащих метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="7bbf3-149">Имя инцидента</span><span class="sxs-lookup"><span data-stu-id="7bbf3-149">Incident naming</span></span>

<span data-ttu-id="7bbf3-150">Чтобы сразу понять область инцидента, имена инцидентов автоматически создаются на основе атрибутов оповещений, таких как количество затронутых конечных точек, пострадавших пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="7bbf3-151">Например: *многоэтапный инцидент на нескольких конечных точках, сообщаемой несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="7bbf3-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="7bbf3-152">Инциденты, существовающие до начала автоматического именования инцидентов, будут сохранять свое имя.</span><span class="sxs-lookup"><span data-stu-id="7bbf3-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="7bbf3-153">См. также</span><span class="sxs-lookup"><span data-stu-id="7bbf3-153">See also</span></span>
- [<span data-ttu-id="7bbf3-154">Очередь инцидентов</span><span class="sxs-lookup"><span data-stu-id="7bbf3-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="7bbf3-155">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="7bbf3-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="7bbf3-156">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="7bbf3-156">Investigate incidents</span></span>](investigate-incidents.md)

