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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502941"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="45420-104">Действия по исправлению, выполняемые после автоматического исследования в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="45420-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="45420-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="45420-105">**Applies to:**</span></span>
- <span data-ttu-id="45420-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="45420-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="45420-107">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="45420-107">Remediation actions</span></span>

<span data-ttu-id="45420-108">Во время и после автоматического исследования в защите от угроз Майкрософт действия по исправлению идентифицируются для вредоносных или подозрительных элементов.</span><span class="sxs-lookup"><span data-stu-id="45420-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="45420-109">Некоторые виды действий по исправлению выполняются на устройствах, которые также называются конечными точками.</span><span class="sxs-lookup"><span data-stu-id="45420-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="45420-110">Для содержимого электронной почты применяются другие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="45420-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="45420-111">Автоматическое расследование завершено после принятия, утверждения или отклонения действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="45420-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="45420-112">В следующей таблице приведены действия по исправлению, которые в настоящее время поддерживаются в Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="45420-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="45420-113">Действия по исправлению устройства (конечная точка)</span><span class="sxs-lookup"><span data-stu-id="45420-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="45420-114">Действия по исправления для электронной почты</span><span class="sxs-lookup"><span data-stu-id="45420-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="45420-115">— Собрать пакет для расследования</span><span class="sxs-lookup"><span data-stu-id="45420-115">- Collect investigation package</span></span> <br/><span data-ttu-id="45420-116">-Изолировать устройство (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="45420-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="45420-117">— Переносе Machine</span><span class="sxs-lookup"><span data-stu-id="45420-117">- Offboard machine</span></span> <br/><span data-ttu-id="45420-118">— Запуск кода в выпуске</span><span class="sxs-lookup"><span data-stu-id="45420-118">- Release code execution</span></span> <br/><span data-ttu-id="45420-119">— Выпуск из карантина</span><span class="sxs-lookup"><span data-stu-id="45420-119">- Release from quarantine</span></span> <br/><span data-ttu-id="45420-120">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="45420-120">- Request sample</span></span> <br/><span data-ttu-id="45420-121">— Ограничить выполнение кода (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="45420-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="45420-122">— Запуск антивирусной проверки</span><span class="sxs-lookup"><span data-stu-id="45420-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="45420-123">— Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="45420-123">- Stop and quarantine</span></span>      |<span data-ttu-id="45420-124">-URL-адрес блока (время нажатия)</span><span class="sxs-lookup"><span data-stu-id="45420-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="45420-125">— Обратимое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="45420-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="45420-126">— Электронная почта на карантине</span><span class="sxs-lookup"><span data-stu-id="45420-126">- Quarantine email</span></span><br/><span data-ttu-id="45420-127">— Вложение вложения электронной почты в карантин</span><span class="sxs-lookup"><span data-stu-id="45420-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="45420-128">– Отключить функцию пересылки для внешней почты</span><span class="sxs-lookup"><span data-stu-id="45420-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="45420-129">Действия по исправлению, которые ожидают утверждения или уже завершены, можно просмотреть в [центре уведомлений](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="45420-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="45420-130">Действия по исправлению следуют при автоматическом расследовании</span><span class="sxs-lookup"><span data-stu-id="45420-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="45420-131">После завершения автоматического исследования дается заключение по каждому рассмотренному свидетельству и определяются действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="45420-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="45420-132">В некоторых случаях действия по исправлению выполняются автоматически. В других случаях действия по исправлению ожидают утверждения.</span><span class="sxs-lookup"><span data-stu-id="45420-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="45420-133">В таблице ниже перечислены возможные заключения и результаты.</span><span class="sxs-lookup"><span data-stu-id="45420-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="45420-134">Заключение</span><span class="sxs-lookup"><span data-stu-id="45420-134">Verdict</span></span>    |<span data-ttu-id="45420-135">Область</span><span class="sxs-lookup"><span data-stu-id="45420-135">Area</span></span>    |<span data-ttu-id="45420-136">Результаты</span><span class="sxs-lookup"><span data-stu-id="45420-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="45420-137">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="45420-137">Malicious</span></span>    |<span data-ttu-id="45420-138">Устройства (конечные точки)</span><span class="sxs-lookup"><span data-stu-id="45420-138">Devices (endpoints)</span></span>    |<span data-ttu-id="45420-139">Действия по исправлению выполняются автоматически</span><span class="sxs-lookup"><span data-stu-id="45420-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="45420-140">Вредоносные</span><span class="sxs-lookup"><span data-stu-id="45420-140">Malicious</span></span>    |<span data-ttu-id="45420-141">Содержимое электронной почты (URL-адреса или вложения)</span><span class="sxs-lookup"><span data-stu-id="45420-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="45420-142">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="45420-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="45420-143">Подозрительные</span><span class="sxs-lookup"><span data-stu-id="45420-143">Suspicious</span></span>    |<span data-ttu-id="45420-144">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="45420-144">Devices or email content</span></span> |<span data-ttu-id="45420-145">Рекомендуемые действия по исправлению ожидают утверждения</span><span class="sxs-lookup"><span data-stu-id="45420-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="45420-146">Угрозы не найдены</span><span class="sxs-lookup"><span data-stu-id="45420-146">No threats found</span></span>    |<span data-ttu-id="45420-147">Устройства или содержимое электронной почты</span><span class="sxs-lookup"><span data-stu-id="45420-147">Devices or email content</span></span>    |<span data-ttu-id="45420-148">Действия по исправлению не требуются</span><span class="sxs-lookup"><span data-stu-id="45420-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="45420-149">Просмотр ожидающего действия в центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="45420-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="45420-150">Если вы считаете, что что-то пошло не так или неправильно, с помощью автоматизированного расследования и функции ответа в Microsoft Threat Protection, сообщите нам о!</span><span class="sxs-lookup"><span data-stu-id="45420-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="45420-151">[Сообщать ложные положительные и отрицательные](mtp-autoir-report-false-positives-negatives.md)значения.</span><span class="sxs-lookup"><span data-stu-id="45420-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="45420-152">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="45420-152">Next steps</span></span>

- [<span data-ttu-id="45420-153">Утверждение или отклонение действий</span><span class="sxs-lookup"><span data-stu-id="45420-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="45420-154">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="45420-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
