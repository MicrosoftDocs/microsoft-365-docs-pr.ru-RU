---
title: Этапы развертывания
description: Узнайте, как развернуть конечную точку Microsoft Defender для конечной точки, подготавливая, настраивая и внося конечные точки в эту службу.
keywords: развертывание, подготовка, настройка, бортовая, фаза, развертывание, развертывание, принятие, настройка
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165169"
---
# <a name="deployment-phases"></a><span data-ttu-id="caeb9-104">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="caeb9-104">Deployment phases</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="caeb9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="caeb9-105">**Applies to:**</span></span>
- [<span data-ttu-id="caeb9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="caeb9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="caeb9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="caeb9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="caeb9-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="caeb9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="caeb9-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="caeb9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="caeb9-110">Узнайте, как развернуть Microsoft Defender для конечной точки, чтобы ваше предприятие воспользовалось профилактической защитой, обнаружением нарушений, автоматическим расследованием и ответом.</span><span class="sxs-lookup"><span data-stu-id="caeb9-110">Learn how to deploy Microsoft Defender for Endpoint so that your enterprise can take advantage of preventative protection, post-breach detection, automated investigation, and response.</span></span> 


<span data-ttu-id="caeb9-111">Это руководство помогает вам работать с заинтересованными сторонами для подготовки среды и бортовых устройств методично, переходя от оценки к содержательному пилоту, к полному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="caeb9-111">This guide helps you work across stakeholders to prepare your environment and then onboard devices in a methodical way, moving from evaluation, to a meaningful pilot, to full deployment.</span></span>

<span data-ttu-id="caeb9-112">Каждый раздел соответствует отдельной статье в этом решении.</span><span class="sxs-lookup"><span data-stu-id="caeb9-112">Each section corresponds to a separate article in this solution.</span></span>

![Изображение этапов развертывания с подробными сведениями из таблицы](images/deployment-guide-phases.png)


![Сводка этапов развертывания: подготовка, настройка, бортовой](images/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="caeb9-115">Этап</span><span class="sxs-lookup"><span data-stu-id="caeb9-115">Phase</span></span> | <span data-ttu-id="caeb9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="caeb9-116">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="caeb9-117">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="caeb9-117">Phase 1: Prepare</span></span>](prepare-deployment.md)| <span data-ttu-id="caeb9-118">Узнайте, что необходимо учитывать при развертывании Defender для конечной точки, таких как утверждения заинтересованных сторон, соображения среды, разрешения доступа и порядок принятия возможностей.</span><span class="sxs-lookup"><span data-stu-id="caeb9-118">Learn about what you need to consider when deploying Defender for Endpoint such as stakeholder approvals, environment considerations, access permissions, and adoption order of capabilities.</span></span> 
| [<span data-ttu-id="caeb9-119">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="caeb9-119">Phase 2: Setup</span></span>](production-deployment.md)|  <span data-ttu-id="caeb9-120">Получите инструкции по начальным шагам, которые необходимо предпринять, чтобы получить доступ к порталу, например к проверке лицензирования, завершению мастера установки и конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="caeb9-120">Get guidance on the initial steps you need to take so that you can access the portal such as validating licensing, completing the setup wizard, and network configuration.</span></span> 
| [<span data-ttu-id="caeb9-121">Этап 3. Подключение</span><span class="sxs-lookup"><span data-stu-id="caeb9-121">Phase 3: Onboard</span></span>](onboarding.md) | <span data-ttu-id="caeb9-122">Узнайте, как использовать кольца развертывания, поддерживаемые средства бортового использования в зависимости от типа конечной точки, и настройка доступных возможностей.</span><span class="sxs-lookup"><span data-stu-id="caeb9-122">Learn how to make use of deployment rings, supported onboarding tools based on the type of endpoint, and configuring available capabilities.</span></span> 


<span data-ttu-id="caeb9-123">После завершения этого руководства вы будете настроены с нужными разрешениями доступа, конечные точки будут на борту и отчеты о данных датчиков службы, а также возможности, такие как защита следующего поколения и снижение поверхности атаки будут на месте.</span><span class="sxs-lookup"><span data-stu-id="caeb9-123">After you've completed this guide, you'll be setup with the right access permissions, your endpoints will be onboarded and reporting sensor data to the service, and capabilities such as next-generation protection and attack surface reduction will be in place.</span></span>



<span data-ttu-id="caeb9-124">Независимо от архитектуры среды и метода развертывания, которые вы выбрали в руководстве по развертыванию [Plan,](deployment-strategy.md) это руководство будет поддерживать вас в конечных точках на борту.</span><span class="sxs-lookup"><span data-stu-id="caeb9-124">Regardless of the environment architecture and method of deployment you choose outlined in the [Plan deployment](deployment-strategy.md) guidance, this guide is going to support you in onboarding endpoints.</span></span> 








## <a name="key-capabilities"></a><span data-ttu-id="caeb9-125">Ключевые возможности</span><span class="sxs-lookup"><span data-stu-id="caeb9-125">Key capabilities</span></span>

<span data-ttu-id="caeb9-126">Несмотря на то, что Microsoft Defender для конечной точки предоставляет множество возможностей, основная цель этого руководства по развертыванию состоит в том, чтобы начать работу с помощью бортовых устройств.</span><span class="sxs-lookup"><span data-stu-id="caeb9-126">While Microsoft Defender for Endpoint provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="caeb9-127">В дополнение к onboarding, это руководство начинается со следующими возможностями.</span><span class="sxs-lookup"><span data-stu-id="caeb9-127">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>



<span data-ttu-id="caeb9-128">Возможность</span><span class="sxs-lookup"><span data-stu-id="caeb9-128">Capability</span></span> | <span data-ttu-id="caeb9-129">Описание</span><span class="sxs-lookup"><span data-stu-id="caeb9-129">Description</span></span> 
:---|:---
<span data-ttu-id="caeb9-130">Обнаружение и устранение угроз на конечных точках</span><span class="sxs-lookup"><span data-stu-id="caeb9-130">Endpoint detection and response</span></span> | <span data-ttu-id="caeb9-131">Для обнаружения, расследования и реагирования на попытки вторжения и активных нарушений на месте работают возможности обнаружения конечных точек и реагирования на них.</span><span class="sxs-lookup"><span data-stu-id="caeb9-131">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span>
<span data-ttu-id="caeb9-132">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="caeb9-132">Next-generation protection</span></span> | <span data-ttu-id="caeb9-133">Чтобы еще больше усилить периметр безопасности сети, Microsoft Defender для конечной точки использует защиту следующего поколения, предназначенную для улавливания всех типов возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="caeb9-133">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>
<span data-ttu-id="caeb9-134">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="caeb9-134">Attack surface reduction</span></span> |  <span data-ttu-id="caeb9-135">Предоставление первой линии защиты в стеке.</span><span class="sxs-lookup"><span data-stu-id="caeb9-135">Provide the first line of defense in the stack.</span></span> <span data-ttu-id="caeb9-136">Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, этот набор возможностей позволяет противостоять атакам и эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="caeb9-136">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

<span data-ttu-id="caeb9-137">Все эти возможности доступны для владельцев лицензий Конечной точки для Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="caeb9-137">All these capabilities are available for Microsoft Defender for Endpoint license holders.</span></span> <span data-ttu-id="caeb9-138">Дополнительные сведения см. [в сведениях о требованиях к лицензированию.](minimum-requirements.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="caeb9-138">For more information, see [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

## <a name="scope"></a><span data-ttu-id="caeb9-139">Область</span><span class="sxs-lookup"><span data-stu-id="caeb9-139">Scope</span></span>

### <a name="in-scope"></a><span data-ttu-id="caeb9-140">В области</span><span class="sxs-lookup"><span data-stu-id="caeb9-140">In scope</span></span>

-   <span data-ttu-id="caeb9-141">Использование Microsoft Endpoint Manager и Microsoft Endpoint Manager конечных точек в службе и настройка возможностей</span><span class="sxs-lookup"><span data-stu-id="caeb9-141">Use of Microsoft Endpoint Manager and Microsoft Endpoint Manager to onboard endpoints into the service and configure capabilities</span></span>

-   <span data-ttu-id="caeb9-142">Включение функций Defender для обнаружение и нейтрализация атак на конечные точки (EDR)</span><span class="sxs-lookup"><span data-stu-id="caeb9-142">Enabling Defender for Endpoint endpoint detection and response (EDR)  capabilities</span></span>

-   <span data-ttu-id="caeb9-143">Включение возможностей платформы защиты конечных точек Defender для конечной точки (EPP)</span><span class="sxs-lookup"><span data-stu-id="caeb9-143">Enabling Defender for Endpoint endpoint protection platform (EPP) capabilities</span></span>

    -   <span data-ttu-id="caeb9-144">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="caeb9-144">Next-generation protection</span></span>

    -   <span data-ttu-id="caeb9-145">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="caeb9-145">Attack surface reduction</span></span>


### <a name="out-of-scope"></a><span data-ttu-id="caeb9-146">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="caeb9-146">Out of scope</span></span>

<span data-ttu-id="caeb9-147">Ниже из этого руководства по развертыванию находятся вне сферы действия:</span><span class="sxs-lookup"><span data-stu-id="caeb9-147">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="caeb9-148">Конфигурация сторонних решений, которые могут интегрироваться с Defender для endpoint</span><span class="sxs-lookup"><span data-stu-id="caeb9-148">Configuration of third-party solutions that might integrate with Defender for Endpoint</span></span>

-   <span data-ttu-id="caeb9-149">Тестирование на проникновение в производственной среде</span><span class="sxs-lookup"><span data-stu-id="caeb9-149">Penetration testing in production environment</span></span>




## <a name="see-also"></a><span data-ttu-id="caeb9-150">См. также</span><span class="sxs-lookup"><span data-stu-id="caeb9-150">See also</span></span>
- [<span data-ttu-id="caeb9-151">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="caeb9-151">Phase 1: Prepare</span></span>](prepare-deployment.md)
- [<span data-ttu-id="caeb9-152">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="caeb9-152">Phase 2: Set up</span></span>](production-deployment.md)
- [<span data-ttu-id="caeb9-153">Этап 3. Подключение</span><span class="sxs-lookup"><span data-stu-id="caeb9-153">Phase 3: Onboard</span></span>](onboarding.md)
- [<span data-ttu-id="caeb9-154">Планирование развертывания</span><span class="sxs-lookup"><span data-stu-id="caeb9-154">Plan deployment</span></span>](deployment-strategy.md)