---
title: Создание индикаторов
ms.reviewer: ''
description: Создание индикаторов для хеш-файлов, IP-адресов, URL-адресов или доменов, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: управление, разрешено, заблокировано, блокируется, очищается, вредоносный, файл, IP-адрес, URL-адреса, домен
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a04f3be1f13fb57cd76cda7115d014f2ba3aa8d6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198841"
---
# <a name="create-indicators"></a><span data-ttu-id="80a14-104">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="80a14-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80a14-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="80a14-105">**Applies to:**</span></span>
- [<span data-ttu-id="80a14-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="80a14-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80a14-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80a14-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="80a14-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="80a14-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="80a14-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="80a14-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="80a14-110">Индикатор компрометации (IoCs) является важной функцией в каждом решении по защите конечной точки.</span><span class="sxs-lookup"><span data-stu-id="80a14-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="80a14-111">Эта возможность позволяет SecOps устанавливать список индикаторов для обнаружения и блокировки (предотвращение и реагирование).</span><span class="sxs-lookup"><span data-stu-id="80a14-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="80a14-112">Создание индикаторов, определяющих обнаружение, предотвращение и исключение сущностями.</span><span class="sxs-lookup"><span data-stu-id="80a14-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="80a14-113">Можно определить действие, которое необходимо принять, а также продолжительность применения действия, а также область действия группы устройств для его применения.</span><span class="sxs-lookup"><span data-stu-id="80a14-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="80a14-114">В настоящее время поддерживаемые источники — это двигатель обнаружения облаков Defender для конечной точки, автоматизированный механизм исследования и устранения последствий, а также двигатель предотвращения конечных точек (антивирус Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="80a14-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="80a14-115">**Движок обнаружения облаков**</span><span class="sxs-lookup"><span data-stu-id="80a14-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="80a14-116">Механизм обнаружения облаков Defender для конечной точки регулярно сканирует собранные данные и пытается соответствовать установленным индикаторам.</span><span class="sxs-lookup"><span data-stu-id="80a14-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="80a14-117">При совпадении действие будет приниматься в соответствии с настройками, указанными для IoC.</span><span class="sxs-lookup"><span data-stu-id="80a14-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="80a14-118">**Двигатель предотвращения конечных точек**</span><span class="sxs-lookup"><span data-stu-id="80a14-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="80a14-119">Тот же список показателей почитается агентом по профилактике.</span><span class="sxs-lookup"><span data-stu-id="80a14-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="80a14-120">Это означает, что если microsoft Defender AV является основной конфигурацией AV, то соответствующими индикаторами будут обработаны в соответствии с настройками.</span><span class="sxs-lookup"><span data-stu-id="80a14-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="80a14-121">Например, если действие "Оповещение и блок", microsoft Defender AV предотвратит выполнение файлов (блок и исправление), и будет поднято соответствующее оповещение.</span><span class="sxs-lookup"><span data-stu-id="80a14-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="80a14-122">С другой стороны, если действие настроено на "Разрешить", microsoft Defender AV не обнаруживает и не блокирует запуск файла.</span><span class="sxs-lookup"><span data-stu-id="80a14-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="80a14-123">**Автоматизированный механизм расследования и восстановления**</span><span class="sxs-lookup"><span data-stu-id="80a14-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="80a14-124">Автоматическое расследование и исправление ведут себя одинаково.</span><span class="sxs-lookup"><span data-stu-id="80a14-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="80a14-125">Если индикатор задат "Разрешить", автоматизированное расследование и исправление будут игнорировать "плохой" вердикт для него.</span><span class="sxs-lookup"><span data-stu-id="80a14-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="80a14-126">Если установлено "Block", автоматизированное расследование и исправление будут относиться к нему как к "плохому".</span><span class="sxs-lookup"><span data-stu-id="80a14-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="80a14-127">Текущие поддерживаемые действия:</span><span class="sxs-lookup"><span data-stu-id="80a14-127">The current supported actions are:</span></span>
- <span data-ttu-id="80a14-128">Разрешить</span><span class="sxs-lookup"><span data-stu-id="80a14-128">Allow</span></span>
- <span data-ttu-id="80a14-129">Только оповещение</span><span class="sxs-lookup"><span data-stu-id="80a14-129">Alert only</span></span>
- <span data-ttu-id="80a14-130">Оповещение и блокировка</span><span class="sxs-lookup"><span data-stu-id="80a14-130">Alert and block</span></span>


<span data-ttu-id="80a14-131">Можно создать индикатор для:</span><span class="sxs-lookup"><span data-stu-id="80a14-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="80a14-132">Files</span><span class="sxs-lookup"><span data-stu-id="80a14-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="80a14-133">IP-адреса, URL-адреса/домены</span><span class="sxs-lookup"><span data-stu-id="80a14-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="80a14-134">Сертификаты</span><span class="sxs-lookup"><span data-stu-id="80a14-134">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="80a14-135">Существует ограничение в 15 000 показателей на одного клиента.</span><span class="sxs-lookup"><span data-stu-id="80a14-135">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="80a14-136">Индикаторы файлов и сертификатов не блокируют [исключения, определенные для антивируса Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="80a14-136">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="80a14-137">Индикаторы не поддерживаются в антивирусе Microsoft Defender в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="80a14-137">Indicators are not supported in Microsoft Defender Antivirus is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="80a14-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="80a14-138">Related topics</span></span>

- [<span data-ttu-id="80a14-139">Создание контекстного IoC</span><span class="sxs-lookup"><span data-stu-id="80a14-139">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="80a14-140">Используйте API индикаторов Endpoint в Microsoft Defender для</span><span class="sxs-lookup"><span data-stu-id="80a14-140">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="80a14-141">Использование интегрированных решений партнеров</span><span class="sxs-lookup"><span data-stu-id="80a14-141">Use partner integrated solutions</span></span>](partner-applications.md)
