---
title: Onboard non-Windows devices to the Microsoft Defender for Endpoint service
description: Настройте устройства без Windows, чтобы они могли отправлять данные датчиков в службу ATP Microsoft Defender.
keywords: onboard non-Windows devices, macos, Linux, device management, configure Windows ATP devices, configure Microsoft Defender for Endpoint devices
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
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166081"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="98cb8-104">Onboard non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="98cb8-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="98cb8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="98cb8-105">**Applies to:**</span></span>
- [<span data-ttu-id="98cb8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="98cb8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98cb8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98cb8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="98cb8-108">**Платформы**</span><span class="sxs-lookup"><span data-stu-id="98cb8-108">**Platforms**</span></span>
- <span data-ttu-id="98cb8-109">macOS</span><span class="sxs-lookup"><span data-stu-id="98cb8-109">macOS</span></span>
- <span data-ttu-id="98cb8-110">Linux</span><span class="sxs-lookup"><span data-stu-id="98cb8-110">Linux</span></span>

><span data-ttu-id="98cb8-111">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="98cb8-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98cb8-112">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="98cb8-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="98cb8-113">Defender for Endpoint предоставляет централизованные операции безопасности как для Windows, так и для неконтроционных платформ.</span><span class="sxs-lookup"><span data-stu-id="98cb8-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="98cb8-114">Вы сможете видеть оповещения из различных поддерживаемых операционных систем (ОС) в Центре безопасности Microsoft Defender и лучше защищать сеть организации.</span><span class="sxs-lookup"><span data-stu-id="98cb8-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="98cb8-115">Вам необходимо знать точные версии дистрофии Linux и macOS, совместимые с Defender для конечной точки для работы интеграции.</span><span class="sxs-lookup"><span data-stu-id="98cb8-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="98cb8-116">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="98cb8-116">For more information, see:</span></span>
- [<span data-ttu-id="98cb8-117">Microsoft Defender для конечной точки для требований к системе Linux</span><span class="sxs-lookup"><span data-stu-id="98cb8-117">Microsoft Defender for Endpoint for Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="98cb8-118">[Требования к системе Microsoft Defender для конечной точки для Mac.](microsoft-defender-endpoint-mac.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="98cb8-118">[Microsoft Defender for Endpoint for Mac system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="98cb8-119">Onboarding non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="98cb8-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="98cb8-120">Необходимо предпринять следующие действия на бортовых устройствах без Windows:</span><span class="sxs-lookup"><span data-stu-id="98cb8-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="98cb8-121">Выберите предпочтительный метод бортовой работы:</span><span class="sxs-lookup"><span data-stu-id="98cb8-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="98cb8-122">Для устройств macOS вы можете выбрать бортовой вариант с помощью ATP Microsoft Defender или через сторонное решение.</span><span class="sxs-lookup"><span data-stu-id="98cb8-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="98cb8-123">Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки для Mac.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)</span><span class="sxs-lookup"><span data-stu-id="98cb8-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>
   - <span data-ttu-id="98cb8-124">Для других устройств, не в том что касается Windows, выберите **onboard non-Windows devices через сторонную интеграцию.**</span><span class="sxs-lookup"><span data-stu-id="98cb8-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
       
     1. <span data-ttu-id="98cb8-125">В области навигации выберите **Партнеров по интероперабельности.**  >  </span><span class="sxs-lookup"><span data-stu-id="98cb8-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="98cb8-126">Убедитесь, что в списке находится сторонное решение.</span><span class="sxs-lookup"><span data-stu-id="98cb8-126">Make sure the third-party solution is listed.</span></span>

        2. <span data-ttu-id="98cb8-127">На **вкладке Приложения-партнеры** выберите партнера, поддерживаюного устройства, не в windows.</span><span class="sxs-lookup"><span data-stu-id="98cb8-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>

        3. <span data-ttu-id="98cb8-128">Выберите **открытую страницу партнера,** чтобы открыть страницу партнера.</span><span class="sxs-lookup"><span data-stu-id="98cb8-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="98cb8-129">Следуйте инструкциям, предоставленным на странице.</span><span class="sxs-lookup"><span data-stu-id="98cb8-129">Follow the instructions provided on the page.</span></span>

        4. <span data-ttu-id="98cb8-130">После создания учетной записи или подписки на решение партнеров необходимо выйти на этап, когда клиенту Глобального администратора в организации будет предложено принять запрос на разрешение от партнерского приложения.</span><span class="sxs-lookup"><span data-stu-id="98cb8-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="98cb8-131">Внимательно ознакомьтесь с запросом разрешений, чтобы убедиться, что он соответствует требуемой службе.</span><span class="sxs-lookup"><span data-stu-id="98cb8-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="98cb8-132">Запустите тест обнаружения, следуя инструкциям сторонних решений.</span><span class="sxs-lookup"><span data-stu-id="98cb8-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="98cb8-133">Offboard non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="98cb8-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="98cb8-134">Следуйте документации стороной, чтобы отключить сторонное решение от Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="98cb8-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="98cb8-135">Удаление разрешений для сторонних решений в клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="98cb8-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="98cb8-136">Войдите на [портал Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="98cb8-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="98cb8-137">Выберите **Azure Active Directory > корпоративных приложений.**</span><span class="sxs-lookup"><span data-stu-id="98cb8-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="98cb8-138">Выберите приложение, которое вы хотите отключить.</span><span class="sxs-lookup"><span data-stu-id="98cb8-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="98cb8-139">Выберите **кнопку Удалить.**</span><span class="sxs-lookup"><span data-stu-id="98cb8-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="98cb8-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="98cb8-140">Related topics</span></span>
- [<span data-ttu-id="98cb8-141">На борту устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="98cb8-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="98cb8-142">Серверы на борту</span><span class="sxs-lookup"><span data-stu-id="98cb8-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="98cb8-143">Настройка параметров прокси и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="98cb8-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="98cb8-144">Устранение неполадок с учетом проблем с бортовой точкой Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="98cb8-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
