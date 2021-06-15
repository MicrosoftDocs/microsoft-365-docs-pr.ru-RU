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
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925663"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b817c-104">Тестирование уменьшения поверхности атаки в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b817c-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b817c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b817c-105">**Applies to:**</span></span>
- [<span data-ttu-id="b817c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b817c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b817c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b817c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b817c-108">Если вы входите в команду безопасности организации, вы можете настроить возможности уменьшения поверхности атаки для работы в режиме аудита, чтобы узнать, как они будут работать в организации.</span><span class="sxs-lookup"><span data-stu-id="b817c-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="b817c-109">В частности, в режиме аудита можно включить правила уменьшения поверхности атаки, защиту от эксплойтов, защиту сети и управляемый доступ к папкам.</span><span class="sxs-lookup"><span data-stu-id="b817c-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="b817c-110">Режим аудита позволяет увидеть запись *того,* что произошло бы, если бы вы включили эту функцию.</span><span class="sxs-lookup"><span data-stu-id="b817c-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="b817c-111">При тестировании работы функций в организации может потребоваться включить режим аудита.</span><span class="sxs-lookup"><span data-stu-id="b817c-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="b817c-112">Это поможет убедиться, что ваши бизнес-приложения не затронуты.</span><span class="sxs-lookup"><span data-stu-id="b817c-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="b817c-113">Вы также можете получить представление о том, сколько попыток изменения подозрительных файлов происходит в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="b817c-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="b817c-114">Эти функции не будут блокировать приложения, скрипты или файлы, которые не будут изменяться.</span><span class="sxs-lookup"><span data-stu-id="b817c-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="b817c-115">Однако журнал Windows событий будет записывать события, как если бы функции были полностью включены.</span><span class="sxs-lookup"><span data-stu-id="b817c-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="b817c-116">В режиме аудита можно просмотреть журнал событий, чтобы узнать, какое влияние эта функция оказала бы, если бы она была включена.</span><span class="sxs-lookup"><span data-stu-id="b817c-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="b817c-117">Чтобы найти проверенные записи, перейдите к приложениям и службам  >  **Microsoft**  >  **Windows**  >  **Защитник Windows**  >  **Operational.**</span><span class="sxs-lookup"><span data-stu-id="b817c-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="b817c-118">Вы можете использовать Defender для конечной точки, чтобы получить более подробные сведения для каждого события, особенно для исследования правил уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="b817c-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="b817c-119">Использование консоли Defender для конечной точки позволяет исследовать проблемы в рамках временной шкалы оповещений [и сценариев расследования.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b817c-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="b817c-120">Чтобы включить режим аудита, можно использовать поставщики групповых политик, PowerShell и служб конфигурации (CSP).</span><span class="sxs-lookup"><span data-stu-id="b817c-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="b817c-121">Вы также можете посетить веб-Защитник Windows [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) тестового поля в demo.wd.microsoft.com, чтобы подтвердить, что функции работают, и посмотреть, как они работают.</span><span class="sxs-lookup"><span data-stu-id="b817c-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="b817c-122">Параметры аудита</span><span class="sxs-lookup"><span data-stu-id="b817c-122">Audit options</span></span> | <span data-ttu-id="b817c-123">Как включить режим аудита</span><span class="sxs-lookup"><span data-stu-id="b817c-123">How to enable audit mode</span></span> | <span data-ttu-id="b817c-124">Просмотр событий</span><span class="sxs-lookup"><span data-stu-id="b817c-124">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="b817c-125">Аудит применяется ко всем событиям</span><span class="sxs-lookup"><span data-stu-id="b817c-125">Audit applies to all events</span></span> | [<span data-ttu-id="b817c-126">Включить контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="b817c-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="b817c-127">События доступа к управляемым папкам</span><span class="sxs-lookup"><span data-stu-id="b817c-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="b817c-128">Аудит применяется к отдельным правилам</span><span class="sxs-lookup"><span data-stu-id="b817c-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="b817c-129">Включить правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="b817c-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="b817c-130">События правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="b817c-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="b817c-131">Аудит применяется ко всем событиям</span><span class="sxs-lookup"><span data-stu-id="b817c-131">Audit applies to all events</span></span> | [<span data-ttu-id="b817c-132">Включить защиту сети</span><span class="sxs-lookup"><span data-stu-id="b817c-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="b817c-133">События защиты сети</span><span class="sxs-lookup"><span data-stu-id="b817c-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="b817c-134">Аудит применяется к отдельным смягчам</span><span class="sxs-lookup"><span data-stu-id="b817c-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="b817c-135">Включить защиту от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="b817c-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="b817c-136">События защиты эксплойтов</span><span class="sxs-lookup"><span data-stu-id="b817c-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


