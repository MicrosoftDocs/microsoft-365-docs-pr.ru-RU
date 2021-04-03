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
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570976"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="22abe-104">Проверка работы функций Microsoft Defender для конечных точек в режиме аудита</span><span class="sxs-lookup"><span data-stu-id="22abe-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22abe-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="22abe-105">**Applies to:**</span></span>
- [<span data-ttu-id="22abe-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="22abe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="22abe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22abe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="22abe-108">Вы можете включить правила уменьшения поверхности атаки, защиту от эксплойтов, защиту сети и контролируемый доступ к папкам в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="22abe-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="22abe-109">Режим аудита позволяет увидеть запись *того,* что произошло бы, если бы вы включили эту функцию.</span><span class="sxs-lookup"><span data-stu-id="22abe-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="22abe-110">При тестировании работы функций в организации может потребоваться включить режим аудита.</span><span class="sxs-lookup"><span data-stu-id="22abe-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="22abe-111">Это поможет убедиться, что ваши бизнес-приложения не затронуты.</span><span class="sxs-lookup"><span data-stu-id="22abe-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="22abe-112">Вы также можете получить представление о том, сколько попыток изменения подозрительных файлов происходит в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="22abe-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="22abe-113">Эти функции не будут блокировать приложения, скрипты или файлы, которые не будут изменяться.</span><span class="sxs-lookup"><span data-stu-id="22abe-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="22abe-114">Однако журнал событий Windows будет записывать события так, как если бы функции были полностью включены.</span><span class="sxs-lookup"><span data-stu-id="22abe-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="22abe-115">В режиме аудита можно просмотреть журнал событий, чтобы узнать, какое влияние эта функция оказала бы, если бы она была включена.</span><span class="sxs-lookup"><span data-stu-id="22abe-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="22abe-116">Чтобы найти проверенные записи, перейдите к **приложениям** и службам  >  **Microsoft**  >  **Windows**  >  **Защитник Windows**  >  **Operational.**</span><span class="sxs-lookup"><span data-stu-id="22abe-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="22abe-117">Вы можете использовать Defender для конечной точки, чтобы получить более подробные сведения для каждого события, особенно для исследования правил уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="22abe-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="22abe-118">Использование консоли Defender для конечной точки позволяет исследовать проблемы в рамках временной шкалы оповещений [и сценариев расследования.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="22abe-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="22abe-119">Чтобы включить режим аудита, можно использовать поставщики групповых политик, PowerShell и служб конфигурации (CSP).</span><span class="sxs-lookup"><span data-stu-id="22abe-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="22abe-120">Вы также можете посетить веб Защитник Windows [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) тестовом сайте demo.wd.microsoft.com, чтобы подтвердить, что функции работают, и посмотреть, как они работают.</span><span class="sxs-lookup"><span data-stu-id="22abe-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="22abe-121">**Параметры аудита**</span><span class="sxs-lookup"><span data-stu-id="22abe-121">**Audit options**</span></span> | <span data-ttu-id="22abe-122">**Как включить режим аудита**</span><span class="sxs-lookup"><span data-stu-id="22abe-122">**How to enable audit mode**</span></span> | <span data-ttu-id="22abe-123">**Просмотр событий**</span><span class="sxs-lookup"><span data-stu-id="22abe-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="22abe-124">Аудит применяется ко всем событиям</span><span class="sxs-lookup"><span data-stu-id="22abe-124">Audit applies to all events</span></span> | [<span data-ttu-id="22abe-125">Включить контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="22abe-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="22abe-126">События доступа к управляемым папкам</span><span class="sxs-lookup"><span data-stu-id="22abe-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="22abe-127">Аудит применяется к отдельным правилам</span><span class="sxs-lookup"><span data-stu-id="22abe-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="22abe-128">Включить правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="22abe-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="22abe-129">События правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="22abe-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="22abe-130">Аудит применяется ко всем событиям</span><span class="sxs-lookup"><span data-stu-id="22abe-130">Audit applies to all events</span></span> | [<span data-ttu-id="22abe-131">Включить защиту сети</span><span class="sxs-lookup"><span data-stu-id="22abe-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="22abe-132">События защиты сети</span><span class="sxs-lookup"><span data-stu-id="22abe-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="22abe-133">Аудит применяется к отдельным смягчам</span><span class="sxs-lookup"><span data-stu-id="22abe-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="22abe-134">Включить защиту от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="22abe-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="22abe-135">События защиты эксплойтов</span><span class="sxs-lookup"><span data-stu-id="22abe-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="22abe-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="22abe-136">Related topics</span></span>

* [<span data-ttu-id="22abe-137">Защита устройств от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="22abe-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="22abe-138">Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="22abe-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="22abe-139">Защита сети</span><span class="sxs-lookup"><span data-stu-id="22abe-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="22abe-140">Защита важных папок</span><span class="sxs-lookup"><span data-stu-id="22abe-140">Protect important folders</span></span>](controlled-folders.md)
