---
title: Настройка Microsoft Defender для конечной точки для функций iOS
description: Описывает, как развернуть Microsoft Defender для конечной точки в iOS-функции
keywords: Microsoft, defender, Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d32d40ac8ce086caedd53e0a69aac2a3025dc702
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842258"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="0ec77-104">Настройка Microsoft Defender для конечной точки для функций iOS</span><span class="sxs-lookup"><span data-stu-id="0ec77-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ec77-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0ec77-105">**Applies to:**</span></span>
- [<span data-ttu-id="0ec77-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0ec77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0ec77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ec77-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0ec77-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0ec77-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0ec77-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0ec77-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="0ec77-110">Защитник для конечной точки на iOS будет использовать VPN для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="0ec77-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0ec77-111">Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства.</span><span class="sxs-lookup"><span data-stu-id="0ec77-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="0ec77-112">Условный доступ с защитником для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="0ec77-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="0ec77-113">Microsoft Defender для конечной точки на iOS наряду с Microsoft Intune и Azure Active Directory позволяет применять политики соответствия требованиям устройств и условного доступа на основе оценки риска устройства.</span><span class="sxs-lookup"><span data-stu-id="0ec77-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="0ec77-114">Defender for Endpoint — это решение mobile Threat Defense (MTD), которое можно развернуть для использования этой возможности с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="0ec77-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="0ec77-115">Дополнительные сведения о том, как настроить условный доступ с Помощью Защитника для конечной точки на iOS, см. в дополнительных сведениях [Defender for Endpoint и Intune.](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="0ec77-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="0ec77-116">Обнаружение джейлбрейка microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0ec77-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="0ec77-117">Microsoft Defender для конечной точки имеет возможность обнаружения неугодных и управляемых устройств, которые являются jailbroken.</span><span class="sxs-lookup"><span data-stu-id="0ec77-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="0ec77-118">Если обнаружено, что устройство является jailbroken, в Центр безопасности будет отчитаться о высокой опасности, а если условный доступ настроен на основе оценки риска устройства, то устройство будет заблокировано для доступа к корпоративным данным. </span><span class="sxs-lookup"><span data-stu-id="0ec77-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="0ec77-119">Веб-защита и VPN</span><span class="sxs-lookup"><span data-stu-id="0ec77-119">Web Protection and VPN</span></span>

<span data-ttu-id="0ec77-120">По умолчанию Защитник для конечной точки на iOS включает и включает функцию веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="0ec77-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="0ec77-121">[Веб-защита](web-protection-overview.md) помогает защитить устройства от веб-угроз и защитить пользователей от фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="0ec77-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="0ec77-122">Защитник для конечной точки на iOS использует VPN, чтобы обеспечить эту защиту.</span><span class="sxs-lookup"><span data-stu-id="0ec77-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="0ec77-123">Обратите внимание, что это локальный VPN, и в отличие от традиционного VPN сетевой трафик не отправляется за пределы устройства.</span><span class="sxs-lookup"><span data-stu-id="0ec77-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="0ec77-124">Хотя по умолчанию включена, могут быть некоторые случаи, которые требуют отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="0ec77-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="0ec77-125">Например, необходимо запустить некоторые приложения, которые не работают при настройке VPN.</span><span class="sxs-lookup"><span data-stu-id="0ec77-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="0ec77-126">В таких случаях можно отключить VPN из приложения на устройстве, следуя следующим ниже шагам:</span><span class="sxs-lookup"><span data-stu-id="0ec77-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="0ec77-127">На устройстве iOS откройте приложение **Параметры,** щелкните или нажмите **кнопку General,** а затем **VPN.**</span><span class="sxs-lookup"><span data-stu-id="0ec77-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="0ec77-128">Щелкните или нажмите кнопку "i" для Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0ec77-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="0ec77-129">Отключение **Подключение по требованию** для отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="0ec77-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ec77-130">![Подключение vpn config по запросу](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="0ec77-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0ec77-131">Веб-защита не будет доступна при отключении VPN.</span><span class="sxs-lookup"><span data-stu-id="0ec77-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="0ec77-132">Чтобы повторно включить веб-защиту, откройте приложение Microsoft Defender для конечной точки на устройстве и нажмите кнопку Начните **VPN.**</span><span class="sxs-lookup"><span data-stu-id="0ec77-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="0ec77-133">Совместное существование нескольких профилей VPN</span><span class="sxs-lookup"><span data-stu-id="0ec77-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="0ec77-134">Apple iOS не поддерживает одновременное активное участие нескольких VPN в масштабе устройств.</span><span class="sxs-lookup"><span data-stu-id="0ec77-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="0ec77-135">Хотя на устройстве может существовать несколько профилей VPN, одновременно может быть активен только один VPN.</span><span class="sxs-lookup"><span data-stu-id="0ec77-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="0ec77-136">Настройка политики соответствия требованиям для устройств, сбитых с джейлбрейка</span><span class="sxs-lookup"><span data-stu-id="0ec77-136">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="0ec77-137">Чтобы защитить корпоративные данные от доступа на устройствах с iOS, которые могут быть защищены от сбоя, рекомендуется настроить следующую политику соответствия требованиям в Intune.</span><span class="sxs-lookup"><span data-stu-id="0ec77-137">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec77-138">Обнаружение джейлбрейка — это возможность, предоставляемая Microsoft Defender для конечной точки на iOS.</span><span class="sxs-lookup"><span data-stu-id="0ec77-138">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="0ec77-139">Однако рекомендуется настроить эту политику в качестве дополнительного уровня защиты от сценариев побега из тюрьмы.</span><span class="sxs-lookup"><span data-stu-id="0ec77-139">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="0ec77-140">Следуйте ниже шагам, чтобы создать политику соответствия требованиям в отношении устройств jailbroken.</span><span class="sxs-lookup"><span data-stu-id="0ec77-140">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="0ec77-141">В [Microsoft Endpoint Manager центре администрирования](https://go.microsoft.com/fwlink/?linkid=2109431)перейдите к политикам соответствия требованиям **устройств**  ->    ->  **Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="0ec77-141">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="0ec77-142">Выберите "iOS/iPadOS" в качестве платформы и нажмите **кнопку Создать**.</span><span class="sxs-lookup"><span data-stu-id="0ec77-142">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ec77-143">![Создание политики](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0ec77-143">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="0ec77-144">Укажите имя политики, например "Политика соответствия требованиям для джейлбрейка".</span><span class="sxs-lookup"><span data-stu-id="0ec77-144">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="0ec77-145">На странице параметры соответствия щелкните, чтобы расширить раздел **"Здоровье** устройств" и нажмите **кнопку Блок** для **устройств Jailbroken.**</span><span class="sxs-lookup"><span data-stu-id="0ec77-145">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ec77-146">![Политика Параметры](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="0ec77-146">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="0ec77-147">В разделе *Действие за несоблюдение* выберите действия в соответствии с вашими требованиями и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0ec77-147">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ec77-148">![Действия политики](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="0ec77-148">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="0ec77-149">В разделе *Назначения выберите* группы пользователей, которые необходимо включить для этой политики, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0ec77-149">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="0ec77-150">В разделе **Обзор+Создание** убедитесь, что вся введенная информация является правильной, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0ec77-150">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="0ec77-151">Настройка настраиваемых индикаторов</span><span class="sxs-lookup"><span data-stu-id="0ec77-151">Configure custom indicators</span></span>

<span data-ttu-id="0ec77-152">Defender for Endpoint на iOS позволяет администраторам настраивать настраиваемые индикаторы и на устройствах iOS.</span><span class="sxs-lookup"><span data-stu-id="0ec77-152">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="0ec77-153">Дополнительные сведения о настройке настраиваемых индикаторов см. в см. [в руб. Управление индикаторами.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="0ec77-153">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="0ec77-154">Defender for Endpoint на iOS поддерживает создание настраиваемой индикаторов только для IP-адресов и URL-адресов/доменов.</span><span class="sxs-lookup"><span data-stu-id="0ec77-154">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="0ec77-155">Сообщить о небезопасном сайте</span><span class="sxs-lookup"><span data-stu-id="0ec77-155">Report unsafe site</span></span>

<span data-ttu-id="0ec77-156">Фишинговые веб-сайты выдают себя за надежные веб-сайты с целью получения личной или финансовой информации.</span><span class="sxs-lookup"><span data-stu-id="0ec77-156">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="0ec77-157">Если вы хотите сообщить о веб-сайте, который может быть фишинг-сайтом, посетите страницу Provide feedback about [network](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) protection page.</span><span class="sxs-lookup"><span data-stu-id="0ec77-157">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

