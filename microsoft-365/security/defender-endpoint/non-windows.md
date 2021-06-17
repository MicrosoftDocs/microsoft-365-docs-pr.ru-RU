---
title: Microsoft Defender для конечной точки на других платформах
description: Узнайте о возможностях Microsoft Defender для конечных точек для Windows платформ
keywords: без окон, mac, macos, Linux, Android
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
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dc5710a73685c67eff17c0f281bd14e48707e60f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964792"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a><span data-ttu-id="5ff4d-104">Microsoft Defender для конечной точки на других платформах</span><span class="sxs-lookup"><span data-stu-id="5ff4d-104">Microsoft Defender for Endpoint for non-Windows platforms</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ff4d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5ff4d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ff4d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ff4d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ff4d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ff4d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5ff4d-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5ff4d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ff4d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5ff4d-110">Корпорация Майкрософт была в пути, чтобы расширить свои ведущие возможности безопасности конечной точки за пределами Windows и Windows Server для macOS, Linux, Android и вскоре iOS.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-110">Microsoft has been on a journey to extend its industry leading endpoint security capabilities beyond Windows and Windows Server to macOS, Linux, Android, and soon iOS.</span></span>

<span data-ttu-id="5ff4d-111">Организации сталкиваются с угрозами на различных платформах и устройствах.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-111">Organizations face threats across a variety of platforms and devices.</span></span> <span data-ttu-id="5ff4d-112">Наши команды обязались строить решения по безопасности не только для *Корпорации* Майкрософт, но и *из* Корпорации Майкрософт, чтобы позволить нашим клиентам защищать и защищать свои неоднородные среды.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-112">Our teams have committed to building security solutions not just *for* Microsoft, but also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span></span> <span data-ttu-id="5ff4d-113">Мы внимательно прислушиваемся к отзывам клиентов и тесно сотрудничаем с нашими клиентами для создания решений, которые отвечают их потребностям.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-113">We're listening to customer feedback and partnering closely with our customers to build solutions that meet their needs.</span></span>

<span data-ttu-id="5ff4d-114">С помощью Microsoft Defender для конечной точки клиенты получают единое представление всех угроз и оповещений в Центр безопасности в Microsoft Defender, на платформах Windows и не Windows, что позволяет им получить полное представление о том, что происходит в их среде, что позволяет им быстрее оценивать угрозы и реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-114">With Microsoft Defender for Endpoint, customers benefit from a unified view of all threats and alerts in the Microsoft Defender Security Center, across Windows and non-Windows platforms, enabling them to get a full picture of what's happening in their environment, which empowers them to more quickly assess and respond to threats.</span></span>

## <a name="microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="5ff4d-115">Microsoft Defender для конечной точки в macOS</span><span class="sxs-lookup"><span data-stu-id="5ff4d-115">Microsoft Defender for Endpoint on macOS</span></span> 

<span data-ttu-id="5ff4d-116">Microsoft Defender для конечной точки на macOS предлагает антивирусные обнаружение и нейтрализация атак на конечные точки (EDR) возможности для трех последних выпущенных версий macOS.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-116">Microsoft Defender for Endpoint on macOS offers antivirus and endpoint detection and response (EDR) capabilities for the three latest released versions of macOS.</span></span> <span data-ttu-id="5ff4d-117">Клиенты могут развертывать и управлять решением через Microsoft Endpoint Manager и Jamf.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-117">Customers can deploy and manage the solution through Microsoft Endpoint Manager and Jamf.</span></span> <span data-ttu-id="5ff4d-118">Как и Microsoft Office на macOS, microsoft Auto Update используется для управления обновлениями Microsoft Defender для конечной точки на Mac.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-118">Just like with Microsoft Office applications on macOS, Microsoft Auto Update is used to manage Microsoft Defender for Endpoint on Mac updates.</span></span> <span data-ttu-id="5ff4d-119">Сведения о ключевых особенностях и преимуществах ознакомьтесь с нашими [объявлениями.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)</span><span class="sxs-lookup"><span data-stu-id="5ff4d-119">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).</span></span>

<span data-ttu-id="5ff4d-120">Дополнительные сведения о том, как начать работу, посетите конечную точку Defender в документации [macOS.](microsoft-defender-endpoint-mac.md)</span><span class="sxs-lookup"><span data-stu-id="5ff4d-120">For more details on how to get started, visit the Defender for Endpoint on macOS [documentation](microsoft-defender-endpoint-mac.md).</span></span>

>[!NOTE]
><span data-ttu-id="5ff4d-121">В настоящее время в конечных точках macOS не поддерживаются следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="5ff4d-121">The following capabilities are not currently supported on macOS endpoints:</span></span>
>- <span data-ttu-id="5ff4d-122">Защита от потери данных</span><span class="sxs-lookup"><span data-stu-id="5ff4d-122">Data loss prevention</span></span>
>- <span data-ttu-id="5ff4d-123">Живой ответ</span><span class="sxs-lookup"><span data-stu-id="5ff4d-123">Live response</span></span>
>- <span data-ttu-id="5ff4d-124">SIEM</span><span class="sxs-lookup"><span data-stu-id="5ff4d-124">SIEM</span></span>


## <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="5ff4d-125">Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="5ff4d-125">Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="5ff4d-126">Microsoft Defender для конечной точки на Linux предлагает профилактические (AV) возможности для серверов Linux.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-126">Microsoft Defender for Endpoint on Linux offers preventative (AV) capabilities for Linux servers.</span></span> <span data-ttu-id="5ff4d-127">Это включает полный опыт командной строки для настройки и управления агентом, инициирования сканов и управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-127">This includes a full command line experience to configure and manage the agent, initiate scans, and manage threats.</span></span> <span data-ttu-id="5ff4d-128">Мы поддерживаем последние версии шести наиболее распространенных дистрибутивов Linux Server: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS или более высоких LTS, SLES 12+, Debian 9+, и Oracle Linux 7.2.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-128">We support recent versions of the six most common Linux Server distributions: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS, or higher LTS, SLES 12+, Debian 9+, and Oracle Linux 7.2.</span></span> <span data-ttu-id="5ff4d-129">Microsoft Defender для конечной точки на Linux можно развернуть и настроить с помощью Puppet, Ansible или с помощью существующего средства управления конфигурацией Linux.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-129">Microsoft Defender for Endpoint on Linux can be deployed and configured using Puppet, Ansible, or using your existing Linux configuration management tool.</span></span> <span data-ttu-id="5ff4d-130">Сведения о ключевых особенностях и преимуществах ознакомьтесь с нашими [объявлениями.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)</span><span class="sxs-lookup"><span data-stu-id="5ff4d-130">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).</span></span>

<span data-ttu-id="5ff4d-131">Дополнительные сведения о том, как начать работу, посетите документацию Microsoft Defender для конечной точки [на](microsoft-defender-endpoint-linux.md)Linux.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-131">For more details on how to get started, visit the Microsoft Defender for Endpoint on Linux [documentation](microsoft-defender-endpoint-linux.md).</span></span>

>[!NOTE]
><span data-ttu-id="5ff4d-132">В настоящее время в конечных точках Linux не поддерживаются следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="5ff4d-132">The following capabilities are not currently supported on Linux endpoints:</span></span>
>- <span data-ttu-id="5ff4d-133">Защита от потери данных</span><span class="sxs-lookup"><span data-stu-id="5ff4d-133">Data loss prevention</span></span>
>- <span data-ttu-id="5ff4d-134">Живой ответ</span><span class="sxs-lookup"><span data-stu-id="5ff4d-134">Live response</span></span>
>- <span data-ttu-id="5ff4d-135">SIEM</span><span class="sxs-lookup"><span data-stu-id="5ff4d-135">SIEM</span></span>



## <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="5ff4d-136">Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="5ff4d-136">Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="5ff4d-137">Microsoft Defender для конечной точки на Android — это наше решение для защиты от мобильных угроз для устройств под управлением Android 6.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-137">Microsoft Defender for Endpoint on Android is our mobile threat defense solution for devices running Android 6.0 and higher.</span></span> <span data-ttu-id="5ff4d-138">Поддерживаются Enterprise (рабочий профиль) и режимы администратора устройств.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-138">Both Android Enterprise (Work Profile) and Device Administrator modes are supported.</span></span> <span data-ttu-id="5ff4d-139">На Android мы предлагаем веб-защиту, которая включает в себя защиту от фишинга, блокировку небезопасных подключений и настройку настраиваемого индикатора.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-139">On Android, we offer web protection, which includes anti-phishing, blocking of unsafe connections, and setting of custom indicators.</span></span> <span data-ttu-id="5ff4d-140">Решение проверяет вредоносные программы и потенциально нежелательные приложения (PUA) и предлагает дополнительные возможности по предотвращению нарушений путем интеграции с Microsoft Endpoint Manager и условным доступом.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-140">The solution scans for malware and potentially unwanted applications (PUA) and offers additional breach prevention capabilities through integration with Microsoft Endpoint Manager and Conditional Access.</span></span> <span data-ttu-id="5ff4d-141">Сведения о ключевых особенностях и преимуществах ознакомьтесь с нашими [объявлениями.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)</span><span class="sxs-lookup"><span data-stu-id="5ff4d-141">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).</span></span>

<span data-ttu-id="5ff4d-142">Дополнительные сведения о том, как начать работу, посетите документацию Microsoft Defender для конечной точки [на](microsoft-defender-endpoint-android.md)Android.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-142">For more details on how to get started, visit the Microsoft Defender for Endpoint on Android [documentation](microsoft-defender-endpoint-android.md).</span></span>

## <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="5ff4d-143">Microsoft Defender для конечной точки в iOS</span><span class="sxs-lookup"><span data-stu-id="5ff4d-143">Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="5ff4d-144">Microsoft Defender для конечной точки на iOS — это наше решение для защиты от мобильных угроз для устройств с iOS 11.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-144">Microsoft Defender for Endpoint on iOS is our mobile threat defense solution for devices running iOS 11.0 and higher.</span></span> <span data-ttu-id="5ff4d-145">Поддерживаются как контролируемые, так и неподконтрольные устройства.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-145">Both Supervised and Unsupervised devices are supported.</span></span> <span data-ttu-id="5ff4d-146">На iOS мы предлагаем веб-защиту, которая включает в себя защиту от фишинга, блокировку небезопасных подключений и настройку настраиваемого индикатора.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-146">On iOS, we offer web protection which includes anti-phishing, blocking unsafe connections, and setting custom indicators.</span></span> <span data-ttu-id="5ff4d-147">Дополнительные сведения о ключевых особенностях и преимуществах читайте в наших [объявлениях.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="5ff4d-147">For more information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span> 

<span data-ttu-id="5ff4d-148">Дополнительные сведения о том, как начать работу, посетите веб-сайт Microsoft Defender для конечной точки в документации по [iOS.](microsoft-defender-endpoint-ios.md)</span><span class="sxs-lookup"><span data-stu-id="5ff4d-148">For more details on how to get started, visit the Microsoft Defender for Endpoint on iOS [documentation](microsoft-defender-endpoint-ios.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5ff4d-149">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="5ff4d-149">Licensing requirements</span></span> 

<span data-ttu-id="5ff4d-150">Лицензированные пользователи могут использовать Microsoft Defender для конечной точки на пяти одновременном устройстве.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-150">Eligible Licensed Users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span> <span data-ttu-id="5ff4d-151">Microsoft Defender для конечной точки также доступен для покупки в поставщик облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="5ff4d-151">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="5ff4d-152">Клиенты могут получить Microsoft Defender для конечной точки на macOS с помощью автономных лицензий Microsoft Defender для конечной точки в Microsoft 365 A5/E5 или Microsoft 365 Security.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-152">Customers can obtain Microsoft Defender for Endpoint on macOS through a standalone Microsoft Defender for Endpoint license, as part of Microsoft 365 A5/E5, or Microsoft 365 Security.</span></span>

<span data-ttu-id="5ff4d-153">Недавно объявленные возможности Microsoft Defender для конечной точки на Android и iOS включены в указанные выше предложения в составе пяти квалифицированных устройств для лицензированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-153">Recently announced capabilities of Microsoft Defender for Endpoint on Android and iOS are included in the above mentioned offers as part of the five qualified devices for eligible licensed users.</span></span>

<span data-ttu-id="5ff4d-154">Defender for Endpoint on Linux доступен через SKU Defender for Endpoint Server, который доступен как для коммерческих, так и для образовательных клиентов.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-154">Defender for Endpoint on Linux is available through the Defender for Endpoint Server SKU that is available for both commercial and education customers.</span></span>

<span data-ttu-id="5ff4d-155">Пожалуйста, свяжитесь с командой учетной записи или CSP для определения цен и дополнительных требований к требованиям.</span><span class="sxs-lookup"><span data-stu-id="5ff4d-155">Please contact your account team or CSP for pricing and additional eligibility requirements.</span></span>
