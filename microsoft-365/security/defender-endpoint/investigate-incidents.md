---
title: Расследование инцидентов в Microsoft Defender для конечной точки
description: См. связанные оповещения, управление инцидентом и метаданные оповещений, которые помогут вам исследовать инцидент
keywords: расследование, инциденты, оповещения, метаданные, риск, источник обнаружения, затронутые устройства, шаблоны, корреляция
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
ms.openlocfilehash: 0b52b6f9b457dbe1a5984c3d68c7077f7037d498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845082"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="66441-104">Расследование инцидентов в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="66441-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="66441-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="66441-105">**Applies to:**</span></span>
- [<span data-ttu-id="66441-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="66441-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="66441-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66441-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="66441-108">Изучите инциденты, влияющие на вашу сеть, поймите, что они означают, и собери доказательства для их устранения.</span><span class="sxs-lookup"><span data-stu-id="66441-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="66441-109">При расследовании инцидента вы увидите:</span><span class="sxs-lookup"><span data-stu-id="66441-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="66441-110">Сведения об инциденте</span><span class="sxs-lookup"><span data-stu-id="66441-110">Incident details</span></span>
- <span data-ttu-id="66441-111">Комментарии и действия инцидента</span><span class="sxs-lookup"><span data-stu-id="66441-111">Incident comments and actions</span></span>
- <span data-ttu-id="66441-112">Вкладки (оповещения, устройства, исследования, доказательства, график)</span><span class="sxs-lookup"><span data-stu-id="66441-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="66441-113">Анализ сведений об инцидентах</span><span class="sxs-lookup"><span data-stu-id="66441-113">Analyze incident details</span></span> 
<span data-ttu-id="66441-114">Щелкните инцидент, чтобы увидеть области **Инцидента**.</span><span class="sxs-lookup"><span data-stu-id="66441-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="66441-115">Выберите **страницу Открытый** инцидент, чтобы увидеть сведения об инциденте и связанные с ними сведения (оповещения, устройства, расследования, доказательства, график).</span><span class="sxs-lookup"><span data-stu-id="66441-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Изображение сведений об инцидентах1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="66441-117">Оповещения</span><span class="sxs-lookup"><span data-stu-id="66441-117">Alerts</span></span>
<span data-ttu-id="66441-118">Вы можете исследовать оповещения и видеть, как они были связаны друг с другом в инциденте.</span><span class="sxs-lookup"><span data-stu-id="66441-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="66441-119">Оповещения сгруппируются в инциденты по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="66441-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="66441-120">Автоматическое расследование . Автоматическое расследование вызвало связанное оповещение при расследовании исходного оповещения</span><span class="sxs-lookup"><span data-stu-id="66441-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="66441-121">Характеристики файла . Файлы, связанные с оповещением, имеют схожие характеристики</span><span class="sxs-lookup"><span data-stu-id="66441-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="66441-122">Ручная связь . Пользователь вручную связал оповещения</span><span class="sxs-lookup"><span data-stu-id="66441-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="66441-123">Proximate time — оповещения запускались на одном устройстве в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="66441-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="66441-124">Тот же файл . Файлы, связанные с оповещением, точно такие же</span><span class="sxs-lookup"><span data-stu-id="66441-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="66441-125">Тот же URL-адрес. URL-адрес, который вызвал оповещение, точно такой же.</span><span class="sxs-lookup"><span data-stu-id="66441-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Изображение вкладки оповещений со страницей сведений об инцидентах, показывающая причины, по которой оповещения были связаны друг с другом в этом инциденте.](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="66441-127">Вы также можете управлять оповещением и видеть метаданные оповещения вместе с другими сведениями.</span><span class="sxs-lookup"><span data-stu-id="66441-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="66441-128">Дополнительные сведения см. в [дополнительных сведениях.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="66441-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="66441-129">Устройства</span><span class="sxs-lookup"><span data-stu-id="66441-129">Devices</span></span>
<span data-ttu-id="66441-130">Вы также можете исследовать устройства, которые являются частью данного инцидента или связаны с ним.</span><span class="sxs-lookup"><span data-stu-id="66441-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="66441-131">Дополнительные сведения см. в [дополнительных сведениях.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="66441-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Изображение вкладки устройств на странице сведения об инцидентах](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="66441-133">Исследования</span><span class="sxs-lookup"><span data-stu-id="66441-133">Investigations</span></span>
<span data-ttu-id="66441-134">Выберите **исследование,** чтобы увидеть все автоматические расследования, запущенные системой в ответ на оповещения об инциденте.</span><span class="sxs-lookup"><span data-stu-id="66441-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Изображение вкладки расследований на странице сведения об инцидентах](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="66441-136">Проявка доказательств</span><span class="sxs-lookup"><span data-stu-id="66441-136">Going through the evidence</span></span>
<span data-ttu-id="66441-137">Microsoft Defender для конечной точки автоматически исследует все поддерживаемые инцидентами события и подозрительные объекты в оповещении, предоставляя автоответчи и сведения о важных файлах, процессах, службах и других.</span><span class="sxs-lookup"><span data-stu-id="66441-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="66441-138">Каждый из проанализировавших сущностям будет помечен как зараженный, исправленный или подозрительный.</span><span class="sxs-lookup"><span data-stu-id="66441-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Изображение вкладки доказательств на странице сведения об инцидентах](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="66441-140">Визуализация связанных угроз кибербезопасности</span><span class="sxs-lookup"><span data-stu-id="66441-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="66441-141">Microsoft Defender для конечной точки агрегируется сведения об угрозах в инцидент, чтобы вы могли видеть шаблоны и корреляции, исходящую из различных точек данных.</span><span class="sxs-lookup"><span data-stu-id="66441-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="66441-142">Такую корреляцию можно просмотреть с помощью диаграммы инцидентов.</span><span class="sxs-lookup"><span data-stu-id="66441-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="66441-143">График инцидентов</span><span class="sxs-lookup"><span data-stu-id="66441-143">Incident graph</span></span>
<span data-ttu-id="66441-144">В **Graph** рассказывается история атаки на кибербезопасность.</span><span class="sxs-lookup"><span data-stu-id="66441-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="66441-145">Например, он показывает, что было точкой входа, какой индикатор компромисса или активности был замечен на каком устройстве.</span><span class="sxs-lookup"><span data-stu-id="66441-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="66441-146">и т.д.</span><span class="sxs-lookup"><span data-stu-id="66441-146">etc.</span></span>

![Изображение диаграммы инцидентов](images/atp-incident-graph-tab.png)

<span data-ttu-id="66441-148">Вы можете щелкнуть круги на графике инцидентов, чтобы просмотреть сведения о вредоносных файлах, связанных обнаружениях файлов, о том, сколько экземпляров было по всему миру, наблюдалось ли это в организации, если да, то сколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="66441-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Изображение сведений об инцидентах](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="66441-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="66441-150">Related topics</span></span>
- [<span data-ttu-id="66441-151">Очередь инцидентов</span><span class="sxs-lookup"><span data-stu-id="66441-151">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="66441-152">Расследование инцидентов в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="66441-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="66441-153">Управление microsoft Defender для инцидентов конечной точки</span><span class="sxs-lookup"><span data-stu-id="66441-153">Manage Microsoft Defender for Endpoint incidents</span></span>](/microsoft-365/security/defender-endpoint/manage-incidents)
