---
title: Защита организации от веб-угроз
description: Узнайте о веб-защите в Microsoft Defender для конечной точки и о том, как она может защитить организацию.
keywords: веб-защита, защита от веб-угроз, просмотр веб-сайтов, безопасность, фишинг, вредоносные программы, эксплойт, веб-сайты, защита сети, Edge, Internet Explorer, Chrome, Firefox, веб-браузер
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688949"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="7134f-104">Защита организации от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="7134f-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7134f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7134f-105">**Applies to:**</span></span>
- [<span data-ttu-id="7134f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7134f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7134f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7134f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7134f-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7134f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7134f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7134f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="7134f-110">Защита веб-угроз является частью [веб-защиты](web-protection-overview.md) в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7134f-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="7134f-111">Он использует [сетевую защиту](network-protection.md) для защиты устройств от веб-угроз.</span><span class="sxs-lookup"><span data-stu-id="7134f-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="7134f-112">Благодаря интеграции с Microsoft Edge и популярными сторонними браузерами, например Chrome и Firefox, защита от веб-угроз останавливает веб-угрозы без прокси-сервера и может защитить устройства во время их езды или на месте.</span><span class="sxs-lookup"><span data-stu-id="7134f-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="7134f-113">Защита от веб-угроз останавливает доступ к фишинг-сайтам, векторам вредоносных программ, сайтам эксплойтов, сайтам с недоверием или низкой репутации, а также сайтам, заблокированным в настраиваемом списке [индикаторов.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="7134f-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="7134f-114">Получение новых настраиваемых индикаторов для устройств может занять до часа.</span><span class="sxs-lookup"><span data-stu-id="7134f-114">It can take up to an hour for devices to receive new custom indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7134f-115">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="7134f-115">Prerequisites</span></span>
<span data-ttu-id="7134f-116">Веб-защита использует защиту сети для обеспечения безопасности просмотра веб-страниц в Microsoft Edge и сторонних веб-браузерах.</span><span class="sxs-lookup"><span data-stu-id="7134f-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="7134f-117">Чтобы включить защиту сети на устройствах:</span><span class="sxs-lookup"><span data-stu-id="7134f-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="7134f-118">Изменить базовый уровень безопасности Defender для конечной точки в веб& **сетевой** защите, чтобы включить защиту сети перед развертыванием или ее передислокатурой.</span><span class="sxs-lookup"><span data-stu-id="7134f-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="7134f-119">Узнайте о проверке и назначении базового уровня безопасности Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7134f-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="7134f-120">Включите защиту сети при использовании конфигурации устройств Intune, SCCM, групповой политики или решения MDM.</span><span class="sxs-lookup"><span data-stu-id="7134f-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="7134f-121">Подробнее о включаемой защите сети</span><span class="sxs-lookup"><span data-stu-id="7134f-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="7134f-122">Если вы установите защиту сети **только для аудита,** блокировка будет недоступной.</span><span class="sxs-lookup"><span data-stu-id="7134f-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="7134f-123">Кроме того, вы сможете обнаруживать и фиксировать попытки доступа к вредоносным и нежелательным веб-сайтам только в Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="7134f-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7134f-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7134f-124">Related topics</span></span>

- [<span data-ttu-id="7134f-125">Обзор веб-защиты</span><span class="sxs-lookup"><span data-stu-id="7134f-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="7134f-126">Защита от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="7134f-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="7134f-127">Мониторинг безопасности в Интернете</span><span class="sxs-lookup"><span data-stu-id="7134f-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="7134f-128">Реагирование на веб-угрозы</span><span class="sxs-lookup"><span data-stu-id="7134f-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="7134f-129">Защита сети</span><span class="sxs-lookup"><span data-stu-id="7134f-129">Network protection</span></span>](network-protection.md)
