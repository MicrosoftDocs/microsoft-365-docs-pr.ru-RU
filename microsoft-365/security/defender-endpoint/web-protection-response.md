---
title: Реагирование на веб-угрозы в ATP Защитника Майкрософт
description: Откликайся на оповещения, связанные с вредоносными и нежелательными веб-сайтами. Понимание того, как защита от веб-угроз информирует конечных пользователей через их веб-браузеры и уведомления Windows
keywords: веб-защита, защита от веб-угроз, просмотр веб-страниц, оповещения, ответы, безопасность, фишинг, вредоносные программы, эксплойт, веб-сайты, защита сети, Edge, Internet Explorer, Chrome, Firefox, веб-браузер, уведомления, конечные пользователи, уведомления Windows, страница блокировки,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9f3873db4f85cec3f5f1a400dcfb7930c6a4faa
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187545"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="6692e-105">Реагирование на веб-угрозы</span><span class="sxs-lookup"><span data-stu-id="6692e-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6692e-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6692e-106">**Applies to:**</span></span>
- [<span data-ttu-id="6692e-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6692e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6692e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6692e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6692e-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="6692e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6692e-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="6692e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="6692e-111">Веб-защита в Microsoft Defender для конечной точки позволяет эффективно исследовать и реагировать на оповещения, относящиеся к вредоносным веб-сайтам и веб-сайтам в настраиваемом списке индикаторов.</span><span class="sxs-lookup"><span data-stu-id="6692e-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="6692e-112">Просмотр оповещений о веб-угрозах</span><span class="sxs-lookup"><span data-stu-id="6692e-112">View web threat alerts</span></span>
<span data-ttu-id="6692e-113">Microsoft Defender для конечной точки создает [следующие](manage-alerts.md) оповещения о вредоносной или подозрительной веб-активности:</span><span class="sxs-lookup"><span data-stu-id="6692e-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="6692e-114">**Подозрительное** подключение, заблокированное сетевой защитой— это предупреждение создается при попытке получить доступ  к вредоносному веб-сайту или веб-сайту в настраиваемом списке индикаторов, которая блокируется сетевой защитой в режиме *блокировки.*</span><span class="sxs-lookup"><span data-stu-id="6692e-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="6692e-115">**Подозрительное** подключение, обнаруженное сетевой защитой, — это предупреждение создается, когда попытка доступа к вредоносному  веб-сайту или веб-сайту в настраиваемом списке индикаторов обнаруживается защитой сети только в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="6692e-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="6692e-116">Каждое оповещение содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="6692e-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="6692e-117">Устройство, пытающееся получить доступ к заблокированным веб-сайту</span><span class="sxs-lookup"><span data-stu-id="6692e-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="6692e-118">Приложение или программа, используемая для отправки веб-запроса</span><span class="sxs-lookup"><span data-stu-id="6692e-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="6692e-119">Вредоносный URL-адрес или URL-адрес в настраиваемом списке индикаторов</span><span class="sxs-lookup"><span data-stu-id="6692e-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="6692e-120">Рекомендуемые действия для ответчиков</span><span class="sxs-lookup"><span data-stu-id="6692e-120">Recommended actions for responders</span></span>

![Изображение оповещений, связанных с защитой от веб-угроз](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="6692e-122">Чтобы уменьшить объем оповещений, Microsoft Defender for Endpoint консолидирует обнаружения веб-угроз для одного домена на одном устройстве каждый день в одно оповещение.</span><span class="sxs-lookup"><span data-stu-id="6692e-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="6692e-123">Только одно оповещение создается и подсчитываются в [отчете о защите веб-сайтов.](web-protection-monitoring.md)</span><span class="sxs-lookup"><span data-stu-id="6692e-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="6692e-124">Проверка сведений о веб-сайте</span><span class="sxs-lookup"><span data-stu-id="6692e-124">Inspect website details</span></span>
<span data-ttu-id="6692e-125">Вы можете погрузиться глубже, выбрав URL-адрес или домен веб-сайта в оповещении.</span><span class="sxs-lookup"><span data-stu-id="6692e-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="6692e-126">Это открывает страницу об этом КОНКРЕТНОМ URL-адресе или домене с различными сведениями, в том числе:</span><span class="sxs-lookup"><span data-stu-id="6692e-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="6692e-127">Устройства, которые пытались получить доступ к веб-сайту</span><span class="sxs-lookup"><span data-stu-id="6692e-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="6692e-128">Инциденты и оповещения, связанные с веб-сайтом</span><span class="sxs-lookup"><span data-stu-id="6692e-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="6692e-129">Как часто веб-сайт был замечен в событиях в организации</span><span class="sxs-lookup"><span data-stu-id="6692e-129">How frequent the website was seen in events in your organization</span></span>

    ![Изображение страницы сведений об объекте домена или URL-адреса](images/wtp-website-details.png)

[<span data-ttu-id="6692e-131">Дополнительные новости о страницах URL-адресов или сущности домена</span><span class="sxs-lookup"><span data-stu-id="6692e-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="6692e-132">Проверка устройства</span><span class="sxs-lookup"><span data-stu-id="6692e-132">Inspect the device</span></span>
<span data-ttu-id="6692e-133">Вы также можете проверить устройство, пытающееся получить доступ к заблокированным URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="6692e-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="6692e-134">Выбор имени устройства на странице оповещений открывает страницу с подробной информацией об устройстве.</span><span class="sxs-lookup"><span data-stu-id="6692e-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="6692e-135">Дополнительные новости о страницах сущности устройства</span><span class="sxs-lookup"><span data-stu-id="6692e-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="6692e-136">Уведомления веб-браузера и Windows для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="6692e-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="6692e-137">С помощью веб-защиты в Microsoft Defender для конечной точки конечным пользователям будет не мешать посещать вредоносные или нежелательные веб-сайты с помощью Microsoft Edge или других браузеров.</span><span class="sxs-lookup"><span data-stu-id="6692e-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="6692e-138">Так как блокировка выполняется с помощью [сетевой защиты,](network-protection.md)они увидят общую ошибку в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="6692e-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="6692e-139">Они также увидят уведомление из Windows.</span><span class="sxs-lookup"><span data-stu-id="6692e-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="6692e-140">![Изображение Microsoft Edge с ошибкой 403 и веб-угрозой уведомления Windows, ](images/wtp-browser-blocking-page.png)
 *заблокированной в Microsoft Edge*</span><span class="sxs-lookup"><span data-stu-id="6692e-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="6692e-141">![Изображение веб-браузера Chrome с предупреждением о безопасном подключении и веб-угрозой уведомления ](images/wtp-chrome-browser-blocking-page.png)
 *Windows, заблокированной в Chrome*</span><span class="sxs-lookup"><span data-stu-id="6692e-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="6692e-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6692e-142">Related topics</span></span>
- [<span data-ttu-id="6692e-143">Обзор веб-защиты</span><span class="sxs-lookup"><span data-stu-id="6692e-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="6692e-144">Фильтрация веб-контента</span><span class="sxs-lookup"><span data-stu-id="6692e-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="6692e-145">Защита от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="6692e-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="6692e-146">Мониторинг веб-безопасности</span><span class="sxs-lookup"><span data-stu-id="6692e-146">Monitor web security</span></span>](web-protection-monitoring.md)
