---
title: Подготовка позиции безопасности к первому инциденту
description: Настройка позы безопасности Microsoft 365 клиента для первого инцидента в Microsoft 365 Defender.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: da9147955c5da9ea727854420b3d4d160583ef73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840939"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="65773-104">Подготовка позиции безопасности к первому инциденту</span><span class="sxs-lookup"><span data-stu-id="65773-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="65773-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="65773-105">**Applies to:**</span></span>
- <span data-ttu-id="65773-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65773-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="65773-107">Подготовка к обработке инцидентов включает создание достаточной защиты сети организации от различных типов инцидентов безопасности.</span><span class="sxs-lookup"><span data-stu-id="65773-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="65773-108">Чтобы снизить риск инцидентов с безопасностью, Национальный институт стандартов и технологий (NIST) рекомендует несколько методов безопасности, включая оценку рисков, ужесточить безопасность хостов, безопасно настраивать сети и предотвращать вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="65773-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="65773-109">Microsoft 365 Defender может помочь в решении нескольких аспектов предотвращения инцидентов:</span><span class="sxs-lookup"><span data-stu-id="65773-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="65773-110">Реализация [нулевой структуры доверия](/security/zero-trust/)</span><span class="sxs-lookup"><span data-stu-id="65773-110">Implementing a [Zero Trust](/security/zero-trust/) framework</span></span>
- <span data-ttu-id="65773-111">Определение позиции безопасности, назначив оценку с [помощью Microsoft Secure Score](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="65773-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="65773-112">Предотвращение угроз с помощью оценок уязвимости в [управлении угрозами и уязвимостью](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="65773-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="65773-113">Понимание последних угроз безопасности, чтобы вы могли подготовиться к ним</span><span class="sxs-lookup"><span data-stu-id="65773-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="65773-114">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="65773-114">Step 1.</span></span> <span data-ttu-id="65773-115">Реализация нулевого доверия</span><span class="sxs-lookup"><span data-stu-id="65773-115">Implement Zero Trust</span></span>

<span data-ttu-id="65773-116">[Zero Trust](/security/zero-trust/) — это интегрированная философия безопасности и целостная стратегия, учитывая сложный характер любой современной среды, включая рабочую силу мобильных устройств и пользователей, устройства, приложения и данные, где бы они ни находились.</span><span class="sxs-lookup"><span data-stu-id="65773-116">[Zero Trust](/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="65773-117">Предоставляя единую стеклянную области для согласованного управления всеми обнаружениями, Microsoft 365 Defender может упростить для вашей группы [](/security/zero-trust/#guiding-principles-of-zero-trust) операций безопасности реализацию руководящих принципов Zero Trust.</span><span class="sxs-lookup"><span data-stu-id="65773-117">By providing a single pane of glass to manage all detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="65773-118">Компоненты Microsoft 365 Defender могут отображать нарушения правил, которые были реализованы для создания политик условного доступа для Zero Trust путем интеграции данных из Microsoft Defender для конечной точки (MDE) или других поставщиков мобильной безопасности в качестве источника информации для политик соответствия требованиям устройств и реализации политик условного доступа на основе устройств.</span><span class="sxs-lookup"><span data-stu-id="65773-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="65773-119">Риск устройства напрямую влияет на то, какие ресурсы будут доступны пользователю этого устройства.</span><span class="sxs-lookup"><span data-stu-id="65773-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="65773-120">Отказ в доступе к ресурсам на основе определенных критериев является основной темой Zero Trust и Microsoft 365 Defender предоставляет сведения, необходимые для определения критериев уровня доверия.</span><span class="sxs-lookup"><span data-stu-id="65773-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="65773-121">Например, Microsoft 365 Defender может предоставлять уровень версии программного обеспечения устройства через страницу Управления угрозами и уязвимостью, а политики условного доступа ограничивают устройства с устаревшими или уязвимыми версиями.</span><span class="sxs-lookup"><span data-stu-id="65773-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="65773-122">Автоматизация является важной частью реализации и поддержания среды нулевого доверия, а также сокращения количества оповещений, которые потенциально могут привести к событиям реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="65773-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="65773-123">Компоненты Microsoft 365 Defender можно автоматизировать, такие [](m365d-autoir.md) как действия по исправлению (известные как расследования инцидента в центре безопасности Microsoft 365), действия уведомления и даже создание билетов поддержки, таких как [ServiceNow](https://microsoft.service-now.com/sp/).</span><span class="sxs-lookup"><span data-stu-id="65773-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="65773-124">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="65773-124">Step 2.</span></span> <span data-ttu-id="65773-125">Определение позиции безопасности организации</span><span class="sxs-lookup"><span data-stu-id="65773-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="65773-126">Далее организации могут использовать microsoft [Secure Score](microsoft-secure-score.md) в Microsoft 365 Defender, чтобы определить текущую позицию безопасности и рассмотреть рекомендации по ее улучшению.</span><span class="sxs-lookup"><span data-stu-id="65773-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="65773-127">Чем выше оценка, тем больше рекомендаций по безопасности и действий по улучшению было принято организацией.</span><span class="sxs-lookup"><span data-stu-id="65773-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="65773-128">Рекомендации по безопасной оценке можно использовать для различных продуктов и позволяют организациям повышать свои оценки еще выше.</span><span class="sxs-lookup"><span data-stu-id="65773-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Пример показателей безопасности Майкрософт в центре безопасности Майкрософт":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="65773-130">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="65773-130">Step 3.</span></span> <span data-ttu-id="65773-131">Оценка уязвимости организации</span><span class="sxs-lookup"><span data-stu-id="65773-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="65773-132">Предотвращение инцидентов может помочь оптимизировать усилия по обеспечению безопасности, чтобы сосредоточиться на критически важных и важных инцидентах безопасности.</span><span class="sxs-lookup"><span data-stu-id="65773-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="65773-133">Уязвимости программного обеспечения часто являются предотвратимой точкой входа для атак, которые могут привести к краже данных, потере данных или нарушению бизнес-операций.</span><span class="sxs-lookup"><span data-stu-id="65773-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="65773-134">Если не происходит никаких атак, операции безопасности должны стремиться к достижению и поддержанию приемлемого уровня уязвимости [в](../defender-endpoint/tvm-exposure-score.md) своей организации.</span><span class="sxs-lookup"><span data-stu-id="65773-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="65773-135">Чтобы проверить ход исправления программного [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) обеспечения, посетите страницу Управления угрозами и уязвимостью в Defender for Endpoint, к которой можно получить доступ из Microsoft 365 Defender через вкладку **More resources.**</span><span class="sxs-lookup"><span data-stu-id="65773-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Пример страницы &quot;Угроза и уязвимость&quot; в центре безопасности Майкрософт"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="65773-137">4. Понимание возникающих угроз</span><span class="sxs-lookup"><span data-stu-id="65773-137">4. Understand emerging threats</span></span>

<span data-ttu-id="65773-138">Используйте [аналитику угроз](threat-analytics.md) в центре Microsoft 365 безопасности, чтобы быть в курсе текущего ландшафта угроз безопасности.</span><span class="sxs-lookup"><span data-stu-id="65773-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="65773-139">Специалисты по безопасности Майкрософт создают отчеты, в них подробно описываются последние киберугрозы, чтобы вы могли понять, как они могут повлиять на Microsoft 365 подписку, устройства и пользователей.</span><span class="sxs-lookup"><span data-stu-id="65773-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="65773-140">Эти отчеты могут включать:</span><span class="sxs-lookup"><span data-stu-id="65773-140">These reports can include:</span></span>

- <span data-ttu-id="65773-141">Активные субъекты угроз и их кампании</span><span class="sxs-lookup"><span data-stu-id="65773-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="65773-142">Популярные и новые методы атаки</span><span class="sxs-lookup"><span data-stu-id="65773-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="65773-143">Критические уязвимости</span><span class="sxs-lookup"><span data-stu-id="65773-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="65773-144">Общие поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="65773-144">Common attack surfaces</span></span>
- <span data-ttu-id="65773-145">Распространенные вредоносные программы</span><span class="sxs-lookup"><span data-stu-id="65773-145">Prevalent malware</span></span>

<span data-ttu-id="65773-146">Аналитика угроз также рассматривает конфигурацию и оповещений, чтобы определить, насколько вы рискуете и есть ли активные оповещения, применимые к отчету.</span><span class="sxs-lookup"><span data-stu-id="65773-146">Threat analytics also looks at your configuration and alerts to determine how at-risk you are and if there are active alerts applicable to a report.</span></span>

<span data-ttu-id="65773-147">Вы можете реализовать рекомендации появляющейся угрозы, чтобы укрепить осанку безопасности и свести к минимуму область поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="65773-147">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="65773-148">Уделайте время в расписании, чтобы регулярно проверять раздел [Threat Analytics](threat-analytics.md) центра Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="65773-148">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="65773-149">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="65773-149">Next step</span></span>

<span data-ttu-id="65773-150">[![Шаг 1. Узнайте, как анализировать и анализировать инциденты](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="65773-150">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="65773-151">Узнайте, как анализировать и анализировать [инциденты.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="65773-151">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65773-152">См. также</span><span class="sxs-lookup"><span data-stu-id="65773-152">See also</span></span>

- [<span data-ttu-id="65773-153">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="65773-153">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="65773-154">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="65773-154">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="65773-155">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="65773-155">Manage incidents</span></span>](manage-incidents.md)
