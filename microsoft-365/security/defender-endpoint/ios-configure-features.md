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
ms.openlocfilehash: dab72da02927c3fff6025eb2d0fa9ed0fdf1d0d7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245280"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="a4b87-104">Настройка Microsoft Defender для конечной точки для функций iOS</span><span class="sxs-lookup"><span data-stu-id="a4b87-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4b87-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a4b87-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4b87-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a4b87-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a4b87-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4b87-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a4b87-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a4b87-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a4b87-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a4b87-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="a4b87-110">Защитник для конечной точки на iOS будет использовать VPN для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="a4b87-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="a4b87-111">Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства.</span><span class="sxs-lookup"><span data-stu-id="a4b87-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="a4b87-112">Условный доступ с защитником для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="a4b87-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="a4b87-113">Microsoft Defender для конечной точки на iOS наряду с Microsoft Intune и Azure Active Directory позволяет применять политики соответствия требованиям устройств и условного доступа на основе оценки риска устройства.</span><span class="sxs-lookup"><span data-stu-id="a4b87-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="a4b87-114">Defender for Endpoint — это решение mobile Threat Defense (MTD), которое можно развернуть для использования этой возможности с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="a4b87-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="a4b87-115">Дополнительные сведения о том, как настроить условный доступ с Помощью Защитника для конечной точки на iOS, см. в дополнительных сведениях [Defender for Endpoint и Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="a4b87-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="a4b87-116">**Обнаружение джейлбрейка Microsoft Defender для конечной точки на iOS в настоящее время находится в стадии предварительного просмотра.**</span><span class="sxs-lookup"><span data-stu-id="a4b87-116">**Jailbreak detection by Microsoft Defender for Endpoint on iOS is currently in preview**.</span></span> <span data-ttu-id="a4b87-117">Если устройство обнаружено, что устройство было сбито с помощью Microsoft Defender для конечной точки, в Центр безопасности будет отчитаться о высокой опасности, а если условный доступ настроен на основе оценки риска устройства, то устройство будет заблокировано от доступа к корпоративным данным.</span><span class="sxs-lookup"><span data-stu-id="a4b87-117">If a device is detected to be jailbroken by Microsoft Defender for Endpoint, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="a4b87-118">Веб-защита и VPN</span><span class="sxs-lookup"><span data-stu-id="a4b87-118">Web Protection and VPN</span></span>

<span data-ttu-id="a4b87-119">По умолчанию Защитник для конечной точки на iOS включает и включает функцию веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="a4b87-119">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="a4b87-120">[Веб-защита](web-protection-overview.md) помогает защитить устройства от веб-угроз и защитить пользователей от фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="a4b87-120">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="a4b87-121">Защитник для конечной точки на iOS использует VPN, чтобы обеспечить эту защиту.</span><span class="sxs-lookup"><span data-stu-id="a4b87-121">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="a4b87-122">Обратите внимание, что это локальный VPN, и в отличие от традиционного VPN сетевой трафик не отправляется за пределы устройства.</span><span class="sxs-lookup"><span data-stu-id="a4b87-122">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="a4b87-123">Хотя по умолчанию включена, могут быть некоторые случаи, которые требуют отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="a4b87-123">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="a4b87-124">Например, необходимо запустить некоторые приложения, которые не работают при настройке VPN.</span><span class="sxs-lookup"><span data-stu-id="a4b87-124">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="a4b87-125">В таких случаях можно отключить VPN из приложения на устройстве, следуя следующим ниже шагам:</span><span class="sxs-lookup"><span data-stu-id="a4b87-125">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="a4b87-126">На устройстве iOS откройте приложение **Параметры,** щелкните или нажмите **кнопку General,** а затем **VPN.**</span><span class="sxs-lookup"><span data-stu-id="a4b87-126">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="a4b87-127">Щелкните или нажмите кнопку "i" для Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4b87-127">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="a4b87-128">Отключение **Подключение по требованию** для отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="a4b87-128">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a4b87-129">![Подключение vpn config по запросу](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="a4b87-129">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="a4b87-130">Веб-защита не будет доступна при отключении VPN.</span><span class="sxs-lookup"><span data-stu-id="a4b87-130">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="a4b87-131">Чтобы повторно включить веб-защиту, откройте приложение Microsoft Defender для конечной точки на устройстве и нажмите кнопку Начните **VPN.**</span><span class="sxs-lookup"><span data-stu-id="a4b87-131">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="a4b87-132">Совместное существование нескольких профилей VPN</span><span class="sxs-lookup"><span data-stu-id="a4b87-132">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="a4b87-133">Apple iOS не поддерживает одновременное активное участие нескольких VPN в масштабе устройств.</span><span class="sxs-lookup"><span data-stu-id="a4b87-133">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="a4b87-134">Хотя на устройстве может существовать несколько профилей VPN, одновременно может быть активен только один VPN.</span><span class="sxs-lookup"><span data-stu-id="a4b87-134">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="a4b87-135">Настройка политики соответствия требованиям для устройств, сбитых с джейлбрейка</span><span class="sxs-lookup"><span data-stu-id="a4b87-135">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="a4b87-136">Чтобы защитить корпоративные данные от доступа на устройствах с iOS, которые могут быть защищены от сбоя, рекомендуется настроить следующую политику соответствия требованиям в Intune.</span><span class="sxs-lookup"><span data-stu-id="a4b87-136">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="a4b87-137">В настоящее время обнаружение джейлбрейка Microsoft Defender для конечной точки на iOS находится в предварительном режиме.</span><span class="sxs-lookup"><span data-stu-id="a4b87-137">At this time jailbreak detection by Microsoft Defender for Endpoint on iOS is in preview.</span></span> <span data-ttu-id="a4b87-138">Рекомендуется настроить эту политику в качестве дополнительного уровня защиты от сценариев побега из тюрьмы.</span><span class="sxs-lookup"><span data-stu-id="a4b87-138">We recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="a4b87-139">Следуйте ниже шагам, чтобы создать политику соответствия требованиям в отношении устройств jailbroken.</span><span class="sxs-lookup"><span data-stu-id="a4b87-139">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="a4b87-140">В [Microsoft Endpoint Manager центре администрирования](https://go.microsoft.com/fwlink/?linkid=2109431)перейдите к политикам соответствия требованиям **устройств**  ->    ->  **Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="a4b87-140">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="a4b87-141">Выберите "iOS/iPadOS" в качестве платформы и нажмите **кнопку Создать**.</span><span class="sxs-lookup"><span data-stu-id="a4b87-141">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a4b87-142">![Создание политики](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="a4b87-142">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="a4b87-143">Укажите имя политики, например "Политика соответствия требованиям для джейлбрейка".</span><span class="sxs-lookup"><span data-stu-id="a4b87-143">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="a4b87-144">На странице параметры соответствия щелкните, чтобы расширить раздел **"Здоровье** устройств" и нажмите **кнопку Блок** для **устройств Jailbroken.**</span><span class="sxs-lookup"><span data-stu-id="a4b87-144">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a4b87-145">![Политика Параметры](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="a4b87-145">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="a4b87-146">В разделе *Действие за несоблюдение* выберите действия в соответствии с вашими требованиями и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4b87-146">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a4b87-147">![Действия политики](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="a4b87-147">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="a4b87-148">В разделе *Назначения выберите* группы пользователей, которые необходимо включить для этой политики, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4b87-148">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="a4b87-149">В разделе **Обзор+Создание** убедитесь, что вся введенная информация является правильной, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a4b87-149">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="a4b87-150">Настройка настраиваемых индикаторов</span><span class="sxs-lookup"><span data-stu-id="a4b87-150">Configure custom indicators</span></span>

<span data-ttu-id="a4b87-151">Defender for Endpoint на iOS позволяет администраторам настраивать настраиваемые индикаторы и на устройствах iOS.</span><span class="sxs-lookup"><span data-stu-id="a4b87-151">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="a4b87-152">Дополнительные сведения о настройке настраиваемых индикаторов см. в см. [в руб. Управление индикаторами.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="a4b87-152">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="a4b87-153">Defender for Endpoint на iOS поддерживает создание настраиваемой индикаторов только для IP-адресов и URL-адресов/доменов.</span><span class="sxs-lookup"><span data-stu-id="a4b87-153">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="a4b87-154">Сообщить о небезопасном сайте</span><span class="sxs-lookup"><span data-stu-id="a4b87-154">Report unsafe site</span></span>

<span data-ttu-id="a4b87-155">Фишинговые веб-сайты выдают себя за надежные веб-сайты с целью получения личной или финансовой информации.</span><span class="sxs-lookup"><span data-stu-id="a4b87-155">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="a4b87-156">Если вы хотите сообщить о веб-сайте, который может быть фишинг-сайтом, посетите страницу Provide feedback about [network](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) protection page.</span><span class="sxs-lookup"><span data-stu-id="a4b87-156">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="a4b87-157">Проблемы с потреблением батареи на iOS при установке Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a4b87-157">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="a4b87-158">Использование батареи приложением вычисляется Apple на основе множества факторов, включая использование ЦП и сети.</span><span class="sxs-lookup"><span data-stu-id="a4b87-158">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="a4b87-159">Microsoft Defender для конечной точки использует локальный VPN-сервер в фоновом режиме для проверки веб-трафика на любые вредоносные веб-сайты или подключения.</span><span class="sxs-lookup"><span data-stu-id="a4b87-159">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="a4b87-160">Сетевые пакеты из любого приложения проходят эту проверку, что приводит к неправильному вычислению использования батареи Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4b87-160">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="a4b87-161">Это создает ложное впечатление для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4b87-161">This gives a false impression to the user.</span></span> <span data-ttu-id="a4b87-162">Фактическое потребление батареи в Microsoft Defender для конечной точки меньше, чем показано на Параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a4b87-162">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="a4b87-163">Это основано на проведенных тестах, проведенных в приложении Microsoft Defender for Endpoint для понимания потребления батареи.</span><span class="sxs-lookup"><span data-stu-id="a4b87-163">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="a4b87-164">Кроме того, используемый VPN является локальным VPN и в отличие от традиционных VPN, сетевой трафик не отправляется за пределы устройства.</span><span class="sxs-lookup"><span data-stu-id="a4b87-164">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
