---
title: Исправление нездоровых датчиков в Microsoft Defender для конечной точки
description: Исправьте датчики устройств, которые сообщают о неправильном или неактивном устройстве, чтобы служба получала данные с устройства.
keywords: неправильно сконфигурированная, неактивность, исправление датчика, состояние датчика, отсутствие данных датчиков, данных датчиков, нарушенная связь, связь
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935369"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ea7af-104">Исправление нездоровых датчиков в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ea7af-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ea7af-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ea7af-105">**Applies to:**</span></span>
- [<span data-ttu-id="ea7af-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ea7af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ea7af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea7af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="ea7af-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ea7af-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ea7af-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ea7af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="ea7af-110">Устройства, которые классифицируются как неправильно сконфигурированы или неактивны, могут быть помечены из-за различных причин.</span><span class="sxs-lookup"><span data-stu-id="ea7af-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="ea7af-111">В этом разделе приводится ряд объяснений того, что могло привести к тому, что устройство было классифицироваться как неактивное или неправильное.</span><span class="sxs-lookup"><span data-stu-id="ea7af-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="ea7af-112">Неактивные устройства</span><span class="sxs-lookup"><span data-stu-id="ea7af-112">Inactive devices</span></span>

<span data-ttu-id="ea7af-113">Неактивное устройство не обязательно помечено из-за проблемы.</span><span class="sxs-lookup"><span data-stu-id="ea7af-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="ea7af-114">Следующие действия, принятые на устройстве, могут привести к категоризированию устройства как неактивного:</span><span class="sxs-lookup"><span data-stu-id="ea7af-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="ea7af-115">Устройство не используется</span><span class="sxs-lookup"><span data-stu-id="ea7af-115">Device is not in use</span></span>

<span data-ttu-id="ea7af-116">Если устройство по какой-либо причине не используется более семи дней, оно останется в состоянии "Неактивно" на портале.</span><span class="sxs-lookup"><span data-stu-id="ea7af-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="ea7af-117">Устройство было переустановлено или переименовано</span><span class="sxs-lookup"><span data-stu-id="ea7af-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="ea7af-118">Переустановленное или переименованное устройство будет создавать новое устройство в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ea7af-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="ea7af-119">Предыдущее устройство останется со статусом "Неактивный" на портале.</span><span class="sxs-lookup"><span data-stu-id="ea7af-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="ea7af-120">Если вы переустановили устройство и развернули пакет Defender for Endpoint, ищите новое имя устройства, чтобы убедиться, что устройство сообщает нормально.</span><span class="sxs-lookup"><span data-stu-id="ea7af-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="ea7af-121">Устройство было отключено</span><span class="sxs-lookup"><span data-stu-id="ea7af-121">Device was offboarded</span></span>
<span data-ttu-id="ea7af-122">Если устройство было отключено, оно по-прежнему будет отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="ea7af-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="ea7af-123">Через семь дней состояние состояния здоровья устройства должно измениться на неактивное.</span><span class="sxs-lookup"><span data-stu-id="ea7af-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="ea7af-124">Устройство не отправляет сигналы</span><span class="sxs-lookup"><span data-stu-id="ea7af-124">Device is not sending signals</span></span>
<span data-ttu-id="ea7af-125">Если устройство не отправляет сигналы в течение более семи дней ни в один из каналов Microsoft Defender для конечных точек по любой причине, включая условия, которые попадают под классификацию неправильного устройства, устройство можно считать неактивным.</span><span class="sxs-lookup"><span data-stu-id="ea7af-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="ea7af-126">Ожидаете ли вы, что устройство будет в состоянии "Active"?</span><span class="sxs-lookup"><span data-stu-id="ea7af-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="ea7af-127">[Откройте билет поддержки.](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)</span><span class="sxs-lookup"><span data-stu-id="ea7af-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="ea7af-128">Неправильно настроенные устройства</span><span class="sxs-lookup"><span data-stu-id="ea7af-128">Misconfigured devices</span></span>
<span data-ttu-id="ea7af-129">Неправильное устройство можно далее классифицировать так:</span><span class="sxs-lookup"><span data-stu-id="ea7af-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="ea7af-130">Нарушение связи</span><span class="sxs-lookup"><span data-stu-id="ea7af-130">Impaired communications</span></span>
- <span data-ttu-id="ea7af-131">Нет данных датчика</span><span class="sxs-lookup"><span data-stu-id="ea7af-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="ea7af-132">Нарушение связи</span><span class="sxs-lookup"><span data-stu-id="ea7af-132">Impaired communications</span></span>
<span data-ttu-id="ea7af-133">Этот статус указывает, что связь между устройством и службой ограничена.</span><span class="sxs-lookup"><span data-stu-id="ea7af-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="ea7af-134">Следующие предлагаемые действия могут помочь устранить проблемы, связанные с неправильно сконфигурованным устройством с нарушениями связи:</span><span class="sxs-lookup"><span data-stu-id="ea7af-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="ea7af-135">Убедитесь, что устройство подключено к Интернету</span><span class="sxs-lookup"><span data-stu-id="ea7af-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="ea7af-136">Для использования датчика Microsoft Defender для конечной точки требуется Microsoft Windows HTTP (WinHTTP), чтобы передавать данные датчика и общаться со службой Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ea7af-136">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="ea7af-137">Проверка подключения клиента к URL-адресам службы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="ea7af-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="ea7af-138">Убедитесь, что конфигурация прокси успешно завершена, что WinHTTP может обнаруживаться и общаться через прокси-сервер в вашей среде, и что прокси-сервер позволяет трафик на URL-адреса службы Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ea7af-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="ea7af-139">Если вы приняли меры по исправлению и состояние устройства по-прежнему неправильно сконфигурировали, [откройте билет поддержки.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="ea7af-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="ea7af-140">Нет данных датчика</span><span class="sxs-lookup"><span data-stu-id="ea7af-140">No sensor data</span></span>
<span data-ttu-id="ea7af-141">Неправильное устройство со статусом "Нет данных датчика" имеет связь со службой, но может сообщать только о частичных данных датчика.</span><span class="sxs-lookup"><span data-stu-id="ea7af-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="ea7af-142">Выполните действия по исправлению известных проблем, связанных с неправильно сконфигурованным устройством со статусом "Нет данных датчика":</span><span class="sxs-lookup"><span data-stu-id="ea7af-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="ea7af-143">Убедитесь, что устройство подключено к Интернету</span><span class="sxs-lookup"><span data-stu-id="ea7af-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="ea7af-144">Для использования датчика Microsoft Defender для конечной точки требуется Microsoft Windows HTTP (WinHTTP), чтобы передавать данные датчика и общаться со службой Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ea7af-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="ea7af-145">Проверка подключения клиента к URL-адресам службы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="ea7af-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="ea7af-146">Убедитесь, что конфигурация прокси успешно завершена, что WinHTTP может обнаруживаться и общаться через прокси-сервер в вашей среде, и что прокси-сервер позволяет трафик на URL-адреса службы Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ea7af-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="ea7af-147">Убедитесь, что служба диагностических данных включена</span><span class="sxs-lookup"><span data-stu-id="ea7af-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="ea7af-148">Если устройства не сообщают правильно, может потребоваться проверить, что служба диагностических данных Windows 10 автоматически запущена и запущена на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="ea7af-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="ea7af-149">Убедитесь антивирусная программа в Microsoft Defender что политика не отключена</span><span class="sxs-lookup"><span data-stu-id="ea7af-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="ea7af-150">Если на ваших устройствах работает сторонний клиент противомалярийных программ, агенту Defender для конечной точки требуется включить антивирусная программа в Microsoft Defender раннего запуска антивирусного программного обеспечения (ELAM).</span><span class="sxs-lookup"><span data-stu-id="ea7af-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="ea7af-151">Если вы приняли меры по исправлению и состояние устройства по-прежнему неправильно сконфигурировали, [откройте билет поддержки.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="ea7af-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea7af-152">См. также</span><span class="sxs-lookup"><span data-stu-id="ea7af-152">See also</span></span>
- [<span data-ttu-id="ea7af-153">Проверка состояния состояния датчика в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ea7af-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
