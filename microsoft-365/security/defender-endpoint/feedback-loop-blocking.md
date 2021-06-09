---
title: Блокировка циклов обратной связи
description: Блокировка циклов обратной связи, также называемая быстрой защитой, является частью возможностей поведенческой блокировки и сдерживания в Microsoft Defender for Endpoint.
keywords: поведенческая блокировка, быстрая защита, блокировка отзывов, Microsoft Defender для конечной точки
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842462"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="50f83-104">Блокировка циклов обратной связи</span><span class="sxs-lookup"><span data-stu-id="50f83-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50f83-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="50f83-105">**Applies to:**</span></span>
- [<span data-ttu-id="50f83-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="50f83-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="50f83-107">Обзор</span><span class="sxs-lookup"><span data-stu-id="50f83-107">Overview</span></span>

<span data-ttu-id="50f83-108">Блокировка циклов обратной связи, также именуемая [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) быстрой защитой, является компонентом возможностей блокировки и сдерживания поведения в [Microsoft Defender для конечной точки.](/windows/security/threat-protection/)</span><span class="sxs-lookup"><span data-stu-id="50f83-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](/windows/security/threat-protection/).</span></span> <span data-ttu-id="50f83-109">При блокировке циклов обратной связи устройства в организации лучше защищены от атак.</span><span class="sxs-lookup"><span data-stu-id="50f83-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="50f83-110">Как работает блокировка циклов обратной связи</span><span class="sxs-lookup"><span data-stu-id="50f83-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="50f83-111">При обнаружении подозрительного поведения или файла, [например](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)антивирусная программа в Microsoft Defender, сведения об этом артефакте отправляются нескольким классификаторам.</span><span class="sxs-lookup"><span data-stu-id="50f83-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="50f83-112">Двигатель цикла быстрой защиты проверяет и сопоставляет информацию с другими сигналами, чтобы прийти к решению о блокировке файла.</span><span class="sxs-lookup"><span data-stu-id="50f83-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="50f83-113">Проверка и классификация артефактов происходит быстро.</span><span class="sxs-lookup"><span data-stu-id="50f83-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="50f83-114">Это приводит к быстрой блокировке подтвержденных вредоносных программ и приводит к защите всей экосистемы.</span><span class="sxs-lookup"><span data-stu-id="50f83-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="50f83-115">При быстрой защите можно остановить атаку на устройстве, других устройствах в организации и устройствах в других организациях, так как атака пытается расширить его опорную позицию.</span><span class="sxs-lookup"><span data-stu-id="50f83-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="50f83-116">Настройка блокировки циклов обратной связи</span><span class="sxs-lookup"><span data-stu-id="50f83-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="50f83-117">Если ваша организация использует Defender для конечной точки, блокировка циклов обратной связи включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50f83-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="50f83-118">Однако быстрая защита возникает благодаря сочетанию возможностей Defender для конечных точек, функций защиты машинного обучения и обмена сигналами в службах безопасности Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="50f83-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="50f83-119">Убедитесь, что включены и настроены следующие функции и возможности Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="50f83-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="50f83-120">Базовые показатели Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="50f83-120">Microsoft Defender for Endpoint baselines</span></span>](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="50f83-121">Устройства, на борту в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="50f83-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="50f83-122">EDR в режиме блокировки</span><span class="sxs-lookup"><span data-stu-id="50f83-122">EDR in block mode</span></span>](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="50f83-123">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="50f83-123">Attack surface reduction</span></span>](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="50f83-124">[Защита нового поколения](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (антивирус)</span><span class="sxs-lookup"><span data-stu-id="50f83-124">[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="50f83-125">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="50f83-125">Related articles</span></span>

- [<span data-ttu-id="50f83-126">Блокировка с учетом поведения и автономность</span><span class="sxs-lookup"><span data-stu-id="50f83-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="50f83-127">(Блог) Блокировка и сдерживание поведения: преобразование оптики в защиту</span><span class="sxs-lookup"><span data-stu-id="50f83-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="50f83-128">Полезные ресурсы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="50f83-128">Helpful Microsoft Defender for Endpoint resources</span></span>](/microsoft-365/security/defender-endpoint/helpful-resources)
