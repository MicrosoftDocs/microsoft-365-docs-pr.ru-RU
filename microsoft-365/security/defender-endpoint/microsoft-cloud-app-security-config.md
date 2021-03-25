---
title: Настройка интеграции microsoft Cloud App Security
ms.reviewer: ''
description: Узнайте, как включить параметры, чтобы включить интеграцию Microsoft Defender для конечных точек с безопасностью облачных приложений Microsoft.
keywords: облако, приложение, безопасность, параметры, интеграция, обнаружение, отчет
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
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076573"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="74b88-104">Настройка безопасности облачных приложений Майкрософт в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="74b88-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74b88-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="74b88-105">**Applies to:**</span></span>
- [<span data-ttu-id="74b88-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="74b88-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="74b88-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74b88-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="74b88-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="74b88-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74b88-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="74b88-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="74b88-110">Чтобы воспользоваться сигналами обнаружения облачных приложений Microsoft Defender для конечных точек, включим интеграцию microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="74b88-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="74b88-111">Эта функция будет доступна с лицензией E5 для корпоративной мобильности [и](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) безопасности на устройствах под управлением Windows 10, версии 1709 (СБОРКА ОС 16299.1085 с [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, версия 1803 (сборка ОС 17134.704 с [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, версия 1809 (СБОРКА ОС 17763.379 с [KB4489899)](https://support.microsoft.com/help/4489899)или более поздние версии Windows 10.</span><span class="sxs-lookup"><span data-stu-id="74b88-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="74b88-112">Подробные сведения о интеграции Microsoft Defender для конечной точки с [безопасностью облачных](https://docs.microsoft.com/cloud-app-security/mde-integration) приложений Microsoft Для подробной интеграции Microsoft Defender для конечной точки с безопасностью облачных приложений Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74b88-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="74b88-113">Включить безопасность облачных приложений Майкрософт в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="74b88-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="74b88-114">В области навигации выберите **Параметры настройки**  >  **Расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="74b88-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="74b88-115">Выберите **microsoft Cloud App Security** и переключить переключатель на **On**.</span><span class="sxs-lookup"><span data-stu-id="74b88-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="74b88-116">Нажмите **кнопку Сохранить предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="74b88-116">Click **Save preferences**.</span></span>

<span data-ttu-id="74b88-117">После активации Microsoft Defender для конечной точки немедленно начнет переададировать сигналы обнаружения в cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="74b88-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="74b88-118">Просмотр собранных данных</span><span class="sxs-lookup"><span data-stu-id="74b88-118">View the data collected</span></span>

<span data-ttu-id="74b88-119">Сведения о просмотре и доступе к данным Microsoft Defender для конечных точек в microsoft Cloud Apps Security см. в обзоре устройств [в области безопасности облачных приложений.](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="74b88-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="74b88-120">Дополнительные сведения об обнаружении облачных данных см. в [ссылке Работа с обнаруженными приложениями.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="74b88-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="74b88-121">Если вы хотите попробовать microsoft Cloud App Security, см. в [приложении Microsoft Cloud Security Trial.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)</span><span class="sxs-lookup"><span data-stu-id="74b88-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="74b88-122">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="74b88-122">Related topic</span></span>
- [<span data-ttu-id="74b88-123">Интеграция microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="74b88-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
