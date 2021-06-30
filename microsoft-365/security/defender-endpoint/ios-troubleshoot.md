---
title: Устранение неполадок и поиск ответов на вопросы, связанные с Microsoft Defender для конечной точки на iOS
description: Устранение неполадок и задаваемая проблема — Microsoft Defender для конечной точки на iOS
keywords: Microsoft, defender, Microsoft Defender for Endpoint, ios, troubleshoot, faq, how to
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
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194977"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="63ef6-104">Устранение неполадок и поиск ответов на вопросы в Microsoft Defender для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="63ef6-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="63ef6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="63ef6-105">**Applies to:**</span></span>
- [<span data-ttu-id="63ef6-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="63ef6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="63ef6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63ef6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="63ef6-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="63ef6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="63ef6-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="63ef6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="63ef6-110">В этом разделе содержится информация об устранении неполадок, которые помогут вам устранить проблемы, которые могут возникнуть при использовании Microsoft Defender для конечной точки в iOS.</span><span class="sxs-lookup"><span data-stu-id="63ef6-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="63ef6-111">Защитник для конечной точки на iOS будет использовать VPN для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="63ef6-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="63ef6-112">Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства.</span><span class="sxs-lookup"><span data-stu-id="63ef6-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="63ef6-113">Приложения не работают при включении VPN</span><span class="sxs-lookup"><span data-stu-id="63ef6-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="63ef6-114">Есть приложения, которые перестают работать при обнаружении активного VPN.</span><span class="sxs-lookup"><span data-stu-id="63ef6-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="63ef6-115">Вы можете отключить VPN во время использования таких приложений.</span><span class="sxs-lookup"><span data-stu-id="63ef6-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="63ef6-116">По умолчанию Защитник для конечной точки на iOS включает и включает функцию веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="63ef6-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="63ef6-117">[Веб-защита](web-protection-overview.md) помогает защитить устройства от веб-угроз и защитить пользователей от фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="63ef6-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="63ef6-118">Защитник для конечной точки на iOS использует VPN, чтобы обеспечить эту защиту.</span><span class="sxs-lookup"><span data-stu-id="63ef6-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="63ef6-119">Обратите внимание, что это локальный VPN, и в отличие от традиционного VPN сетевой трафик не отправляется за пределы устройства.</span><span class="sxs-lookup"><span data-stu-id="63ef6-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="63ef6-120">Хотя по умолчанию включена, могут быть некоторые случаи, которые требуют отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="63ef6-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="63ef6-121">Например, необходимо запустить некоторые приложения, которые не работают при настройке VPN.</span><span class="sxs-lookup"><span data-stu-id="63ef6-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="63ef6-122">В таких случаях можно отключить VPN из приложения на устройстве, следуя следующим ниже шагам:</span><span class="sxs-lookup"><span data-stu-id="63ef6-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="63ef6-123">На устройстве iOS откройте приложение **Параметры,** щелкните или нажмите **кнопку General,** а затем **VPN.**</span><span class="sxs-lookup"><span data-stu-id="63ef6-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="63ef6-124">Щелкните или нажмите кнопку "i" для Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="63ef6-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="63ef6-125">Отключение **Подключение по требованию** для отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="63ef6-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="63ef6-126">![Подключение vpn config по запросу](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="63ef6-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="63ef6-127">Веб-защита не будет доступна при отключении VPN.</span><span class="sxs-lookup"><span data-stu-id="63ef6-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="63ef6-128">Чтобы повторно включить веб-защиту, откройте приложение Microsoft Defender для конечной точки на устройстве и нажмите кнопку Начните **VPN.**</span><span class="sxs-lookup"><span data-stu-id="63ef6-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-with-multiple-vpn-profiles"></a><span data-ttu-id="63ef6-129">Совместное существование с несколькими профилями VPN</span><span class="sxs-lookup"><span data-stu-id="63ef6-129">Co-existence with multiple VPN profiles</span></span>

<span data-ttu-id="63ef6-130">Apple iOS не поддерживает одновременное активное участие нескольких VPN **в** масштабе устройств.</span><span class="sxs-lookup"><span data-stu-id="63ef6-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="63ef6-131">Хотя на устройстве может существовать несколько профилей VPN, одновременно может быть активен только один VPN.</span><span class="sxs-lookup"><span data-stu-id="63ef6-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="63ef6-132">Microsoft Defender для VPN конечной точки может сосуществовать  с другими VPN, настроенными как приложение или *"Личный".*</span><span class="sxs-lookup"><span data-stu-id="63ef6-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="63ef6-133">Потребление батареи</span><span class="sxs-lookup"><span data-stu-id="63ef6-133">Battery consumption</span></span>

<span data-ttu-id="63ef6-134">В приложении Параметры iOS отображается только использование батареи приложений, видимых пользователю в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="63ef6-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="63ef6-135">Использование батареи приложениями, показанными на экране, только в течение этого времени и вычисляется iOS на основе множества факторов, включая использование ЦП и Сети.</span><span class="sxs-lookup"><span data-stu-id="63ef6-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="63ef6-136">Microsoft Defender для конечной точки использует локальный VPN-сервер в фоновом режиме для проверки веб-трафика на любые вредоносные веб-сайты или подключения.</span><span class="sxs-lookup"><span data-stu-id="63ef6-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="63ef6-137">Сетевые пакеты из любого приложения проходят эту проверку, что приводит к неправильному вычислению использования батареи Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="63ef6-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="63ef6-138">Фактическое потребление батареи в Microsoft Defender для конечной точки значительно меньше, чем то, что показано на Параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="63ef6-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="63ef6-139">В среднем ежедневное использование батареи Microsoft Defender для конечной точки, запущенной в фоновом режиме, составляет примерно **8,81%** от общего расхода батареи в этот день.</span><span class="sxs-lookup"><span data-stu-id="63ef6-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="63ef6-140">Эта метрика сообщается Apple на основе фактического использования Microsoft Defender для конечной точки на устройствах конечного пользователя и по причинам, указанным выше, также может быть учтена в других приложениях, которые имеют сетевой активности.</span><span class="sxs-lookup"><span data-stu-id="63ef6-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="63ef6-141">Кроме того, используемый VPN является локальным VPN и в отличие от традиционного VPN, сетевой трафик не отправляется за пределы устройства.</span><span class="sxs-lookup"><span data-stu-id="63ef6-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="63ef6-142">Использование данных</span><span class="sxs-lookup"><span data-stu-id="63ef6-142">Data usage</span></span>

<span data-ttu-id="63ef6-143">Microsoft Defender для конечной точки использует локальный VPN-сервер для проверки веб-трафика на любые вредоносные веб-сайты или подключения.</span><span class="sxs-lookup"><span data-stu-id="63ef6-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="63ef6-144">По этой причине использование данных в Microsoft Defender для конечных точек может быть неправильно учтено.</span><span class="sxs-lookup"><span data-stu-id="63ef6-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="63ef6-145">Мы также заметили, что если устройство находится только в сотовой сети, использование данных, о чем сообщает поставщик услуг, очень близко к фактическому потреблению, в то время как в приложении Параметры Apple показывает от 1,5 до 2x фактических потребляемых данных.</span><span class="sxs-lookup"><span data-stu-id="63ef6-145">We have also observed that if the device is on cellular network only, the data usage reported by service provider is very close to the actual consumption whereas in the Settings app, Apple shows about 1.5x to 2x of actual data consumed.</span></span>

<span data-ttu-id="63ef6-146">У нас есть аналогичные наблюдения и с другими VPN-службами, и мы сообщили об этом в Apple.</span><span class="sxs-lookup"><span data-stu-id="63ef6-146">We have similar observations with other VPN services as well and have reported this to Apple.</span></span>

<span data-ttu-id="63ef6-147">Кроме того, для microsoft Defender для конечной точки крайне важно быть в курсе наших дополнительных служб, чтобы обеспечить лучшую защиту.</span><span class="sxs-lookup"><span data-stu-id="63ef6-147">In addition, it is critical for Microsoft Defender for Endpoint to be up to date with our backend services to provide better protection.</span></span> <span data-ttu-id="63ef6-148">Однако мы работаем над оптимизацией использования данных Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="63ef6-148">However, we are working on optimizing the data usage by Microsoft Defender for Endpoint.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="63ef6-149">Сообщить о небезопасном сайте</span><span class="sxs-lookup"><span data-stu-id="63ef6-149">Report unsafe site</span></span>

<span data-ttu-id="63ef6-150">Фишинговые веб-сайты выдают себя за надежные веб-сайты с целью получения личной или финансовой информации.</span><span class="sxs-lookup"><span data-stu-id="63ef6-150">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="63ef6-151">Чтобы сообщить о веб-сайте, который может быть фишинг-сайтом, посетите страницу Provide feedback about [network](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) protection page.</span><span class="sxs-lookup"><span data-stu-id="63ef6-151">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="63ef6-152">Обнаружен вредоносный сайт</span><span class="sxs-lookup"><span data-stu-id="63ef6-152">Malicious site detected</span></span>

<span data-ttu-id="63ef6-153">Microsoft Defender для конечной точки защищает вас от фишинга или других веб-атак.</span><span class="sxs-lookup"><span data-stu-id="63ef6-153">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="63ef6-154">Если обнаружен вредоносный сайт, подключение блокируется, и на портал Центра безопасности организации отправляется оповещение.</span><span class="sxs-lookup"><span data-stu-id="63ef6-154">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="63ef6-155">Оповещение включает доменное имя подключения, удаленный IP-адрес и сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="63ef6-155">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="63ef6-156">Кроме того, уведомление отображается на устройстве iOS.</span><span class="sxs-lookup"><span data-stu-id="63ef6-156">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="63ef6-157">Нажатие на уведомление открывает следующий экран для просмотра сведений.</span><span class="sxs-lookup"><span data-stu-id="63ef6-157">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63ef6-158">![Изображение сайта, сообщаемого как небезопасное уведомление](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="63ef6-158">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="63ef6-159">Данные и конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="63ef6-159">Data and Privacy</span></span>

<span data-ttu-id="63ef6-160">Сведения о собранных данных и конфиденциальности см. в материале [Privacy Information - Microsoft Defender for Endpoint on iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="63ef6-160">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

