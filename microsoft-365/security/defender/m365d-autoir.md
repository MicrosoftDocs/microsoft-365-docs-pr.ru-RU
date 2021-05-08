---
title: Автоматическое расследование и ответ в Microsoft 365 Defender
description: Обзор возможностей автоматического расследования и ответа, также называемых самовосстановления, в Microsoft 365 Defender
keywords: автоматическое, исследование, оповещение, триггер, действие, исправление, самовосстановления
search.appverid: met150
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
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259539"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="56ab1-104">Автоматическое расследование и ответ в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56ab1-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="56ab1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="56ab1-105">**Applies to:**</span></span>
- <span data-ttu-id="56ab1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56ab1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="56ab1-107">Если ваша организация использует [Microsoft 365 Defender,](microsoft-365-defender.md)группа операций безопасности получает оповещение Microsoft 365 центра безопасности при обнаружении вредоносных или подозрительных действий или артефактов.</span><span class="sxs-lookup"><span data-stu-id="56ab1-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="56ab1-108">Учитывая, казалось бы, бесконечный поток угроз, которые могут поступать, группы безопасности часто сталкиваются с проблемой решения большого объема оповещений.</span><span class="sxs-lookup"><span data-stu-id="56ab1-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="56ab1-109">К счастью, Microsoft 365 Defender включает в себя функции автоматического расследования и устранения (AIR), которые помогут вашей группе операций безопасности эффективнее и эффективнее устранять угрозы.</span><span class="sxs-lookup"><span data-stu-id="56ab1-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="56ab1-110">В этой статье представлен обзор air и ссылки на последующие действия и дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="56ab1-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="56ab1-111">Хотите попробовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="56ab1-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="56ab1-112">Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или [запустить пилотный проект в производственной среде](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="56ab1-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="56ab1-113">Как работает автоматизированное исследование и самовосстановления</span><span class="sxs-lookup"><span data-stu-id="56ab1-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="56ab1-114">По мере запуска оповещений о безопасности ваша группа операций безопасности должна инициализации этих оповещений и принять меры для защиты организации.</span><span class="sxs-lookup"><span data-stu-id="56ab1-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="56ab1-115">Определение приоритета и анализ оповещений могут отнимать очень много времени, особенно в условиях постоянного появления новых оповещений во время анализа.</span><span class="sxs-lookup"><span data-stu-id="56ab1-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="56ab1-116">Службы обеспечения безопасности могут быть перегружены из-за огромного количества угроз, которые им нужно отслеживать и от которых необходимо защищать.</span><span class="sxs-lookup"><span data-stu-id="56ab1-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="56ab1-117">Автоматизированные возможности исследования и реагирования, с самовосстановления, в Microsoft 365 Defender может помочь.</span><span class="sxs-lookup"><span data-stu-id="56ab1-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="56ab1-118">Просмотрите следующее видео, чтобы узнать, как работает самовосстановления:</span><span class="sxs-lookup"><span data-stu-id="56ab1-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="56ab1-119">В Microsoft 365 Defender автоматизированные исследования и ответы с помощью функций самовосстановления работают на ваших устройствах, & контенте и удостоверениях.</span><span class="sxs-lookup"><span data-stu-id="56ab1-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="56ab1-120">В этой статье описывается, как работает автоматическое расследование и ответы.</span><span class="sxs-lookup"><span data-stu-id="56ab1-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="56ab1-121">Чтобы настроить эти возможности, см. в перенастройке возможности автоматического расследования и ответа [в Microsoft 365 Defender.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="56ab1-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="56ab1-122">Собственный виртуальный аналитик</span><span class="sxs-lookup"><span data-stu-id="56ab1-122">Your own virtual analyst</span></span>

<span data-ttu-id="56ab1-123">Imagine виртуального аналитика в группе операций по безопасности уровня 1 или 2 уровня.</span><span class="sxs-lookup"><span data-stu-id="56ab1-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="56ab1-124">Виртуальный аналитик имитирует идеальные действия, которые должен предпринять отдел обеспечения безопасности для анализа и устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="56ab1-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="56ab1-125">Виртуальный аналитик может работать в 24x7 с неограниченной емкостью и взять на себя значительную нагрузку исследований и устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="56ab1-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="56ab1-126">Такой виртуальный аналитик может значительно сократить время реагирования, освободив команду операций безопасности для других важных угроз или стратегических проектов.</span><span class="sxs-lookup"><span data-stu-id="56ab1-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="56ab1-127">Если этот сценарий звучит как научная фантастика, это не так!</span><span class="sxs-lookup"><span data-stu-id="56ab1-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="56ab1-128">Такой виртуальный аналитик является частью пакета Microsoft 365 Defender, и его имя — автоматическое исследование *и ответ.*</span><span class="sxs-lookup"><span data-stu-id="56ab1-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="56ab1-129">Возможности автоматического расследования и реагирования позволяют группе операций безопасности значительно увеличить возможности организации по работе с оповещениями о безопасности и инцидентами.</span><span class="sxs-lookup"><span data-stu-id="56ab1-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="56ab1-130">С помощью автоматизированного расследования и реагирования можно снизить затраты на работу с действиями по расследованию и исправлению и получить максимальное количество средств из пакета защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="56ab1-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="56ab1-131">Автоматизированные возможности расследования и реагирования помогают вашей группе по работе с безопасностью:</span><span class="sxs-lookup"><span data-stu-id="56ab1-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="56ab1-132">Определение того, требуется ли угроза действий.</span><span class="sxs-lookup"><span data-stu-id="56ab1-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="56ab1-133">Принятие (или рекомендация) любых необходимых действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="56ab1-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="56ab1-134">Определение того, следует ли и какие другие исследования должны происходить.</span><span class="sxs-lookup"><span data-stu-id="56ab1-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="56ab1-135">повторяет весь этот процесс с другими оповещениями.</span><span class="sxs-lookup"><span data-stu-id="56ab1-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="56ab1-136">Процесс автоматизированного анализа</span><span class="sxs-lookup"><span data-stu-id="56ab1-136">The automated investigation process</span></span>

<span data-ttu-id="56ab1-137">Оповещение создает инцидент, который может начать автоматическое расследование.</span><span class="sxs-lookup"><span data-stu-id="56ab1-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="56ab1-138">Автоматизированное расследование приводит к вынесению вердикта по каждому фрагменту доказательств.</span><span class="sxs-lookup"><span data-stu-id="56ab1-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="56ab1-139">Вердикты могут быть:</span><span class="sxs-lookup"><span data-stu-id="56ab1-139">Verdicts can be:</span></span>
- <span data-ttu-id="56ab1-140">*Злоумышленная*</span><span class="sxs-lookup"><span data-stu-id="56ab1-140">*Malicious*</span></span>
- <span data-ttu-id="56ab1-141">*Подозрительные*</span><span class="sxs-lookup"><span data-stu-id="56ab1-141">*Suspicious*</span></span> 
- <span data-ttu-id="56ab1-142">*Угрозы не найдены*</span><span class="sxs-lookup"><span data-stu-id="56ab1-142">*No threats found*</span></span> 

<span data-ttu-id="56ab1-143">Определены действия по исправлению вредоносных или подозрительных сущностями.</span><span class="sxs-lookup"><span data-stu-id="56ab1-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="56ab1-144">Примеры действий по исправлению:</span><span class="sxs-lookup"><span data-stu-id="56ab1-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="56ab1-145">Отправка файла на карантин</span><span class="sxs-lookup"><span data-stu-id="56ab1-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="56ab1-146">Остановка процесса</span><span class="sxs-lookup"><span data-stu-id="56ab1-146">Stopping a process</span></span>
- <span data-ttu-id="56ab1-147">Изолирование устройства</span><span class="sxs-lookup"><span data-stu-id="56ab1-147">Isolating a device</span></span>
- <span data-ttu-id="56ab1-148">Блокировка URL-адреса</span><span class="sxs-lookup"><span data-stu-id="56ab1-148">Blocking a URL</span></span> 
- <span data-ttu-id="56ab1-149">Другие действия</span><span class="sxs-lookup"><span data-stu-id="56ab1-149">Other actions</span></span>

<span data-ttu-id="56ab1-150">Дополнительные сведения см. в см. в Microsoft 365 [Действия по исправлению.](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="56ab1-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="56ab1-151">В зависимости [от](m365d-configure-auto-investigation-response.md) того, как настраиваются возможности автоматического расследования и реагирования для вашей организации, действия по исправлению будут приниматься автоматически или только после утверждения вашей командой операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="56ab1-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="56ab1-152">Все действия, ожидающих или завершенных, перечислены в [центре действий.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="56ab1-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="56ab1-153">Во время проведения анализа все другие связанные с ним оповещения добавляются в анализ до его завершения.</span><span class="sxs-lookup"><span data-stu-id="56ab1-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="56ab1-154">Если затрагиваемая сущность видна в другом месте, автоматизированное расследование расширяет его область, включая его, и процесс расследования повторяется.</span><span class="sxs-lookup"><span data-stu-id="56ab1-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="56ab1-155">В Microsoft 365 Defender каждое автоматическое расследование коррелирует сигналы в Microsoft Defender for Identity, Microsoft Defender для конечной точки и Microsoft Defender для Office 365, как по сумме в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="56ab1-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="56ab1-156">Объекты</span><span class="sxs-lookup"><span data-stu-id="56ab1-156">Entities</span></span> |<span data-ttu-id="56ab1-157">Службы защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="56ab1-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="56ab1-158">Устройства (также именуемые конечными точками или машинами)</span><span class="sxs-lookup"><span data-stu-id="56ab1-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="56ab1-159">Защитник для конечной точки</span><span class="sxs-lookup"><span data-stu-id="56ab1-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="56ab1-160">Локальное поведение пользователей Active Directory, поведение сущности и действия</span><span class="sxs-lookup"><span data-stu-id="56ab1-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="56ab1-161">Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="56ab1-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="56ab1-162">Содержимое электронной почты (сообщения электронной почты, которые могут содержать файлы и URL-адреса)</span><span class="sxs-lookup"><span data-stu-id="56ab1-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="56ab1-163">Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="56ab1-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="56ab1-164">Не каждое оповещение вызывает автоматическое расследование, и не каждое расследование приводит к автоматическим действиям по исправлению.</span><span class="sxs-lookup"><span data-stu-id="56ab1-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="56ab1-165">Это зависит от настройки автоматического расследования и ответа для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56ab1-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="56ab1-166">См. [в этой версии Настройка возможностей автоматического расследования и ответа.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="56ab1-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="56ab1-167">Просмотр списка расследований</span><span class="sxs-lookup"><span data-stu-id="56ab1-167">Viewing a list of investigations</span></span>

<span data-ttu-id="56ab1-168">Чтобы просмотреть расследования, перейдите на страницу **Происшествия.**</span><span class="sxs-lookup"><span data-stu-id="56ab1-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="56ab1-169">Выберите инцидент и выберите вкладку **"Исследования".** Дополнительные сведения см. [в материале Details and results of an automated investigation.](m365d-autoir-results.md)</span><span class="sxs-lookup"><span data-stu-id="56ab1-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="56ab1-170">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="56ab1-170">Next steps</span></span>

- [<span data-ttu-id="56ab1-171">См. необходимые условия для автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="56ab1-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="56ab1-172">Настройка автоматического расследования и ответа для организации</span><span class="sxs-lookup"><span data-stu-id="56ab1-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="56ab1-173">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="56ab1-173">Learn more about the Action center</span></span>](m365d-action-center.md)
