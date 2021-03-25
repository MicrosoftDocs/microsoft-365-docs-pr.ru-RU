---
title: Оценка Microsoft 365 Defender
description: Установите пробную лабораторию или пилотную среду Microsoft 365 Defender, чтобы опробовыть и испытать решение безопасности, предназначенное для защиты устройств, удостоверений, данных и приложений в организации.
keywords: Microsoft Threat Protection trial, try Microsoft Threat Protection, assessment Microsoft Threat Protection, Microsoft Threat Protection assessment lab, Microsoft Threat Protection pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076654"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="fd098-104">Создание пробной лаборатории или пилотной среды Для Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd098-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fd098-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fd098-105">**Applies to:**</span></span>
- <span data-ttu-id="fd098-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd098-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="fd098-107">В этом руководстве помогают настраивать лабораторную среду с пользователями и группами, а затем помогают определить конфигурацию возможностей в Microsoft 365 Defender, чтобы можно было имитировать угрозу и получить значимый пробный результат.</span><span class="sxs-lookup"><span data-stu-id="fd098-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="fd098-108">Целью создания этой пробной лаборатории или пилотной среды является демонстрация комплексных и интегрированных возможностей Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fd098-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="fd098-109">Изучите, как это интеллектуальное решение безопасности обнаруживает, предотвращает, автоматически расследует и реагирует на расширенные угрозы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="fd098-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="fd098-110">Вы будете руководствоваться действиями по началу оценки Защитника Microsoft 365 на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd098-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="fd098-111">Цель состоит в том, чтобы помочь вам настроить решение безопасности либо в лаборатории с пробной учетной записью, либо в пилотной среде в производстве с полной лицензией.</span><span class="sxs-lookup"><span data-stu-id="fd098-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="fd098-112">Подготовка пробной лаборатории или пилотной среды может помочь вам представить случаи использования операций безопасности для лиц, принимающих решения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="fd098-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="fd098-113">После запуска имитации атак и удовлетворенных результатами вы можете полностью развернуть и использовать его в организации с помощью специалистов по техническим продажам Майкрософт или экспертов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="fd098-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="fd098-114">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="fd098-114">This guide will help you:</span></span>
- <span data-ttu-id="fd098-115">Настройка лабораторного сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="fd098-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="fd098-116">Настройка Active Directory с пользователями и группами</span><span class="sxs-lookup"><span data-stu-id="fd098-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="fd098-117">Настройка и настройка Microsoft Defender для удостоверений, Microsoft Defender для Office 365, Microsoft Defender для конечной точки и microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fd098-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="fd098-118">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="fd098-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="fd098-119">Имитация атаки угрозы для создания тестового инцидента или оповещения в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd098-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="fd098-120">Для достижения оптимальных результатов выполните инструкции по настройке лаборатории как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="fd098-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="fd098-121">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="fd098-121">Deployment phases</span></span>

<span data-ttu-id="fd098-122">Создание среды пробной лаборатории Microsoft 365 Defender имеет три этапа.</span><span class="sxs-lookup"><span data-stu-id="fd098-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Этапы развертывания: подготовка, настройка, бортовой](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="fd098-124">Этап</span><span class="sxs-lookup"><span data-stu-id="fd098-124">Phase</span></span> | <span data-ttu-id="fd098-125">Описание</span><span class="sxs-lookup"><span data-stu-id="fd098-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="fd098-126">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="fd098-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="fd098-127">Узнайте, что необходимо учитывать при развертывании Microsoft 365 Defender в пробной лаборатории или пилотной среде:</span><span class="sxs-lookup"><span data-stu-id="fd098-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="fd098-128">- Заинтересованные лица и вход</span><span class="sxs-lookup"><span data-stu-id="fd098-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="fd098-129">- Соображения среды</span><span class="sxs-lookup"><span data-stu-id="fd098-129">- Environment considerations</span></span> <br><span data-ttu-id="fd098-130">- Доступ</span><span class="sxs-lookup"><span data-stu-id="fd098-130">- Access</span></span> <br><span data-ttu-id="fd098-131">- Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fd098-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="fd098-132">- Порядок конфигурации</span><span class="sxs-lookup"><span data-stu-id="fd098-132">- Configuration order</span></span>
|[<span data-ttu-id="fd098-133">Этап 2. Установка</span><span class="sxs-lookup"><span data-stu-id="fd098-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="fd098-134">Сначала необходимо получить доступ к Центру безопасности Microsoft 365, чтобы настроить пробную лабораторию или пилотную среду Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fd098-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="fd098-135">Вы будете руководствоваться:</span><span class="sxs-lookup"><span data-stu-id="fd098-135">You'll be guided to:</span></span><br><br><span data-ttu-id="fd098-136">- Зарегистриройся на microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="fd098-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="fd098-137">- Настройка домена</span><span class="sxs-lookup"><span data-stu-id="fd098-137">- Configure domain</span></span><br><span data-ttu-id="fd098-138">- Назначение лицензий Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fd098-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="fd098-139">- Завершите мастер установки на портале</span><span class="sxs-lookup"><span data-stu-id="fd098-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="fd098-140">Этап 3. Настройка & на борту</span><span class="sxs-lookup"><span data-stu-id="fd098-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="fd098-141">Настройка каждого столба и конечных точек Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fd098-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="fd098-142">Вы будете руководствоваться:</span><span class="sxs-lookup"><span data-stu-id="fd098-142">You'll be guided to:</span></span><br><br><span data-ttu-id="fd098-143">- Настройка Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="fd098-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="fd098-144">- Настройка безопасности облачных приложений Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fd098-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="fd098-145">- Настройка Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="fd098-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="fd098-146">- Настройка Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd098-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="fd098-147">После завершения этого руководства вы бы определили заинтересованных лиц и необходимые разрешения, получили бы соответствующие разрешения доступа, подписались на пробные, настроенные домены и каждый из столбов Microsoft 365 Defender, а конечные точки будут присоединены к службе.</span><span class="sxs-lookup"><span data-stu-id="fd098-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="fd098-148">Ключевые возможности</span><span class="sxs-lookup"><span data-stu-id="fd098-148">Key capabilities</span></span>

<span data-ttu-id="fd098-149">Несмотря на то, что Microsoft 365 Defender предоставляет множество возможностей, основная цель этого руководства по развертыванию состоит в том, чтобы начать работу с помощью бортовых устройств.</span><span class="sxs-lookup"><span data-stu-id="fd098-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="fd098-150">В дополнение к onboarding, это руководство начинается со следующими возможностями.</span><span class="sxs-lookup"><span data-stu-id="fd098-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="fd098-151">Возможность</span><span class="sxs-lookup"><span data-stu-id="fd098-151">Capability</span></span> | <span data-ttu-id="fd098-152">Описание</span><span class="sxs-lookup"><span data-stu-id="fd098-152">Description</span></span> 
:---|:---
<span data-ttu-id="fd098-153">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="fd098-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="fd098-154">Защита всей инврионации Office 365 от сегодняшних угроз</span><span class="sxs-lookup"><span data-stu-id="fd098-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="fd098-155">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="fd098-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="fd098-156">Определяет и обнаруживает угрозы в отношении скомпрометированных удостоверений и вредоносных действий инсайдеров.</span><span class="sxs-lookup"><span data-stu-id="fd098-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="fd098-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fd098-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="fd098-158">Обеспечивает богатую видимость, управление перемещениями данных и обнаружение киберугроз в облачных службах.</span><span class="sxs-lookup"><span data-stu-id="fd098-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="fd098-159">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd098-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="fd098-160">Предотвращает, обнаруживает и предоставляет возможности реагирования на расширенные угрозы с комплексной безопасностью конечных точек.</span><span class="sxs-lookup"><span data-stu-id="fd098-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="fd098-161">В области</span><span class="sxs-lookup"><span data-stu-id="fd098-161">In scope</span></span>

<span data-ttu-id="fd098-162">В этом руководстве находятся следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="fd098-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="fd098-163">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fd098-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="fd098-164">Настройка защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd098-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="fd098-165">Зарегистрируйся в Microsoft 365 E5 Trial или используйте полную лицензию, если запущен пилотный</span><span class="sxs-lookup"><span data-stu-id="fd098-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="fd098-166">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="fd098-166">Configure domain</span></span>
    -   <span data-ttu-id="fd098-167">Назначение лицензий Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fd098-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="fd098-168">Завершение мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="fd098-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="fd098-169">Настройка всех столпов Microsoft 365 Defender на основе практических методов</span><span class="sxs-lookup"><span data-stu-id="fd098-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="fd098-170">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="fd098-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="fd098-171">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="fd098-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="fd098-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fd098-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="fd098-173">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd098-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="fd098-174">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="fd098-174">Out of scope</span></span>

<span data-ttu-id="fd098-175">Ниже из этого руководства по развертыванию находятся вне сферы действия:</span><span class="sxs-lookup"><span data-stu-id="fd098-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="fd098-176">Конфигурация сторонних решений, которые могут интегрироваться с Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd098-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="fd098-177">Тестирование на проникновение в производственной среде</span><span class="sxs-lookup"><span data-stu-id="fd098-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="fd098-178">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fd098-178">Next step</span></span>
<span data-ttu-id="fd098-179">[Этап 1. Подготовка](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="fd098-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="fd098-180">Подготовка пробной лаборатории или пилотной среды Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd098-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>