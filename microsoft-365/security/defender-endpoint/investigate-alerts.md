---
title: Исследование оповещений Microsoft Defender для конечных точек
description: Используйте параметры исследования, чтобы получить сведения о оповещениях, влияющих на вашу сеть, что они означают и как их устранить.
keywords: исследование, исследование, устройства, устройство, очередь оповещений, панель мониторинга, IP-адрес, файл, отправка, отправка, глубокий анализ, хронология, поиск, домен, URL-адрес, IP
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 8b3b864e716957c24893d2097249440b0a90f10a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186105"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="1ba48-104">Исследование оповещений в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1ba48-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1ba48-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1ba48-105">**Applies to:**</span></span>
- [<span data-ttu-id="1ba48-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1ba48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1ba48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ba48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1ba48-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1ba48-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1ba48-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1ba48-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="1ba48-110">Изучите оповещения, влияющие на вашу сеть, поймите, что они означают, и как их устранить.</span><span class="sxs-lookup"><span data-stu-id="1ba48-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="1ba48-111">Выберите оповещение из очереди оповещений, чтобы перейти на страницу оповещения.</span><span class="sxs-lookup"><span data-stu-id="1ba48-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="1ba48-112">В этом представлении содержится название оповещения, затронутые активы, боковые области сведений и история оповещений.</span><span class="sxs-lookup"><span data-stu-id="1ba48-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="1ba48-113">На странице оповещение начните расследование с выбора затронутых активов или любых сущностями в представлении дерева истории оповещения.</span><span class="sxs-lookup"><span data-stu-id="1ba48-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="1ba48-114">Области данных автоматически заполняются дополнительными сведениями о выбранном.</span><span class="sxs-lookup"><span data-stu-id="1ba48-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="1ba48-115">Чтобы узнать, какие сведения можно просмотреть здесь, ознакомьтесь с оповещениями [Review в Microsoft Defender для конечной точки.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts)</span><span class="sxs-lookup"><span data-stu-id="1ba48-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="1ba48-116">Исследование с помощью истории оповещений</span><span class="sxs-lookup"><span data-stu-id="1ba48-116">Investigate using the alert story</span></span>

<span data-ttu-id="1ba48-117">В истории оповещений рассказывается о срабатывном оповещении, связанных событиях, которые произошли до и после, а также других связанных с ними сущностях.</span><span class="sxs-lookup"><span data-stu-id="1ba48-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="1ba48-118">Объекты являются щелкаемыми, и все объекты, которые не являются оповещением, расширяются с помощью значка расширения на правой стороне карты этого объекта.</span><span class="sxs-lookup"><span data-stu-id="1ba48-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="1ba48-119">Объект в фокусе будет указан синей полосой на левой стороне карточки этого объекта, а оповещение в заголовке сначала будет в центре внимания.</span><span class="sxs-lookup"><span data-stu-id="1ba48-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="1ba48-120">Расширь сущностями, чтобы просмотреть сведения с первого взгляда.</span><span class="sxs-lookup"><span data-stu-id="1ba48-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="1ba48-121">Выбор объекта переключит контекст области данных на эту сущность и позволит вам просмотреть дополнительные сведения, а также управлять этим объектом.</span><span class="sxs-lookup"><span data-stu-id="1ba48-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="1ba48-122">Выбор *...* справа от карточки сущности покажет все действия, доступные для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="1ba48-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="1ba48-123">Эти же действия отображаются в области сведений, когда объект находится в фокусе.</span><span class="sxs-lookup"><span data-stu-id="1ba48-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="1ba48-124">В разделе история оповещения может содержаться несколько оповещений, при этом дополнительные оповещения, связанные с одним деревом выполнения, отображаются до или после выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="1ba48-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Пример истории оповещений с оповещением в фокусе и расширенными картами](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="1ba48-126">Действие из области сведений</span><span class="sxs-lookup"><span data-stu-id="1ba48-126">Take action from the details pane</span></span>

<span data-ttu-id="1ba48-127">После выбора объекта, интересуемого, области сведений будут отображаться сведения о выбранном типе объекта, исторические сведения,  когда она доступна, и предлагают элементы управления для принятия действий по этому объекту непосредственно со страницы оповещения.</span><span class="sxs-lookup"><span data-stu-id="1ba48-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="1ba48-128">После того как вы закончили исследование, возвращайся к запущенной оповещению, пометив состояние оповещений как **Разрешено** и классифицировать его как false **alert** или **True alert**.</span><span class="sxs-lookup"><span data-stu-id="1ba48-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="1ba48-129">Классификация оповещений помогает настроить эту возможность, чтобы обеспечить более верные оповещения и меньше ложных оповещений.</span><span class="sxs-lookup"><span data-stu-id="1ba48-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="1ba48-130">Если классифицировать его как настоящее оповещение, можно также выбрать определение, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="1ba48-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Фрагмент области сведений с разрешенным оповещением и выпадательным определением расширен](images/alert-details-resolved-true.png)

<span data-ttu-id="1ba48-132">Если вы столкнулись с ложным оповещением с помощью бизнес-приложения, создайте правило подавления, чтобы избежать такого оповещения в будущем.</span><span class="sxs-lookup"><span data-stu-id="1ba48-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![действия и классификация в области сведений с выделенным правилом подавления](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="1ba48-134">Если у вас возникли проблемы, не описанные выше, используйте кнопку для предоставления отзывов 🙂 или открытия билета поддержки.</span><span class="sxs-lookup"><span data-stu-id="1ba48-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1ba48-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1ba48-135">Related topics</span></span>
- [<span data-ttu-id="1ba48-136">Просмотр и организация очереди оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="1ba48-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="1ba48-137">Управление оповещениями Защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="1ba48-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="1ba48-138">Исследование файла, связанного с предупреждением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ba48-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="1ba48-139">Исследование устройств в списке устройств Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="1ba48-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="1ba48-140">Исследование IP-адреса, связанного с оповещением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ba48-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="1ba48-141">Исследование домена, связанного с предупреждением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ba48-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="1ba48-142">Исследование учетной записи пользователя в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1ba48-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


