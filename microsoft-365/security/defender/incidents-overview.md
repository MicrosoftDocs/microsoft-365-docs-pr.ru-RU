---
title: Инциденты в Microsoft 365 Defender
description: Выясните, какие инциденты видно на других устройствах, у других пользователей и в почтовых ящиках.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
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
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861627"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="4c822-104">Инциденты в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c822-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4c822-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4c822-105">**Applies to:**</span></span>
- <span data-ttu-id="4c822-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c822-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="4c822-107">Хотите попробовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="4c822-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="4c822-108">Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или [запустить пилотный проект в производственной среде](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="4c822-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="4c822-109">Инцидент в Microsoft 365 Defender — это коллекция коррелирующих оповещений и связанных данных, которые составляют историю атаки.</span><span class="sxs-lookup"><span data-stu-id="4c822-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="4c822-110">Службы и приложения Microsoft 365 создают оповещения при обнаружении подозрительного или вредоносного события или действия.</span><span class="sxs-lookup"><span data-stu-id="4c822-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="4c822-111">Отдельные оповещения предоставляют ценные подсказки о завершенной или продолжающейся атаке.</span><span class="sxs-lookup"><span data-stu-id="4c822-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="4c822-112">Однако в атаках обычно используются различные методы для различных типов сущностями, например устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="4c822-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="4c822-113">Результатом является несколько оповещений для нескольких сущностями в клиенте.</span><span class="sxs-lookup"><span data-stu-id="4c822-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="4c822-114">Поскольку сведение отдельных оповещений вместе, чтобы получить представление об атаке, может быть сложным и трудоемким, Microsoft 365 Defender автоматически совмещает оповещения и связанные с ними сведения в инцидент.</span><span class="sxs-lookup"><span data-stu-id="4c822-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Как Защитник Microsoft 365 сопоставляет события из сущностями с инцидентом":::

<span data-ttu-id="4c822-116">Просмотрите краткий обзор инцидентов в Microsoft 365 Defender (4 минуты).</span><span class="sxs-lookup"><span data-stu-id="4c822-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="4c822-117">Группировка связанных оповещений в инцидент дает полное представление об атаке.</span><span class="sxs-lookup"><span data-stu-id="4c822-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="4c822-118">Например, вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="4c822-118">For example, you can see:</span></span>

- <span data-ttu-id="4c822-119">Где началась атака.</span><span class="sxs-lookup"><span data-stu-id="4c822-119">Where the attack started.</span></span>
- <span data-ttu-id="4c822-120">Какие тактики были использованы.</span><span class="sxs-lookup"><span data-stu-id="4c822-120">What tactics were used.</span></span>
- <span data-ttu-id="4c822-121">Как далеко атака прошла в клиента.</span><span class="sxs-lookup"><span data-stu-id="4c822-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="4c822-122">Масштабы атаки, такие как количество устройств, пользователей и почтовых ящиков, пострадали.</span><span class="sxs-lookup"><span data-stu-id="4c822-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="4c822-123">Все данные, связанные с атакой.</span><span class="sxs-lookup"><span data-stu-id="4c822-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="4c822-124">Если [включено,](m365d-enable.md)Microsoft 365 Defender может автоматически исследовать и устранять оповещения с помощью автоматизации и искусственного интеллекта.</span><span class="sxs-lookup"><span data-stu-id="4c822-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="4c822-125">Вы также можете выполнить дополнительные действия по исправлению для устранения атаки.</span><span class="sxs-lookup"><span data-stu-id="4c822-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="4c822-126">Инциденты и оповещения в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c822-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="4c822-127">Вы управляете инцидентами из & оповещения **> инцидентов** при быстром запуске центра безопасности Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4c822-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="4c822-128">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="4c822-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Страница Инциденты в центре безопасности Microsoft 365":::

<span data-ttu-id="4c822-130">При выборе имени инцидента отображается сводка об инциденте и предоставляется доступ к вкладкам с дополнительной информацией.</span><span class="sxs-lookup"><span data-stu-id="4c822-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Пример страницы Сводки инцидента в центре безопасности Microsoft 365":::

<span data-ttu-id="4c822-132">Дополнительные вкладки для инцидента:</span><span class="sxs-lookup"><span data-stu-id="4c822-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="4c822-133">Оповещения</span><span class="sxs-lookup"><span data-stu-id="4c822-133">Alerts</span></span> 

  <span data-ttu-id="4c822-134">Все оповещения, связанные с инцидентом, и их сведения.</span><span class="sxs-lookup"><span data-stu-id="4c822-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="4c822-135">Устройства</span><span class="sxs-lookup"><span data-stu-id="4c822-135">Devices</span></span>

  <span data-ttu-id="4c822-136">Все устройства, которые были идентифицированы как часть или связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="4c822-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4c822-137">Пользователи</span><span class="sxs-lookup"><span data-stu-id="4c822-137">Users</span></span>

  <span data-ttu-id="4c822-138">Все пользователи, которые были идентифицированы как часть или связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="4c822-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4c822-139">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="4c822-139">Mailboxes</span></span>

  <span data-ttu-id="4c822-140">Все почтовые ящики, которые были идентифицированы как часть или связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="4c822-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4c822-141">Исследования</span><span class="sxs-lookup"><span data-stu-id="4c822-141">Investigations</span></span>

  <span data-ttu-id="4c822-142">Все автоматические расследования, инициированные оповещениями об инциденте.</span><span class="sxs-lookup"><span data-stu-id="4c822-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="4c822-143">Доказательства и ответы</span><span class="sxs-lookup"><span data-stu-id="4c822-143">Evidence and Response</span></span>

  <span data-ttu-id="4c822-144">Все поддерживаемые события и подозрительные объекты в оповещении об инциденте.</span><span class="sxs-lookup"><span data-stu-id="4c822-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="4c822-145">Вот связь между инцидентом и его данными и вкладками инцидента в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c822-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Связь инцидента и его данных с вкладками инцидента в центре безопасности Microsoft 365":::

## <a name="next-step"></a><span data-ttu-id="4c822-147">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="4c822-147">Next step</span></span>

<span data-ttu-id="4c822-148">В очереди инцидента со страницы **Incidents** перечислены самые последние инциденты.</span><span class="sxs-lookup"><span data-stu-id="4c822-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="4c822-149">Отсюда можно:</span><span class="sxs-lookup"><span data-stu-id="4c822-149">From here, you can:</span></span>

- <span data-ttu-id="4c822-150">Узнайте, какие инциденты следует [приоритизировать](incident-queue.md) в зависимости от серьезности и других факторов.</span><span class="sxs-lookup"><span data-stu-id="4c822-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="4c822-151">Выполните [расследование](investigate-incidents.md) инцидента.</span><span class="sxs-lookup"><span data-stu-id="4c822-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="4c822-152">[Управление инцидентами,](manage-incidents.md)включая переименование, назначение, классификацию и добавление тегов для рабочего процесса управления инцидентами.</span><span class="sxs-lookup"><span data-stu-id="4c822-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
