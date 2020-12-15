---
title: Автоматическое исследование и реагирование в Microsoft 365 Defender
description: Обзор возможностей автоматического исследования и реагирования, также называемых средствами самостоятельного восстановления, в Microsoft 365 Defender
keywords: автоматизированный, исследование, оповещение, триггер, действие, исправление, самостоятельное исправление
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683311"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="1c584-104">Автоматическое исследование и реагирование в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c584-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1c584-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1c584-105">**Applies to:**</span></span>
- <span data-ttu-id="1c584-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c584-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="1c584-107">Хотите испытать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="1c584-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="1c584-108">Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или запустить [пилотный проект в производственной среде.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="1c584-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="1c584-109">Как работают автоматизированные исследования и самовосстановления</span><span class="sxs-lookup"><span data-stu-id="1c584-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="1c584-110">По мере инициации оповещений системы безопасности ваша группа по работе с безопасностью должна инициализации этих оповещений и принять меры для защиты организации.</span><span class="sxs-lookup"><span data-stu-id="1c584-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="1c584-111">Определение приоритета и анализ оповещений могут отнимать очень много времени, особенно в условиях постоянного появления новых оповещений во время анализа.</span><span class="sxs-lookup"><span data-stu-id="1c584-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="1c584-112">Службы обеспечения безопасности могут быть перегружены из-за огромного количества угроз, которые им нужно отслеживать и от которых необходимо защищать.</span><span class="sxs-lookup"><span data-stu-id="1c584-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="1c584-113">Возможность автоматического исследования и реагирования с помощью функции самостоятельного восстановления в Microsoft 365 Defender может помочь.</span><span class="sxs-lookup"><span data-stu-id="1c584-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="1c584-114">Посмотрите следующее видео, чтобы узнать, как работает самовосстановления:</span><span class="sxs-lookup"><span data-stu-id="1c584-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="1c584-115">В Microsoft 365 Defender автоматизированное исследование и реагирование на них с помощью функций самостоятельного восстановления работает на всех устройствах, на разных устройствах, & содержимым и удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="1c584-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="1c584-116">В этой статье описывается, как работают автоматизированные исследования и реагирование на них.</span><span class="sxs-lookup"><span data-stu-id="1c584-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="1c584-117">Чтобы настроить эти возможности, см. настройку автоматизированного исследования и реагирования [на них в Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="1c584-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="1c584-118">Ваш собственный виртуальный аналитик</span><span class="sxs-lookup"><span data-stu-id="1c584-118">Your own virtual analyst</span></span>

<span data-ttu-id="1c584-119">Представьте, что у вас есть виртуальный аналитик в вашей службе обеспечения безопасности уровня 1 / уровня 2.</span><span class="sxs-lookup"><span data-stu-id="1c584-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="1c584-120">Виртуальный аналитик имитирует идеальные действия, которые должен предпринять отдел обеспечения безопасности для анализа и устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="1c584-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="1c584-121">Виртуальный помощник может работать в круглосуточном режиме с неограниченной нагрузкой, а также взять на себя значительную часть анализа и устранений угроз.</span><span class="sxs-lookup"><span data-stu-id="1c584-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="1c584-122">Такой виртуальный помощник может значительно сократить время реагирования, освободив вашу службу обеспечения безопасности для других важных стратегических проектов.</span><span class="sxs-lookup"><span data-stu-id="1c584-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="1c584-123">Если этот сценарий похож на звуковую вымышленный, это не так!</span><span class="sxs-lookup"><span data-stu-id="1c584-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="1c584-124">Такой виртуальный аналитик входит в состав набора Microsoft 365 Defender, и его имя — автоматизированное исследование и *реагирование.*</span><span class="sxs-lookup"><span data-stu-id="1c584-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="1c584-125">Автоматизированное исследование и реагирование на них позволяет группе по работе с безопасностью значительно повысить способность организации работать с оповещениями и инцидентами системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c584-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="1c584-126">Автоматизированное исследование и реагирование на них позволяет снизить затраты на расследования и действия по исправлению угроз, а также максимально использовать свой набор средств защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="1c584-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="1c584-127">автоматизированное исследование и реагирование на них помогают вашей группе операций безопасности:</span><span class="sxs-lookup"><span data-stu-id="1c584-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="1c584-128">определяет, требует ли угроза выполнения какого-либо действия;</span><span class="sxs-lookup"><span data-stu-id="1c584-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="1c584-129">выполняет (или рекомендуют) все необходимые действия по исправлению;</span><span class="sxs-lookup"><span data-stu-id="1c584-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="1c584-130">определяет, какие дополнительные анализы необходимо провести, а также</span><span class="sxs-lookup"><span data-stu-id="1c584-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="1c584-131">повторяет весь этот процесс с другими оповещениями.</span><span class="sxs-lookup"><span data-stu-id="1c584-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="1c584-132">Процесс автоматизированного анализа</span><span class="sxs-lookup"><span data-stu-id="1c584-132">The automated investigation process</span></span>

<span data-ttu-id="1c584-133">**Оповещение** > **инцидент** > **автоматизированный анализ угроз** > **заключение** > **действие по исправлению**</span><span class="sxs-lookup"><span data-stu-id="1c584-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="1c584-134">Инициированное оповещение создает инцидент, который может запустить автоматическое исследование.</span><span class="sxs-lookup"><span data-stu-id="1c584-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="1c584-135">Это может привести к необходимости одного или нескольких действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="1c584-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="1c584-136">В Microsoft 365 Defender каждое автоматизированное исследование сопоставляет сигналы в Microsoft Defender для удостоверений, Microsoft Defender для конечной точки и Защитника Office 365, как по резюмируется в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="1c584-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="1c584-137">Объекты</span><span class="sxs-lookup"><span data-stu-id="1c584-137">Entities</span></span> |<span data-ttu-id="1c584-138">Службы защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="1c584-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="1c584-139">Устройства (также называемые конечными точками)</span><span class="sxs-lookup"><span data-stu-id="1c584-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="1c584-140">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1c584-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="1c584-141">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="1c584-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="1c584-142">Содержимое электронной почты (файлы и сообщения в почтовых ящиках)</span><span class="sxs-lookup"><span data-stu-id="1c584-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="1c584-143">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="1c584-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="1c584-144">Каждое исследование создает заключение *(вредоносные,* подозрительные или угрозы не *найдены)* для каждого фрагмента исследуемого свидетельства.</span><span class="sxs-lookup"><span data-stu-id="1c584-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="1c584-145">В зависимости от типа угрозы и итоговых результатов решения действия по исправлению происходят автоматически или после утверждения командой операций безопасности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1c584-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="1c584-146">Ожидающие выполнения и завершенные действия отображаются в списке [Центре уведомлений](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="1c584-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="1c584-147">Во время проведения анализа все другие связанные с ним оповещения добавляются в анализ до его завершения.</span><span class="sxs-lookup"><span data-stu-id="1c584-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="1c584-148">Если скомпрометировавший себя объект встречается в другом месте, в процессе автоматизированного анализа исследуемая область будет расширена, чтобы включить этот объект, и будет выполнен общий сценарий безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c584-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="1c584-149">Не каждое оповещение запускает автоматизированное исследование, и не каждое исследование приводит к автоматизированным действиям по исправлению; Все зависит от настройки автоматизированного исследования и реагирования на них в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1c584-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="1c584-150">См. "Настройка автоматизированного исследования и реагирования на них [в Microsoft 365 Defender".](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="1c584-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="1c584-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1c584-151">Next steps</span></span>

- [<span data-ttu-id="1c584-152">См. необходимые условия для автоматического исследования и реагирования в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c584-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="1c584-153">Настройка автоматического исследования и реагирования на них в организации</span><span class="sxs-lookup"><span data-stu-id="1c584-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="1c584-154">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="1c584-154">Learn more about the Action center</span></span>](mtp-action-center.md)
