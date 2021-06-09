---
title: Подключение с помощью Microsoft Endpoint Manager
description: Узнайте, как в Microsoft Defender для конечной точки использовать Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, Microsoft endpoint manager
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
ms.openlocfilehash: f3442528f6d9239219f0b4638f75758a055717de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842642"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="5d9b8-104">Подключение с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5d9b8-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d9b8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5d9b8-105">**Applies to:**</span></span>
- [<span data-ttu-id="5d9b8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5d9b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5d9b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d9b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5d9b8-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5d9b8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d9b8-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5d9b8-110">Эта статья является частью руководства по развертыванию и выступает в качестве примера бортового метода.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="5d9b8-111">В разделе [Планирование](deployment-strategy.md) для бортовых устройств для службы было предоставлено несколько методов.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="5d9b8-112">В этом разделе описывается облачная архитектура.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="5d9b8-113">![Изображение облачной архитектуры ](images/cloud-native-architecture.png)
 *Схема архитектуры среды*</span><span class="sxs-lookup"><span data-stu-id="5d9b8-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="5d9b8-114">Несмотря на то, что Defender для конечной точки поддерживает вовсю различные конечные точки и средства, эта статья не охватывает их.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="5d9b8-115">Сведения об общей онбордации с помощью других поддерживаемых средств развертывания и методов см. в [обзоре onboarding.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="5d9b8-116">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) — это платформа решений, которая объединяет несколько служб.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-116">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="5d9b8-117">Он включает [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) для управления облачными устройствами.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-117">It includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="5d9b8-118">В этом разделе данная тема направляет пользователей в:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-118">This topic guides users in:</span></span>
- <span data-ttu-id="5d9b8-119">Шаг 1. Назначить конфигурации на службе с помощью onboarding devices, создав группу в Microsoft Endpoint Manager (MEM)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="5d9b8-120">Шаг 2. Настройка функций Defender для конечных точек с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5d9b8-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="5d9b8-121">Это руководство по введению в борт поможет вам пройти следующие основные действия, которые необходимо предпринять при использовании Microsoft Endpoint Manager:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="5d9b8-122">Определение целевых устройств или пользователей</span><span class="sxs-lookup"><span data-stu-id="5d9b8-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="5d9b8-123">Создание группы Azure Active Directory (пользователь или устройство)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="5d9b8-124">Создание профиля конфигурации</span><span class="sxs-lookup"><span data-stu-id="5d9b8-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="5d9b8-125">В Microsoft Endpoint Manager мы будем направлять вас в создании отдельной политики для каждой возможности.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="5d9b8-126">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="5d9b8-126">Resources</span></span>


<span data-ttu-id="5d9b8-127">Вот ссылки, необходимые для остальной части процесса:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="5d9b8-128">Портал MEM</span><span class="sxs-lookup"><span data-stu-id="5d9b8-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="5d9b8-129">Центр безопасности</span><span class="sxs-lookup"><span data-stu-id="5d9b8-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="5d9b8-130">Базовые показатели безопасности Intune</span><span class="sxs-lookup"><span data-stu-id="5d9b8-130">Intune Security baselines</span></span>](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="5d9b8-131">Дополнительные сведения о Microsoft Endpoint Manager, ознакомьтесь с этими ресурсами:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="5d9b8-132">Microsoft Endpoint Manager страницы</span><span class="sxs-lookup"><span data-stu-id="5d9b8-132">Microsoft Endpoint Manager page</span></span>](/mem/)
- [<span data-ttu-id="5d9b8-133">Сообщение в блоге о схождении Intune и ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="5d9b8-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="5d9b8-134">Введение видео на MEM</span><span class="sxs-lookup"><span data-stu-id="5d9b8-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="5d9b8-135">Шаг 1. На борту устройств путем создания группы в MEM для назначения конфигураций на</span><span class="sxs-lookup"><span data-stu-id="5d9b8-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="5d9b8-136">Определение целевых устройств или пользователей</span><span class="sxs-lookup"><span data-stu-id="5d9b8-136">Identify target devices or users</span></span>
<span data-ttu-id="5d9b8-137">В этом разделе мы создадим тестовую группу для назначения конфигураций.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="5d9b8-138">Intune использует Azure Active Directory (Azure AD) для управления устройствами и пользователями.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="5d9b8-139">В качестве администратора Intune можно настроить группы в соответствии с вашими организационными потребностями.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="5d9b8-140">Дополнительные сведения см. в [добавлении групп для организации пользователей и устройств.](/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-140">For more information, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="5d9b8-141">Создание группы</span><span class="sxs-lookup"><span data-stu-id="5d9b8-141">Create a group</span></span>

1.  <span data-ttu-id="5d9b8-142">Откройте портал MEM.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d9b8-143">Open **Groups > New Group**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-144">![Изображение Microsoft Endpoint Manager 1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="5d9b8-145">Введите сведения и создайте новую группу.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-146">![Изображение Microsoft Endpoint Manager 2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="5d9b8-147">Добавьте тестовый пользователь или устройство.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="5d9b8-148">Откройте новую **группу из > групп.**</span><span class="sxs-lookup"><span data-stu-id="5d9b8-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="5d9b8-149">Выберите  **члены > добавить членов**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="5d9b8-150">Найдите тестовый пользователь или устройство и выберите его.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-151">![Изображение Microsoft Endpoint Manager 3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="5d9b8-152">Теперь в группе тестирования есть член, который необходимо протестировать.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="5d9b8-153">Шаг 2. Создание политик конфигурации для настройки возможностей Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="5d9b8-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="5d9b8-154">В следующем разделе будет создаваться ряд политик конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="5d9b8-155">Во-первых, это политика конфигурации, чтобы выбрать, какие группы пользователей или устройств будут на борту в Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="5d9b8-156">Обнаружение и устранение угроз на конечных точках</span><span class="sxs-lookup"><span data-stu-id="5d9b8-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="5d9b8-157">Затем вы продолжите создание нескольких различных типов политик безопасности конечных точек:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="5d9b8-158">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="5d9b8-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="5d9b8-159">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="5d9b8-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="5d9b8-160">Обнаружение и устранение угроз на конечных точках</span><span class="sxs-lookup"><span data-stu-id="5d9b8-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="5d9b8-161">Откройте портал MEM.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d9b8-162">Перейдите к **службе безопасности > endpoint detection and response**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="5d9b8-163">Нажмите **кнопку Создать профиль**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-164">![Изображение Microsoft Endpoint Manager 4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="5d9b8-165">В платформе выберите Windows 10 и более **поздний, Profile - Endpoint detection and response > Create**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="5d9b8-166">Введите имя и описание, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-167">![Изображение Microsoft Endpoint Manager 5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="5d9b8-168">Выберите параметры по мере необходимости, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-169">![Изображение Microsoft Endpoint Manager 6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d9b8-170">В этом примере это было автоматически заполнено, так как Defender для конечной точки уже интегрирован с Intune.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="5d9b8-171">Дополнительные сведения об интеграции см. в дополнительных сведениях [включить Microsoft Defender для конечной точки в Intune.](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="5d9b8-172">Ниже приводится пример того, что вы увидите, когда Microsoft Defender для конечной точки не интегрирована с Intune:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Изображение портала Microsoft Endpoint Manager 7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="5d9b8-174">При необходимости добавьте теги области, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-175">![Изображение Microsoft Endpoint Manager 8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="5d9b8-176">Добавьте тестовую группу, нажав на **Выберите группы,** чтобы включить и выбрать группу, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-177">![Изображение Microsoft Endpoint Manager 9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="5d9b8-178">Просмотрите и примите, а затем выберите  **Create**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-179">![Изображение Microsoft Endpoint Manager 10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="5d9b8-180">Вы можете просмотреть завершенную политику.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-181">![Изображение Microsoft Endpoint Manager 11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="5d9b8-182">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="5d9b8-182">Next-generation protection</span></span>

1.  <span data-ttu-id="5d9b8-183">Откройте портал MEM.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d9b8-184">Перейдите в **конечную > антивирусную > создать политику**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-185">![Изображение портала Microsoft Endpoint Manager 12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="5d9b8-186">Выберите **платформу — Windows 10 и более поздние — Windows и профиль — антивирусная программа в Microsoft Defender > Создать**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="5d9b8-187">Введите имя и описание, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-188">![Изображение портала Microsoft Endpoint Manager 13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="5d9b8-189">На странице **Параметры** конфигурации : Установите конфигурации, необходимые для антивирусная программа в Microsoft Defender (облачная защита, исключения, Real-Time защита и исправление).</span><span class="sxs-lookup"><span data-stu-id="5d9b8-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-190">![Изображение Microsoft Endpoint Manager 14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="5d9b8-191">При необходимости добавьте теги области, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-192">![Изображение Microsoft Endpoint Manager 15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="5d9b8-193">Выберите группы, которые необходимо включить, назначьте тестовой группе, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-194">![Изображение Microsoft Endpoint Manager 16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="5d9b8-195">Просмотрите и создайте, а затем выберите  **Create**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-196">![Изображение Microsoft Endpoint Manager 17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="5d9b8-197">Вы увидите созданную политику конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-198">![Изображение Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="5d9b8-199">Уменьшение поверхности атаки — правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5d9b8-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="5d9b8-200">Откройте портал MEM.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d9b8-201">Перейдите к **области безопасности конечных точек > для уменьшения поверхности Attack.**</span><span class="sxs-lookup"><span data-stu-id="5d9b8-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="5d9b8-202">Выберите  **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="5d9b8-203">Выберите **платформы - Windows 10 и более поздних — Профиль - Правила** уменьшения поверхности атаки > Создать .</span><span class="sxs-lookup"><span data-stu-id="5d9b8-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-204">![Изображение портала Microsoft Endpoint Manager 19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="5d9b8-205">Введите имя и описание, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-206">![Изображение Microsoft Endpoint Manager 20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="5d9b8-207">На странице **Параметры конфигурации:** Установите конфигурации, необходимые для правил уменьшения поверхности Атаки, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d9b8-208">Мы настроим все правила снижения поверхности атаки на аудит.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="5d9b8-209">Дополнительные сведения см. в [правилах уменьшения поверхности Attack.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-210">![Изображение Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="5d9b8-211">Добавьте теги области по мере необходимости, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-212">![Изображение Microsoft Endpoint Manager 22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="5d9b8-213">Выберите группы, включив и назначив группе тестирования, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-214">![Изображение Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="5d9b8-215">Просмотрите сведения, а затем выберите  **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-216">![Изображение Microsoft Endpoint Manager 24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="5d9b8-217">Просмотр политики.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-218">![Изображение Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="5d9b8-219">Уменьшение поверхности атаки — веб-защита</span><span class="sxs-lookup"><span data-stu-id="5d9b8-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="5d9b8-220">Откройте портал MEM.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d9b8-221">Перейдите к **области безопасности конечных точек > для уменьшения поверхности Attack.**</span><span class="sxs-lookup"><span data-stu-id="5d9b8-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="5d9b8-222">Выберите  **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="5d9b8-223">Выберите **Windows 10 и более поздний — веб> создать**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-224">![Изображение Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="5d9b8-225">Введите имя и описание, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-226">![Изображение Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="5d9b8-227">На странице **Параметры конфигурации**: Установите конфигурации, необходимые для веб-защиты, а затем выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d9b8-228">Мы настраиваем веб-защиту для блокировки.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="5d9b8-229">Дополнительные сведения см. в [веб-защите.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-230">![Изображение Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="5d9b8-231">Добавьте теги области по мере **необходимости > Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-232">![Изображение Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="5d9b8-233">Выберите **Назначение для тестирования группы > Далее**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-234">![Изображение Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="5d9b8-235">Выберите **обзор и создайте > создать**.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-236">![Изображение Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="5d9b8-237">Просмотр политики.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-238">![Изображение Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="5d9b8-239">Проверка параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="5d9b8-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="5d9b8-240">Подтверждение примененных политик</span><span class="sxs-lookup"><span data-stu-id="5d9b8-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="5d9b8-241">После того, как политика конфигурации назначена, на ее применение уйма времени займет некоторое время.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="5d9b8-242">Сведения о сроках см. в [сведениях о конфигурации Intune.](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-242">For information on timing, see [Intune configuration information](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="5d9b8-243">Чтобы подтвердить, что политика конфигурации применена к тестовом устройству, выполните следующий процесс для каждой политики конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="5d9b8-244">Откройте портал MEM и перейдите к соответствующей политике, как показано на шагах выше.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="5d9b8-245">В следующем примере показаны параметры защиты следующего поколения.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-246">[![Изображение Microsoft Endpoint Manager portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="5d9b8-247">Выберите политику **конфигурации,** чтобы просмотреть состояние политики.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-248">[![Изображение Microsoft Endpoint Manager portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="5d9b8-249">Чтобы  **увидеть состояние,** выберите состояние устройства.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-250">[![Изображение Microsoft Endpoint Manager portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="5d9b8-251">Чтобы  **увидеть** состояние, выберите состояние пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-252">[![Изображение Microsoft Endpoint Manager portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="5d9b8-253">Выберите  **состояние per-setting,** чтобы увидеть состояние.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="5d9b8-254">Это представление очень полезно для определения параметров, которые конфликтуют с другой политикой.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-255">[![Изображение Microsoft Endpoint Manager portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="5d9b8-256">Обнаружение и устранение угроз на конечных точках</span><span class="sxs-lookup"><span data-stu-id="5d9b8-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="5d9b8-257">Перед применением конфигурации не следует Endpoint Protection службу Defender для Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-258">[![Изображение панели Services1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="5d9b8-259">После того, как конфигурация будет применена, необходимо Endpoint Protection службу Defender for Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-260">[![Изображение панели Services2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="5d9b8-261">После запуска служб на устройстве устройство отображается в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-262">[![Изображение Центр безопасности в Microsoft Defender ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="5d9b8-263">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="5d9b8-263">Next-generation protection</span></span>

1.  <span data-ttu-id="5d9b8-264">Прежде чем применять политику на тестовом устройстве, вы должны иметь возможность вручную управлять настройками, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-265">![Изображение параметра page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="5d9b8-266">После того, как политика будет применена, вы не сможете вручную управлять настройками.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d9b8-267">На следующем изображении **включаем облачную защиту** и включаем защиту в режиме реального времени. </span><span class="sxs-lookup"><span data-stu-id="5d9b8-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d9b8-268">![Изображение параметра page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="5d9b8-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="5d9b8-269">Уменьшение поверхности атаки — правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5d9b8-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="5d9b8-270">Перед тем как применить политику на тестовом устройстве, введите окно PowerShell и введите `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="5d9b8-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="5d9b8-271">Это должно отвечать следующими строками без контента:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="5d9b8-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="5d9b8-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="5d9b8-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Изображение командной строки1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="5d9b8-276">После применения политики на тестовом устройстве откройте powerShell Windows и введите `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="5d9b8-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="5d9b8-277">Это должно отвечать следующими строками содержимым, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="5d9b8-277">This should respond with the following lines with content as shown below:</span></span>

    ![Изображение командной строки2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="5d9b8-279">Уменьшение поверхности атаки — веб-защита</span><span class="sxs-lookup"><span data-stu-id="5d9b8-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="5d9b8-280">На тестовом устройстве откройте powerShell Windows и введите `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="5d9b8-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="5d9b8-281">Это должно отвечать с 0, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-281">This should respond with a 0 as shown below.</span></span>

    ![Изображение командной строки3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="5d9b8-283">После применения политики откройте powerShell Windows и введите `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="5d9b8-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="5d9b8-284">Это должно отвечать с 1, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5d9b8-284">This should respond with a 1 as shown below.</span></span>

    ![Изображение командной строки4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
