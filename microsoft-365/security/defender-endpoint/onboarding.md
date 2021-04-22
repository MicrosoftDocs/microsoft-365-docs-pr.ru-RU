---
title: На борту службы Microsoft Defender для конечных точек
description: Узнайте, как переназначить конечные точки в службу Microsoft Defender для конечных точек
keywords: защитник Microsoft для конечной точки, на борту, развертывание
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
ms.openlocfilehash: f63b4f81f454fec60a26c7cb063d66bed4a2bead
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933545"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="5c8c9-104">На борту службы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="5c8c9-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c8c9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5c8c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="5c8c9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5c8c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c8c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c8c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5c8c9-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5c8c9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5c8c9-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5c8c9-110">Узнайте о различных этапах развертывания Microsoft Defender для конечной точки и о настройке возможностей решения.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="5c8c9-111">Развертывание Defender для конечной точки — это трех этапный процесс:</span><span class="sxs-lookup"><span data-stu-id="5c8c9-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="5c8c9-112">[![этап развертывания — подготовка](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="5c8c9-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="5c8c9-113">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="5c8c9-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="5c8c9-114">[![этап развертывания — установка](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="5c8c9-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="5c8c9-115">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="5c8c9-115">Phase 2: Setup</span></span>](production-deployment.md) | ![этап развертывания — на борту](images/phase-diagrams/onboard.png)<br><span data-ttu-id="5c8c9-117">Этап 3. Подключение</span><span class="sxs-lookup"><span data-stu-id="5c8c9-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="5c8c9-118">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="5c8c9-118">*You are here!*</span></span>|

<span data-ttu-id="5c8c9-119">В настоящее время вы находитесь на этапе вмеяния.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="5c8c9-120">Вот шаги, которые необходимо предпринять для развертывания Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="5c8c9-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="5c8c9-121">Шаг 1. Конечные точки на борту службы</span><span class="sxs-lookup"><span data-stu-id="5c8c9-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="5c8c9-122">Шаг 2. Настройка возможностей</span><span class="sxs-lookup"><span data-stu-id="5c8c9-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="5c8c9-123">Шаг 1. Конечные точки на борту с помощью любого из поддерживаемых средств управления</span><span class="sxs-lookup"><span data-stu-id="5c8c9-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="5c8c9-124">В [разделе Развертывание](deployment-strategy.md) Plan описаны общие действия, которые необходимо предпринять для развертывания Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="5c8c9-125">Просмотрите это видео, чтобы получить краткий обзор процесса работы с бортовой частью и узнать о доступных средствах и методах.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="5c8c9-126">После определения архитектуры необходимо решить, какой метод развертывания использовать.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="5c8c9-127">Инструмент развертывания, который вы выбираете, влияет на то, как вы работаете с конечными точками на борту службы.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="5c8c9-128">Параметры onboarding tool</span><span class="sxs-lookup"><span data-stu-id="5c8c9-128">Onboarding tool options</span></span>

<span data-ttu-id="5c8c9-129">В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="5c8c9-130">Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c8c9-130">Endpoint</span></span>     | <span data-ttu-id="5c8c9-131">Параметры инструмента</span><span class="sxs-lookup"><span data-stu-id="5c8c9-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="5c8c9-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="5c8c9-132">**Windows**</span></span>  |  [<span data-ttu-id="5c8c9-133">Локальный скрипт (до 10 устройств)</span><span class="sxs-lookup"><span data-stu-id="5c8c9-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="5c8c9-134">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="5c8c9-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="5c8c9-135">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="5c8c9-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="5c8c9-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5c8c9-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="5c8c9-137">Скрипты VDI</span><span class="sxs-lookup"><span data-stu-id="5c8c9-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="5c8c9-138">Интеграция с Защитником Azure</span><span class="sxs-lookup"><span data-stu-id="5c8c9-138">Integration with Azure Defender</span></span>](configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="5c8c9-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="5c8c9-139">**macOS**</span></span>    | [<span data-ttu-id="5c8c9-140">Локальные сценарии</span><span class="sxs-lookup"><span data-stu-id="5c8c9-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="5c8c9-141">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c8c9-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="5c8c9-142">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="5c8c9-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="5c8c9-143">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5c8c9-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="5c8c9-144">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="5c8c9-144">**Linux Server**</span></span> | [<span data-ttu-id="5c8c9-145">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="5c8c9-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="5c8c9-146">Puppet</span><span class="sxs-lookup"><span data-stu-id="5c8c9-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="5c8c9-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="5c8c9-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="5c8c9-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="5c8c9-148">**iOS**</span></span>      | [<span data-ttu-id="5c8c9-149">На основе приложения</span><span class="sxs-lookup"><span data-stu-id="5c8c9-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="5c8c9-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="5c8c9-150">**Android**</span></span>  | [<span data-ttu-id="5c8c9-151">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c8c9-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="5c8c9-152">Шаг 2. Настройка возможностей</span><span class="sxs-lookup"><span data-stu-id="5c8c9-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="5c8c9-153">После настроя конечных точек вы настроите различные возможности, такие как обнаружение конечной точки и реагирование, защита следующего поколения и уменьшение поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="5c8c9-154">Пример развертывания</span><span class="sxs-lookup"><span data-stu-id="5c8c9-154">Example deployments</span></span>
<span data-ttu-id="5c8c9-155">В этом руководстве по развертыванию мы назначим вам использование двух средств развертывания для конечных точек на борту и настройку возможностей.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="5c8c9-156">Средства в примере развертывания:</span><span class="sxs-lookup"><span data-stu-id="5c8c9-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="5c8c9-157">Подключение с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5c8c9-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="5c8c9-158">Подключение с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5c8c9-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="5c8c9-159">Используя указанные выше средства развертывания, вы будете руководствоваться настройкой следующих возможностей Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="5c8c9-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="5c8c9-160">Конфигурация обнаружения конечных точек и ответов</span><span class="sxs-lookup"><span data-stu-id="5c8c9-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="5c8c9-161">Конфигурация защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="5c8c9-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="5c8c9-162">Конфигурация уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5c8c9-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c8c9-163">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="5c8c9-163">Related topics</span></span>
- [<span data-ttu-id="5c8c9-164">Подключение с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5c8c9-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="5c8c9-165">Подключение с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5c8c9-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="5c8c9-166">Безопасные документы в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5c8c9-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
