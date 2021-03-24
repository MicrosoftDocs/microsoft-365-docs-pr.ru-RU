---
title: Устранение неполадок с производительностью atP Microsoft Defender для Mac
description: Устранение неполадок с производительностью в ATP Microsoft Defender для Mac.
keywords: Microsoft, defender, atp, mac, performance
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070261"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="fd3a0-104">Устранение неполадок с производительностью для Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="fd3a0-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fd3a0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-105">**Applies to:**</span></span>

- [<span data-ttu-id="fd3a0-106">Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="fd3a0-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="fd3a0-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd3a0-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="fd3a0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd3a0-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fd3a0-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="fd3a0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fd3a0-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="fd3a0-111">В этом разделе приводится ряд общих действий, которые можно использовать для сужение проблем производительности, связанных с Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="fd3a0-112">Защита в режиме реального времени (RTP) — это функция Microsoft Defender для конечной точки для Mac, которая непрерывно отслеживает и защищает устройство от угроз.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="fd3a0-113">Он состоит из мониторинга файлов и процессов и других процессов.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="fd3a0-114">В зависимости от запущенных приложений и характеристик устройства вы можете испытывать неоптимальную производительность при запуске Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="fd3a0-115">В частности, приложения или системные процессы, которые имеют доступ к многим ресурсам в течение короткого времени, могут привести к проблеме производительности в Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="fd3a0-116">Для устранения неполадок и устранения этих проблем можно использовать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fd3a0-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="fd3a0-117">Отключать защиту в режиме реального времени с помощью одного из следующих методов и наблюдать, повышается ли производительность.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="fd3a0-118">Этот подход помогает сузить, вносит ли Microsoft Defender для Конечной точки для Mac вклад в проблемы производительности.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="fd3a0-119">Если устройство не управляется организацией, защита в режиме реального времени может быть отключена с помощью одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="fd3a0-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="fd3a0-120">Из пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-120">From the user interface.</span></span> <span data-ttu-id="fd3a0-121">Откройте Microsoft Defender для конечной точки для Mac и перейдите к **управлению настройками.**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![Управление скриншотом защиты в режиме реального времени](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="fd3a0-123">Из терминала.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-123">From the Terminal.</span></span> <span data-ttu-id="fd3a0-124">В целях безопасности эта операция требует высоты.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="fd3a0-125">Если устройство управляется организацией, защита в режиме реального времени может быть отключена администратором с помощью инструкций в наборе предпочтений [для Microsoft Defender для конечной](mac-preferences.md)точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="fd3a0-126">Откройте finder и перейдите **к**  >  **утилитам приложений**.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="fd3a0-127">Откройте **монитор активности** и проанализируйте, какие приложения используют ресурсы в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="fd3a0-128">Типичные примеры включают обновление программного обеспечения и компиляторы.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="fd3a0-129">Настройка Microsoft Defender для конечной точки для Mac с исключениями для процессов или расположения дисков, которые способствуют повышению производительности и повторной защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="fd3a0-130">Сведения см. в материале Настройка и проверка [исключений для Microsoft Defender для конечной точки для Mac.](mac-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="fd3a0-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
