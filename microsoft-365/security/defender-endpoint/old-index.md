---
title: Защита от угроз (Windows 10)
description: Microsoft Defender для конечной точки — это унифицированная платформа безопасности для конечных точек, которая обеспечивает превентивную защиту, обнаружение после взлома, автоматическое исследования и реагирование.
keywords: защита от угроз, расширенный уровень защиты от угроз Microsoft Defender, уменьшение поверхности атаки, защита следующего поколения, обнаружение конечных точек и реагирование, автоматическое расследование и реагирование, эксперты microsoft threat, Microsoft Secure Score для устройств, передовая охота, охота на киберугрозы, защита от веб-угроз
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 4206519d62feb82bbc297659e01b0cc3902b83dc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069207"
---
# <a name="threat-protection"></a><span data-ttu-id="e71fe-104">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="e71fe-104">Threat Protection</span></span>
<span data-ttu-id="e71fe-105">[Microsoft Defender для конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) — это унифицированная платформа безопасности для конечных точек, которая обеспечивает превентивную защиту, обнаружение после взлома, автоматическое исследования и реагирование.</span><span class="sxs-lookup"><span data-stu-id="e71fe-105">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="e71fe-106">Defender for Endpoint защищает конечные точки от киберугроз, обнаруживает расширенные атаки и нарушения данных, автоматизирует инциденты с безопасностью и улучшает осанку безопасности.</span><span class="sxs-lookup"><span data-stu-id="e71fe-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="e71fe-107">Позволяет пользователям легко получать доступ к облачным службам и приложениям на месте и включить современные возможности управления для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="e71fe-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="e71fe-108">Дополнительные сведения см. в [дополнительных сведениях о безопасности удаленных сотрудников.](https://docs.microsoft.com/enterprise-mobility-security/remote-work/)</span><span class="sxs-lookup"><span data-stu-id="e71fe-108">For more information, see [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="e71fe-109">Microsoft Defender для конечной точки</center></span><span class="sxs-lookup"><span data-stu-id="e71fe-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="e71fe-110"><b>Управление & уязвимостей</b></center></a></span><span class="sxs-lookup"><span data-stu-id="e71fe-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="e71fe-111"><b>Уменьшение поверхности атаки</b></center></a></span><span class="sxs-lookup"><span data-stu-id="e71fe-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="e71fe-112"><b>Защита следующего поколения</b></a></center></span><span class="sxs-lookup"><span data-stu-id="e71fe-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="e71fe-113"><b>Обнаружение конечных точек и реагирование</b></a></center></span><span class="sxs-lookup"><span data-stu-id="e71fe-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="e71fe-114"><b>Автоматическое расследование и исправление</b></a></center></span><span class="sxs-lookup"><span data-stu-id="e71fe-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="e71fe-115"><b>Эксперты по угрозам Майкрософт</b></a></center></span><span class="sxs-lookup"><span data-stu-id="e71fe-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="e71fe-116">
<a href="#apis"><center><b>Централизованная конфигурация и администрирование, API</a></span><span class="sxs-lookup"><span data-stu-id="e71fe-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="e71fe-117"><a href="#mtp"><center><b>Защитник Microsoft 365</a></span><span class="sxs-lookup"><span data-stu-id="e71fe-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="e71fe-118">**[Управление & уязвимостей](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="e71fe-119">Эта встроенная возможность использует подход к обнаружению, приоритетизации и исправлению уязвимостей конечной точки и неправильной оценки с учетом изменения рисков на основе игры.</span><span class="sxs-lookup"><span data-stu-id="e71fe-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="e71fe-120">Обзор управления & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="e71fe-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e71fe-121">Начало работы</span><span class="sxs-lookup"><span data-stu-id="e71fe-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="e71fe-122">Доступ к вашей позе безопасности</span><span class="sxs-lookup"><span data-stu-id="e71fe-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="e71fe-123">Улучшение осанки безопасности и снижение риска</span><span class="sxs-lookup"><span data-stu-id="e71fe-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e71fe-124">Понимание уязвимостей на устройствах</span><span class="sxs-lookup"><span data-stu-id="e71fe-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="e71fe-125">**[Сокращение направлений атак](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="e71fe-126">Набор возможностей уменьшения поверхности атаки обеспечивает первую линию защиты в стеке.</span><span class="sxs-lookup"><span data-stu-id="e71fe-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="e71fe-127">Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, этот набор возможностей позволяет противостоять атакам и эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="e71fe-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="e71fe-128">Изолирование на основе оборудования</span><span class="sxs-lookup"><span data-stu-id="e71fe-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="e71fe-129">Элемент управления приложениями</span><span class="sxs-lookup"><span data-stu-id="e71fe-129">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="e71fe-130">Управление устройствами</span><span class="sxs-lookup"><span data-stu-id="e71fe-130">Device control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="e71fe-131">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="e71fe-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="e71fe-132">[Защита сети,](network-protection.md) [веб-защита](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e71fe-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="e71fe-133">Управляемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="e71fe-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="e71fe-134">Брандмауэр сети</span><span class="sxs-lookup"><span data-stu-id="e71fe-134">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="e71fe-135">Правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="e71fe-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="e71fe-136">**[Защита следующего поколения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-136">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="e71fe-137">Чтобы еще больше усилить периметр безопасности сети, Microsoft Defender для конечной точки использует защиту следующего поколения, предназначенную для улавливания всех типов возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="e71fe-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="e71fe-138">Мониторинг поведения</span><span class="sxs-lookup"><span data-stu-id="e71fe-138">Behavior monitoring</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="e71fe-139">Защита на основе облака</span><span class="sxs-lookup"><span data-stu-id="e71fe-139">Cloud-based protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="e71fe-140">Машинное обучение</span><span class="sxs-lookup"><span data-stu-id="e71fe-140">Machine learning</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="e71fe-141">Защита URL-адресов</span><span class="sxs-lookup"><span data-stu-id="e71fe-141">URL Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="e71fe-142">Автоматическая служба песочницы</span><span class="sxs-lookup"><span data-stu-id="e71fe-142">Automated sandbox service</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="e71fe-143">**[Обнаружение и устранение угроз на конечных точках](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="e71fe-144">Для обнаружения, расследования и реагирования на попытки вторжения и активных нарушений на месте работают возможности обнаружения конечных точек и реагирования на них.</span><span class="sxs-lookup"><span data-stu-id="e71fe-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="e71fe-145">С помощью advanced hunting у вас есть средство охоты на угрозы на основе запросов, которое позволяет упреждающий поиск нарушений и создание настраиваемого обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e71fe-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="e71fe-146">Alerts</span><span class="sxs-lookup"><span data-stu-id="e71fe-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="e71fe-147">Исторические конечные данные</span><span class="sxs-lookup"><span data-stu-id="e71fe-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="e71fe-148">Оркестровка ответов</span><span class="sxs-lookup"><span data-stu-id="e71fe-148">Response orchestration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="e71fe-149">Коллекция судебной экспертизы</span><span class="sxs-lookup"><span data-stu-id="e71fe-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="e71fe-150">Сведения об угрозах</span><span class="sxs-lookup"><span data-stu-id="e71fe-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="e71fe-151">Расширенные службы детонации и анализа</span><span class="sxs-lookup"><span data-stu-id="e71fe-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="e71fe-152">Расширенная охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="e71fe-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="e71fe-153">Настраиваемое обнаружение</span><span class="sxs-lookup"><span data-stu-id="e71fe-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="e71fe-154">**[Автоматическое исследование и защита](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="e71fe-155">Помимо быстрого реагирования на расширенные атаки, Microsoft Defender for Endpoint предлагает возможности автоматического расследования и устранения, которые помогают уменьшить объем оповещений в минутах масштабирования.</span><span class="sxs-lookup"><span data-stu-id="e71fe-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="e71fe-156">Автоматическое исследование и защита</span><span class="sxs-lookup"><span data-stu-id="e71fe-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="e71fe-157">Просмотр сведений и результатов автоматических исследований</span><span class="sxs-lookup"><span data-stu-id="e71fe-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="e71fe-158">Просмотр и утверждение действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="e71fe-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="e71fe-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="e71fe-160">Новая служба управляемой охоты на угрозы в Microsoft Defender для Endpoint предоставляет активную охоту, приоритеты и дополнительные сведения и контекст.</span><span class="sxs-lookup"><span data-stu-id="e71fe-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="e71fe-161">Эксперты Microsoft Threat также наделяет центры операций безопасности (SOCs) возможностями для быстрого и точного реагирования на угрозы.</span><span class="sxs-lookup"><span data-stu-id="e71fe-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="e71fe-162">Целевое уведомление об атаке</span><span class="sxs-lookup"><span data-stu-id="e71fe-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="e71fe-163">Эксперты по запросу</span><span class="sxs-lookup"><span data-stu-id="e71fe-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="e71fe-164">Настройка службы управляемого охотничьего ружья Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e71fe-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="e71fe-165">**[Централизованная конфигурация и администрирование, API](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="e71fe-166">Интеграция Microsoft Defender для конечной точки в существующие процессы.</span><span class="sxs-lookup"><span data-stu-id="e71fe-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="e71fe-167">Адаптация</span><span class="sxs-lookup"><span data-stu-id="e71fe-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="e71fe-168">Интеграция API и SIEM</span><span class="sxs-lookup"><span data-stu-id="e71fe-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="e71fe-169">Открытые API</span><span class="sxs-lookup"><span data-stu-id="e71fe-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="e71fe-170">Управление доступом на основе ролей (RBAC)</span><span class="sxs-lookup"><span data-stu-id="e71fe-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="e71fe-171">Отчеты и тенденции</span><span class="sxs-lookup"><span data-stu-id="e71fe-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="e71fe-172">**[Интеграция с решениями Майкрософт](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="e71fe-173">Microsoft Defender для конечной точки напрямую интегрируется с различными решениями Майкрософт, в том числе:</span><span class="sxs-lookup"><span data-stu-id="e71fe-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="e71fe-174">Intune</span><span class="sxs-lookup"><span data-stu-id="e71fe-174">Intune</span></span>
- <span data-ttu-id="e71fe-175">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="e71fe-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="e71fe-176">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="e71fe-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="e71fe-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="e71fe-177">Azure Defender</span></span>
- <span data-ttu-id="e71fe-178">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e71fe-178">Skype for Business</span></span>
- <span data-ttu-id="e71fe-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e71fe-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="e71fe-180">**[Защитник Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="e71fe-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="e71fe-181">С помощью Microsoft 365 Defender, Microsoft Defender для endpoint и различных решений безопасности Майкрософт формируется единый пакет корпоративной защиты до и после нарушения, который интегрируется в конечную точку, удостоверение, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки.</span><span class="sxs-lookup"><span data-stu-id="e71fe-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>