---
title: Microsoft 365 Defender
description: Защитник Microsoft 365 — это решение защиты от угроз, разработанное для защиты устройств, удостоверений, данных и приложений.
keywords: Общие сведения о защите от угроз Майкрософт, безопасности кибератак, повышенной постоянной угрозе, корпоративной безопасности, устройствах, устройствах, удостоверениях, пользователях, данных, приложениях, инцидентах, автоматическом расследовании и исправлении, расширенное Поиск
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 573f30dc3d8a43a337a4333dbaf05baf916857fa
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357907"
---
# <a name="microsoft-365-defender"></a><span data-ttu-id="c9950-104">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9950-104">Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c9950-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c9950-105">**Applies to:**</span></span>
- <span data-ttu-id="c9950-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9950-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="c9950-107">Хотите работать с защитником Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c9950-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="c9950-108">Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или [запустить пилотный проект в рабочей](https://aka.ms/m365d-pilotplaybook)среде.</span><span class="sxs-lookup"><span data-stu-id="c9950-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="c9950-109">Защитник Microsoft 365 является единым готовым пакетом защиты от ненарушений, который управляет обнаружением, предотвращением, исследованием и ответами на конечные точки, удостоверения, сообщения электронной почты и приложения для обеспечения интегрированной защиты от изощренных атак.</span><span class="sxs-lookup"><span data-stu-id="c9950-109">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span>

<span data-ttu-id="c9950-110">С помощью встроенного решения для защитника Microsoft 365 специалисты по безопасности могут объединить угрозу, чтобы каждый из этих продуктов получал и определил всю область и влияние угрозы. сведения о том, как она была введена в среду, каковы ее влияние и как в настоящее время влияет на организацию.</span><span class="sxs-lookup"><span data-stu-id="c9950-110">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that each of these products receive and determine the full scope and impact of the threat; how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="c9950-111">Защитник Microsoft 365 выполняет автоматическое действие, чтобы предотвратить или прекратить атаку и самостоятельное почтовые ящики, конечные точки и удостоверения пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9950-111">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span>  


<center><h2><span data-ttu-id="c9950-112">Службы защитника Microsoft 365</center></span><span class="sxs-lookup"><span data-stu-id="c9950-112">Microsoft 365 Defender services</center></span></span></h2>
<table><tr><td><span data-ttu-id="c9950-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Защитник Майкрософт для конечной точки</b></center></span><span class="sxs-lookup"><span data-stu-id="c9950-113"><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></span></span></a></td>
<td><span data-ttu-id="c9950-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Защитник Майкрософт для Office 365</b></center></span><span class="sxs-lookup"><span data-stu-id="c9950-114"><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></span></span></a></td>
<td><span data-ttu-id="c9950-115"><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Защитник Майкрософт для удостоверения</b></a></center></span><span class="sxs-lookup"><span data-stu-id="c9950-115"><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></span></span></td>
<td><span data-ttu-id="c9950-116"><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span><span class="sxs-lookup"><span data-stu-id="c9950-116"><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></span></span></td>
</tr>
</table>
<br>


>[!TIP]
><span data-ttu-id="c9950-117">Ознакомьтесь с [интерактивным руководством по Защитнику Microsoft 365](https://aka.ms/MTP-Interactive-Guide).</span><span class="sxs-lookup"><span data-stu-id="c9950-117">Check out this [Microsoft 365 Defender interactive guide](https://aka.ms/MTP-Interactive-Guide).</span></span>


<span data-ttu-id="c9950-118">Набор защитника Microsoft 365 защищает:</span><span class="sxs-lookup"><span data-stu-id="c9950-118">Microsoft 365 Defender suite protects:</span></span> 
- <span data-ttu-id="c9950-119">**Конечные точки с защитником Майкрософт для** конечной точки — это платформа единой конечной точки для защиты от вирусов, обнаружения нарушений подлинности, автоматического исследования и ответа.</span><span class="sxs-lookup"><span data-stu-id="c9950-119">**Endpoints with Microsoft Defender for Endpoint** - Microsoft Defender for Endpoint is a unified endpoint platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> 
- <span data-ttu-id="c9950-120">**Электронная почта и совместная работа с защитником Майкрософт для office 365** — защитник для Office 365 защищает организацию от вредоносных угроз, исносящихся к сообщениям электронной почты, ссылкам (URL-адресам) и средствам совместной работы.</span><span class="sxs-lookup"><span data-stu-id="c9950-120">**Email and collaboration with Microsoft Defender for Office 365** - Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools.</span></span> 
- <span data-ttu-id="c9950-121">**Удостоверения с помощью защитника Майкрософт для удостоверения и защиты удостоверений Azure AD** — защитник Майкрософт для удостоверения использует сигналы Active Directory для обнаружения, обнаружения и исследования сложных угроз, скомпрометированных удостоверений и действий по предварительной попытке, направленным в Организации.</span><span class="sxs-lookup"><span data-stu-id="c9950-121">**Identities with Microsoft Defender for Identity and Azure AD Identity Protection** - Microsoft Defender for Identity uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> 
- <span data-ttu-id="c9950-122">**Приложения с Microsoft Cloud App Security** -Microsoft Cloud App Security — это комплексное решение, которое позволяет глубоко отображать, строго управлять данными и улучшенную защиту облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="c9950-122">**Applications with Microsoft Cloud App security** - Microsoft Cloud App security is a comprehensive cross-SaaS solution bringing deep visibility, strong data controls, and enhanced threat protection to your cloud apps.</span></span> 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

<span data-ttu-id="c9950-123">Уникальный межсайтовый уровень защитника Microsoft 365 дополняет отдельные компоненты набора следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c9950-123">Microsoft 365 Defender's unique cross-product layer augments the individual suite components to:</span></span>
- <span data-ttu-id="c9950-124">Защита от атак и координация защитных ответов в наборе через обмен сигналами и автоматические действия</span><span class="sxs-lookup"><span data-stu-id="c9950-124">Help protect against attacks and coordinate defensive responses across the suite through signal sharing and automated actions</span></span>
- <span data-ttu-id="c9950-125">Соблюдайте закадровую закадровую статью об атаках по оповещениям, поведению и контексту для групп безопасности, присоединяя данные в оповещениях, подозрительных событиях и затронутых ресурсах к инцидентам.</span><span class="sxs-lookup"><span data-stu-id="c9950-125">Narrate the full story of the attack across product alerts, behaviors, and context for security teams by joining data on alerts, suspicious events and impacted assets to 'incidents'</span></span>
- <span data-ttu-id="c9950-126">Автоматизация ответа на компромисс путем запуска самовосстановления для затронутых активов с помощью автоматизированного исправления</span><span class="sxs-lookup"><span data-stu-id="c9950-126">Automate response to compromise by triggering self-healing for impacted assets through automated remediation</span></span>
- <span data-ttu-id="c9950-127">Разрешите Teams Security выполнять подробную и эффективную Поиск угроз для данных конечной точки и данных Office</span><span class="sxs-lookup"><span data-stu-id="c9950-127">Enable security teams to perform detailed and effective threat hunting across endpoint and Office data</span></span>

<span data-ttu-id="c9950-128">![Изображение страницы обзора инцидента](../../media/overview-incident.png)</span><span class="sxs-lookup"><span data-stu-id="c9950-128">![Image of incident overview page](../../media/overview-incident.png)</span></span> <br>
<span data-ttu-id="c9950-129">Происшествие между продуктами (обзор)</span><span class="sxs-lookup"><span data-stu-id="c9950-129">Cross-product incident (Overview)</span></span>

<span data-ttu-id="c9950-130">![Изображение очереди оповещений](../../media/incident-list.png)</span><span class="sxs-lookup"><span data-stu-id="c9950-130">![Image of alerts queue](../../media/incident-list.png)</span></span><br>
<span data-ttu-id="c9950-131">Все связанные оповещения по продуктам набора сопоставлены с одним инцидентом (представление "оповещения").</span><span class="sxs-lookup"><span data-stu-id="c9950-131">All related alerts across the suite products correlated together into a single incident (alerts view)</span></span>

<span data-ttu-id="c9950-132">![Изображение очереди инцидентов](../../media/advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="c9950-132">![Image of incident queue](../../media/advanced-hunting.png)</span></span><br>
<span data-ttu-id="c9950-133">Поиск на основе запросов на основе необработанных данных электронной почты и конечных точек</span><span class="sxs-lookup"><span data-stu-id="c9950-133">Query-based hunting on top of email and endpoint raw data</span></span>


<span data-ttu-id="c9950-134">Функции перекрестного продукта защитника Microsoft 365 включают:</span><span class="sxs-lookup"><span data-stu-id="c9950-134">Microsoft 365 Defender cross-product features include:</span></span> 
- <span data-ttu-id="c9950-135">**Односторонняя область прозрачности** — Центральное представление всей информации об обнаруженных и затронутых активах, автоматических действиях и связанных свидетельствах в одной очереди и одной области в [Security.Microsoft.com](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c9950-135">**Cross-product single pane of glass** - Central view all information for detections, impacted assets, automated actions taken, and related evidence in a single queue and a single pane in [security.microsoft.com](https://security.microsoft.com).</span></span> 
- <span data-ttu-id="c9950-136">**Объединенные происшествия очередь** — чтобы помочь специалистам по безопасности сосредоточиться на том, что является критическим, обеспечивая полную область атак, подверженность затронутым активам и автоматизированные действия по исправлению группируются и помещаются своевременно.</span><span class="sxs-lookup"><span data-stu-id="c9950-136">**Combined incidents queue** - To help security professionals focus on what is critical by ensuring the full attack scope, impacted assets and automated remediation actions are grouped together and surfaced in a timely manner.</span></span> 
- <span data-ttu-id="c9950-137">**Автоматическое реагирование на угрозы** критической информации об угрозе совместно используется в режиме реального времени между продуктами защитника Microsoft 365 для прекращения процесса атаки.</span><span class="sxs-lookup"><span data-stu-id="c9950-137">**Automatic response to threats** - Critical threat information is shared in real time between the Microsoft 365 Defender products to help stop the progression of an attack.</span></span> <span data-ttu-id="c9950-138">Например, если вредоносный файл обнаружен в конечной точке, защищенной защитником Майкрософт для конечной точки, он попросит Защитнику Office 365 просканировать и удалить файл из всех сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c9950-138">For example, if a malicious file is detected on an endpoint protected by Microsoft Defender for Endpoint, it will instruct Defender for Office 365 to scan and remove the file from all e-mail messages.</span></span> <span data-ttu-id="c9950-139">По всему комплекту безопасности Microsoft 365 файл будет заблокирован.</span><span class="sxs-lookup"><span data-stu-id="c9950-139">The file will be blocked on sight by the entire Microsoft 365 security suite.</span></span>
- <span data-ttu-id="c9950-140">**Самовосстановление для скомпрометированных устройств, удостоверений пользователей и почтовых ящиков** — защитник Microsoft 365 использует автоматические действия и "Playbooks" для восстановления затронутых активов в безопасном состоянии.</span><span class="sxs-lookup"><span data-stu-id="c9950-140">**Self-healing for compromised devices, user identities, and mailboxes** - Microsoft 365 Defender uses AI-powered automatic actions and playbooks to remediate impacted assets back to a secure state.</span></span> <span data-ttu-id="c9950-141">Защитник Microsoft 365 использует функции автоматического исправления, чтобы гарантировать, что все затронутые активы, связанные с инцидентом, будут автоматически исправлены там, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="c9950-141">Microsoft 365 Defender leverages automatic remediation capabilities of the suite products to ensure all impacted assets related to an incident are automatically remediated where possible.</span></span>
- <span data-ttu-id="c9950-142">**Межпродуктная угроза** "Поиск вирусов". Teams могут использовать свои уникальные организационные знания для поиска подписывания нарушений, создавая собственные пользовательские запросы для необработанных данных, собранных различными продуктами для защиты.</span><span class="sxs-lookup"><span data-stu-id="c9950-142">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries over the raw data collected by the various protection products.</span></span> <span data-ttu-id="c9950-143">Защитник Microsoft 365 предоставляет доступ на основе запросов к 30 дням из исторических необработанных сигналов и данных оповещений между конечной точкой и защитником Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9950-143">Microsoft 365 Defender provides query-based access to 30 days of historic raw signals and alert data across endpoint and Microsoft Defender for Office 365 data.</span></span> 


## <a name="get-started"></a><span data-ttu-id="c9950-144">Начало работы</span><span class="sxs-lookup"><span data-stu-id="c9950-144">Get started</span></span>
<span data-ttu-id="c9950-145">Для включения службы в центре безопасности Microsoft 365 по адресу [Security.Microsoft.com](https://security.microsoft.com)должны быть выполнены требования к лицензированию защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9950-145">Microsoft 365 Defender licensing requirements must be met before you can enable the service in the Microsoft 365 security center at [security.microsoft.com](https://security.microsoft.com).</span></span> <span data-ttu-id="c9950-146">Для получения дополнительных сведений прочитайте:</span><span class="sxs-lookup"><span data-stu-id="c9950-146">For more information, read:</span></span>
- [<span data-ttu-id="c9950-147">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="c9950-147">Licensing requirements</span></span>](prerequisites.md#licensing-requirements)
- [<span data-ttu-id="c9950-148">Включение Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9950-148">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
