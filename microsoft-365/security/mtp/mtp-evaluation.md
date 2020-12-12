---
title: Оценка Защитника Microsoft 365
description: Настройка пробной лабораторной или пилотной среды Microsoft 365 Defender для использования решения по обеспечению безопасности, предназначенного для защиты устройств, удостоверений, данных и приложений в организации.
keywords: Пробная версия Защиты от угроз (Майкрософт), попробуйте Microsoft Threat Protection, оцените Защиту от угроз (Майкрософт), лабораторию оценки Защиты от угроз (Майкрософт), пилотный проект Защиты от угроз (Майкрософт), кибербезопасность, advanced persistent threat, корпоративная безопасность, устройства, устройство, удостоверение, пользователи, данные, приложения, инциденты, автоматизированное исследование и устранение, расширенный поиск
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659637"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="c94fa-104">Создание пробной или пилотной среды Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c94fa-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c94fa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c94fa-105">**Applies to:**</span></span>
- <span data-ttu-id="c94fa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c94fa-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="c94fa-107">Это руководство поможет вам при настройке лабораторной среды с пользователями и группами, а затем поможет вам с настройкой возможностей в Microsoft 365 Defender, чтобы можно было имитировать угрозы и получить осмысленный результат пробной проверки.</span><span class="sxs-lookup"><span data-stu-id="c94fa-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="c94fa-108">Цель создания этой пробной лабораторной или пилотной среды — показать всесторонние и интегрированные возможности Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c94fa-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="c94fa-109">Изучите, как это интеллектуальное решение безопасности обнаруживает, предотвращает, автоматически исследует и реагирует на сложные угрозы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c94fa-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="c94fa-110">Вам будет порекомендоваться начать оценку Защитника Microsoft 365 на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="c94fa-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="c94fa-111">Цель состоит в том, чтобы помочь вам настроить решение для обеспечения безопасности в лабораторной среде с пробной учетной записью или в пилотной среде в производственной среде с полной лицензией.</span><span class="sxs-lookup"><span data-stu-id="c94fa-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="c94fa-112">Подготовка пробной лабораторной или пилотной среды поможет вам представить дела использования операций безопасности для лиц, принимающих решения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c94fa-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="c94fa-113">После запуска имитации атаки и удовлетворены результатами, вы можете полностью развернуть и развернуть его в своей организации с помощью специалистов по техническому отделу продаж Майкрософт или экспертов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c94fa-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="c94fa-114">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="c94fa-114">This guide will help you:</span></span>
- <span data-ttu-id="c94fa-115">Настройка сервера лаборатории и компьютеров</span><span class="sxs-lookup"><span data-stu-id="c94fa-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="c94fa-116">Настройка Active Directory для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="c94fa-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="c94fa-117">Настройка Microsoft Defender для удостоверений, Microsoft Defender для Office 365, Microsoft Defender для конечной точки и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c94fa-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c94fa-118">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="c94fa-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="c94fa-119">Имитация атаки с угрозой для создания тестового инцидента или оповещения в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c94fa-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="c94fa-120">Для достижения оптимальных результатов следуйте инструкциям по лабораторной настройке как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="c94fa-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="c94fa-121">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="c94fa-121">Deployment phases</span></span>

<span data-ttu-id="c94fa-122">Существует три этапа создания лабораторной среды пробной среды Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c94fa-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Этапы развертывания: подготовка, настройка, ветвь](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="c94fa-124">Этап</span><span class="sxs-lookup"><span data-stu-id="c94fa-124">Phase</span></span> | <span data-ttu-id="c94fa-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c94fa-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="c94fa-126">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="c94fa-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="c94fa-127">Узнайте, что необходимо учитывать при развертывании Microsoft 365 Defender в тестовой или пилотной среде:</span><span class="sxs-lookup"><span data-stu-id="c94fa-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="c94fa-128">- Заинтересованные лица и выключите</span><span class="sxs-lookup"><span data-stu-id="c94fa-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="c94fa-129">- Вопросы среды</span><span class="sxs-lookup"><span data-stu-id="c94fa-129">- Environment considerations</span></span> <br><span data-ttu-id="c94fa-130">- Access</span><span class="sxs-lookup"><span data-stu-id="c94fa-130">- Access</span></span> <br><span data-ttu-id="c94fa-131">- Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c94fa-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c94fa-132">- Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="c94fa-132">- Configuration order</span></span>
|[<span data-ttu-id="c94fa-133">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="c94fa-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="c94fa-134">Сначала необходимо получить доступ к Центру безопасности Microsoft 365, чтобы настроить пробную или пилотную среду Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c94fa-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="c94fa-135">Вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="c94fa-135">You'll be guided to:</span></span><br><br><span data-ttu-id="c94fa-136">- Зарегистрироваться для пробной пробной пробной службы Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c94fa-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="c94fa-137">- Настройка домена</span><span class="sxs-lookup"><span data-stu-id="c94fa-137">- Configure domain</span></span><br><span data-ttu-id="c94fa-138">- Назначение лицензий Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c94fa-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="c94fa-139">— Завершение работы мастера настройки на портале</span><span class="sxs-lookup"><span data-stu-id="c94fa-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="c94fa-140">Этап 3. Настройка & в &</span><span class="sxs-lookup"><span data-stu-id="c94fa-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="c94fa-141">Настройте каждую опору Защитника Microsoft 365 и конечные точки в составе службы.</span><span class="sxs-lookup"><span data-stu-id="c94fa-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="c94fa-142">Вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="c94fa-142">You'll be guided to:</span></span><br><br><span data-ttu-id="c94fa-143">- Настройка Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="c94fa-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="c94fa-144">- Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c94fa-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="c94fa-145">- Настройка Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="c94fa-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="c94fa-146">- Настройка Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c94fa-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="c94fa-147">После завершения работы с этим руководством вы определили бы заинтересованных лиц и необходимые утверждения, получили бы необходимые разрешения на доступ, выполнили регистрацию в пробном составе, настроили домены и все опоры Защитника Microsoft 365, а конечные точки будут присоединены к службе.</span><span class="sxs-lookup"><span data-stu-id="c94fa-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="c94fa-148">Ключевые возможности</span><span class="sxs-lookup"><span data-stu-id="c94fa-148">Key capabilities</span></span>

<span data-ttu-id="c94fa-149">Несмотря на то что Microsoft 365 Defender предоставляет множество возможностей, основное назначение этого руководства по развертыванию — начать работу с устройствами.</span><span class="sxs-lookup"><span data-stu-id="c94fa-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="c94fa-150">В дополнение к введению, в этом руководстве вы можете начать работу со следующими возможностями.</span><span class="sxs-lookup"><span data-stu-id="c94fa-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="c94fa-151">Возможность</span><span class="sxs-lookup"><span data-stu-id="c94fa-151">Capability</span></span> | <span data-ttu-id="c94fa-152">Описание</span><span class="sxs-lookup"><span data-stu-id="c94fa-152">Description</span></span> 
:---|:---
<span data-ttu-id="c94fa-153">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="c94fa-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="c94fa-154">Помогает защитить весь процесс envrionment Office 365 от современных угроз</span><span class="sxs-lookup"><span data-stu-id="c94fa-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="c94fa-155">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="c94fa-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="c94fa-156">Определяет и обнаруживает угрозы для скомпрометных удостоверений и вредоносных действий внутри программы.</span><span class="sxs-lookup"><span data-stu-id="c94fa-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="c94fa-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c94fa-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="c94fa-158">Обеспечивает богатые возможности видимости, контроля перемещения данных и обнаружения киберугроз в облачных службах.</span><span class="sxs-lookup"><span data-stu-id="c94fa-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="c94fa-159">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c94fa-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="c94fa-160">Предотвращает, обнаруживает и предоставляет возможности реагирования на сложные угрозы с комплексной безопасностью конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c94fa-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="c94fa-161">Область действия</span><span class="sxs-lookup"><span data-stu-id="c94fa-161">In scope</span></span>

<span data-ttu-id="c94fa-162">Для данного руководства в области действия находятся следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c94fa-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="c94fa-163">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c94fa-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="c94fa-164">Настройка Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c94fa-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="c94fa-165">Зарегистрируйся на пробной версией Microsoft 365 E5 или используйте полную лицензию, если вы используете пилотную версию</span><span class="sxs-lookup"><span data-stu-id="c94fa-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="c94fa-166">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="c94fa-166">Configure domain</span></span>
    -   <span data-ttu-id="c94fa-167">Назначение лицензий Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c94fa-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="c94fa-168">Завершение работы мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="c94fa-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="c94fa-169">Настройка всех основ Защитника Microsoft 365 на основе практических методик</span><span class="sxs-lookup"><span data-stu-id="c94fa-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="c94fa-170">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="c94fa-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="c94fa-171">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="c94fa-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="c94fa-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c94fa-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="c94fa-173">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c94fa-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="c94fa-174">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="c94fa-174">Out of scope</span></span>

<span data-ttu-id="c94fa-175">Это руководство по развертыванию выходит за рамки следующих областей:</span><span class="sxs-lookup"><span data-stu-id="c94fa-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="c94fa-176">Настройка сторонних решений, которые могут интегрироваться с Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c94fa-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="c94fa-177">Тестирование проникновения в производственную среду</span><span class="sxs-lookup"><span data-stu-id="c94fa-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="c94fa-178">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="c94fa-178">Next step</span></span>
<span data-ttu-id="c94fa-179">[Этап 1. Подготовка](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="c94fa-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="c94fa-180">Подготовка пробной или пилотной среды Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c94fa-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
