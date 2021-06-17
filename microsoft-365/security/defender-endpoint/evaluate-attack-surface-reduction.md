---
title: Оценка правил сокращения направлений атак
description: Узнайте, как уменьшение поверхности атаки блокирует и предотвращает атаки с помощью настраиваемой демонстрации.
keywords: Уменьшение поверхности атаки, бедра, система предотвращения вторжений на хост, правила защиты, антиэкспозиция, антиэкспплойт, эксплойт, профилактика инфекции, оценка, тестирование, демонстрация
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a5fa8e46de0a6561d3377ce77e38bd59aa97f3c4
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984728"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="e77e2-104">Оценка правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="e77e2-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e77e2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e77e2-105">**Applies to:**</span></span>

- [<span data-ttu-id="e77e2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e77e2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e77e2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e77e2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e77e2-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e77e2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e77e2-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e77e2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="e77e2-110">Правила уменьшения поверхности атаки помогают предотвратить действия, обычно используемые вредоносными программами для компрометации устройств или сетей.</span><span class="sxs-lookup"><span data-stu-id="e77e2-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="e77e2-111">Правила уменьшения поверхности атаки помогают закрыть многие из общих точек входа, используемых вредоносными программами и программами-вымогателями.</span><span class="sxs-lookup"><span data-stu-id="e77e2-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span>

<span data-ttu-id="e77e2-112">Установите правила уменьшения поверхности атаки для устройств, работающих с любыми из следующих выпусков и версий Windows:</span><span class="sxs-lookup"><span data-stu-id="e77e2-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="e77e2-113">Windows 10 Pro версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e77e2-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="e77e2-114">Windows 10 Корпоративная версии [1709](/windows/whats-new/whats-new-windows-10-version-1709) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e77e2-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="e77e2-115">Windows Сервер, [версия 1803 (полугодовой канал)](/windows-server/get-started/whats-new-in-windows-server-1803) или более поздний</span><span class="sxs-lookup"><span data-stu-id="e77e2-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="e77e2-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e77e2-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> <span data-ttu-id="e77e2-117">Включение правил снижения службы атак на Windows Server 2016 может привести к неожиданным результатам и производительности сервера.</span><span class="sxs-lookup"><span data-stu-id="e77e2-117">Enabling attack service reduction rules on Windows Server 2016 might lead to unexpected results, and impact server performance.</span></span> <span data-ttu-id="e77e2-118">Мы не рекомендуем включать или развернуть правила уменьшения поверхности атаки на неподключаемой платформе.</span><span class="sxs-lookup"><span data-stu-id="e77e2-118">We do not recommend enabling or deploying attack surface reduction rules to unsupported platforms.</span></span>

<span data-ttu-id="e77e2-119">Узнайте, как оценить правила уменьшения поверхности атаки, [включив](audit-windows-defender.md) режим аудита для тестирования функции непосредственно в организации.</span><span class="sxs-lookup"><span data-stu-id="e77e2-119">Learn how to evaluate attack surface reduction rules by [enabling audit mode](audit-windows-defender.md) to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="e77e2-120">Вы также можете посетить веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint в demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и посмотреть, как она работает. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="e77e2-120">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="e77e2-121">Использование режима аудита для измерения воздействия</span><span class="sxs-lookup"><span data-stu-id="e77e2-121">Use audit mode to measure impact</span></span>

<span data-ttu-id="e77e2-122">Включай правила уменьшения поверхности атаки в режиме аудита, чтобы просмотреть запись приложений, которые были бы заблокированы, если бы функция была полностью включена.</span><span class="sxs-lookup"><span data-stu-id="e77e2-122">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="e77e2-123">Проверьте, как эта функция будет работать в организации, чтобы убедиться, что она не влияет на ваши бизнес-приложения.</span><span class="sxs-lookup"><span data-stu-id="e77e2-123">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="e77e2-124">Вы также можете получить представление о том, как часто правила будут работать при нормальном использовании.</span><span class="sxs-lookup"><span data-stu-id="e77e2-124">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="e77e2-125">Чтобы включить правило уменьшения поверхности атаки в режиме аудита, используйте следующий cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e77e2-125">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="e77e2-126">Где значение GUID правила уменьшения поверхности `<rule ID>` [атаки.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="e77e2-126">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="e77e2-127">Чтобы включить все добавленные правила уменьшения поверхности атаки в режиме аудита, используйте следующий cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e77e2-127">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="e77e2-128">Если вы хотите полностью проверять, как будут работать правила уменьшения поверхности атаки в вашей организации, вам потребуется использовать средство управления для развертывания этого параметра на устройствах в сети (s).</span><span class="sxs-lookup"><span data-stu-id="e77e2-128">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="e77e2-129">Для настройки и развертывания параметра можно также использовать поставщики услуг групповой политики, intune или службы управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="e77e2-129">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="e77e2-130">Дополнительные статьи в статье Правила уменьшения [поверхности](attack-surface-reduction.md) атаки.</span><span class="sxs-lookup"><span data-stu-id="e77e2-130">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="e77e2-131">Просмотр событий уменьшения поверхности атаки в Windows viewer событий</span><span class="sxs-lookup"><span data-stu-id="e77e2-131">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="e77e2-132">Чтобы просмотреть заблокированные приложения, откройте viewer событий и фильтр для event ID 1121 в журнале Microsoft-Windows-Защитник Windows/Operational.</span><span class="sxs-lookup"><span data-stu-id="e77e2-132">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="e77e2-133">В следующей таблице перечислены все события защиты сети.</span><span class="sxs-lookup"><span data-stu-id="e77e2-133">The following table lists all network protection events.</span></span>

<span data-ttu-id="e77e2-134">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e77e2-134">Event ID</span></span> | <span data-ttu-id="e77e2-135">Описание</span><span class="sxs-lookup"><span data-stu-id="e77e2-135">Description</span></span>
-|-
 <span data-ttu-id="e77e2-136">5007</span><span class="sxs-lookup"><span data-stu-id="e77e2-136">5007</span></span> | <span data-ttu-id="e77e2-137">Событие при смене параметров</span><span class="sxs-lookup"><span data-stu-id="e77e2-137">Event when settings are changed</span></span>
 <span data-ttu-id="e77e2-138">1121</span><span class="sxs-lookup"><span data-stu-id="e77e2-138">1121</span></span> | <span data-ttu-id="e77e2-139">Событие, когда правило уменьшения поверхности атаки загореется в режиме блокировки</span><span class="sxs-lookup"><span data-stu-id="e77e2-139">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="e77e2-140">1122</span><span class="sxs-lookup"><span data-stu-id="e77e2-140">1122</span></span> | <span data-ttu-id="e77e2-141">Событие, когда правило уменьшения поверхности атаки загореется в режиме аудита</span><span class="sxs-lookup"><span data-stu-id="e77e2-141">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="e77e2-142">Настройка правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="e77e2-142">Customize attack surface reduction rules</span></span>

<span data-ttu-id="e77e2-143">Во время оценки может потребоваться настроить каждое правило по отдельности или исключить возможность оценки определенных файлов и процессов этой функцией.</span><span class="sxs-lookup"><span data-stu-id="e77e2-143">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="e77e2-144">Сведения [о настройке](customize-attack-surface-reduction.md) функции с помощью средств управления, включая политики групповой политики и CSP MDM, см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="e77e2-144">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="e77e2-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e77e2-145">See also</span></span>

- [<span data-ttu-id="e77e2-146">Уменьшение поверхностей атаки с помощью правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="e77e2-146">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="e77e2-147">Используйте режим аудита для оценки Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="e77e2-147">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
- [<span data-ttu-id="e77e2-148">Сокращение направлений атак: вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="e77e2-148">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
