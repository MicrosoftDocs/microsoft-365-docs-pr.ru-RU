---
title: Действия по исправлению, выполняемые после автоматического исследования в защите от угроз Майкрософт
description: Обзор действий по исправлению, которые следуют за автоматизированным расследованиям в защите от угроз Майкрософт
keywords: автоматизированный, анализ, оповещение, триггер, действие, исправление
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 232d19cb0bcb6a2f91c1bdad15d842ec7396499c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201055"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="85c36-104">Действия по исправлению, выполняемые после автоматического исследования в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="85c36-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="85c36-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="85c36-105">**Applies to:**</span></span>
- <span data-ttu-id="85c36-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="85c36-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="85c36-107">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="85c36-107">Remediation actions</span></span>

<span data-ttu-id="85c36-108">Во время и после автоматического исследования в защите от угроз Майкрософт действия по исправлению идентифицируются для вредоносных или подозрительных элементов.</span><span class="sxs-lookup"><span data-stu-id="85c36-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="85c36-109">Некоторые виды действий по исправлению выполняются на устройствах, которые также называются конечными точками.</span><span class="sxs-lookup"><span data-stu-id="85c36-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="85c36-110">Для содержимого электронной почты применяются другие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="85c36-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="85c36-111">Автоматическое расследование завершено после принятия, утверждения или отклонения действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="85c36-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="85c36-112">В следующей таблице приведены действия по исправлению, которые в настоящее время поддерживаются в Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="85c36-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="85c36-113">Действия по исправлению устройства (конечная точка)</span><span class="sxs-lookup"><span data-stu-id="85c36-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="85c36-114">Действия по исправления для электронной почты</span><span class="sxs-lookup"><span data-stu-id="85c36-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="85c36-115">— Собрать пакет для расследования</span><span class="sxs-lookup"><span data-stu-id="85c36-115">- Collect investigation package</span></span> <br/><span data-ttu-id="85c36-116">-Изолировать устройство (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="85c36-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="85c36-117">— Переносе Machine</span><span class="sxs-lookup"><span data-stu-id="85c36-117">- Offboard machine</span></span> <br/><span data-ttu-id="85c36-118">— Запуск кода в выпуске</span><span class="sxs-lookup"><span data-stu-id="85c36-118">- Release code execution</span></span> <br/><span data-ttu-id="85c36-119">— Выпуск из карантина</span><span class="sxs-lookup"><span data-stu-id="85c36-119">- Release from quarantine</span></span> <br/><span data-ttu-id="85c36-120">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="85c36-120">- Request sample</span></span> <br/><span data-ttu-id="85c36-121">— Ограничить выполнение кода (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="85c36-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="85c36-122">— Запуск антивирусной проверки</span><span class="sxs-lookup"><span data-stu-id="85c36-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="85c36-123">— Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="85c36-123">- Stop and quarantine</span></span>      |<span data-ttu-id="85c36-124">-URL-адрес блока (время нажатия)</span><span class="sxs-lookup"><span data-stu-id="85c36-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="85c36-125">— Обратимое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="85c36-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="85c36-126">— Электронная почта на карантине</span><span class="sxs-lookup"><span data-stu-id="85c36-126">- Quarantine email</span></span><br/><span data-ttu-id="85c36-127">— Вложение вложения электронной почты в карантин</span><span class="sxs-lookup"><span data-stu-id="85c36-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="85c36-128">– Отключить функцию пересылки для внешней почты</span><span class="sxs-lookup"><span data-stu-id="85c36-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="85c36-129">Действия по исправлению, которые ожидают утверждения или уже завершены, можно просмотреть в [центре уведомлений](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="85c36-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="85c36-130">Действия по исправлению следуют при автоматическом расследовании</span><span class="sxs-lookup"><span data-stu-id="85c36-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="85c36-131">При завершении автоматизированного исследования достигается вредоносности для всех участвующих в них доказательств.</span><span class="sxs-lookup"><span data-stu-id="85c36-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="85c36-132">В зависимости от вредоносности выполняется идентификация действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="85c36-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="85c36-133">В некоторых случаях действия по исправлению выполняются автоматически. В других случаях действия по исправлению ожидают утверждения.</span><span class="sxs-lookup"><span data-stu-id="85c36-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="85c36-134">Все зависит от того, как [настроено автоматическое исследование и отклик](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="85c36-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="85c36-135">В таблице ниже перечислены возможные заключения и результаты.</span><span class="sxs-lookup"><span data-stu-id="85c36-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="85c36-136">Заключение</span><span class="sxs-lookup"><span data-stu-id="85c36-136">Verdict</span></span>    |<span data-ttu-id="85c36-137">Область</span><span class="sxs-lookup"><span data-stu-id="85c36-137">Area</span></span>    |<span data-ttu-id="85c36-138">Результаты</span><span class="sxs-lookup"><span data-stu-id="85c36-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="85c36-139">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="85c36-139">Malicious</span></span>    |<span data-ttu-id="85c36-140">Устройства (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="85c36-140">Devices (endpoints)</span></span>    |<span data-ttu-id="85c36-141">Действия по исправлению берутся автоматически (предполагается, что для [групп устройств](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) вашей организации настроено **Автоматическое исправление угроз**).</span><span class="sxs-lookup"><span data-stu-id="85c36-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="85c36-142">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="85c36-142">Malicious</span></span>    |<span data-ttu-id="85c36-143">Содержимое электронной почты (URL-адреса или вложения)</span><span class="sxs-lookup"><span data-stu-id="85c36-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="85c36-144">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="85c36-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="85c36-145">Подозрительные</span><span class="sxs-lookup"><span data-stu-id="85c36-145">Suspicious</span></span>    |<span data-ttu-id="85c36-146">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="85c36-146">Devices or email content</span></span> |<span data-ttu-id="85c36-147">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="85c36-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="85c36-148">Угрозы не найдены</span><span class="sxs-lookup"><span data-stu-id="85c36-148">No threats found</span></span>    |<span data-ttu-id="85c36-149">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="85c36-149">Devices or email content</span></span>    |<span data-ttu-id="85c36-150">Действия по исправлению не требуются</span><span class="sxs-lookup"><span data-stu-id="85c36-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="85c36-151">Указывает, будут ли действия по исправлению выполняться автоматически или только при утверждении, зависит от определенных параметров, таких как политики групп устройств Организации.</span><span class="sxs-lookup"><span data-stu-id="85c36-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="85c36-152">Чтобы узнать больше, ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="85c36-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="85c36-153">Настройка автоматизированного расследования и возможностей реагирования в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="85c36-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="85c36-154">Способы исправления угроз на устройствах</span><span class="sxs-lookup"><span data-stu-id="85c36-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="85c36-155">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="85c36-155">Next steps</span></span>

- [<span data-ttu-id="85c36-156">Посещение Центра уведомлений</span><span class="sxs-lookup"><span data-stu-id="85c36-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="85c36-157">Утверждение или отклонение ожидающих выполнения действий</span><span class="sxs-lookup"><span data-stu-id="85c36-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="85c36-158">Обработка ложных срабатываний/отрицательных результатов в автоматизированном расследовании и возможностях реагирования</span><span class="sxs-lookup"><span data-stu-id="85c36-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
