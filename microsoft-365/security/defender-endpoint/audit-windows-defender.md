---
title: Проверка работы функций Microsoft Defender для конечных точек в режиме аудита
description: Режим аудита позволяет увидеть, как Microsoft Defender для конечной точки будет защищать устройства при его включении.
keywords: использование охраны, аудита, аудита, режима, включенного, отключенного, тестирования, демонстрации, оценки, лаборатории
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985100"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3c69c-104">Тестирование уменьшения поверхности атаки в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c69c-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c69c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3c69c-105">**Applies to:**</span></span>

- [<span data-ttu-id="3c69c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c69c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3c69c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c69c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3c69c-108">В составе группы безопасности организации можно настроить возможности уменьшения поверхности атаки для работы в режиме аудита, чтобы узнать, как они будут работать.</span><span class="sxs-lookup"><span data-stu-id="3c69c-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="3c69c-109">В режиме аудита можно включить:</span><span class="sxs-lookup"><span data-stu-id="3c69c-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="3c69c-110">Правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="3c69c-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="3c69c-111">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="3c69c-111">Exploit protection</span></span>
- <span data-ttu-id="3c69c-112">Защита сети</span><span class="sxs-lookup"><span data-stu-id="3c69c-112">Network protection</span></span>
- <span data-ttu-id="3c69c-113">И управляемый доступ к папкам в режиме аудита</span><span class="sxs-lookup"><span data-stu-id="3c69c-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="3c69c-114">Режим аудита позволяет увидеть запись *того,* что произошло бы, если бы вы включили эту функцию.</span><span class="sxs-lookup"><span data-stu-id="3c69c-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="3c69c-115">Вы можете включить режим аудита при тестировании работы функций.</span><span class="sxs-lookup"><span data-stu-id="3c69c-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="3c69c-116">Это поможет убедиться, что ваши бизнес-приложения не затронуты.</span><span class="sxs-lookup"><span data-stu-id="3c69c-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="3c69c-117">Вы также можете получить представление о том, сколько попыток изменения подозрительных файлов происходит в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="3c69c-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="3c69c-118">Эти функции не будут блокировать приложения, скрипты или файлы, которые не будут изменяться.</span><span class="sxs-lookup"><span data-stu-id="3c69c-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="3c69c-119">Однако журнал Windows событий будет записывать события, как если бы функции были полностью включены.</span><span class="sxs-lookup"><span data-stu-id="3c69c-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="3c69c-120">В режиме аудита можно просмотреть журнал событий, чтобы узнать, какое влияние эта функция имела бы, если бы она была включена.</span><span class="sxs-lookup"><span data-stu-id="3c69c-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="3c69c-121">Чтобы найти проверенные записи, перейдите к приложениям и службам  >  **Microsoft**  >  **Windows**  >  **Защитник Windows**  >  **Operational.**</span><span class="sxs-lookup"><span data-stu-id="3c69c-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="3c69c-122">Используйте Defender для конечной точки, чтобы получить более подробные сведения для каждого события, особенно для исследования правил уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="3c69c-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="3c69c-123">Использование консоли Defender для конечной точки позволяет исследовать проблемы в рамках временной шкалы оповещений [и сценариев расследования.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3c69c-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="3c69c-124">Режим аудита можно включить с помощью поставщиков групповой политики, PowerShell и служб конфигурации (CSP).</span><span class="sxs-lookup"><span data-stu-id="3c69c-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="3c69c-125">Вы также можете посетить веб-Защитник Windows [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) тестового поля в demo.wd.microsoft.com, чтобы подтвердить, что функции работают, и посмотреть, как они работают.</span><span class="sxs-lookup"><span data-stu-id="3c69c-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="3c69c-126">Параметры аудита</span><span class="sxs-lookup"><span data-stu-id="3c69c-126">Audit options</span></span> | <span data-ttu-id="3c69c-127">Как включить режим аудита</span><span class="sxs-lookup"><span data-stu-id="3c69c-127">How to enable audit mode</span></span> | <span data-ttu-id="3c69c-128">Просмотр событий</span><span class="sxs-lookup"><span data-stu-id="3c69c-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="3c69c-129">Аудит применяется ко всем событиям</span><span class="sxs-lookup"><span data-stu-id="3c69c-129">Audit applies to all events</span></span> | [<span data-ttu-id="3c69c-130">Включить контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="3c69c-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="3c69c-131">События доступа к управляемым папкам</span><span class="sxs-lookup"><span data-stu-id="3c69c-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="3c69c-132">Аудит применяется к отдельным правилам</span><span class="sxs-lookup"><span data-stu-id="3c69c-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="3c69c-133">Включить правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="3c69c-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="3c69c-134">События правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="3c69c-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="3c69c-135">Аудит применяется ко всем событиям</span><span class="sxs-lookup"><span data-stu-id="3c69c-135">Audit applies to all events</span></span> | [<span data-ttu-id="3c69c-136">Включить защиту сети</span><span class="sxs-lookup"><span data-stu-id="3c69c-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="3c69c-137">События защиты сети</span><span class="sxs-lookup"><span data-stu-id="3c69c-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="3c69c-138">Аудит применяется к отдельным смягчам</span><span class="sxs-lookup"><span data-stu-id="3c69c-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="3c69c-139">Включить защиту от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="3c69c-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="3c69c-140">События защиты эксплойтов</span><span class="sxs-lookup"><span data-stu-id="3c69c-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
