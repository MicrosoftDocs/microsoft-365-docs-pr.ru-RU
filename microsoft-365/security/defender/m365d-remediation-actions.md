---
title: Действия по исправлению в Microsoft 365 Defender
description: Получите обзор действий по исправлению, которые следуют автоматическим расследованиям в Microsoft 365 Defender
keywords: автоматизированный, анализ, оповещение, триггер, действие, исправление
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 31162944f4728f2c84efbe2cd5eafbd0c70e00f6
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245856"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="9bf63-104">Действия по исправлению в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bf63-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9bf63-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9bf63-105">**Applies to:**</span></span>
- <span data-ttu-id="9bf63-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bf63-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="9bf63-107">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="9bf63-107">Remediation actions</span></span>

<span data-ttu-id="9bf63-108">Во время и после автоматического расследования в Microsoft 365 Defender выявляются действия по исправлению вредоносных или подозрительных элементов.</span><span class="sxs-lookup"><span data-stu-id="9bf63-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="9bf63-109">На устройствах принимаются некоторые действия по исправлению, которые также называют конечными точками.</span><span class="sxs-lookup"><span data-stu-id="9bf63-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="9bf63-110">Другие действия по исправлению принимаются в отношении контента электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9bf63-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="9bf63-111">Автоматические расследования завершались после выполнения действий по исправлению, утверждения или отказа.</span><span class="sxs-lookup"><span data-stu-id="9bf63-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bf63-112">Независимо от того, принимаются ли действия по исправлению автоматически или только после утверждения, зависит от определенных параметров, например от уровня автоматизации.</span><span class="sxs-lookup"><span data-stu-id="9bf63-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="9bf63-113">Дополнительные статьи см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="9bf63-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="9bf63-114">Настройка возможностей автоматического расследования и ответа в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bf63-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="9bf63-115">Устранение угроз на устройствах</span><span class="sxs-lookup"><span data-stu-id="9bf63-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="9bf63-116">Угрозы и действия по исправлению в контенте совместной & электронной почты</span><span class="sxs-lookup"><span data-stu-id="9bf63-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="9bf63-117">В следующей таблице подводятся итоги действий по исправлению, которые в настоящее время поддерживаются в Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="9bf63-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="9bf63-118">Действия по исправлению устройства (конечной точки)</span><span class="sxs-lookup"><span data-stu-id="9bf63-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="9bf63-119">Действия по исправления для электронной почты</span><span class="sxs-lookup"><span data-stu-id="9bf63-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="9bf63-120">- Сбор пакета расследований</span><span class="sxs-lookup"><span data-stu-id="9bf63-120">- Collect investigation package</span></span> <br/><span data-ttu-id="9bf63-121">- Изолировать устройство (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="9bf63-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="9bf63-122">- Offboard machine</span><span class="sxs-lookup"><span data-stu-id="9bf63-122">- Offboard machine</span></span> <br/><span data-ttu-id="9bf63-123">- Выполнение кода выпуска</span><span class="sxs-lookup"><span data-stu-id="9bf63-123">- Release code execution</span></span> <br/><span data-ttu-id="9bf63-124">- Освобождение от карантина</span><span class="sxs-lookup"><span data-stu-id="9bf63-124">- Release from quarantine</span></span> <br/><span data-ttu-id="9bf63-125">- Пример запроса</span><span class="sxs-lookup"><span data-stu-id="9bf63-125">- Request sample</span></span> <br/><span data-ttu-id="9bf63-126">- Ограничение выполнения кода (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="9bf63-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="9bf63-127">- Запуск антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="9bf63-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="9bf63-128">- Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="9bf63-128">- Stop and quarantine</span></span>      |<span data-ttu-id="9bf63-129">- Блокировка URL-адреса (время щелчка мыши)</span><span class="sxs-lookup"><span data-stu-id="9bf63-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="9bf63-130">- Мягкое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="9bf63-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="9bf63-131">- Электронная почта карантина</span><span class="sxs-lookup"><span data-stu-id="9bf63-131">- Quarantine email</span></span><br/><span data-ttu-id="9bf63-132">- Карантин вложения электронной почты</span><span class="sxs-lookup"><span data-stu-id="9bf63-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="9bf63-133">- Отключение внешней пересылаемой почты</span><span class="sxs-lookup"><span data-stu-id="9bf63-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="9bf63-134">Действия по исправлению, ожидающих утверждения или уже завершенных, можно просмотреть в [Центре действий.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="9bf63-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="9bf63-135">Действия по исправлению, которые следуют автоматическим расследованиям</span><span class="sxs-lookup"><span data-stu-id="9bf63-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="9bf63-136">По завершению автоматического расследования выносим вердикт по каждому доказательству.</span><span class="sxs-lookup"><span data-stu-id="9bf63-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="9bf63-137">В зависимости от вердикта выявляются действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="9bf63-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="9bf63-138">В некоторых случаях действия по исправлению выполняются автоматически. В других случаях действия по исправлению ожидают утверждения.</span><span class="sxs-lookup"><span data-stu-id="9bf63-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="9bf63-139">Все зависит от настройки [автоматического расследования](m365d-configure-auto-investigation-response.md)и ответа.</span><span class="sxs-lookup"><span data-stu-id="9bf63-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="9bf63-140">В таблице ниже перечислены возможные заключения и результаты.</span><span class="sxs-lookup"><span data-stu-id="9bf63-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="9bf63-141">Заключение</span><span class="sxs-lookup"><span data-stu-id="9bf63-141">Verdict</span></span>    | <span data-ttu-id="9bf63-142">Область</span><span class="sxs-lookup"><span data-stu-id="9bf63-142">Area</span></span>    | <span data-ttu-id="9bf63-143">Результаты</span><span class="sxs-lookup"><span data-stu-id="9bf63-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="9bf63-144">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="9bf63-144">Malicious</span></span>    | <span data-ttu-id="9bf63-145">Устройства (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="9bf63-145">Devices (endpoints)</span></span>    | <span data-ttu-id="9bf63-146">Действия по исправлению принимаются автоматически (при [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) условии, что группы устройств вашей организации настроены на **полное устранение** угроз автоматически)</span><span class="sxs-lookup"><span data-stu-id="9bf63-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="9bf63-147">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="9bf63-147">Malicious</span></span>    | <span data-ttu-id="9bf63-148">Содержимое электронной почты (URL-адреса или вложения)</span><span class="sxs-lookup"><span data-stu-id="9bf63-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="9bf63-149">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="9bf63-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="9bf63-150">Подозрительные</span><span class="sxs-lookup"><span data-stu-id="9bf63-150">Suspicious</span></span>    | <span data-ttu-id="9bf63-151">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="9bf63-151">Devices or email content</span></span> | <span data-ttu-id="9bf63-152">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="9bf63-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="9bf63-153">Угрозы не найдены</span><span class="sxs-lookup"><span data-stu-id="9bf63-153">No threats found</span></span>    | <span data-ttu-id="9bf63-154">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="9bf63-154">Devices or email content</span></span>    | <span data-ttu-id="9bf63-155">Действия по исправлению не требуются</span><span class="sxs-lookup"><span data-stu-id="9bf63-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="9bf63-156">Действия по исправлению, которые принимаются вручную</span><span class="sxs-lookup"><span data-stu-id="9bf63-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="9bf63-157">Помимо действий по исправлению последствий, которые следуют автоматическим расследованиям, группа операций безопасности может выполнять определенные действия по исправлению вручную.</span><span class="sxs-lookup"><span data-stu-id="9bf63-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="9bf63-158">К ним относятся следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9bf63-158">These include the following actions:</span></span>

- <span data-ttu-id="9bf63-159">Действие ручного устройства, например изоляция устройства или карантин файлов.</span><span class="sxs-lookup"><span data-stu-id="9bf63-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="9bf63-160">Ручное действие электронной почты, например мягкое удаление сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9bf63-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="9bf63-161">[Расширенные действия по охоте](../defender-endpoint/advanced-hunting-overview.md) на устройствах или электронной почте.</span><span class="sxs-lookup"><span data-stu-id="9bf63-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="9bf63-162">[Действие обозревателя](../office-365-security/threat-explorer.md) по контенту электронной почты, например перенос электронной почты на нежелательное, электронное письмо с мягким удалением или жесткое удаление электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9bf63-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="9bf63-163">Действие [живого ответа](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) вручную, например удаление файла, остановка процесса и удаление запланированной задачи.</span><span class="sxs-lookup"><span data-stu-id="9bf63-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="9bf63-164">Live response action with [Microsoft Defender for Endpoint API](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span><span class="sxs-lookup"><span data-stu-id="9bf63-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="9bf63-165">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="9bf63-165">Next steps</span></span>

- [<span data-ttu-id="9bf63-166">Посещение Центра уведомлений</span><span class="sxs-lookup"><span data-stu-id="9bf63-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="9bf63-167">Просмотр и управление действиями по исправлению</span><span class="sxs-lookup"><span data-stu-id="9bf63-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="9bf63-168">Обработка ложных срабатыва-</span><span class="sxs-lookup"><span data-stu-id="9bf63-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
