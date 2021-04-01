---
title: Перенос из Symantec в Microsoft Defender для конечной точки
description: Сведения о том, как перейти из Symantec в Microsoft Defender для конечной точки
keywords: миграция, защита от угроз защитника Windows, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218804"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="5c6bc-104">Перенос из Symantec в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5c6bc-104">Migrate from Symantec to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="5c6bc-105">Если вы планируете перейти с Symantec Endpoint Protection (Symantec) на [Microsoft Defender для](https://docs.microsoft.com/windows/security/threat-protection) конечной точки (Microsoft Defender для конечной точки), вы находитесь в правильном месте.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-105">If you are planning to switch from Symantec Endpoint Protection (Symantec) to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="5c6bc-106">Используйте эту статью в качестве руководства.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-106">Use this article as a guide.</span></span>

<span data-ttu-id="5c6bc-107">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-107">**Applies to:**</span></span>
- [<span data-ttu-id="5c6bc-108">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5c6bc-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c6bc-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c6bc-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Обзор переноса из Symantec в Defender для конечной точки":::

<span data-ttu-id="5c6bc-111">При переходе от Symantec к Defender для endpoint вы начинаете с решения Symantec в активном режиме, настраиваете Defender для конечной точки в пассивном режиме, на борту в Defender для конечной точки, а затем установите Defender for Endpoint в активный режим и удалите Symantec.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-111">When you make the switch from Symantec to Defender for Endpoint, you begin with your Symantec solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove Symantec.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="5c6bc-112">Процесс миграции</span><span class="sxs-lookup"><span data-stu-id="5c6bc-112">The migration process</span></span>

<span data-ttu-id="5c6bc-113">При переходе из Symantec в Microsoft Defender для конечной точки следует процесс, который можно разделить на три этапа, как описано в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="5c6bc-113">When you switch from Symantec to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![Этапы миграции — подготовка, настройка, бортовой](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="5c6bc-115">Этап</span><span class="sxs-lookup"><span data-stu-id="5c6bc-115">Phase</span></span> |<span data-ttu-id="5c6bc-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5c6bc-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="5c6bc-117">Подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="5c6bc-117">Prepare for your migration</span></span>](symantec-to-microsoft-defender-atp-prepare.md) |<span data-ttu-id="5c6bc-118">На **этапе Подготовки** вы получите Microsoft Defender для конечной точки, спланируйте роли и разрешения и получите доступ к Центру безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-118">During the **Prepare** phase, you get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="5c6bc-119">Вы также настройте прокси-сервер устройства и параметры Интернета, чтобы включить связь между устройствами организации и Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="5c6bc-120">Настройка Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5c6bc-120">Set up Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-setup.md) |<span data-ttu-id="5c6bc-121">На **этапе установки** настраиваются параметры и исключения для антивируса Microsoft Defender, Microsoft Defender для конечной точки и защиты конечных точек Symantec.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-121">During the **Setup** phase, you configure settings and exclusions for Microsoft Defender Antivirus, Microsoft Defender for Endpoint, and Symantec Endpoint Protection.</span></span> <span data-ttu-id="5c6bc-122">Вы также создаете группы устройств, коллекции и организационные подразделения.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-122">You also create device groups, collections, and organizational units.</span></span> <span data-ttu-id="5c6bc-123">Наконец, настраиваются политики защиты от антивирусных программ и параметры защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-123">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="5c6bc-124">Onboard to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c6bc-124">Onboard to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-onboard.md) |<span data-ttu-id="5c6bc-125">На **этапе onboard** вы на борту устройств в Microsoft Defender для конечной точки и убедитесь, что эти устройства общаются с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-125">During the **Onboard** phase, you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5c6bc-126">Наконец, необходимо удалить Symantec и убедиться, что защита через Microsoft Defender для конечной точки находится в активном режиме.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-126">Last, you uninstall Symantec and make sure protection through Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="5c6bc-127">Что включено в Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5c6bc-127">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="5c6bc-128">В этом руководстве по [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) миграции основное внимание уделяется возможностям обнаружения и реагирования конечных точек следующего поколения в качестве отправной точки для перехода в Microsoft Defender для конечной точки. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)</span><span class="sxs-lookup"><span data-stu-id="5c6bc-128">In this migration guide, we focus on [next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) and [endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5c6bc-129">Тем не менее, Microsoft Defender для конечной точки включает в себя гораздо больше, чем антивирусная и конечная точка защиты.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-129">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="5c6bc-130">Microsoft Defender для конечной точки — это унифицированная платформа безопасности для конечных точек, которая обеспечивает превентивную защиту, обнаружение после взлома, автоматическое исследования и реагирование.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-130">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="5c6bc-131">В следующей таблице обобщены функции и возможности в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-131">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="5c6bc-132">Feature/Capability</span><span class="sxs-lookup"><span data-stu-id="5c6bc-132">Feature/Capability</span></span> | <span data-ttu-id="5c6bc-133">Описание</span><span class="sxs-lookup"><span data-stu-id="5c6bc-133">Description</span></span> |
|---|---|
| [<span data-ttu-id="5c6bc-134">Управление & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="5c6bc-134">Threat & vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | <span data-ttu-id="5c6bc-135">Возможности управления & уязвимостей помогают выявлять, оценивать и устранять недостатки в конечных точках (например, устройствах).</span><span class="sxs-lookup"><span data-stu-id="5c6bc-135">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="5c6bc-136">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="5c6bc-136">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | <span data-ttu-id="5c6bc-137">Правила уменьшения поверхности атаки помогают защитить устройства и приложения организации от киберугроз и атак.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-137">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="5c6bc-138">Защита следующего поколения</span><span class="sxs-lookup"><span data-stu-id="5c6bc-138">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | <span data-ttu-id="5c6bc-139">Защита следующего поколения включает антивирус Microsoft Defender, который помогает блокировать угрозы и вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-139">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="5c6bc-140">Обнаружение и устранение угроз на конечных точках</span><span class="sxs-lookup"><span data-stu-id="5c6bc-140">Endpoint detection and response</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | <span data-ttu-id="5c6bc-141">Возможности обнаружения и реагирования конечной точки обнаруживают, исследуют и реагируют на попытки вторжения и активные нарушения.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-141">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="5c6bc-142">Расширенная охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="5c6bc-142">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="5c6bc-143">Расширенные возможности охоты позволяют группе операций безопасности находить индикаторы и объекты известных или потенциальных угроз.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-143">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="5c6bc-144">Блокировка и сдерживание поведения</span><span class="sxs-lookup"><span data-stu-id="5c6bc-144">Behavioral blocking and containment</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | <span data-ttu-id="5c6bc-145">Возможности поведенческой блокировки и сдерживания помогают выявлять и останавливать угрозы, основываясь на их поведении и деревьях обработки даже при выполнении угрозы.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-145">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="5c6bc-146">Автоматическое исследование и защита</span><span class="sxs-lookup"><span data-stu-id="5c6bc-146">Automated investigation and remediation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | <span data-ttu-id="5c6bc-147">Возможности автоматического расследования и реагирования проверяют оповещения и принимают незамедлительных действий по устранению нарушений.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-147">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="5c6bc-148">[Служба охоты на угрозы](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Эксперты по угрозам Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="5c6bc-148">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="5c6bc-149">Службы охоты на угрозы предоставляют группам операций безопасности мониторинг и анализ на уровне экспертов, а также для обеспечения того, чтобы критические угрозы не были пропущены.</span><span class="sxs-lookup"><span data-stu-id="5c6bc-149">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="5c6bc-150">**Хотите узнать больше? См. [в веб-сайте Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection).**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-150">**Want to learn more? See [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span></span>

## <a name="next-step"></a><span data-ttu-id="5c6bc-151">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="5c6bc-151">Next step</span></span>

- <span data-ttu-id="5c6bc-152">Приступить к [подготовке к миграции](symantec-to-microsoft-defender-atp-prepare.md).</span><span class="sxs-lookup"><span data-stu-id="5c6bc-152">Proceed to [Prepare for your migration](symantec-to-microsoft-defender-atp-prepare.md).</span></span>