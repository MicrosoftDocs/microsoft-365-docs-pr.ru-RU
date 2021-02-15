---
title: Оценка Microsoft 365 Defender
description: Настройка пробной лабораторной или пилотной среды Microsoft 365 Defender для использования решения по обеспечению безопасности, предназначенного для защиты устройств, удостоверений, данных и приложений в организации.
keywords: Пробная версия Защиты от угроз (Майкрософт), попробуйте Microsoft Threat Protection, оцените Защиту от угроз (Майкрософт), лабораторию оценки Защиты от угроз (Майкрософт), пилотный проект Защиты от угроз (Майкрософт), кибербезопасность, advanced persistent threat, корпоративная безопасность, устройства, устройство, удостоверение, пользователи, данные, приложения, инциденты, автоматизированное исследование и устранение, расширенный поиск
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930214"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="b7e50-104">Создание пробной лабораторной или пилотной среды Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7e50-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b7e50-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b7e50-105">**Applies to:**</span></span>
- <span data-ttu-id="b7e50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7e50-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="b7e50-107">Это руководство поможет вам при настройке лабораторной среды с пользователями и группами, а затем поможет вам с настройкой возможностей в Microsoft 365 Defender, чтобы можно было имитировать угрозу и получить осмысленный результат пробной проверки.</span><span class="sxs-lookup"><span data-stu-id="b7e50-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="b7e50-108">Цель создания этой пробной лабораторной или пилотной среды — показать всесторонние и интегрированные возможности Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7e50-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="b7e50-109">Изучите, как это интеллектуальное решение безопасности обнаруживает, предотвращает, автоматически исследует и реагирует на сложные угрозы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b7e50-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="b7e50-110">Вам будет порекомендоваться начать оценку Защитника Microsoft 365 на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="b7e50-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="b7e50-111">Цель состоит в том, чтобы помочь вам настроить решение для обеспечения безопасности в лабораторной среде с пробной учетной записью или в пилотной среде в производственной среде с полной лицензией.</span><span class="sxs-lookup"><span data-stu-id="b7e50-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="b7e50-112">Подготовка пробной лабораторной или пилотной среды поможет вам представить дела использования операций безопасности для лиц, принимающих решения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b7e50-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="b7e50-113">После запуска имитации атаки и удовлетворены результатами, вы можете полностью развернуть и развернуть его в своей организации с помощью специалистов по техническому отделу продаж Майкрософт или экспертов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b7e50-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="b7e50-114">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="b7e50-114">This guide will help you:</span></span>
- <span data-ttu-id="b7e50-115">Настройка сервера лаборатории и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b7e50-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="b7e50-116">Настройка Active Directory для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="b7e50-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="b7e50-117">Настройка Microsoft Defender для удостоверений, Microsoft Defender для Office 365, Microsoft Defender для конечной точки и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b7e50-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b7e50-118">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b7e50-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="b7e50-119">Имитация атаки с угрозой для создания тестового инцидента или оповещения в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7e50-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="b7e50-120">Для достижения оптимальных результатов следуйте инструкциям по лабораторной настройке как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="b7e50-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="b7e50-121">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="b7e50-121">Deployment phases</span></span>

<span data-ttu-id="b7e50-122">Существует три этапа создания лабораторной среды для пробной работы в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b7e50-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Этапы развертывания: подготовка, настройка, ветвь](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="b7e50-124">Этап</span><span class="sxs-lookup"><span data-stu-id="b7e50-124">Phase</span></span> | <span data-ttu-id="b7e50-125">Description</span><span class="sxs-lookup"><span data-stu-id="b7e50-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="b7e50-126">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="b7e50-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="b7e50-127">Узнайте, что необходимо учитывать при развертывании Microsoft 365 Defender в тестовой или пилотной среде:</span><span class="sxs-lookup"><span data-stu-id="b7e50-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="b7e50-128">- Заинтересованные лица и выключите</span><span class="sxs-lookup"><span data-stu-id="b7e50-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="b7e50-129">- Вопросы среды</span><span class="sxs-lookup"><span data-stu-id="b7e50-129">- Environment considerations</span></span> <br><span data-ttu-id="b7e50-130">- Access</span><span class="sxs-lookup"><span data-stu-id="b7e50-130">- Access</span></span> <br><span data-ttu-id="b7e50-131">- Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7e50-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b7e50-132">- Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="b7e50-132">- Configuration order</span></span>
|[<span data-ttu-id="b7e50-133">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="b7e50-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="b7e50-134">Сначала необходимо получить доступ к Центру безопасности Microsoft 365, чтобы настроить пробную или пилотную среду Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b7e50-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="b7e50-135">Вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="b7e50-135">You'll be guided to:</span></span><br><br><span data-ttu-id="b7e50-136">- Зарегистрироваться для пробной службы Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b7e50-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="b7e50-137">- Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b7e50-137">- Configure domain</span></span><br><span data-ttu-id="b7e50-138">- Назначение лицензий Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b7e50-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="b7e50-139">— Завершение работы мастера настройки на портале</span><span class="sxs-lookup"><span data-stu-id="b7e50-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="b7e50-140">Этап 3. Настройка & в &</span><span class="sxs-lookup"><span data-stu-id="b7e50-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="b7e50-141">Настройте каждую опору Защитника Microsoft 365 и конечные точки в составе службы.</span><span class="sxs-lookup"><span data-stu-id="b7e50-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="b7e50-142">Вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="b7e50-142">You'll be guided to:</span></span><br><br><span data-ttu-id="b7e50-143">- Настройка Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b7e50-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="b7e50-144">- Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b7e50-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="b7e50-145">- Настройка Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="b7e50-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="b7e50-146">- Настройка Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7e50-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="b7e50-147">После завершения работы с этим руководством вы определили бы заинтересованных лиц и необходимые утверждения, получили бы необходимые разрешения на доступ, выполнили регистрацию в пробном составе, настроили домены и все опоры Защитника Microsoft 365, а конечные точки будут присоединены к службе.</span><span class="sxs-lookup"><span data-stu-id="b7e50-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="b7e50-148">Ключевые возможности</span><span class="sxs-lookup"><span data-stu-id="b7e50-148">Key capabilities</span></span>

<span data-ttu-id="b7e50-149">Несмотря на то что Microsoft 365 Defender предоставляет множество возможностей, основное назначение этого руководства по развертыванию — начать работу с устройствами.</span><span class="sxs-lookup"><span data-stu-id="b7e50-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="b7e50-150">В дополнение к введению, в этом руководстве вы можете начать работу со следующими возможностями.</span><span class="sxs-lookup"><span data-stu-id="b7e50-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="b7e50-151">Возможность</span><span class="sxs-lookup"><span data-stu-id="b7e50-151">Capability</span></span> | <span data-ttu-id="b7e50-152">Описание</span><span class="sxs-lookup"><span data-stu-id="b7e50-152">Description</span></span> 
:---|:---
<span data-ttu-id="b7e50-153">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b7e50-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="b7e50-154">Помогает защитить весь процесс envrionment Office 365 от современных угроз</span><span class="sxs-lookup"><span data-stu-id="b7e50-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="b7e50-155">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="b7e50-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="b7e50-156">Определяет и обнаруживает угрозы для скомпрометных удостоверений и вредоносных действий внутри программы.</span><span class="sxs-lookup"><span data-stu-id="b7e50-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="b7e50-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b7e50-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="b7e50-158">Обеспечивает богатые возможности видимости, контроля перемещения данных и обнаружения киберугроз в облачных службах.</span><span class="sxs-lookup"><span data-stu-id="b7e50-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="b7e50-159">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7e50-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="b7e50-160">Предотвращает, обнаруживает и предоставляет возможности реагирования на сложные угрозы с комплексной безопасностью конечных точек.</span><span class="sxs-lookup"><span data-stu-id="b7e50-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="b7e50-161">Область действия</span><span class="sxs-lookup"><span data-stu-id="b7e50-161">In scope</span></span>

<span data-ttu-id="b7e50-162">Для данного руководства в области действия находятся следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b7e50-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="b7e50-163">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7e50-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="b7e50-164">Настройка Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7e50-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="b7e50-165">Зарегистрируйся на пробной версией Microsoft 365 E5 или используйте полную лицензию, если вы используете пилотную версию</span><span class="sxs-lookup"><span data-stu-id="b7e50-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="b7e50-166">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b7e50-166">Configure domain</span></span>
    -   <span data-ttu-id="b7e50-167">Назначение лицензий Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b7e50-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="b7e50-168">Завершение работы мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="b7e50-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="b7e50-169">Настройка всех основ Защитника Microsoft 365 на основе лучших методик</span><span class="sxs-lookup"><span data-stu-id="b7e50-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="b7e50-170">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b7e50-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="b7e50-171">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="b7e50-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="b7e50-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b7e50-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="b7e50-173">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7e50-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="b7e50-174">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="b7e50-174">Out of scope</span></span>

<span data-ttu-id="b7e50-175">Это руководство по развертыванию выходит за рамки следующих областей:</span><span class="sxs-lookup"><span data-stu-id="b7e50-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="b7e50-176">Настройка сторонних решений, которые могут интегрироваться с Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7e50-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="b7e50-177">Тестирование проникновения в производственную среду</span><span class="sxs-lookup"><span data-stu-id="b7e50-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="b7e50-178">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b7e50-178">Next step</span></span>
<span data-ttu-id="b7e50-179">[Этап 1. Подготовка](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="b7e50-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="b7e50-180">Подготовка пробной или пилотной среды Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7e50-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
