---
title: Настройка условного доступа в Microsoft Defender для конечной точки
description: Узнайте о действиях, которые необходимо выполнить в Intune, Microsoft Defender Security Center и Azure для реализации условного доступа
keywords: условный доступ, условный, доступ, риск устройства, уровень риска, интеграция, интеграция intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 482f86d4a0a181b72a0a33eeb1a857dce0664584
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893653"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b9962-104">Настройка условного доступа в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b9962-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9962-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b9962-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9962-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b9962-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9962-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9962-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b9962-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b9962-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9962-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b9962-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b9962-110">В этом разделе вы сможете выполнить все необходимые действия для правильной реализации условного доступа.</span><span class="sxs-lookup"><span data-stu-id="b9962-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="b9962-111">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="b9962-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="b9962-112">Важно отметить, что зарегистрированные устройства Azure AD не поддерживаются в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="b9962-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="b9962-113">Поддерживаются только зарегистрированные устройства Intune.</span><span class="sxs-lookup"><span data-stu-id="b9962-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="b9962-114">Необходимо убедиться, что все устройства зарегистрированы в Intune.</span><span class="sxs-lookup"><span data-stu-id="b9962-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="b9962-115">Для регистрации устройств в Intune можно использовать любой из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b9962-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="b9962-116">ИТ-администратор. Дополнительные сведения о том, как включить автоматическую регистрацию, см. в [записи Windows](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="b9962-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="b9962-117">Конечный пользователь. Дополнительные сведения о регистрации устройства Windows 10 в Intune см. в записи устройства [Windows 10 в Intune.](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="b9962-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="b9962-118">Альтернатива для конечных пользователей. Дополнительные сведения о присоединении к домену Azure AD см. в примере [How to: Plan your Azure AD join implementation.](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)</span><span class="sxs-lookup"><span data-stu-id="b9962-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="b9962-119">Необходимо предпринять действия в Центре безопасности Защитника Майкрософт, портале Intune и портале Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b9962-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="b9962-120">Важно отметить необходимые роли для доступа к этим порталам и реализации условного доступа:</span><span class="sxs-lookup"><span data-stu-id="b9962-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="b9962-121">**Центр безопасности Защитника** Майкрософт . Для включаемой интеграции необходимо войти на портал с ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="b9962-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="b9962-122">**Intune** . Необходимо войти на портал с правами администратора безопасности с разрешениями управления.</span><span class="sxs-lookup"><span data-stu-id="b9962-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="b9962-123">**Портал Azure AD** . Вам потребуется войти в качестве глобального администратора, администратора безопасности или администратора условного доступа.</span><span class="sxs-lookup"><span data-stu-id="b9962-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="b9962-124">Вам понадобится среда Microsoft Intune с управляемым управлением Intune и устройствами Azure AD с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b9962-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="b9962-125">Чтобы включить условный доступ, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b9962-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="b9962-126">Шаг 1. Включи подключение Microsoft Intune из Центра безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b9962-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="b9962-127">Шаг 2. Включение интеграции Defender для конечных точек в Intune</span><span class="sxs-lookup"><span data-stu-id="b9962-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="b9962-128">Шаг 3. Создание политики соответствия требованиям в Intune</span><span class="sxs-lookup"><span data-stu-id="b9962-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="b9962-129">Шаг 4. Назначение политики</span><span class="sxs-lookup"><span data-stu-id="b9962-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="b9962-130">Шаг 5. Создание политики условного доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="b9962-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="b9962-131">Шаг 1. Включив подключение Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b9962-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="b9962-132">В области навигации выберите **параметры**  >  **Расширенные возможности**  >  **подключения Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="b9962-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="b9962-133">Перенастройка параметра Microsoft Intune **для On**.</span><span class="sxs-lookup"><span data-stu-id="b9962-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="b9962-134">Нажмите **кнопку Сохранить предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="b9962-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="b9962-135">Шаг 2. Включение интеграции Defender для конечных точек в Intune</span><span class="sxs-lookup"><span data-stu-id="b9962-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="b9962-136">Войдите на [портал Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b9962-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b9962-137">Выберите **соответствие требованиям** устройства Microsoft Defender  >  **ATP**.</span><span class="sxs-lookup"><span data-stu-id="b9962-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="b9962-138">Установите **подключение устройств Windows 10.0.15063+** к расширенным средствам защиты от угроз Microsoft Defender. </span><span class="sxs-lookup"><span data-stu-id="b9962-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="b9962-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9962-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="b9962-140">Шаг 3. Создание политики соответствия требованиям в Intune</span><span class="sxs-lookup"><span data-stu-id="b9962-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="b9962-141">На [портале Azure](https://portal.azure.com)выберите **все службы,** фильтруем **на Intune** и выберите **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="b9962-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="b9962-142">Выбор **политик соответствия требованиям** к  >    >  **устройству Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="b9962-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="b9962-143">Введите **имя** и **описание**.</span><span class="sxs-lookup"><span data-stu-id="b9962-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="b9962-144">В **Платформе** выберите **Windows 10 и более поздние версии.**</span><span class="sxs-lookup"><span data-stu-id="b9962-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="b9962-145">В **параметрах "Здоровье** устройства" установите **параметр Require the device to be at or under the Device Threat Level** to your preferred level:</span><span class="sxs-lookup"><span data-stu-id="b9962-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="b9962-146">**Обеспечено.** Этот уровень является наиболее безопасным.</span><span class="sxs-lookup"><span data-stu-id="b9962-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="b9962-147">Устройство не может иметь существующих угроз и по-прежнему получать доступ к ресурсам компании.</span><span class="sxs-lookup"><span data-stu-id="b9962-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="b9962-148">Если найдены какие-либо угрозы, устройство оценивается как некомплиентное.</span><span class="sxs-lookup"><span data-stu-id="b9962-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="b9962-149">**Низкий** уровень. Устройство соответствует требованиям, если существуют только угрозы низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="b9962-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="b9962-150">Устройства со средним или высоким уровнем угрозы не соответствуют требованиям.</span><span class="sxs-lookup"><span data-stu-id="b9962-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="b9962-151">**Medium.** Устройство соответствует требованиям, если угрозы, найденные на устройстве, являются низкими или средними.</span><span class="sxs-lookup"><span data-stu-id="b9962-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="b9962-152">При обнаружении угроз высокого уровня устройство определяется как некомплиентное.</span><span class="sxs-lookup"><span data-stu-id="b9962-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="b9962-153">**Высокий.** Этот уровень является наименее безопасным и позволяет использовать все уровни угроз.</span><span class="sxs-lookup"><span data-stu-id="b9962-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="b9962-154">Поэтому устройства с высоким, средним или низким уровнем угроз считаются совместимыми.</span><span class="sxs-lookup"><span data-stu-id="b9962-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="b9962-155">Выберите **ОК** и **создайте** для сохранения изменений (и создания политики).</span><span class="sxs-lookup"><span data-stu-id="b9962-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="b9962-156">Шаг 4. Назначение политики</span><span class="sxs-lookup"><span data-stu-id="b9962-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="b9962-157">На [портале Azure](https://portal.azure.com)выберите **все службы,** фильтруем **на Intune** и выберите **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="b9962-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="b9962-158">Выберите **политики соответствия** требованиям> политики соответствия требованиям Microsoft Defender  >   ATP.</span><span class="sxs-lookup"><span data-stu-id="b9962-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="b9962-159">Выберите **Назначения**.</span><span class="sxs-lookup"><span data-stu-id="b9962-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="b9962-160">Включите или исключите группы Azure AD, чтобы назначить им политику.</span><span class="sxs-lookup"><span data-stu-id="b9962-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="b9962-161">Чтобы развернуть политику в группы, выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9962-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="b9962-162">Пользовательские устройства, на которые ориентирована политика, оцениваются на соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="b9962-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="b9962-163">Шаг 5. Создание политики условного доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="b9962-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="b9962-164">На [портале Azure](https://portal.azure.com)откройте политику условного доступа **Azure Active Directory**  >    >  **.**</span><span class="sxs-lookup"><span data-stu-id="b9962-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="b9962-165">Введите имя **политики** и выберите **пользователей и группы.**</span><span class="sxs-lookup"><span data-stu-id="b9962-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="b9962-166">Используйте параметры Включить или Исключить, чтобы добавить группы для политики и выбрать **Готово.**</span><span class="sxs-lookup"><span data-stu-id="b9962-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="b9962-167">Выберите **облачные приложения** и выберите, какие приложения защищать.</span><span class="sxs-lookup"><span data-stu-id="b9962-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="b9962-168">Например, выберите **Выберите приложения** и выберите Office **365 SharePoint Online** и Office **365 Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="b9962-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="b9962-169">Нажмите **Готово**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b9962-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="b9962-170">Выберите **приложения Conditions** Client  >  **для** применения политики к приложениям и браузерам.</span><span class="sxs-lookup"><span data-stu-id="b9962-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="b9962-171">Например, выберите **Да,** а затем включить **браузер и** **мобильные приложения и настольные клиенты.**</span><span class="sxs-lookup"><span data-stu-id="b9962-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="b9962-172">Нажмите **Готово**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b9962-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="b9962-173">Выберите **Грант,** чтобы применить условный доступ на основе соответствия требованиям устройства.</span><span class="sxs-lookup"><span data-stu-id="b9962-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="b9962-174">Например, выберите **устройство Grant Access**  >  **Require, которое должно быть помечено как совместимый.**</span><span class="sxs-lookup"><span data-stu-id="b9962-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="b9962-175">Выберите **Выберите Выберите,** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="b9962-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="b9962-176">Выберите **политику Включить,** а **затем создайте для** сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="b9962-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="b9962-177">Дополнительные сведения см. в [ссылке Включить ATP Защитника Майкрософт с условным доступом в Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="b9962-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="b9962-178">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b9962-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9962-179">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b9962-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
