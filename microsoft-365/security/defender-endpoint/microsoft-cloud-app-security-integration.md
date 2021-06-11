---
title: Обзор интеграции Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender для конечной точки интегрируется с Cloud App Security путем переададки всех действий в сети облачных приложений.
keywords: облако, приложение, сеть, видимость, использование
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844746"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="8c13d-104">Microsoft Cloud App Security в обзоре Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8c13d-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8c13d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8c13d-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c13d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8c13d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c13d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c13d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="8c13d-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8c13d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c13d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8c13d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8c13d-110">Microsoft Cloud App Security (Cloud App Security) — это комплексное решение, которое обеспечивает видимость облачных приложений и служб, позволяя контролировать и ограничивать доступ к облачным приложениям, при этом соблюдая требования соответствия требованиям к данным, хранимым в облаке.</span><span class="sxs-lookup"><span data-stu-id="8c13d-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="8c13d-111">Дополнительные сведения см. [в Cloud App Security.](/cloud-app-security/what-is-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="8c13d-111">For more information, see [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="8c13d-112">Эта функция доступна с лицензией E5 для Enterprise Mobility + Security [устройств,](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) работающих Windows 10 версии 1809 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8c13d-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="8c13d-113">Microsoft Defender для конечной точки и Cloud App Security интеграции</span><span class="sxs-lookup"><span data-stu-id="8c13d-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="8c13d-114">Cloud App Security зависит от журналов облачного трафика, которые перенаправлются в него с корпоративных брандмауэров и прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="8c13d-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="8c13d-115">Microsoft Defender для конечной точки интегрируется с Cloud App Security, собирая и переадребуя все действия сети облачных приложений, обеспечивая беспрецедентную видимость для использования облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="8c13d-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="8c13d-116">Функция мониторинга встроена в устройство, обеспечивая полное освещение сетевой активности.</span><span class="sxs-lookup"><span data-stu-id="8c13d-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="8c13d-117">Интеграция обеспечивает следующие основные улучшения существующего Cloud App Security обнаружения:</span><span class="sxs-lookup"><span data-stu-id="8c13d-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="8c13d-118">Доступно везде . Так как сетевое действие собирается непосредственно из конечной точки, оно доступно везде, где устройство находится, в корпоративной сети или отключено, так как это больше не зависит от трафика, переназначенного через корпоративный брандмауэр или прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="8c13d-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="8c13d-119">Работает вне коробки, конфигурация не требуется - перенакладка журналов облачного трафика в Cloud App Security требует конфигурации брандмауэра и прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="8c13d-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="8c13d-120">При интеграции Defender для Cloud App Security и конечной точки конфигурация не требуется.</span><span class="sxs-lookup"><span data-stu-id="8c13d-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="8c13d-121">Просто включи его в Центр безопасности в Microsoft Defender параметры, и вы хорошо идти.</span><span class="sxs-lookup"><span data-stu-id="8c13d-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="8c13d-122">Контекст устройства — в журналах облачного трафика отсутствует контекст устройства.</span><span class="sxs-lookup"><span data-stu-id="8c13d-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="8c13d-123">Защитник для сетевой активности Endpoint сообщается в контексте устройства (какое устройство было доступно облачному приложению), поэтому вы можете точно понять, где (устройство) проходило сетевое действие, помимо того, кто (пользователь) выполнял его.</span><span class="sxs-lookup"><span data-stu-id="8c13d-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="8c13d-124">Дополнительные сведения об обнаружении облачных данных см. в [ссылке Работа с обнаруженными приложениями.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="8c13d-124">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="8c13d-125">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="8c13d-125">Related topic</span></span>

- [<span data-ttu-id="8c13d-126">Настройка интеграции Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8c13d-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
