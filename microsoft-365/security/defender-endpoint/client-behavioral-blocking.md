---
title: Блокировка поведения клиента
description: Блокировка поведения клиента является частью возможностей блокировки и сдерживания поведения в ATP Microsoft Defender
keywords: поведенческая блокировка, быстрая защита, поведение клиентов, ATP Защитника Майкрософт
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
ms.openlocfilehash: c37a1180f9def51daa4229418b05abe7cf787aa3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165265"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="02eda-104">Блокировка поведения клиента</span><span class="sxs-lookup"><span data-stu-id="02eda-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02eda-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="02eda-105">**Applies to:**</span></span>
- [<span data-ttu-id="02eda-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="02eda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02eda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02eda-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="02eda-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="02eda-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="02eda-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="02eda-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="02eda-110">Обзор</span><span class="sxs-lookup"><span data-stu-id="02eda-110">Overview</span></span>

<span data-ttu-id="02eda-111">Клиентская поведенческая блокировка является компонентом [возможностей](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) блокировки и сдерживания поведения в Защитнике для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="02eda-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="02eda-112">Поскольку подозрительные действия обнаруживаются на устройствах (также именуются клиентами или конечными точками), артефакты (например, файлы или приложения) блокируются, проверяются и устраняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="02eda-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Облачная и клиентская защита":::

<span data-ttu-id="02eda-114">Защита от антивирусов лучше всего работает в паре с облачной защитой.</span><span class="sxs-lookup"><span data-stu-id="02eda-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="02eda-115">Как работает блокировка поведения клиента</span><span class="sxs-lookup"><span data-stu-id="02eda-115">How client behavioral blocking works</span></span>

<span data-ttu-id="02eda-116">[Антивирус Microsoft Defender может](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) обнаруживать подозрительные действия, вредоносный код, атаки без файлов и в памяти и другие действия на устройстве.</span><span class="sxs-lookup"><span data-stu-id="02eda-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="02eda-117">При обнаружении подозрительных поведений антивирус Microsoft Defender отслеживает и отправляет эти подозрительные действия и деревья процессов в службу защиты облаков.</span><span class="sxs-lookup"><span data-stu-id="02eda-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="02eda-118">Машинное обучение различает вредоносные приложения и хорошее поведение в миллисекунд и классифицирует каждый артефакт.</span><span class="sxs-lookup"><span data-stu-id="02eda-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="02eda-119">Почти в режиме реального времени, как только артефакт будет обнаружен вредоносным, он блокируется на устройстве.</span><span class="sxs-lookup"><span data-stu-id="02eda-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="02eda-120">При обнаружении подозрительного [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) поведения создается оповещение, которое отображается в Центре безопасности Защитника Майкрософт ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="02eda-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="02eda-121">Клиентская поведенческая блокировка эффективна, так как она не только помогает предотвратить начало атаки, но и помогает остановить приступив к выполнению.</span><span class="sxs-lookup"><span data-stu-id="02eda-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="02eda-122">Кроме того, при блокировке [циклов](feedback-loop-blocking.md) обратной связи (еще одна возможность блокировки и сдерживания поведения) атаки предотвращаются на других устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="02eda-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="02eda-123">Обнаружение на основе поведения</span><span class="sxs-lookup"><span data-stu-id="02eda-123">Behavior-based detections</span></span>

<span data-ttu-id="02eda-124">Обнаружения на основе поведения называются в соответствии с [матрицей ATT MITRE&CK для предприятия](https://attack.mitre.org/matrices/enterprise).</span><span class="sxs-lookup"><span data-stu-id="02eda-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="02eda-125">Конвенция именования помогает определить стадию атаки, на которой было отмечено вредоносное поведение:</span><span class="sxs-lookup"><span data-stu-id="02eda-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="02eda-126">Tactic</span><span class="sxs-lookup"><span data-stu-id="02eda-126">Tactic</span></span> |   <span data-ttu-id="02eda-127">Имя угрозы обнаружения</span><span class="sxs-lookup"><span data-stu-id="02eda-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="02eda-128">Начальный доступ</span><span class="sxs-lookup"><span data-stu-id="02eda-128">Initial Access</span></span> | <span data-ttu-id="02eda-129">Поведение:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="02eda-130">Выполнение</span><span class="sxs-lookup"><span data-stu-id="02eda-130">Execution</span></span>  | <span data-ttu-id="02eda-131">Поведение:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="02eda-132">Упорство</span><span class="sxs-lookup"><span data-stu-id="02eda-132">Persistence</span></span>    | <span data-ttu-id="02eda-133">Поведение:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="02eda-134">Эскалация привилегий</span><span class="sxs-lookup"><span data-stu-id="02eda-134">Privilege Escalation</span></span>   | <span data-ttu-id="02eda-135">Поведение:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="02eda-136">Уклонение от защиты</span><span class="sxs-lookup"><span data-stu-id="02eda-136">Defense Evasion</span></span>    | <span data-ttu-id="02eda-137">Поведение:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="02eda-138">Доступ к учетным данным</span><span class="sxs-lookup"><span data-stu-id="02eda-138">Credential Access</span></span>  | <span data-ttu-id="02eda-139">Поведение:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="02eda-140">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="02eda-140">Discovery</span></span>  | <span data-ttu-id="02eda-141">Поведение:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="02eda-142">Lateral Movement</span><span class="sxs-lookup"><span data-stu-id="02eda-142">Lateral Movement</span></span> | <span data-ttu-id="02eda-143">Поведение:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="02eda-144">Collection</span><span class="sxs-lookup"><span data-stu-id="02eda-144">Collection</span></span> |   <span data-ttu-id="02eda-145">Поведение:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="02eda-146">Команда и управление</span><span class="sxs-lookup"><span data-stu-id="02eda-146">Command and Control</span></span> | <span data-ttu-id="02eda-147">Поведение:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="02eda-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="02eda-148">Exfiltration</span></span>   | <span data-ttu-id="02eda-149">Поведение:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="02eda-150">Влияние</span><span class="sxs-lookup"><span data-stu-id="02eda-150">Impact</span></span> | <span data-ttu-id="02eda-151">Поведение:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="02eda-152">Uncategorized</span><span class="sxs-lookup"><span data-stu-id="02eda-152">Uncategorized</span></span>  | <span data-ttu-id="02eda-153">Поведение:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="02eda-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="02eda-154">Дополнительные данные о конкретных угрозах см. в недавней **[глобальной активности угроз.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="02eda-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="02eda-155">Настройка клиентской поведенческой блокировки</span><span class="sxs-lookup"><span data-stu-id="02eda-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="02eda-156">Если ваша организация использует Defender для конечной точки, клиентская поведенческая блокировка включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="02eda-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="02eda-157">Однако, чтобы воспользоваться всеми возможностями Defender для [](behavioral-blocking-containment.md)конечной точки, включая поведенческую блокировку и сдерживание, убедитесь, что включены и настроены следующие функции и возможности Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="02eda-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="02eda-158">Базовые показатели Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="02eda-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="02eda-159">Устройства, на борту для Защитника для конечной точки</span><span class="sxs-lookup"><span data-stu-id="02eda-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="02eda-160">EDR в режиме блокировки</span><span class="sxs-lookup"><span data-stu-id="02eda-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="02eda-161">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="02eda-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="02eda-162">[Защита нового поколения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (антивирус)</span><span class="sxs-lookup"><span data-stu-id="02eda-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="02eda-163">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="02eda-163">Related articles</span></span>

- [<span data-ttu-id="02eda-164">Блокировка и сдерживание поведения</span><span class="sxs-lookup"><span data-stu-id="02eda-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="02eda-165">Блокировка циклов обратной связи</span><span class="sxs-lookup"><span data-stu-id="02eda-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="02eda-166">(Блог) Блокировка и сдерживание поведения: преобразование оптики в защиту</span><span class="sxs-lookup"><span data-stu-id="02eda-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="02eda-167">Полезные ресурсы Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="02eda-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
