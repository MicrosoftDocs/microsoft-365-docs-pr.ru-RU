---
title: Настройка интеграции Microsoft Cloud App Security
ms.reviewer: ''
description: Узнайте, как включить параметры, чтобы включить интеграцию Microsoft Defender для конечных точек с Microsoft Cloud App Security.
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
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844758"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9d33c-104">Настройка Microsoft Cloud App Security в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9d33c-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d33c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9d33c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d33c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9d33c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d33c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d33c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9d33c-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9d33c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9d33c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9d33c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="9d33c-110">Чтобы воспользоваться сигналами обнаружения облачных приложений Microsoft Defender для конечных точек, включим Microsoft Cloud App Security интеграцию.</span><span class="sxs-lookup"><span data-stu-id="9d33c-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="9d33c-111">Эта функция будет доступна с лицензией E5 для [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) на устройствах под управлением Windows 10 версии 1709 (СБОРКА ОС 16299.1085 с [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, версия 1803 (сборка ОС 17134.704 с [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, версия 1809 (СБОРКА ОС 17763.379 с [KB4489899)](https://support.microsoft.com/help/4489899)или более поздние Windows 10 версии.</span><span class="sxs-lookup"><span data-stu-id="9d33c-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="9d33c-112">Подробные сведения об интеграции [Microsoft Defender для конечной](/cloud-app-security/mde-integration) точки с Microsoft Cloud App Security для подробной интеграции Microsoft Defender для конечной точки с Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9d33c-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9d33c-113">Включить Microsoft Cloud App Security в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9d33c-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="9d33c-114">В области навигации выберите **Параметры настройки**  >  **Расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="9d33c-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="9d33c-115">Выберите **Microsoft Cloud App Security** и переключить переключатель **на On**.</span><span class="sxs-lookup"><span data-stu-id="9d33c-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="9d33c-116">Нажмите **кнопку Сохранить предпочтения**.</span><span class="sxs-lookup"><span data-stu-id="9d33c-116">Click **Save preferences**.</span></span>

<span data-ttu-id="9d33c-117">После активации Microsoft Defender для конечной точки немедленно начнет переададировать сигналы обнаружения в Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9d33c-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="9d33c-118">Просмотр собранных данных</span><span class="sxs-lookup"><span data-stu-id="9d33c-118">View the data collected</span></span>

<span data-ttu-id="9d33c-119">Сведения о просмотре и доступе к данным Microsoft Defender для конечных точек в microsoft Cloud Apps Security см. в [Cloud App Security.](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="9d33c-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="9d33c-120">Дополнительные сведения об обнаружении облачных данных см. в [ссылке Работа с обнаруженными приложениями.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="9d33c-120">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="9d33c-121">Если вы хотите попробовать Microsoft Cloud App Security, см. [Microsoft Cloud App Security пробной.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)</span><span class="sxs-lookup"><span data-stu-id="9d33c-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="9d33c-122">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="9d33c-122">Related topic</span></span>
- [<span data-ttu-id="9d33c-123">Microsoft Cloud App Security интеграции</span><span class="sxs-lookup"><span data-stu-id="9d33c-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
