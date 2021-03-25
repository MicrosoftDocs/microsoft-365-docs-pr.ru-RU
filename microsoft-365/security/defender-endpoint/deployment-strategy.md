---
title: Планирование развертывания конечной точки в Microsoft Defender
description: Выберите лучшую стратегию развертывания Microsoft Defender для конечных точек для среды
keywords: развертывание, планирование, стратегия развертывания, локальное облако, управление по прему, оценке, бортовой, локальной, групповой политике, гп, менеджеру конечных точек, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163579"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="b65f1-104">Планирование развертывания конечной точки в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b65f1-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b65f1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b65f1-105">**Applies to:**</span></span>
- [<span data-ttu-id="b65f1-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b65f1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b65f1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b65f1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b65f1-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b65f1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b65f1-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b65f1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="b65f1-110">Запланируйте развертывание Microsoft Defender для конечной точки, чтобы максимально повысить возможности безопасности в пакете и лучше защитить свое предприятие от киберугроз.</span><span class="sxs-lookup"><span data-stu-id="b65f1-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="b65f1-111">Это решение содержит рекомендации по выявлению архитектуры среды, выбор типа средства развертывания, который наилучшим образом соответствует вашим потребностям, и инструкции по настройке возможностей.</span><span class="sxs-lookup"><span data-stu-id="b65f1-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![Изображение потока развертывания](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="b65f1-113">Шаг 1. Определение архитектуры</span><span class="sxs-lookup"><span data-stu-id="b65f1-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="b65f1-114">Мы понимаем, что каждая корпоративная среда уникальна, поэтому мы предоставили несколько вариантов, чтобы предоставить вам гибкость при выборе способов развертывания службы.</span><span class="sxs-lookup"><span data-stu-id="b65f1-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="b65f1-115">В зависимости от среды некоторые средства лучше подходят для определенных архитектур.</span><span class="sxs-lookup"><span data-stu-id="b65f1-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="b65f1-116">Используйте следующий материал, чтобы выбрать соответствующую архитектуру Defender для конечной точки, которая лучше всего подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b65f1-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="b65f1-117">Item</span><span class="sxs-lookup"><span data-stu-id="b65f1-117">Item</span></span> | <span data-ttu-id="b65f1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b65f1-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="b65f1-119">[![Изображение большого пальца для стратегии развертывания Defender для конечной точки](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="b65f1-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="b65f1-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="b65f1-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="b65f1-121">Материалы по архитектуре помогут вам спланировать развертывание для следующих архитектур:</span><span class="sxs-lookup"><span data-stu-id="b65f1-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="b65f1-122">Облачное развертывание</span><span class="sxs-lookup"><span data-stu-id="b65f1-122">Cloud-native</span></span> </li><li> <span data-ttu-id="b65f1-123">Совместное управление</span><span class="sxs-lookup"><span data-stu-id="b65f1-123">Co-management</span></span> </li><li> <span data-ttu-id="b65f1-124">Локальное развертывание</span><span class="sxs-lookup"><span data-stu-id="b65f1-124">On-premise</span></span></li><li><span data-ttu-id="b65f1-125">Оценка и локальное внедрение</span><span class="sxs-lookup"><span data-stu-id="b65f1-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="b65f1-126">Шаг 2. Выбор метода развертывания</span><span class="sxs-lookup"><span data-stu-id="b65f1-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="b65f1-127">Defender for Endpoint поддерживает различные конечные точки, которые можно использовать на борту службы.</span><span class="sxs-lookup"><span data-stu-id="b65f1-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="b65f1-128">В следующей таблице перечислены поддерживаемые конечные точки и соответствующий инструмент развертывания, который можно использовать для правильного планирования развертывания.</span><span class="sxs-lookup"><span data-stu-id="b65f1-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="b65f1-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="b65f1-129">Endpoint</span></span>     | <span data-ttu-id="b65f1-130">Средство развертывания</span><span class="sxs-lookup"><span data-stu-id="b65f1-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="b65f1-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b65f1-131">**Windows**</span></span>  |  [<span data-ttu-id="b65f1-132">Локальный скрипт (до 10 устройств)</span><span class="sxs-lookup"><span data-stu-id="b65f1-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="b65f1-133">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="b65f1-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="b65f1-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="b65f1-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="b65f1-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b65f1-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="b65f1-136">Скрипты VDI</span><span class="sxs-lookup"><span data-stu-id="b65f1-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="b65f1-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="b65f1-137">**macOS**</span></span>    | [<span data-ttu-id="b65f1-138">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="b65f1-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="b65f1-139">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b65f1-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="b65f1-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="b65f1-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="b65f1-141">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="b65f1-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="b65f1-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="b65f1-142">**Linux Server**</span></span> | [<span data-ttu-id="b65f1-143">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="b65f1-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="b65f1-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="b65f1-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="b65f1-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="b65f1-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="b65f1-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="b65f1-146">**iOS**</span></span>      | [<span data-ttu-id="b65f1-147">На основе приложения</span><span class="sxs-lookup"><span data-stu-id="b65f1-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="b65f1-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="b65f1-148">**Android**</span></span>  | [<span data-ttu-id="b65f1-149">Менеджер конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b65f1-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="b65f1-150">Шаг 3. Настройка возможностей</span><span class="sxs-lookup"><span data-stu-id="b65f1-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="b65f1-151">После использования конечных точек настройте возможности безопасности в Defender для конечной точки, чтобы можно было максимально повысить надежность защиты, доступную в наборе.</span><span class="sxs-lookup"><span data-stu-id="b65f1-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="b65f1-152">Возможности включают в себя:</span><span class="sxs-lookup"><span data-stu-id="b65f1-152">Capabilities include:</span></span>

- <span data-ttu-id="b65f1-153">Обнаружение и устранение угроз на конечных точках</span><span class="sxs-lookup"><span data-stu-id="b65f1-153">Endpoint detection and response</span></span>
- <span data-ttu-id="b65f1-154">Защита следующего поколения</span><span class="sxs-lookup"><span data-stu-id="b65f1-154">Next-generation protection</span></span>
- <span data-ttu-id="b65f1-155">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="b65f1-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="b65f1-156">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b65f1-156">Related topics</span></span>
- [<span data-ttu-id="b65f1-157">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="b65f1-157">Deployment phases</span></span>](deployment-phases.md)
