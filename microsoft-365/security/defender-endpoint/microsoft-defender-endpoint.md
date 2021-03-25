---
title: Microsoft Defender для конечной точки
description: Microsoft Defender для конечной точки — это платформа безопасности конечной точки предприятия, которая помогает защититься от сложных постоянных угроз.
keywords: введение в Microsoft Defender для конечной точки, введение в Microsoft Defender Advanced Threat Protection, введение в Microsoft Defender ATP, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, датчик поведения машины, облачная безопасность, аналитика, разведка угроз, уменьшение поверхности атак, защита от атак следующего поколения, автоматическое расследование и исправление, эксперты microsoft threat, безопасный результат, расширенный уровень охоты, защита от угроз Майкрософт, охота на киберугрозы
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8c5d02a4d76ae7e031ad9f3af0db282cc4cb45ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187319"
---
# <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="96744-104">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="96744-104">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="96744-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="96744-105">**Applies to:**</span></span>
- [<span data-ttu-id="96744-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="96744-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96744-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96744-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="96744-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="96744-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="96744-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="96744-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> <span data-ttu-id="96744-110">Дополнительные сведения о возможностях и функциях Windows 10 Enterprise Edition см. в [выпуске Windows 10 Enterprise.](https://www.microsoft.com/WindowsForBusiness/buy)</span><span class="sxs-lookup"><span data-stu-id="96744-110">For more info about Windows 10 Enterprise Edition features and functionality, see [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span></span>

<span data-ttu-id="96744-111">Microsoft Defender for Endpoint — это корпоративная платформа безопасности конечной точки, предназначенная для предотвращения, обнаружения, обнаружения, обнаружения и реагирования на расширенные угрозы.</span><span class="sxs-lookup"><span data-stu-id="96744-111">Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span>
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

<span data-ttu-id="96744-112">Defender for Endpoint использует следующую комбинацию технологий, встроенных в Windows 10 и надежную облачную службу Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="96744-112">Defender for Endpoint uses the following combination of technology built into Windows 10 and Microsoft's robust cloud service:</span></span>

-   <span data-ttu-id="96744-113">Датчики поведения конечной точки. Встроенные в Windows 10, эти датчики собирают и обрабатывает поведенческие сигналы из операционной системы и отправляют эти данные датчика в частный изолированный облачный экземпляр Microsoft Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="96744-113">**Endpoint behavioral sensors**: Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and send this sensor data to your private, isolated, cloud instance of Microsoft Defender for Endpoint.</span></span>


-   <span data-ttu-id="96744-114">Аналитика облачной **безопасности:** использование больших данных, обучения устройствам и уникальной оптики Microsoft в экосистеме Windows, корпоративных облачных продуктов (например, Office 365) и сетевых активов, поведенческие сигналы преобразуются в аналитические сведения, обнаружения и рекомендуемые ответы на расширенные угрозы.</span><span class="sxs-lookup"><span data-stu-id="96744-114">**Cloud security analytics**: Leveraging big-data, device-learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products (such as Office 365), and online assets, behavioral signals are translated into insights, detections, and recommended responses to advanced threats.</span></span>

-   <span data-ttu-id="96744-115">Сведения об угрозах. Созданные охотниками Майкрософт, группами безопасности и дополненные сведениями об угрозах, предоставляемыми партнерами, сведения об угрозах позволяют Defender for Endpoint определять средства, методы и процедуры злоумышленника, а также создавать оповещения при их наблюдении в собранных данных датчиков.</span><span class="sxs-lookup"><span data-stu-id="96744-115">**Threat intelligence**: Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.</span></span>

<center><h2><span data-ttu-id="96744-116">Microsoft Defender для конечной точки</center></span><span class="sxs-lookup"><span data-stu-id="96744-116">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><span data-ttu-id="96744-117"><b>Управление & уязвимостей</b></center></a></span><span class="sxs-lookup"><span data-stu-id="96744-117"><b>Threat & Vulnerability Management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><span data-ttu-id="96744-118"><b>Уменьшение поверхности атаки</b></center></a></span><span class="sxs-lookup"><span data-stu-id="96744-118"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <span data-ttu-id="96744-119"><b>Защита следующего поколения</b></a></center></span><span class="sxs-lookup"><span data-stu-id="96744-119"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <span data-ttu-id="96744-120"><b>Обнаружение конечных точек и реагирование</b></a></center></span><span class="sxs-lookup"><span data-stu-id="96744-120"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <span data-ttu-id="96744-121"><b>Автоматическое расследование и исправление</b></a></center></span><span class="sxs-lookup"><span data-stu-id="96744-121"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <span data-ttu-id="96744-122"><b>Эксперты по угрозам Майкрософт</b></a></center></span><span class="sxs-lookup"><span data-stu-id="96744-122"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="96744-123">
<a href="#apis"><center><b>Централизованная конфигурация и администрирование, API</a></span><span class="sxs-lookup"><span data-stu-id="96744-123">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="96744-124"><a href="#mtp"><center><b>Защита от угроз Майкрософт</a></span><span class="sxs-lookup"><span data-stu-id="96744-124"><a href="#mtp"><center><b>Microsoft Threat Protection</a></span></span></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - <span data-ttu-id="96744-125">Узнайте о последних улучшениях в Defender для конечной точки: что нового в [Microsoft Defender для конечной точки](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="96744-125">Learn about the latest enhancements in Defender for Endpoint: [What's new in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
> - <span data-ttu-id="96744-126">В недавней оценке MITRE Microsoft Defender for Endpoint продемонстрировала передовые в отрасли возможности оптики и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="96744-126">Microsoft Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="96744-127">Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="96744-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<a name="tvm"></a>

<span data-ttu-id="96744-128">**[Управление & уязвимостей](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="96744-129">Эта встроенная возможность использует подход к обнаружению, приоритетизации и исправлению уязвимостей конечной точки и неправильной оценки с учетом изменения рисков на основе игры.</span><span class="sxs-lookup"><span data-stu-id="96744-129">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span> 

<a name="asr"></a>

<span data-ttu-id="96744-130">**[Сокращение направлений атак](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-130">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="96744-131">Набор возможностей уменьшения поверхности атаки обеспечивает первую линию защиты в стеке.</span><span class="sxs-lookup"><span data-stu-id="96744-131">The attack surface reduction set of capabilities provides the first line of defense in the stack.</span></span> <span data-ttu-id="96744-132">Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, возможности сопротивляются атакам и эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="96744-132">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, the capabilities resist attacks and exploitation.</span></span> <span data-ttu-id="96744-133">Этот набор возможностей также [](network-protection.md) включает защиту сети и [веб-защиту,](web-protection-overview.md)которые регулируют доступ к вредоносным IP-адресам, доменам и URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="96744-133">This set of capabilities also includes [network protection](network-protection.md) and [web protection](web-protection-overview.md), which regulate access to malicious IP addresses, domains, and URLs.</span></span> 

<a name="ngp"></a>

<span data-ttu-id="96744-134">**[Защита следующего поколения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="96744-134">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="96744-135">Чтобы еще больше усилить периметр безопасности сети, Microsoft Defender для конечной точки использует защиту следующего поколения, предназначенную для улавливания всех типов возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="96744-135">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

<a name="edr"></a>

<span data-ttu-id="96744-136">**[Обнаружение и устранение угроз на конечных точках](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-136">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="96744-137">Для обнаружения, расследования и реагирования на расширенные угрозы, которые могли оказаться за первыми двумя столпами безопасности, вложены возможности обнаружения конечных точек и их реагирования.</span><span class="sxs-lookup"><span data-stu-id="96744-137">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to advanced threats that may have made it past the first two security pillars.</span></span> <span data-ttu-id="96744-138">[Расширенный способ охоты](advanced-hunting-overview.md) предоставляет средство для поиска угроз на основе запросов, которое позволяет упреждающий поиск нарушений и создание настраиваемого обнаружения.</span><span class="sxs-lookup"><span data-stu-id="96744-138">[Advanced hunting](advanced-hunting-overview.md) provides a query-based threat-hunting tool that lets you proactively find breaches and create custom detections.</span></span>

<a name="ai"></a>

<span data-ttu-id="96744-139">**[Автоматическое исследование и защита](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-139">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="96744-140">В сочетании с возможностью быстрого реагирования на расширенные атаки Microsoft Defender for Endpoint предлагает возможности автоматического расследования и устранения, которые помогают уменьшить объем оповещений в минутах масштабирования.</span><span class="sxs-lookup"><span data-stu-id="96744-140">In conjunction with being able to quickly respond to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span> 

<a name="ss"></a>

<span data-ttu-id="96744-141">**[Microsoft Secure Score для устройств](tvm-microsoft-secure-score-devices.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span></span><br>

<span data-ttu-id="96744-142">Defender for Endpoint включает microsoft Secure Score for Devices, чтобы помочь вам динамически оценить состояние безопасности корпоративной сети, определить незащищенные системы и принять рекомендуемые действия для повышения общей безопасности организации.</span><span class="sxs-lookup"><span data-stu-id="96744-142">Defender for Endpoint includes Microsoft Secure Score for Devices to help you dynamically assess the security state of your enterprise network, identify unprotected systems, and take recommended actions to improve the overall security of your organization.</span></span>

<a name="mte"></a>

<span data-ttu-id="96744-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="96744-144">Новая служба управляемой охоты на угрозы Microsoft Defender для конечной точки обеспечивает активную охоту, приоритеты и дополнительные сведения, которые расширяют возможности центров операций безопасности (SOCs) для быстрого и точного реагирования на угрозы.</span><span class="sxs-lookup"><span data-stu-id="96744-144">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights that further empower Security operation centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

>[!IMPORTANT]
><span data-ttu-id="96744-145">Защитник для клиентов конечных точек должен обратиться в службу управляемой охоты на угрозы microsoft Threat Experts для получения активных уведомлений о целевых атаках и для совместной работы с экспертами по запросу.</span><span class="sxs-lookup"><span data-stu-id="96744-145">Defender for Endpoint customers need to apply for the Microsoft Threat Experts managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand.</span></span> <span data-ttu-id="96744-146">Эксперты по запросу — это служба надстройки.</span><span class="sxs-lookup"><span data-stu-id="96744-146">Experts on Demand is an add-on service.</span></span> <span data-ttu-id="96744-147">Целевые уведомления о атаке всегда включаются после того, как вы были приняты в службу управляемых угроз Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="96744-147">Targeted Attack Notifications are always included after you have been accepted into Microsoft Threat Experts managed threat hunting service.</span></span><p>
><p><span data-ttu-id="96744-148">Если вы еще не зарегистрированы и хотите испытать его преимущества, перейдите в <b>параметры</b> > <b>Общие</b> > <b></b> расширенные функции > <b>Microsoft Threat Experts</b> для применения.</span><span class="sxs-lookup"><span data-stu-id="96744-148">If you are not enrolled yet and would like to experience its benefits, go to <b>Settings</b> > <b>General</b> > <b>Advanced features</b> > <b>Microsoft Threat Experts</b> to apply.</span></span> <span data-ttu-id="96744-149">После его 30-дневного использования вы получите преимущества целевых уведомлений об атаке и запустите 90-дневную пробную работу экспертов по запросу.</span><span class="sxs-lookup"><span data-stu-id="96744-149">Once accepted, you will get the benefits of Targeted Attack Notifications, and start a  90-day trial of Experts on Demand.</span></span> <span data-ttu-id="96744-150">Свяжитесь со своим представителем Майкрософт, чтобы получить полный список экспертов по подписке На запрос.</span><span class="sxs-lookup"><span data-stu-id="96744-150">Contact your Microsoft representative to get a full Experts on Demand subscription.</span></span>

<a name="apis"></a>

<span data-ttu-id="96744-151">**[Централизованная конфигурация и администрирование, API](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-151">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="96744-152">Интеграция Microsoft Defender для конечной точки в существующие процессы.</span><span class="sxs-lookup"><span data-stu-id="96744-152">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>

<a name="mtp"></a>

<span data-ttu-id="96744-153">**[Интеграция с решениями Майкрософт](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="96744-153">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
<span data-ttu-id="96744-154">Defender for Endpoint напрямую интегрируется с различными решениями Майкрософт, в том числе:</span><span class="sxs-lookup"><span data-stu-id="96744-154">Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="96744-155">Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="96744-155">Azure Security Center</span></span>
- <span data-ttu-id="96744-156">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="96744-156">Azure Sentinel</span></span>
- <span data-ttu-id="96744-157">Intune</span><span class="sxs-lookup"><span data-stu-id="96744-157">Intune</span></span>
- <span data-ttu-id="96744-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="96744-158">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="96744-159">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="96744-159">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="96744-160">Microsoft Defender для Office</span><span class="sxs-lookup"><span data-stu-id="96744-160">Microsoft Defender for Office</span></span>
- <span data-ttu-id="96744-161">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="96744-161">Skype for Business</span></span>

<span data-ttu-id="96744-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="96744-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
<span data-ttu-id="96744-163">С помощью Microsoft 365 Defender, Defender for Endpoint и различных решений безопасности Майкрософт формируется единый пакет корпоративной защиты до и после нарушения, который интегрируется в конечную точку, удостоверение, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки.</span><span class="sxs-lookup"><span data-stu-id="96744-163">With Microsoft 365 Defender, Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>


## <a name="related-topic"></a><span data-ttu-id="96744-164">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="96744-164">Related topic</span></span>
[<span data-ttu-id="96744-165">Microsoft Defender для конечной точки помогает обнаруживать сложные угрозы</span><span class="sxs-lookup"><span data-stu-id="96744-165">Microsoft Defender for Endpoint helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
