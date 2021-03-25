---
title: Onboard to the Microsoft Defender ATP service
description: Узнайте, как переназначить конечные точки в службу ATP Защитника Майкрософт
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186933"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="feac9-103">На борту службы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="feac9-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="feac9-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="feac9-104">**Applies to:**</span></span>
- [<span data-ttu-id="feac9-105">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="feac9-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="feac9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="feac9-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="feac9-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="feac9-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="feac9-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="feac9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="feac9-109">Узнайте о различных этапах развертывания Microsoft Defender для конечной точки и о настройке возможностей решения.</span><span class="sxs-lookup"><span data-stu-id="feac9-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="feac9-110">Развертывание Defender для конечной точки — это трех этапный процесс:</span><span class="sxs-lookup"><span data-stu-id="feac9-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="feac9-111">[![этап развертывания — подготовка](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="feac9-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="feac9-112">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="feac9-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="feac9-113">[![этап развертывания — установка](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="feac9-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="feac9-114">Этап 2. Установка</span><span class="sxs-lookup"><span data-stu-id="feac9-114">Phase 2: Setup</span></span>](production-deployment.md) | ![этап развертывания — на борту](images/phase-diagrams/onboard.png)<br><span data-ttu-id="feac9-116">Этап 3. На борту</span><span class="sxs-lookup"><span data-stu-id="feac9-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="feac9-117">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="feac9-117">*You are here!*</span></span>|

<span data-ttu-id="feac9-118">В настоящее время вы находитесь на этапе вмеяния.</span><span class="sxs-lookup"><span data-stu-id="feac9-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="feac9-119">Вот шаги, которые необходимо предпринять для развертывания Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="feac9-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="feac9-120">Шаг 1. Конечные точки на борту службы</span><span class="sxs-lookup"><span data-stu-id="feac9-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="feac9-121">Шаг 2. Настройка возможностей</span><span class="sxs-lookup"><span data-stu-id="feac9-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="feac9-122">Шаг 1. Конечные точки на борту с помощью любого из поддерживаемых средств управления</span><span class="sxs-lookup"><span data-stu-id="feac9-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="feac9-123">В [разделе Развертывание](deployment-strategy.md) Plan описаны общие действия, которые необходимо предпринять для развертывания Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="feac9-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="feac9-124">Просмотрите это видео, чтобы получить краткий обзор процесса работы с бортовой частью и узнать о доступных средствах и методах.</span><span class="sxs-lookup"><span data-stu-id="feac9-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="feac9-125">После определения архитектуры необходимо решить, какой метод развертывания использовать.</span><span class="sxs-lookup"><span data-stu-id="feac9-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="feac9-126">Инструмент развертывания, который вы выбираете, влияет на то, как вы работаете с конечными точками на борту службы.</span><span class="sxs-lookup"><span data-stu-id="feac9-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="feac9-127">Параметры onboarding tool</span><span class="sxs-lookup"><span data-stu-id="feac9-127">Onboarding tool options</span></span>

<span data-ttu-id="feac9-128">В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.</span><span class="sxs-lookup"><span data-stu-id="feac9-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="feac9-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="feac9-129">Endpoint</span></span>     | <span data-ttu-id="feac9-130">Параметры инструмента</span><span class="sxs-lookup"><span data-stu-id="feac9-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="feac9-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="feac9-131">**Windows**</span></span>  |  [<span data-ttu-id="feac9-132">Локальный скрипт (до 10 устройств)</span><span class="sxs-lookup"><span data-stu-id="feac9-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="feac9-133">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="feac9-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="feac9-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="feac9-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="feac9-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="feac9-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="feac9-136">Скрипты VDI</span><span class="sxs-lookup"><span data-stu-id="feac9-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="feac9-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="feac9-137">**macOS**</span></span>    | [<span data-ttu-id="feac9-138">Локальные сценарии</span><span class="sxs-lookup"><span data-stu-id="feac9-138">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="feac9-139">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="feac9-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="feac9-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="feac9-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="feac9-141">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="feac9-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="feac9-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="feac9-142">**Linux Server**</span></span> | [<span data-ttu-id="feac9-143">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="feac9-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="feac9-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="feac9-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="feac9-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="feac9-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="feac9-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="feac9-146">**iOS**</span></span>      | [<span data-ttu-id="feac9-147">На основе приложения</span><span class="sxs-lookup"><span data-stu-id="feac9-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="feac9-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="feac9-148">**Android**</span></span>  | [<span data-ttu-id="feac9-149">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="feac9-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="feac9-150">Шаг 2. Настройка возможностей</span><span class="sxs-lookup"><span data-stu-id="feac9-150">Step 2: Configure capabilities</span></span>
<span data-ttu-id="feac9-151">После настроя конечных точек вы настроите различные возможности, такие как обнаружение конечной точки и реагирование, защита следующего поколения и уменьшение поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="feac9-151">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="feac9-152">Пример развертывания</span><span class="sxs-lookup"><span data-stu-id="feac9-152">Example deployments</span></span>
<span data-ttu-id="feac9-153">В этом руководстве по развертыванию мы назначим вам использование двух средств развертывания для конечных точек на борту и настройку возможностей.</span><span class="sxs-lookup"><span data-stu-id="feac9-153">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="feac9-154">Средства в примере развертывания:</span><span class="sxs-lookup"><span data-stu-id="feac9-154">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="feac9-155">Onboarding using Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="feac9-155">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="feac9-156">Onboarding using Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="feac9-156">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="feac9-157">Используя указанные выше средства развертывания, вы будете руководствоваться настройкой следующих возможностей Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="feac9-157">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="feac9-158">Конфигурация обнаружения конечных точек и ответов</span><span class="sxs-lookup"><span data-stu-id="feac9-158">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="feac9-159">Конфигурация защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="feac9-159">Next-generation protection configuration</span></span>
- <span data-ttu-id="feac9-160">Конфигурация уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="feac9-160">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="feac9-161">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="feac9-161">Related topics</span></span>
- [<span data-ttu-id="feac9-162">Onboarding using Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="feac9-162">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="feac9-163">Onboarding using Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="feac9-163">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
