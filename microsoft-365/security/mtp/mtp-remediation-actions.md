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
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955595"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="3367c-104">Действия по исправлению, выполняемые после автоматического исследования в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3367c-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="3367c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3367c-105">**Applies to:**</span></span>
- <span data-ttu-id="3367c-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3367c-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="3367c-107">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="3367c-107">Remediation actions</span></span>

<span data-ttu-id="3367c-108">Во время и после автоматического исследования в защите от угроз Майкрософт действия по исправлению идентифицируются для вредоносных или подозрительных элементов.</span><span class="sxs-lookup"><span data-stu-id="3367c-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="3367c-109">Некоторые виды действий по исправлению выполняются на устройствах, которые также называются конечными точками.</span><span class="sxs-lookup"><span data-stu-id="3367c-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="3367c-110">Для содержимого электронной почты применяются другие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="3367c-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="3367c-111">Автоматическое расследование завершено после принятия, утверждения или отклонения действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="3367c-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="3367c-112">В следующей таблице приведены действия по исправлению, которые в настоящее время поддерживаются в Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="3367c-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="3367c-113">Действия по исправлению устройства (конечная точка)</span><span class="sxs-lookup"><span data-stu-id="3367c-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="3367c-114">Действия по исправления для электронной почты</span><span class="sxs-lookup"><span data-stu-id="3367c-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="3367c-115">Файл карантина</span><span class="sxs-lookup"><span data-stu-id="3367c-115">Quarantine file</span></span><br/><span data-ttu-id="3367c-116">Удаление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="3367c-116">Remove registry key</span></span><br/><span data-ttu-id="3367c-117">Прекращение процесса</span><span class="sxs-lookup"><span data-stu-id="3367c-117">Kill process</span></span> <br/><span data-ttu-id="3367c-118">Остановка службы</span><span class="sxs-lookup"><span data-stu-id="3367c-118">Stop service</span></span> <br/><span data-ttu-id="3367c-119">Отключение драйвера</span><span class="sxs-lookup"><span data-stu-id="3367c-119">Disable driver</span></span> <br/><span data-ttu-id="3367c-120">Удаление запланированной задачи</span><span class="sxs-lookup"><span data-stu-id="3367c-120">Remove scheduled task</span></span>      |<span data-ttu-id="3367c-121">Обратимое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="3367c-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="3367c-122">Блокирование URL-адреса (во время щелчка)</span><span class="sxs-lookup"><span data-stu-id="3367c-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="3367c-123">Отключение внешней переадресации почты</span><span class="sxs-lookup"><span data-stu-id="3367c-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="3367c-124">Действия по исправлению, которые ожидают утверждения или уже завершены, можно просмотреть в [центре уведомлений](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="3367c-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="3367c-125">Действия по исправлению следуют при автоматическом расследовании</span><span class="sxs-lookup"><span data-stu-id="3367c-125">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="3367c-126">После завершения автоматического исследования дается заключение по каждому рассмотренному свидетельству и определяются действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="3367c-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="3367c-127">В некоторых случаях действия по исправлению выполняются автоматически. В других случаях действия по исправлению ожидают утверждения.</span><span class="sxs-lookup"><span data-stu-id="3367c-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="3367c-128">В таблице ниже перечислены возможные заключения и результаты.</span><span class="sxs-lookup"><span data-stu-id="3367c-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="3367c-129">Заключение</span><span class="sxs-lookup"><span data-stu-id="3367c-129">Verdict</span></span>    |<span data-ttu-id="3367c-130">Область</span><span class="sxs-lookup"><span data-stu-id="3367c-130">Area</span></span>    |<span data-ttu-id="3367c-131">Результаты</span><span class="sxs-lookup"><span data-stu-id="3367c-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="3367c-132">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="3367c-132">Malicious</span></span>    |<span data-ttu-id="3367c-133">Устройства (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="3367c-133">Devices (endpoints)</span></span>    |<span data-ttu-id="3367c-134">Действия по исправлению выполняются автоматически</span><span class="sxs-lookup"><span data-stu-id="3367c-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="3367c-135">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="3367c-135">Malicious</span></span>    |<span data-ttu-id="3367c-136">Содержимое электронной почты (URL-адреса или вложения)</span><span class="sxs-lookup"><span data-stu-id="3367c-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="3367c-137">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="3367c-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="3367c-138">Подозрительные</span><span class="sxs-lookup"><span data-stu-id="3367c-138">Suspicious</span></span>    |<span data-ttu-id="3367c-139">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="3367c-139">Devices or email content</span></span> |<span data-ttu-id="3367c-140">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="3367c-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="3367c-141">Угрозы не найдены</span><span class="sxs-lookup"><span data-stu-id="3367c-141">No threats found</span></span>    |<span data-ttu-id="3367c-142">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="3367c-142">Devices or email content</span></span>    |<span data-ttu-id="3367c-143">Действия по исправлению не требуются</span><span class="sxs-lookup"><span data-stu-id="3367c-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="3367c-144">Просмотр ожидающего действия в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="3367c-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="3367c-145">Если вы считаете, что что-то пошло не так или неправильно, с помощью автоматизированного расследования и функции ответа в Microsoft Threat Protection, сообщите нам о!</span><span class="sxs-lookup"><span data-stu-id="3367c-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="3367c-146">[Сообщать ложные положительные и отрицательные](mtp-autoir-report-false-positives-negatives.md)значения.</span><span class="sxs-lookup"><span data-stu-id="3367c-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3367c-147">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="3367c-147">Next steps</span></span>

- [<span data-ttu-id="3367c-148">Утверждение или отклонение действий</span><span class="sxs-lookup"><span data-stu-id="3367c-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="3367c-149">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="3367c-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
