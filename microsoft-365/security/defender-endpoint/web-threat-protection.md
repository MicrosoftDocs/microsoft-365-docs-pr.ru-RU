---
title: Защита организации от веб-угроз
description: Узнайте о веб-защите в ATP Microsoft Defender и о том, как она может защитить организацию.
keywords: веб-защита, защита от веб-угроз, просмотр веб-сайтов, безопасность, фишинг, вредоносные программы, эксплойт, веб-сайты, защита сети, Edge, Internet Explorer, Chrome, Firefox, веб-браузер
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
ms.openlocfilehash: 3376308988213b84bc7badb96ebacdf706d1ca5f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071670"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="2ee9d-104">Защита организации от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="2ee9d-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ee9d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2ee9d-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ee9d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2ee9d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2ee9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ee9d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2ee9d-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2ee9d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ee9d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="2ee9d-110">Защита веб-угроз является частью [веб-защиты](web-protection-overview.md) в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="2ee9d-111">Он использует [сетевую защиту](network-protection.md) для защиты устройств от веб-угроз.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="2ee9d-112">Благодаря интеграции с Microsoft Edge и популярными сторонними браузерами, например Chrome и Firefox, защита от веб-угроз останавливает веб-угрозы без прокси-сервера и может защитить устройства во время их езды или на месте.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="2ee9d-113">Защита от веб-угроз останавливает доступ к фишинг-сайтам, векторам вредоносных программ, сайтам эксплойтов, сайтам с недоверием или низкой репутации, а также сайтам, заблокированным в настраиваемом списке [индикаторов.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="2ee9d-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="2ee9d-114">Для получения новых индикаторов клиентов устройствам может занять до часа.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-114">It can take up to an hour for devices to receive new customer indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ee9d-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2ee9d-115">Prerequisites</span></span>
<span data-ttu-id="2ee9d-116">Веб-защита использует защиту сети для обеспечения безопасности просмотра веб-страниц в Microsoft Edge и сторонних веб-браузерах.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="2ee9d-117">Чтобы включить защиту сети на устройствах:</span><span class="sxs-lookup"><span data-stu-id="2ee9d-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="2ee9d-118">Изменить базовый уровень безопасности Defender для конечной точки в веб& **сетевой** защите, чтобы включить защиту сети перед развертыванием или ее передислокатурой.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="2ee9d-119">Узнайте о проверке и назначении базового уровня безопасности Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2ee9d-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="2ee9d-120">Включите защиту сети при использовании конфигурации устройств Intune, SCCM, групповой политики или решения MDM.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="2ee9d-121">Подробнее о включаемой защите сети</span><span class="sxs-lookup"><span data-stu-id="2ee9d-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="2ee9d-122">Если вы установите защиту сети **только для аудита,** блокировка будет недоступной.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="2ee9d-123">Кроме того, вы сможете обнаруживать и фиксировать попытки доступа к вредоносным и нежелательным веб-сайтам только в Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2ee9d-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ee9d-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2ee9d-124">Related topics</span></span>

- [<span data-ttu-id="2ee9d-125">Обзор веб-защиты</span><span class="sxs-lookup"><span data-stu-id="2ee9d-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="2ee9d-126">Защита от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="2ee9d-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="2ee9d-127">Мониторинг веб-безопасности</span><span class="sxs-lookup"><span data-stu-id="2ee9d-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="2ee9d-128">Реагирование на веб-угрозы</span><span class="sxs-lookup"><span data-stu-id="2ee9d-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="2ee9d-129">Защита сети</span><span class="sxs-lookup"><span data-stu-id="2ee9d-129">Network protection</span></span>](network-protection.md)
