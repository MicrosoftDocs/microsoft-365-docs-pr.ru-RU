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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266055"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="d6f80-104">Действия по исправлению, выполняемые после автоматического исследования в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d6f80-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="d6f80-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d6f80-105">**Applies to:**</span></span>
- <span data-ttu-id="d6f80-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d6f80-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="d6f80-107">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="d6f80-107">Remediation actions</span></span>

<span data-ttu-id="d6f80-108">Во время и после автоматического исследования в защите от угроз Майкрософт действия по исправлению идентифицируются для вредоносных или подозрительных элементов.</span><span class="sxs-lookup"><span data-stu-id="d6f80-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="d6f80-109">Некоторые виды действий по исправлению выполняются на устройствах, которые также называются конечными точками.</span><span class="sxs-lookup"><span data-stu-id="d6f80-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="d6f80-110">Для содержимого электронной почты применяются другие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="d6f80-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="d6f80-111">Автоматическое расследование завершено после принятия, утверждения или отклонения действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="d6f80-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="d6f80-112">В следующей таблице приведены действия по исправлению, которые в настоящее время поддерживаются в Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="d6f80-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="d6f80-113">Действия по исправлению устройства (конечная точка)</span><span class="sxs-lookup"><span data-stu-id="d6f80-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="d6f80-114">Действия по исправления для электронной почты</span><span class="sxs-lookup"><span data-stu-id="d6f80-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="d6f80-115">Файл карантина</span><span class="sxs-lookup"><span data-stu-id="d6f80-115">Quarantine file</span></span><br/><span data-ttu-id="d6f80-116">Удаление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="d6f80-116">Remove registry key</span></span><br/><span data-ttu-id="d6f80-117">Прекращение процесса</span><span class="sxs-lookup"><span data-stu-id="d6f80-117">Kill process</span></span> <br/><span data-ttu-id="d6f80-118">Остановка службы</span><span class="sxs-lookup"><span data-stu-id="d6f80-118">Stop service</span></span> <br/><span data-ttu-id="d6f80-119">Отключение драйвера</span><span class="sxs-lookup"><span data-stu-id="d6f80-119">Disable driver</span></span> <br/><span data-ttu-id="d6f80-120">Удаление запланированной задачи</span><span class="sxs-lookup"><span data-stu-id="d6f80-120">Remove scheduled task</span></span>      |<span data-ttu-id="d6f80-121">Обратимое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="d6f80-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="d6f80-122">Блокирование URL-адреса (во время щелчка)</span><span class="sxs-lookup"><span data-stu-id="d6f80-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="d6f80-123">Отключение внешней переадресации почты</span><span class="sxs-lookup"><span data-stu-id="d6f80-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="d6f80-124">Действия по исправлению, которые ожидают утверждения или уже завершены, можно просмотреть в [центре уведомлений](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="d6f80-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="d6f80-125">Вердиктс и результаты, указанные при автоматическом расследовании</span><span class="sxs-lookup"><span data-stu-id="d6f80-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="d6f80-126">После завершения автоматического исследования дается заключение по каждому рассмотренному свидетельству и определяются действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="d6f80-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="d6f80-127">В некоторых случаях действия по исправлению выполняются автоматически. В других случаях действия по исправлению ожидают утверждения.</span><span class="sxs-lookup"><span data-stu-id="d6f80-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="d6f80-128">В таблице ниже перечислены возможные заключения и результаты.</span><span class="sxs-lookup"><span data-stu-id="d6f80-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="d6f80-129">Заключение</span><span class="sxs-lookup"><span data-stu-id="d6f80-129">Verdict</span></span>    |<span data-ttu-id="d6f80-130">Область</span><span class="sxs-lookup"><span data-stu-id="d6f80-130">Area</span></span>   |<span data-ttu-id="d6f80-131">Результаты</span><span class="sxs-lookup"><span data-stu-id="d6f80-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="d6f80-132">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="d6f80-132">Malicious</span></span>  |<span data-ttu-id="d6f80-133">Устройства (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="d6f80-133">Devices (endpoints)</span></span>    |<span data-ttu-id="d6f80-134">Действия по исправлению выполняются автоматически</span><span class="sxs-lookup"><span data-stu-id="d6f80-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="d6f80-135">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="d6f80-135">Malicious</span></span>  |<span data-ttu-id="d6f80-136">Содержимое электронной почты (URL-адреса или вложения)</span><span class="sxs-lookup"><span data-stu-id="d6f80-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="d6f80-137">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="d6f80-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="d6f80-138">Подозрительные</span><span class="sxs-lookup"><span data-stu-id="d6f80-138">Suspicious</span></span> |<span data-ttu-id="d6f80-139">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="d6f80-139">Devices or email content</span></span> |<span data-ttu-id="d6f80-140">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="d6f80-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="d6f80-141">Чистые</span><span class="sxs-lookup"><span data-stu-id="d6f80-141">Clean</span></span>  |<span data-ttu-id="d6f80-142">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="d6f80-142">Devices or email content</span></span>   |<span data-ttu-id="d6f80-143">Действия по исправлению не требуются</span><span class="sxs-lookup"><span data-stu-id="d6f80-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="d6f80-144">Просмотр ожидающего действия в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="d6f80-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="d6f80-145">Если вы считаете, что что-то пошло не так или неправильно, с помощью автоматизированного расследования и функции ответа в Microsoft Threat Protection, сообщите нам о!</span><span class="sxs-lookup"><span data-stu-id="d6f80-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="d6f80-146">[Сообщать ложные положительные и отрицательные](mtp-autoir-report-false-positives-negatives.md)значения.</span><span class="sxs-lookup"><span data-stu-id="d6f80-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6f80-147">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="d6f80-147">Next steps</span></span>

- [<span data-ttu-id="d6f80-148">Утверждение или отклонение действий</span><span class="sxs-lookup"><span data-stu-id="d6f80-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="d6f80-149">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="d6f80-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
