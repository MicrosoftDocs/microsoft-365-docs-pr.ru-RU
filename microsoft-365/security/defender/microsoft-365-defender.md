---
title: Microsoft 365 Defender
description: Microsoft 365 Defender — это скоординированное решение защиты от угроз, предназначенное для защиты устройств, удостоверений, данных и приложений.
keywords: введение в Microsoft Threat Protection, кибербезопасность, расширенные постоянные угрозы, корпоративная безопасность, устройства, устройства, удостоверения, пользователи, данные, приложения, инциденты, автоматическое расследование и исправление, расширенный поиск
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f789053e0922ee81155a243bbaa7b3ab5b0f6d87
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072694"
---
# <a name="microsoft-365-defender"></a><span data-ttu-id="81cd2-104">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81cd2-104">Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81cd2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="81cd2-105">**Applies to:**</span></span>
- <span data-ttu-id="81cd2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81cd2-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="81cd2-107">Хотите испытать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="81cd2-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="81cd2-108">Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или запустить [пилотный проект в производстве.](m365d-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="81cd2-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="81cd2-109">Microsoft 365 Defender — это единый пакет защиты предприятия до и после взлома, который встроенным образом координирует обнаружение, предотвращение, расследование и реагирование между конечными точками, удостоверениями, электронной почтой и приложениями для обеспечения интегрированной защиты от комплексных атак.</span><span class="sxs-lookup"><span data-stu-id="81cd2-109">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span>

<span data-ttu-id="81cd2-110">С интегрированным решением Microsoft 365 Defender специалисты по безопасности могут сшить вместе сигналы угрозы, получаемые каждым из этих продуктов, и определить полный охват и влияние угрозы; как он вошел в среду, на что она влияет, и как она в настоящее время влияет на организацию.</span><span class="sxs-lookup"><span data-stu-id="81cd2-110">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that each of these products receive and determine the full scope and impact of the threat; how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="81cd2-111">Microsoft 365 Defender принимает автоматические меры для предотвращения или остановки атаки и самостоятельного заживления затронутых почтовых ящиков, конечных точек и удостоверений пользователей.</span><span class="sxs-lookup"><span data-stu-id="81cd2-111">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span>  


<center><h2><span data-ttu-id="81cd2-112">Службы Microsoft 365 Defender</center></span><span class="sxs-lookup"><span data-stu-id="81cd2-112">Microsoft 365 Defender services</center></span></span></h2>
<table><tr><td><span data-ttu-id="81cd2-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender для конечной точки</b></center></span><span class="sxs-lookup"><span data-stu-id="81cd2-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></span></span></a></td>
<td><span data-ttu-id="81cd2-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender для Office 365</b></center></span><span class="sxs-lookup"><span data-stu-id="81cd2-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></span></span></a></td>
<td><span data-ttu-id="81cd2-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Защитник Майкрософт для удостоверения</b></a></center></span><span class="sxs-lookup"><span data-stu-id="81cd2-115"><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></span></span></td>
<td><span data-ttu-id="81cd2-116"><center><b><a href="/cloud-app-security/"><b>Безопасность облачных приложений Майкрософт</b></a></center></span><span class="sxs-lookup"><span data-stu-id="81cd2-116"><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span></span></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a><span data-ttu-id="81cd2-117">Интерактивное руководство Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81cd2-117">Microsoft 365 Defender interactive guide</span></span>

<span data-ttu-id="81cd2-118">В этом интерактивном руководстве вы узнаете, как защитить свою организацию с помощью Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="81cd2-118">In this interactive guide, you'll learn how to protect your organization with Microsoft 365 Defender.</span></span> <span data-ttu-id="81cd2-119">Вы увидите, как Microsoft 365 Defender может помочь вам обнаруживать риски безопасности, расследовать атаки в организации и автоматически предотвращать вредные действия.</span><span class="sxs-lookup"><span data-stu-id="81cd2-119">You'll see how Microsoft 365 Defender can help you detect security risks, investigate attacks to your organization, and prevent harmful activities automatically.</span></span>

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



<span data-ttu-id="81cd2-120">С набором приложений Microsoft 365 Defender защищены:</span><span class="sxs-lookup"><span data-stu-id="81cd2-120">Microsoft 365 Defender suite protects:</span></span> 
- <span data-ttu-id="81cd2-121">**Конечные** точки с Microsoft Defender для конечной точки — Microsoft Defender для конечной точки — это единая конечная платформа для профилактической защиты, обнаружения после нарушения, автоматического расследования и ответа.</span><span class="sxs-lookup"><span data-stu-id="81cd2-121">**Endpoints with Microsoft Defender for Endpoint** - Microsoft Defender for Endpoint is a unified endpoint platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> 
- <span data-ttu-id="81cd2-122">Электронная почта и совместная работа с **Microsoft Defender для Office 365** — Defender for Office 365 защищает организацию от вредоносных угроз, создаваемых электронными сообщениями, ссылками (URL-адресами) и средствами совместной работы.</span><span class="sxs-lookup"><span data-stu-id="81cd2-122">**Email and collaboration with Microsoft Defender for Office 365** - Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools.</span></span> 
- <span data-ttu-id="81cd2-123">Удостоверения с помощью Microsoft Defender для удостоверений и **Azure AD Identity Protection** — Microsoft Defender for Identity использует сигналы Active Directory для идентификации, обнаружения и расследования расширенных угроз, скомпрометированных удостоверений и вредоносных действий инсайдеров, направленных в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="81cd2-123">**Identities with Microsoft Defender for Identity and Azure AD Identity Protection** - Microsoft Defender for Identity uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="81cd2-124">Приложения с **безопасностью облачных** приложений Microsoft Cloud App — это комплексное решение cross-SaaS, которое позволяет получить глубокую видимость, усилить управление данными и повысить защиту от угроз в облачных приложениях.</span><span class="sxs-lookup"><span data-stu-id="81cd2-124">**Applications with Microsoft Cloud App security** - Microsoft Cloud App security is a comprehensive cross-SaaS solution bringing deep visibility, strong data controls, and enhanced threat protection to your cloud apps.</span></span> 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

<span data-ttu-id="81cd2-125">Уникальный меж продуктовый слой Microsoft 365 Defender дополняет отдельные компоненты пакета:</span><span class="sxs-lookup"><span data-stu-id="81cd2-125">Microsoft 365 Defender's unique cross-product layer augments the individual suite components to:</span></span>
- <span data-ttu-id="81cd2-126">Помощь в защите от атак и координации защитных ответов в наборе с помощью обмена сигналами и автоматизированных действий</span><span class="sxs-lookup"><span data-stu-id="81cd2-126">Help protect against attacks and coordinate defensive responses across the suite through signal sharing and automated actions</span></span>
- <span data-ttu-id="81cd2-127">Повествуем полную версию об атаке на группы безопасности, в том что касается оповещений, поведения и контекста продуктов, присоединив данные о оповещениях, подозрительных событиях и влияниях активов на "инциденты"</span><span class="sxs-lookup"><span data-stu-id="81cd2-127">Narrate the full story of the attack across product alerts, behaviors, and context for security teams by joining data on alerts, suspicious events and impacted assets to 'incidents'</span></span>
- <span data-ttu-id="81cd2-128">Автоматизация ответа на компромисс путем запуска самовосстановления для влияемого актива с помощью автоматической рекультивации</span><span class="sxs-lookup"><span data-stu-id="81cd2-128">Automate response to compromise by triggering self-healing for impacted assets through automated remediation</span></span>
- <span data-ttu-id="81cd2-129">Включить группы безопасности для выполнения подробной и эффективной охоты на угрозы через конечные точки и данные Office</span><span class="sxs-lookup"><span data-stu-id="81cd2-129">Enable security teams to perform detailed and effective threat hunting across endpoint and Office data</span></span>

<span data-ttu-id="81cd2-130">![Изображение страницы обзор инцидентов](../../media/overview-incident.png)</span><span class="sxs-lookup"><span data-stu-id="81cd2-130">![Image of incident overview page](../../media/overview-incident.png)</span></span> <br>
<span data-ttu-id="81cd2-131">Инцидент с перекрестным продуктом (Обзор)</span><span class="sxs-lookup"><span data-stu-id="81cd2-131">Cross-product incident (Overview)</span></span>

<span data-ttu-id="81cd2-132">![Изображение очереди оповещений](../../media/incident-list.png)</span><span class="sxs-lookup"><span data-stu-id="81cd2-132">![Image of alerts queue](../../media/incident-list.png)</span></span><br>
<span data-ttu-id="81cd2-133">Все связанные оповещений в продуктах набора соотносятся с одним инцидентом (представление оповещений)</span><span class="sxs-lookup"><span data-stu-id="81cd2-133">All related alerts across the suite products correlated together into a single incident (alerts view)</span></span>

<span data-ttu-id="81cd2-134">![Изображение очереди инцидента](../../media/advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="81cd2-134">![Image of incident queue](../../media/advanced-hunting.png)</span></span><br>
<span data-ttu-id="81cd2-135">Охота на основе запросов в верхней части необработанных данных электронной почты и конечных точек</span><span class="sxs-lookup"><span data-stu-id="81cd2-135">Query-based hunting on top of email and endpoint raw data</span></span>


<span data-ttu-id="81cd2-136">Кросс-продукт Microsoft 365 Defender включает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="81cd2-136">Microsoft 365 Defender cross-product features include:</span></span> 
- <span data-ttu-id="81cd2-137"> Однотекугольное единое стекло продукта — центральный просмотр всей информации для обнаружения, влияния активов, автоматизированных действий и связанных с ними доказательств в одной очереди и одной области [в security.microsoft.com](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="81cd2-137">**Cross-product single pane of glass** - Central view all information for detections, impacted assets, automated actions taken, and related evidence in a single queue and a single pane in [security.microsoft.com](https://security.microsoft.com).</span></span> 
- <span data-ttu-id="81cd2-138">**Комбинированные** очереди инцидентов . Чтобы помочь специалистам по безопасности сосредоточиться на том, что имеет решающее значение, обеспечивая полную область атаки, влияние активов и автоматизированных действий по исправлению сгруппировать и всплыть своевременно.</span><span class="sxs-lookup"><span data-stu-id="81cd2-138">**Combined incidents queue** - To help security professionals focus on what is critical by ensuring the full attack scope, impacted assets and automated remediation actions are grouped together and surfaced in a timely manner.</span></span> 
- <span data-ttu-id="81cd2-139">**Автоматическая реакция на угрозы** — сведения о критических угрозах в режиме реального времени делятся между продуктами Microsoft 365 Defender, чтобы остановить продвижение атаки.</span><span class="sxs-lookup"><span data-stu-id="81cd2-139">**Automatic response to threats** - Critical threat information is shared in real time between the Microsoft 365 Defender products to help stop the progression of an attack.</span></span> <span data-ttu-id="81cd2-140">Например, если вредоносный файл обнаружен на конечной точке, защищенной Защитником Майкрософт для конечной точки, он будет инструктировать Defender for Office 365 сканировать и удалять файл из всех сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="81cd2-140">For example, if a malicious file is detected on an endpoint protected by Microsoft Defender for Endpoint, it will instruct Defender for Office 365 to scan and remove the file from all e-mail messages.</span></span> <span data-ttu-id="81cd2-141">Файл будет заблокирован на виду всем пакетом безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81cd2-141">The file will be blocked on sight by the entire Microsoft 365 security suite.</span></span>
- <span data-ttu-id="81cd2-142">Самовосстановления для скомпрометированных **устройств,** удостоверений пользователей и почтовых ящиков — Microsoft 365 Defender использует автоматические действия и книги с питанием от ИИ для восстановления пострадавших активов в безопасном состоянии.</span><span class="sxs-lookup"><span data-stu-id="81cd2-142">**Self-healing for compromised devices, user identities, and mailboxes** - Microsoft 365 Defender uses AI-powered automatic actions and playbooks to remediate impacted assets back to a secure state.</span></span> <span data-ttu-id="81cd2-143">Microsoft 365 Defender использует возможности автоматического восстановления продуктов пакета, чтобы обеспечить автоматическое исправление всех связанных с инцидентом активов, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="81cd2-143">Microsoft 365 Defender leverages automatic remediation capabilities of the suite products to ensure all impacted assets related to an incident are automatically remediated where possible.</span></span>
- <span data-ttu-id="81cd2-144">**Межпродукционная** охота на угрозы . Группы безопасности могут использовать свои уникальные организационные знания для охоты на признаки компромисса, создавая собственные настраиваемые запросы на необработанные данные, собранные различными средствами защиты.</span><span class="sxs-lookup"><span data-stu-id="81cd2-144">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries over the raw data collected by the various protection products.</span></span> <span data-ttu-id="81cd2-145">Microsoft 365 Defender предоставляет доступ на основе запросов к 30 дням исторических необработанных сигналов и данных оповещения по конечным точкам и данным Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="81cd2-145">Microsoft 365 Defender provides query-based access to 30 days of historic raw signals and alert data across endpoint and Microsoft Defender for Office 365 data.</span></span> 


## <a name="get-started"></a><span data-ttu-id="81cd2-146">Начало работы</span><span class="sxs-lookup"><span data-stu-id="81cd2-146">Get started</span></span>
<span data-ttu-id="81cd2-147">Требования к лицензированию Microsoft 365 Defender должны быть выполнены, прежде чем вы сможете включить службу в центре безопасности Microsoft 365 в [security.microsoft.com](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="81cd2-147">Microsoft 365 Defender licensing requirements must be met before you can enable the service in the Microsoft 365 security center at [security.microsoft.com](https://security.microsoft.com).</span></span> <span data-ttu-id="81cd2-148">Дополнительные сведения читайте в публикации "Ъ".</span><span class="sxs-lookup"><span data-stu-id="81cd2-148">For more information, read:</span></span>
- [<span data-ttu-id="81cd2-149">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="81cd2-149">Licensing requirements</span></span>](prerequisites.md#licensing-requirements)
- [<span data-ttu-id="81cd2-150">Включив защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="81cd2-150">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)