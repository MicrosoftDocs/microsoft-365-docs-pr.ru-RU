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
ms.openlocfilehash: f025f23242c28f698e6f67755cc59d21c4463914
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782949"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="329a5-104">Действия по исправлению в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="329a5-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="329a5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="329a5-105">**Applies to:**</span></span>
- <span data-ttu-id="329a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="329a5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="329a5-107">Во время и после автоматического расследования в Microsoft 365 Defender выявляются действия по исправлению вредоносных или подозрительных элементов.</span><span class="sxs-lookup"><span data-stu-id="329a5-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="329a5-108">На устройствах принимаются некоторые действия по исправлению, которые также называют конечными точками.</span><span class="sxs-lookup"><span data-stu-id="329a5-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="329a5-109">Другие действия по исправлению принимаются в отношении контента электронной почты.</span><span class="sxs-lookup"><span data-stu-id="329a5-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="329a5-110">Автоматические расследования завершались после выполнения действий по исправлению, утверждения или отказа.</span><span class="sxs-lookup"><span data-stu-id="329a5-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="329a5-111">Независимо от того, принимаются ли действия по исправлению автоматически или только после утверждения, зависит от определенных параметров, например от уровня автоматизации.</span><span class="sxs-lookup"><span data-stu-id="329a5-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="329a5-112">Дополнительные статьи см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="329a5-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="329a5-113">Настройка возможностей автоматического расследования и ответа в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="329a5-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="329a5-114">Устранение угроз на устройствах</span><span class="sxs-lookup"><span data-stu-id="329a5-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="329a5-115">Угрозы и действия по исправлению в контенте совместной & электронной почты</span><span class="sxs-lookup"><span data-stu-id="329a5-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="329a5-116">В следующей таблице подводятся итоги действий по исправлению, которые в настоящее время поддерживаются в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="329a5-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="329a5-117">Действия по исправлению устройства (конечной точки)</span><span class="sxs-lookup"><span data-stu-id="329a5-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="329a5-118">Действия по исправления для электронной почты</span><span class="sxs-lookup"><span data-stu-id="329a5-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="329a5-119">- Сбор пакета расследований</span><span class="sxs-lookup"><span data-stu-id="329a5-119">- Collect investigation package</span></span> <br/><span data-ttu-id="329a5-120">- Изолировать устройство (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="329a5-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="329a5-121">- Offboard machine</span><span class="sxs-lookup"><span data-stu-id="329a5-121">- Offboard machine</span></span> <br/><span data-ttu-id="329a5-122">- Выполнение кода выпуска</span><span class="sxs-lookup"><span data-stu-id="329a5-122">- Release code execution</span></span> <br/><span data-ttu-id="329a5-123">- Освобождение от карантина</span><span class="sxs-lookup"><span data-stu-id="329a5-123">- Release from quarantine</span></span> <br/><span data-ttu-id="329a5-124">- Пример запроса</span><span class="sxs-lookup"><span data-stu-id="329a5-124">- Request sample</span></span> <br/><span data-ttu-id="329a5-125">- Ограничение выполнения кода (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="329a5-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="329a5-126">- Запуск антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="329a5-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="329a5-127">- Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="329a5-127">- Stop and quarantine</span></span>      |<span data-ttu-id="329a5-128">- Блокировка URL-адреса (время щелчка мыши)</span><span class="sxs-lookup"><span data-stu-id="329a5-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="329a5-129">- Мягкое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="329a5-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="329a5-130">- Электронная почта карантина</span><span class="sxs-lookup"><span data-stu-id="329a5-130">- Quarantine email</span></span><br/><span data-ttu-id="329a5-131">- Карантин вложения электронной почты</span><span class="sxs-lookup"><span data-stu-id="329a5-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="329a5-132">- Отключение внешней пересылаемой почты</span><span class="sxs-lookup"><span data-stu-id="329a5-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="329a5-133">Действия по исправлению, ожидающих утверждения или уже завершенных, можно просмотреть в [Центре действий.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="329a5-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="329a5-134">Действия по исправлению, которые следуют автоматическим расследованиям</span><span class="sxs-lookup"><span data-stu-id="329a5-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="329a5-135">По завершению автоматического расследования выносим вердикт по каждому доказательству.</span><span class="sxs-lookup"><span data-stu-id="329a5-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="329a5-136">В зависимости от вердикта выявляются действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="329a5-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="329a5-137">В некоторых случаях действия по исправлению выполняются автоматически. В других случаях действия по исправлению ожидают утверждения.</span><span class="sxs-lookup"><span data-stu-id="329a5-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="329a5-138">Все зависит от настройки [автоматического расследования](m365d-configure-auto-investigation-response.md)и ответа.</span><span class="sxs-lookup"><span data-stu-id="329a5-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="329a5-139">В таблице ниже перечислены возможные заключения и результаты.</span><span class="sxs-lookup"><span data-stu-id="329a5-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="329a5-140">Заключение</span><span class="sxs-lookup"><span data-stu-id="329a5-140">Verdict</span></span>    | <span data-ttu-id="329a5-141">Затронутые сущности</span><span class="sxs-lookup"><span data-stu-id="329a5-141">Affected entities</span></span>    | <span data-ttu-id="329a5-142">Результаты</span><span class="sxs-lookup"><span data-stu-id="329a5-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="329a5-143">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="329a5-143">Malicious</span></span>    | <span data-ttu-id="329a5-144">Устройства (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="329a5-144">Devices (endpoints)</span></span>    | <span data-ttu-id="329a5-145">Действия по исправлению принимаются автоматически (при [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) условии, что группы устройств вашей организации настроены на **полное устранение** угроз автоматически)</span><span class="sxs-lookup"><span data-stu-id="329a5-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="329a5-146">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="329a5-146">Malicious</span></span>    | <span data-ttu-id="329a5-147">Содержимое электронной почты (URL-адреса или вложения)</span><span class="sxs-lookup"><span data-stu-id="329a5-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="329a5-148">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="329a5-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="329a5-149">Подозрительные</span><span class="sxs-lookup"><span data-stu-id="329a5-149">Suspicious</span></span>    | <span data-ttu-id="329a5-150">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="329a5-150">Devices or email content</span></span> | <span data-ttu-id="329a5-151">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="329a5-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="329a5-152">Угрозы не найдены</span><span class="sxs-lookup"><span data-stu-id="329a5-152">No threats found</span></span>    | <span data-ttu-id="329a5-153">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="329a5-153">Devices or email content</span></span>    | <span data-ttu-id="329a5-154">Действия по исправлению не требуются</span><span class="sxs-lookup"><span data-stu-id="329a5-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="329a5-155">Действия по исправлению, которые принимаются вручную</span><span class="sxs-lookup"><span data-stu-id="329a5-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="329a5-156">Помимо действий по исправлению последствий, которые следуют автоматическим расследованиям, группа операций безопасности может выполнять определенные действия по исправлению вручную.</span><span class="sxs-lookup"><span data-stu-id="329a5-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="329a5-157">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="329a5-157">These include the following:</span></span>

- <span data-ttu-id="329a5-158">Действие ручного устройства, например изоляция устройства или карантин файлов</span><span class="sxs-lookup"><span data-stu-id="329a5-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="329a5-159">Ручное действие электронной почты, например мягкие удаления сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="329a5-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="329a5-160">[Расширенные действия по охоте](../defender-endpoint/advanced-hunting-overview.md) на устройствах или электронной почте</span><span class="sxs-lookup"><span data-stu-id="329a5-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="329a5-161">[Действия проводника](../office-365-security/threat-explorer.md) по контенту электронной почты, такие как перенос электронной почты на нежелательное, электронное сообщение с мягким удалением или жесткое удаление электронной почты.</span><span class="sxs-lookup"><span data-stu-id="329a5-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="329a5-162">Действие [живого ответа](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) вручную, например удаление файла, остановка процесса и удаление запланированной задачи</span><span class="sxs-lookup"><span data-stu-id="329a5-162">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="329a5-163">Live response action with [Microsoft Defender for Endpoint API](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span><span class="sxs-lookup"><span data-stu-id="329a5-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="329a5-164">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="329a5-164">Next steps</span></span>

- [<span data-ttu-id="329a5-165">Посещение Центра уведомлений</span><span class="sxs-lookup"><span data-stu-id="329a5-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="329a5-166">Просмотр и управление действиями по исправлению</span><span class="sxs-lookup"><span data-stu-id="329a5-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="329a5-167">Устранение ложных срабатыва-</span><span class="sxs-lookup"><span data-stu-id="329a5-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
