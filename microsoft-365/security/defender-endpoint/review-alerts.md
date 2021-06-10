---
title: Просмотр оповещений в Microsoft Defender для конечной точки
description: Просмотрите сведения об оповещении, в том числе визуализированную историю оповещения и сведения для каждого шага цепочки.
keywords: инциденты, инциденты, машины, устройства, пользователи, оповещений, оповещений, расследования, графа, доказательств
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844026"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="63f3e-104">Просмотр оповещений в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="63f3e-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="63f3e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="63f3e-105">**Applies to:**</span></span>
- [<span data-ttu-id="63f3e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="63f3e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="63f3e-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="63f3e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="63f3e-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="63f3e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="63f3e-109">Страница оповещений в Microsoft Defender для конечной точки обеспечивает полный контекст оповещения, объединяя сигналы атаки и оповещения, связанные с выбранным оповещением, для создания подробной истории оповещения.</span><span class="sxs-lookup"><span data-stu-id="63f3e-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="63f3e-110">Быстрое изучение, исследование и эффективное действие оповещений, влияющих на организацию.</span><span class="sxs-lookup"><span data-stu-id="63f3e-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="63f3e-111">Понять, почему они были вызваны, и их влияние из одного расположения.</span><span class="sxs-lookup"><span data-stu-id="63f3e-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="63f3e-112">Дополнительные сведения в этом обзоре.</span><span class="sxs-lookup"><span data-stu-id="63f3e-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="63f3e-113">Начало работы с оповещением</span><span class="sxs-lookup"><span data-stu-id="63f3e-113">Getting started with an alert</span></span>

<span data-ttu-id="63f3e-114">Выбор имени оповещений в Защитнике для конечной точки высадит вас на его странице оповещений.</span><span class="sxs-lookup"><span data-stu-id="63f3e-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="63f3e-115">На странице оповещения вся информация будет показана в контексте выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="63f3e-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="63f3e-116">Каждая страница оповещения состоит из 4 разделов:</span><span class="sxs-lookup"><span data-stu-id="63f3e-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="63f3e-117">**В заголовке** оповещений указывается имя оповещений, которое напоминает о том, какое предупреждение началось ваше текущее расследование независимо от выбранного на странице.</span><span class="sxs-lookup"><span data-stu-id="63f3e-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="63f3e-118">[**Затронутые активы**](#review-affected-assets) перечисляют карточки устройств и пользователей, затронутых этим оповещением, которые можно щелкнуть для получения дополнительных сведений и действий.</span><span class="sxs-lookup"><span data-stu-id="63f3e-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="63f3e-119">В **истории оповещений** отображаются все объекты, связанные с оповещением, связанные представлением дерева.</span><span class="sxs-lookup"><span data-stu-id="63f3e-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="63f3e-120">Оповещение в заголовке будет в центре внимания при первой посадке на выбранной странице оповещения.</span><span class="sxs-lookup"><span data-stu-id="63f3e-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="63f3e-121">Сущностями в истории оповещения являются расширяемыми и щелкаемыми, чтобы предоставить дополнительные сведения и ускорить ответ, позволяя вам принимать меры прямо в контексте страницы оповещения.</span><span class="sxs-lookup"><span data-stu-id="63f3e-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="63f3e-122">Используйте историю оповещений, чтобы начать расследование.</span><span class="sxs-lookup"><span data-stu-id="63f3e-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="63f3e-123">Узнайте, как исследовать [оповещения в Microsoft Defender для конечной точки.](/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="63f3e-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="63f3e-124">На **области сведений** сначала покажутся сведения об выбранном оповещении с подробными сведениями и действиями, связанными с этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="63f3e-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="63f3e-125">Если выбрать какой-либо из затронутых активов или сущностях в истории оповещений, области сведений изменятся, чтобы предоставить контекстную информацию и действия для выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="63f3e-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="63f3e-126">Обратите внимание на состояние обнаружения оповещений.</span><span class="sxs-lookup"><span data-stu-id="63f3e-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="63f3e-127">Предотвращено. Попытка подозрительных действий была предотвращена.</span><span class="sxs-lookup"><span data-stu-id="63f3e-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="63f3e-128">Например, файл не был написан на диск или выполнен.</span><span class="sxs-lookup"><span data-stu-id="63f3e-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="63f3e-129">![Страница оповещений, на которой отображается угроза, была предотвращена](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="63f3e-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="63f3e-130">Заблокировано — подозрительное поведение было выполнено, а затем заблокировано.</span><span class="sxs-lookup"><span data-stu-id="63f3e-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="63f3e-131">Например, был выполнен процесс, но поскольку впоследствии он выставил подозрительные действия, процесс был прекращен.</span><span class="sxs-lookup"><span data-stu-id="63f3e-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="63f3e-132">![Страница оповещений, показывающая угрозу, была заблокирована](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="63f3e-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="63f3e-133">Обнаружено. Обнаружена атака, которая, возможно, по-прежнему активна.</span><span class="sxs-lookup"><span data-stu-id="63f3e-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="63f3e-134">![Обнаружена страница оповещений с угрозой](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="63f3e-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="63f3e-135">Затем вы также  можете просмотреть сведения об автоматическом расследовании в области сведений оповещений, чтобы узнать, какие действия уже приняты, а также прочитать описание оповещений о рекомендуемых действиях.</span><span class="sxs-lookup"><span data-stu-id="63f3e-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![Фрагмент области сведений с описанием оповещений и разделами автоматического расследования](images/alert-air-and-alert-description.png)

<span data-ttu-id="63f3e-137">Другие сведения, доступные в области сведений при открываемом оповещении, включают методы MITRE, исходные и дополнительные контекстные сведения.</span><span class="sxs-lookup"><span data-stu-id="63f3e-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="63f3e-138">Просмотр затронутых активов</span><span class="sxs-lookup"><span data-stu-id="63f3e-138">Review affected assets</span></span>

<span data-ttu-id="63f3e-139">Выбор устройства или карточки пользователя в разделах с затронутыми активами переключается на сведения об устройстве или пользователе в области сведений.</span><span class="sxs-lookup"><span data-stu-id="63f3e-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="63f3e-140">**Для устройств** область данных будет отображать сведения о самом устройстве, например домене, операционной системе и IP.</span><span class="sxs-lookup"><span data-stu-id="63f3e-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="63f3e-141">Также доступны активные оповещений и зарегистрированные на этом устройстве пользователи.</span><span class="sxs-lookup"><span data-stu-id="63f3e-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="63f3e-142">Вы можете принять незамедлительных действий, изолировать устройство, ограничить выполнение приложения или запуск антивирусного сканирования.</span><span class="sxs-lookup"><span data-stu-id="63f3e-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="63f3e-143">Кроме того, можно собрать пакет исследований, инициировать автоматическое расследование или перейти на страницу устройства для изучения с точки зрения устройства.</span><span class="sxs-lookup"><span data-stu-id="63f3e-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![Фрагмент области сведений при выборе устройства](images/device-page-details.png)

- <span data-ttu-id="63f3e-145">**Для пользователей** в области сведений будут отображаться подробные сведения о пользователе, такие как имя пользователя SAM и SID, а также типы логотипов, выполняемые этим пользователем, а также любые оповещения и инциденты, связанные с ним.</span><span class="sxs-lookup"><span data-stu-id="63f3e-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="63f3e-146">Чтобы продолжить исследование с точки зрения этого пользователя, можно выбрать страницу *Open* user.</span><span class="sxs-lookup"><span data-stu-id="63f3e-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![Фрагмент области сведений при выборе пользователя](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="63f3e-148">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="63f3e-148">Related topics</span></span>

- [<span data-ttu-id="63f3e-149">Просмотр и организация очереди инцидентов</span><span class="sxs-lookup"><span data-stu-id="63f3e-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="63f3e-150">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="63f3e-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="63f3e-151">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="63f3e-151">Manage incidents</span></span>](manage-incidents.md)
