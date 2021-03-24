---
title: Устранение неполадок в Microsoft Defender для проблем службы конечных точек
description: Поиск решений и работа с известными вопросами, такими как ошибки сервера при попытке получить доступ к службе.
keywords: устранение неполадок защитника Майкрософт для конечной точки, устранение неполадок в Windows ATP, ошибка сервера, отказ в доступе, недействительные учетные данные, отсутствие данных, портал мониторинга, разрешить, просмотр событий
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: bd211a56ee9ed6aa871c8d55149247a4755bc863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072902"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="b1213-104">Проблемы службы устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="b1213-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1213-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b1213-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1213-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b1213-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b1213-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1213-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b1213-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b1213-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b1213-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b1213-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="b1213-110">В этом разделе будут решаться проблемы, которые могут возникнуть при использовании службы расширенных угроз Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b1213-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="b1213-111">Ошибка сервера. Доступ отказано из-за недействительных учетных данных</span><span class="sxs-lookup"><span data-stu-id="b1213-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="b1213-112">Если при попытке доступа к службе вы столкнулись с ошибкой сервера, необходимо изменить параметры cookie браузера.</span><span class="sxs-lookup"><span data-stu-id="b1213-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="b1213-113">Настройте браузер, чтобы разрешить файлы cookie.</span><span class="sxs-lookup"><span data-stu-id="b1213-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="b1213-114">Элементы или данные, отсутствующие на портале</span><span class="sxs-lookup"><span data-stu-id="b1213-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="b1213-115">Если некоторые элементы пользовательского интерфейса или данные отсутствуют в Центре безопасности Microsoft Defender, возможно, параметры прокси-сервера блокируют его.</span><span class="sxs-lookup"><span data-stu-id="b1213-115">If some UI elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="b1213-116">Убедитесь, `*.securitycenter.windows.com` что этот список включен в список прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="b1213-116">Make sure that `*.securitycenter.windows.com` is included the proxy allow list.</span></span>


> [!NOTE]
> <span data-ttu-id="b1213-117">При добавлении следующих конечных точек необходимо использовать протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b1213-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="b1213-118">Microsoft Defender для службы конечных точек показывает журналы событий или ошибок в viewer событий</span><span class="sxs-lookup"><span data-stu-id="b1213-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="b1213-119">В разделе Обзор событий и ошибок с помощью [viewer](event-error-codes.md) событий см. список ID событий, которые сообщаются службой Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="b1213-119">See the topic [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="b1213-120">В этой теме также содержатся действия по устранению неполадок при ошибках событий.</span><span class="sxs-lookup"><span data-stu-id="b1213-120">The topic also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="b1213-121">Служба Microsoft Defender для конечных точек не удается запустить после перезагрузки и показывает ошибку 577</span><span class="sxs-lookup"><span data-stu-id="b1213-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="b1213-122">Если бортовые устройства успешно завершатся, но Microsoft Defender для конечной точки не начинается после перезагрузки и показывает ошибку 577, убедитесь, что Защитник Windows не отключена политикой.</span><span class="sxs-lookup"><span data-stu-id="b1213-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="b1213-123">Дополнительные сведения см. в [веб-сайте Убедитесь,](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)что антивирус Microsoft Defender не отключен политикой.</span><span class="sxs-lookup"><span data-stu-id="b1213-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="b1213-124">Известные проблемы с региональными форматами</span><span class="sxs-lookup"><span data-stu-id="b1213-124">Known issues with regional formats</span></span>

<span data-ttu-id="b1213-125">**Форматы даты и времени**</span><span class="sxs-lookup"><span data-stu-id="b1213-125">**Date and time formats**</span></span><br>
<span data-ttu-id="b1213-126">Известны некоторые проблемы с форматами времени и даты.</span><span class="sxs-lookup"><span data-stu-id="b1213-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="b1213-127">Поддерживаются следующие форматы дат:</span><span class="sxs-lookup"><span data-stu-id="b1213-127">The following date formats are supported:</span></span>
- <span data-ttu-id="b1213-128">MM/dd/yyyyy</span><span class="sxs-lookup"><span data-stu-id="b1213-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="b1213-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="b1213-129">dd/MM/yyyy</span></span>

<span data-ttu-id="b1213-130">В настоящее время не поддерживаются следующие форматы даты и времени:</span><span class="sxs-lookup"><span data-stu-id="b1213-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="b1213-131">Формат date yyyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="b1213-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="b1213-132">Формат даты dd/MM/yyy</span><span class="sxs-lookup"><span data-stu-id="b1213-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="b1213-133">Формат даты с yy.</span><span class="sxs-lookup"><span data-stu-id="b1213-133">Date format with yy.</span></span> <span data-ttu-id="b1213-134">Будет показываться только yyyy.</span><span class="sxs-lookup"><span data-stu-id="b1213-134">Will only show yyyy.</span></span>
- <span data-ttu-id="b1213-135">Формат времени HH:mm:ss не поддерживается (12-часовой формат AM/PM не поддерживается).</span><span class="sxs-lookup"><span data-stu-id="b1213-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="b1213-136">Поддерживается только 24-часовой формат.</span><span class="sxs-lookup"><span data-stu-id="b1213-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="b1213-137">**Использование запятой, чтобы указать тысячу**</span><span class="sxs-lookup"><span data-stu-id="b1213-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="b1213-138">Поддержка использования запятой в качестве сепаратора в числах не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b1213-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="b1213-139">Регионы, в которых число разделено запятой, чтобы указать тысячу, будут видеть использование точки только в качестве разделитора.</span><span class="sxs-lookup"><span data-stu-id="b1213-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="b1213-140">Например, 15,5K отображается как 15,5K.</span><span class="sxs-lookup"><span data-stu-id="b1213-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="b1213-141">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b1213-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1213-142">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b1213-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="b1213-143">Клиент Microsoft Defender для конечной точки был автоматически создан в Европе</span><span class="sxs-lookup"><span data-stu-id="b1213-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="b1213-144">При использовании Центра безопасности Azure для мониторинга серверов автоматически создается клиент Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="b1213-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="b1213-145">Данные Microsoft Defender для конечных точек хранятся в Европе по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1213-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="b1213-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b1213-146">Related topics</span></span>
- [<span data-ttu-id="b1213-147">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="b1213-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="b1213-148">Просмотр событий и ошибок с помощью viewer событий</span><span class="sxs-lookup"><span data-stu-id="b1213-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
