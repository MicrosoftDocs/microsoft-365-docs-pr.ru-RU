---
title: Включить среду оценки для Microsoft Cloud App Security
description: Узнайте архитектуру MCAS в Microsoft Defender для Office 365 и узнайте о взаимодействии между Microsoft 365 Defender продуктами.
keywords: Microsoft 365 Defender пробной версии попробуйте Microsoft 365 Defender, оцените Microsoft 365 Defender, Microsoft 365 Defender лаборатории оценки, пилот Microsoft 365 Defender, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователей, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458545"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="c1660-104">Включить среду оценки для Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c1660-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="c1660-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c1660-105">**Applies to:**</span></span>

- <span data-ttu-id="c1660-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1660-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c1660-107">Эта статья [— шаг 2 из 2](eval-defender-mcas-overview.md) в процессе настройки среды оценки для Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c1660-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="c1660-108">Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c1660-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="c1660-109">В этой статье вы можете получить доступ к порталу Cloud App Security и настроить необходимую интеграцию для сбора данных трафика облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="c1660-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="c1660-110">Чтобы найти облачные приложения, используемые в среде, можно сделать одно или оба следующих:</span><span class="sxs-lookup"><span data-stu-id="c1660-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="c1660-111">Быстро встать и работать с cloud Discovery, интегрируясь с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c1660-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c1660-112">Эта нативная интеграция позволяет сразу же приступить к сбору данных по облачному трафику на Windows 10 устройствах, в сети и вне ее.</span><span class="sxs-lookup"><span data-stu-id="c1660-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="c1660-113">Чтобы узнать все облачные приложения, доступ к которые доступны на всех устройствах, подключенных к сети, разместите Cloud App Security журнала на брандмауэрах и других прокси-экранах.</span><span class="sxs-lookup"><span data-stu-id="c1660-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="c1660-114">Это собирает данные из конечных точек и отправляет их в Cloud App Security для анализа.</span><span class="sxs-lookup"><span data-stu-id="c1660-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="c1660-115">Cloud App Security интегрируется с некоторыми сторонними прокси для еще большего потенциала.</span><span class="sxs-lookup"><span data-stu-id="c1660-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="c1660-116">В этой статье содержатся рекомендации по обоим методам.</span><span class="sxs-lookup"><span data-stu-id="c1660-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="c1660-117">Чтобы настроить Microsoft Cloud App Security, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="c1660-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![Действия, позволяющие Microsoft Cloud App Security Microsoft в среде оценки Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="c1660-119">Шаг 1. Подключение на портал Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c1660-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="c1660-120">Шаг 2. Интеграция с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c1660-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="c1660-121">Шаг 3. Развертывание Cloud App Security журнала на брандмауэрах и других прокси</span><span class="sxs-lookup"><span data-stu-id="c1660-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="c1660-122">Шаг 4. Просмотр панели мониторинга облачного обнаружения, чтобы узнать, какие приложения используются в организации</span><span class="sxs-lookup"><span data-stu-id="c1660-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="c1660-123">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="c1660-123">Step 1.</span></span> <span data-ttu-id="c1660-124">Подключение на портал Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c1660-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="c1660-125">Чтобы проверить лицензирование и подключиться к порталу Cloud App Security, см. в обзоре [Quickstart: Начало работы с Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="c1660-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="c1660-126">Если вы не можете сразу подключиться к порталу, может потребоваться добавить IP-адрес в допустимый список брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="c1660-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="c1660-127">См. [основные настройки для Cloud App Security.](/cloud-app-security/general-setup)</span><span class="sxs-lookup"><span data-stu-id="c1660-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="c1660-128">Если у вас по-прежнему возникли проблемы, просмотрите [требования к сети.](/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="c1660-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="c1660-129">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="c1660-129">Step 2.</span></span> <span data-ttu-id="c1660-130">Интеграция с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c1660-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c1660-131">Microsoft Cloud App Security интегрируется с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c1660-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="c1660-132">Интеграция упрощает внедрение cloud Discovery, расширяет возможности cloud Discovery за пределами корпоративной сети и позволяет вести исследование на основе устройств.</span><span class="sxs-lookup"><span data-stu-id="c1660-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="c1660-133">Эта интеграция показывает облачные приложения и службы, к которым можно получить доступ с ИТ-Windows 10 устройств.</span><span class="sxs-lookup"><span data-stu-id="c1660-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="c1660-134">Если вы уже настроили Microsoft Defender для конечной точки, настройка интеграции с Cloud App Security является Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c1660-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="c1660-135">После включаемой интеграции можно вернуться на портал Cloud App Security и просмотреть богатые данные на панели мониторинга обнаружения облаков.</span><span class="sxs-lookup"><span data-stu-id="c1660-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="c1660-136">Для выполнения этих задач см. [в веб-сайте Microsoft Defender для интеграции](/cloud-app-security/mde-integration)конечных точек с Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c1660-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="c1660-137">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="c1660-137">Step 3.</span></span> <span data-ttu-id="c1660-138">Развертывание Cloud App Security журнала на брандмауэрах и других прокси</span><span class="sxs-lookup"><span data-stu-id="c1660-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="c1660-139">Для покрытия всех устройств, подключенных к сети, разместите Cloud App Security журнала на брандмауэрах и других прокси для сбора данных с конечных точек и отправки их в Cloud App Security для анализа.</span><span class="sxs-lookup"><span data-stu-id="c1660-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="c1660-140">Если вы используете один из следующих безопасных веб-шлюзов (SWG), Cloud App Security обеспечивает бесшовное развертывание и интеграцию:</span><span class="sxs-lookup"><span data-stu-id="c1660-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="c1660-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="c1660-141">Zscaler</span></span>
- <span data-ttu-id="c1660-142">iboss</span><span class="sxs-lookup"><span data-stu-id="c1660-142">iboss</span></span>
- <span data-ttu-id="c1660-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="c1660-143">Corrata</span></span>
- <span data-ttu-id="c1660-144">Безопасность Menlo</span><span class="sxs-lookup"><span data-stu-id="c1660-144">Menlo Security</span></span>

<span data-ttu-id="c1660-145">Дополнительные сведения об интеграции с этими сетевыми устройствами см. в [сайте Set up Cloud Discovery.](/cloud-app-security/set-up-cloud-discovery)</span><span class="sxs-lookup"><span data-stu-id="c1660-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="c1660-146">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="c1660-146">Step 4.</span></span> <span data-ttu-id="c1660-147">Просмотр панели мониторинга облачного обнаружения, чтобы узнать, какие приложения используются в организации</span><span class="sxs-lookup"><span data-stu-id="c1660-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="c1660-148">Панель мониторинга обнаружения облаков предназначена для получения дополнительных данных о том, как облачные приложения используются в организации.</span><span class="sxs-lookup"><span data-stu-id="c1660-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="c1660-149">Он предоставляет краткий обзор используемых приложений, открытых оповещений и уровней риска приложений в организации.</span><span class="sxs-lookup"><span data-stu-id="c1660-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="c1660-150">Чтобы начать работу с панели мониторинга cloud Discovery, см. в странице [Работа с обнаруженными приложениями.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="c1660-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1660-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c1660-151">Next steps</span></span>

<span data-ttu-id="c1660-152">Шаг 3 из 3. [Пилотный Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="c1660-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="c1660-153">Возвращайся к обзору [для Оценки Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c1660-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="c1660-154">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c1660-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>