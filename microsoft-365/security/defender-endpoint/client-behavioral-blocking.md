---
title: Блокировка с учетом поведения клиента
description: Блокировка поведения клиента является частью возможностей поведенческой блокировки и сдерживания в Microsoft Defender for Endpoint
keywords: поведенческая блокировка, быстрая защита, поведение клиента, Microsoft Defender для endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795962"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="1b299-104">Блокировка с учетом поведения клиента</span><span class="sxs-lookup"><span data-stu-id="1b299-104">Client behavioral blocking</span></span>

<span data-ttu-id="1b299-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1b299-105">**Applies to:**</span></span>
- [<span data-ttu-id="1b299-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1b299-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1b299-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b299-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1b299-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1b299-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1b299-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1b299-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="1b299-110">Обзор</span><span class="sxs-lookup"><span data-stu-id="1b299-110">Overview</span></span>

<span data-ttu-id="1b299-111">Клиентская поведенческая блокировка является компонентом [возможностей](behavioral-blocking-containment.md) блокировки и сдерживания поведения в Защитнике для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1b299-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="1b299-112">Поскольку подозрительные действия обнаруживаются на устройствах (также именуются клиентами или конечными точками), артефакты (например, файлы или приложения) блокируются, проверяются и устраняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="1b299-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Облачная и клиентская защита":::

<span data-ttu-id="1b299-114">Защита от антивирусов лучше всего работает в паре с облачной защитой.</span><span class="sxs-lookup"><span data-stu-id="1b299-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="1b299-115">Как работает блокировка поведения клиента</span><span class="sxs-lookup"><span data-stu-id="1b299-115">How client behavioral blocking works</span></span>

<span data-ttu-id="1b299-116">[антивирусная программа в Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) может обнаруживать подозрительные действия, вредоносный код, атаки без файлов и в памяти и другие действия на устройстве.</span><span class="sxs-lookup"><span data-stu-id="1b299-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="1b299-117">При обнаружении подозрительного поведения антивирусная программа в Microsoft Defender отслеживает и отправляет эти подозрительные действия и деревья процессов в службу защиты облаков.</span><span class="sxs-lookup"><span data-stu-id="1b299-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="1b299-118">Машинное обучение различает вредоносные приложения и хорошее поведение в миллисекунд и классифицирует каждый артефакт.</span><span class="sxs-lookup"><span data-stu-id="1b299-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="1b299-119">Почти в режиме реального времени, как только артефакт будет обнаружен вредоносным, он блокируется на устройстве.</span><span class="sxs-lookup"><span data-stu-id="1b299-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="1b299-120">При обнаружении подозрительного [](alerts-queue.md) поведения создается оповещение, которое отображается в Центр безопасности в Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="1b299-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="1b299-121">Клиентская поведенческая блокировка эффективна, так как она не только помогает предотвратить начало атаки, но и помогает остановить приступив к выполнению.</span><span class="sxs-lookup"><span data-stu-id="1b299-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="1b299-122">Кроме того, при блокировке [циклов](feedback-loop-blocking.md) обратной связи (еще одна возможность блокировки и сдерживания поведения) атаки предотвращаются на других устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="1b299-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="1b299-123">Обнаружение на основе поведения</span><span class="sxs-lookup"><span data-stu-id="1b299-123">Behavior-based detections</span></span>

<span data-ttu-id="1b299-124">Обнаружения на основе поведения называются в соответствии с [матрицей ATT MITRE&CK для](https://attack.mitre.org/matrices/enterprise)Enterprise .</span><span class="sxs-lookup"><span data-stu-id="1b299-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="1b299-125">Конвенция именования помогает определить стадию атаки, на которой было отмечено вредоносное поведение:</span><span class="sxs-lookup"><span data-stu-id="1b299-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="1b299-126">Tactic</span><span class="sxs-lookup"><span data-stu-id="1b299-126">Tactic</span></span> |   <span data-ttu-id="1b299-127">Имя угрозы обнаружения</span><span class="sxs-lookup"><span data-stu-id="1b299-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="1b299-128">Начальный доступ</span><span class="sxs-lookup"><span data-stu-id="1b299-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="1b299-129">Выполнение</span><span class="sxs-lookup"><span data-stu-id="1b299-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="1b299-130">Упорство</span><span class="sxs-lookup"><span data-stu-id="1b299-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="1b299-131">Эскалация привилегий</span><span class="sxs-lookup"><span data-stu-id="1b299-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="1b299-132">Уклонение от защиты</span><span class="sxs-lookup"><span data-stu-id="1b299-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="1b299-133">Доступ к учетным данным</span><span class="sxs-lookup"><span data-stu-id="1b299-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="1b299-134">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="1b299-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="1b299-135">Lateral Movement</span><span class="sxs-lookup"><span data-stu-id="1b299-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="1b299-136">Collection</span><span class="sxs-lookup"><span data-stu-id="1b299-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="1b299-137">Команда и управление</span><span class="sxs-lookup"><span data-stu-id="1b299-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="1b299-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="1b299-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="1b299-139">Влияние</span><span class="sxs-lookup"><span data-stu-id="1b299-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="1b299-140">Uncategorized</span><span class="sxs-lookup"><span data-stu-id="1b299-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="1b299-141">Дополнительные данные о конкретных угрозах см. в недавней **[глобальной активности угроз.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="1b299-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="1b299-142">Настройка клиентской поведенческой блокировки</span><span class="sxs-lookup"><span data-stu-id="1b299-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="1b299-143">Если ваша организация использует Defender для конечной точки, клиентская поведенческая блокировка включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1b299-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="1b299-144">Однако, чтобы воспользоваться всеми возможностями Defender для [](behavioral-blocking-containment.md)конечной точки, включая поведенческую блокировку и сдерживание, убедитесь, что включены и настроены следующие функции и возможности Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="1b299-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="1b299-145">Базовые показатели Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1b299-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="1b299-146">Устройства, на борту для Защитника для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1b299-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="1b299-147">EDR в режиме блокировки</span><span class="sxs-lookup"><span data-stu-id="1b299-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="1b299-148">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="1b299-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="1b299-149">[Защита нового поколения](configure-microsoft-defender-antivirus-features.md) (антивирусные, антивирусные и другие возможности защиты от угроз)</span><span class="sxs-lookup"><span data-stu-id="1b299-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

