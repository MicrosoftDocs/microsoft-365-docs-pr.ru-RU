---
title: Onboard non-Windows для службы Microsoft Defender для конечных точек
description: Настройте нестандартные Windows, чтобы они могли отправлять данные датчиков в службу Microsoft Defender для конечных точек.
keywords: onboard non-Windows, macos, linux, device management, configure Microsoft Defender for Endpoint devices
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
ms.openlocfilehash: 4aff505f9f35b6144360eed5992ac36cf0847617
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454713"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="ca381-104">Подключение устройствах, отличных от Windows</span><span class="sxs-lookup"><span data-stu-id="ca381-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ca381-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ca381-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca381-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ca381-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ca381-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca381-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ca381-108">**Платформы**</span><span class="sxs-lookup"><span data-stu-id="ca381-108">**Platforms**</span></span>
- <span data-ttu-id="ca381-109">macOS</span><span class="sxs-lookup"><span data-stu-id="ca381-109">macOS</span></span>
- <span data-ttu-id="ca381-110">Linux</span><span class="sxs-lookup"><span data-stu-id="ca381-110">Linux</span></span>

><span data-ttu-id="ca381-111">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ca381-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ca381-112">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ca381-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="ca381-113">Defender for Endpoint предоставляет централизованный опыт операций безопасности для Windows, а также Windows платформ.</span><span class="sxs-lookup"><span data-stu-id="ca381-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="ca381-114">Вы сможете видеть оповещения из различных поддерживаемых операционных систем (ОС) в Microsoft 365 Defender и лучше защищать сеть организации.</span><span class="sxs-lookup"><span data-stu-id="ca381-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft 365 Defender and better protect your organization's network.</span></span> 

<span data-ttu-id="ca381-115">Вам необходимо знать точные версии дистрофии Linux и macOS, совместимые с Defender для конечной точки для работы интеграции.</span><span class="sxs-lookup"><span data-stu-id="ca381-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="ca381-116">Подробнее:</span><span class="sxs-lookup"><span data-stu-id="ca381-116">For more information, see:</span></span>
- [<span data-ttu-id="ca381-117">Microsoft Defender для конечной точки в требованиях к системе Linux</span><span class="sxs-lookup"><span data-stu-id="ca381-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="ca381-118">[Microsoft Defender для конечной точки в требованиях к системе macOS.](microsoft-defender-endpoint-mac.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="ca381-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="ca381-119">Onboarding non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="ca381-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="ca381-120">Необходимо предпринять следующие действия для бортовых Windows устройств:</span><span class="sxs-lookup"><span data-stu-id="ca381-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="ca381-121">Выберите предпочтительный метод бортовой работы:</span><span class="sxs-lookup"><span data-stu-id="ca381-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="ca381-122">Для устройств macOS вы можете выбрать бортовой вариант через Microsoft Defender для конечной точки или через сторонное решение.</span><span class="sxs-lookup"><span data-stu-id="ca381-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="ca381-123">Дополнительные сведения см. [в сайте Microsoft Defender для конечной точки на Mac.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)</span><span class="sxs-lookup"><span data-stu-id="ca381-123">For more information, see [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="ca381-124">Для других устройств, Windows других устройств, выберите Windows устройства с помощью **сторонних интеграций.**</span><span class="sxs-lookup"><span data-stu-id="ca381-124">For other non-Windows devices, choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="ca381-125">В области навигации выберите **Партнеров по интероперабельности.**  >  </span><span class="sxs-lookup"><span data-stu-id="ca381-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="ca381-126">Убедитесь, что в списке находится сторонное решение.</span><span class="sxs-lookup"><span data-stu-id="ca381-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="ca381-127">На **вкладке Приложения партнеров** выберите партнера, который поддерживает Windows устройства.</span><span class="sxs-lookup"><span data-stu-id="ca381-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="ca381-128">Выберите **открытую страницу партнера,** чтобы открыть страницу партнера.</span><span class="sxs-lookup"><span data-stu-id="ca381-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="ca381-129">Следуйте инструкциям, предоставленным на странице.</span><span class="sxs-lookup"><span data-stu-id="ca381-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="ca381-130">После создания учетной записи или подписки на решение партнеров необходимо выйти на этап, когда клиенту Глобального администратора в организации будет предложено принять запрос на разрешение от партнерского приложения.</span><span class="sxs-lookup"><span data-stu-id="ca381-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="ca381-131">Внимательно ознакомьтесь с запросом разрешений, чтобы убедиться, что он соответствует требуемой службе.</span><span class="sxs-lookup"><span data-stu-id="ca381-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="ca381-132">Запустите тест обнаружения, следуя инструкциям сторонних решений.</span><span class="sxs-lookup"><span data-stu-id="ca381-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="ca381-133">Offboard non-Windows устройств</span><span class="sxs-lookup"><span data-stu-id="ca381-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="ca381-134">Следуйте документации стороной, чтобы отключить сторонное решение от Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca381-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="ca381-135">Удаление разрешений для сторонних решений в клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ca381-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="ca381-136">Войдите на [портал Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="ca381-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="ca381-137">Выберите **Azure Active Directory > Enterprise приложения**.</span><span class="sxs-lookup"><span data-stu-id="ca381-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="ca381-138">Выберите приложение, которое вы хотите отключить.</span><span class="sxs-lookup"><span data-stu-id="ca381-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="ca381-139">Выберите **кнопку Удалить.**</span><span class="sxs-lookup"><span data-stu-id="ca381-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ca381-140">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ca381-140">Related topics</span></span>
- [<span data-ttu-id="ca381-141">Подключение устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="ca381-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="ca381-142">Серверы на борту</span><span class="sxs-lookup"><span data-stu-id="ca381-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="ca381-143">Настройка параметров прокси-сервера и соединения с Интернетом</span><span class="sxs-lookup"><span data-stu-id="ca381-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="ca381-144">Устранение неполадок с учетом проблем с бортовой точкой Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ca381-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
