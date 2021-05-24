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
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636282"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="8f544-104">Устранение неполадок и поиск ответов на вопросы в Microsoft Defender для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="8f544-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f544-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8f544-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f544-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8f544-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f544-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f544-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8f544-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8f544-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8f544-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8f544-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="8f544-110">В этом разделе содержится информация об устранении неполадок, которые помогут вам устранить проблемы, которые могут возникнуть при использовании Microsoft Defender для конечной точки в iOS.</span><span class="sxs-lookup"><span data-stu-id="8f544-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="8f544-111">Защитник для конечной точки на iOS будет использовать VPN для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="8f544-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="8f544-112">Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства.</span><span class="sxs-lookup"><span data-stu-id="8f544-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="8f544-113">Приложения не работают при включении VPN</span><span class="sxs-lookup"><span data-stu-id="8f544-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="8f544-114">Есть приложения, которые перестают работать при обнаружении активного VPN.</span><span class="sxs-lookup"><span data-stu-id="8f544-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="8f544-115">Вы можете отключить VPN во время использования таких приложений.</span><span class="sxs-lookup"><span data-stu-id="8f544-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="8f544-116">По умолчанию Защитник для конечной точки на iOS включает и включает функцию веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="8f544-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="8f544-117">[Веб-защита](web-protection-overview.md) помогает защитить устройства от веб-угроз и защитить пользователей от фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="8f544-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="8f544-118">Защитник для конечной точки на iOS использует VPN, чтобы обеспечить эту защиту.</span><span class="sxs-lookup"><span data-stu-id="8f544-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="8f544-119">Обратите внимание, что это локальный VPN, и в отличие от традиционного VPN сетевой трафик не отправляется за пределы устройства.</span><span class="sxs-lookup"><span data-stu-id="8f544-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="8f544-120">Хотя по умолчанию включена, могут быть некоторые случаи, которые требуют отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="8f544-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="8f544-121">Например, необходимо запустить некоторые приложения, которые не работают при настройке VPN.</span><span class="sxs-lookup"><span data-stu-id="8f544-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="8f544-122">В таких случаях можно отключить VPN из приложения на устройстве, следуя следующим ниже шагам:</span><span class="sxs-lookup"><span data-stu-id="8f544-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="8f544-123">На устройстве iOS откройте приложение **Параметры,** щелкните или нажмите **кнопку General,** а затем **VPN.**</span><span class="sxs-lookup"><span data-stu-id="8f544-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="8f544-124">Щелкните или нажмите кнопку "i" для Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8f544-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="8f544-125">Отключение **Подключение по требованию** для отключения VPN.</span><span class="sxs-lookup"><span data-stu-id="8f544-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8f544-126">![Подключение vpn config по запросу](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="8f544-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="8f544-127">Веб-защита не будет доступна при отключении VPN.</span><span class="sxs-lookup"><span data-stu-id="8f544-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="8f544-128">Чтобы повторно включить веб-защиту, откройте приложение Microsoft Defender для конечной точки на устройстве и нажмите кнопку Начните **VPN.**</span><span class="sxs-lookup"><span data-stu-id="8f544-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="8f544-129">Проблемы с несколькими профилями VPN</span><span class="sxs-lookup"><span data-stu-id="8f544-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="8f544-130">Apple iOS не поддерживает одновременное активное участие нескольких VPN в масштабе устройств.</span><span class="sxs-lookup"><span data-stu-id="8f544-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="8f544-131">Хотя на устройстве может существовать несколько профилей VPN, одновременно может быть активен только один VPN.</span><span class="sxs-lookup"><span data-stu-id="8f544-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="8f544-132">Потребление батареи</span><span class="sxs-lookup"><span data-stu-id="8f544-132">Battery consumption</span></span>

<span data-ttu-id="8f544-133">Использование батареи приложением вычисляется Apple на основе множества факторов, включая использование ЦП и сети.</span><span class="sxs-lookup"><span data-stu-id="8f544-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="8f544-134">Microsoft Defender для конечной точки использует локальный VPN-сервер в фоновом режиме для проверки веб-трафика на любые вредоносные веб-сайты или подключения.</span><span class="sxs-lookup"><span data-stu-id="8f544-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="8f544-135">Сетевые пакеты из любого приложения проходят эту проверку, что приводит к неправильному вычислению использования батареи Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8f544-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="8f544-136">Это создает ложное впечатление для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f544-136">This gives a false impression to the user.</span></span> <span data-ttu-id="8f544-137">Фактическое потребление батареи в Microsoft Defender для конечной точки меньше, чем показано на Параметры на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8f544-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="8f544-138">Это основано на проведенных тестах, проведенных в приложении Microsoft Defender for Endpoint для понимания потребления батареи.</span><span class="sxs-lookup"><span data-stu-id="8f544-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="8f544-139">Кроме того, используемый VPN является локальным VPN и в отличие от традиционного VPN, сетевой трафик не отправляется за пределы устройства.</span><span class="sxs-lookup"><span data-stu-id="8f544-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="8f544-140">Использование данных</span><span class="sxs-lookup"><span data-stu-id="8f544-140">Data usage</span></span>

<span data-ttu-id="8f544-141">Microsoft Defender для конечной точки использует локальный VPN-сервер для проверки веб-трафика на любые вредоносные веб-сайты или подключения.</span><span class="sxs-lookup"><span data-stu-id="8f544-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="8f544-142">По этой причине Apple неточно передает данные в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8f544-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="8f544-143">Фактическое использование данных в Microsoft Defender для конечной точки не является значительным и значительно меньше, чем то, что показано в Параметры данных на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8f544-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="8f544-144">Сообщить о небезопасном сайте</span><span class="sxs-lookup"><span data-stu-id="8f544-144">Report unsafe site</span></span>

<span data-ttu-id="8f544-145">Фишинговые веб-сайты выдают себя за надежные веб-сайты с целью получения личной или финансовой информации.</span><span class="sxs-lookup"><span data-stu-id="8f544-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="8f544-146">Чтобы сообщить о веб-сайте, который может быть фишинг-сайтом, посетите страницу Provide feedback about [network](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) protection page.</span><span class="sxs-lookup"><span data-stu-id="8f544-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="8f544-147">Обнаружен вредоносный сайт</span><span class="sxs-lookup"><span data-stu-id="8f544-147">Malicious site detected</span></span>

<span data-ttu-id="8f544-148">Microsoft Defender для конечной точки защищает вас от фишинга или других веб-атак.</span><span class="sxs-lookup"><span data-stu-id="8f544-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="8f544-149">Если обнаружен вредоносный сайт, подключение блокируется, и на портал Центра безопасности организации отправляется оповещение.</span><span class="sxs-lookup"><span data-stu-id="8f544-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="8f544-150">Оповещение включает доменное имя подключения, удаленный IP-адрес и сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="8f544-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="8f544-151">Кроме того, уведомление отображается на устройстве iOS.</span><span class="sxs-lookup"><span data-stu-id="8f544-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="8f544-152">Нажатие на уведомление открывает следующий экран для просмотра сведений.</span><span class="sxs-lookup"><span data-stu-id="8f544-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8f544-153">![Изображение сайта, сообщаемого как небезопасное уведомление](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="8f544-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="8f544-154">Данные и конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="8f544-154">Data and Privacy</span></span>

<span data-ttu-id="8f544-155">Сведения о собранных данных и конфиденциальности см. в материале [Privacy Information - Microsoft Defender for Endpoint on iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="8f544-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

