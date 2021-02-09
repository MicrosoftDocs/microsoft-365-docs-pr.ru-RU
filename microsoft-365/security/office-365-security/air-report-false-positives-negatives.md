---
title: Как сообщить о ложных срабатывах или ложных отрицательных результатах после автоматического исследования в Microsoft Defender для Office 365
description: Было ли обнаружено что-то пропущенное или неправильное с помощью AIR в Microsoft Defender для Office 365? Узнайте, как отправлять ложные положительные или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
keywords: автоматизированный, исследование, оповещение, триггер, действие, исправление, ложное срабатываение, ложный отрицательный результат
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4ccc023a72ca450b1f0a433410206ccce59cb5f1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142985"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="4dbe4-105">Как сообщать о ложных срабатываах и отрицательных результатах в автоматизированных исследованиях и реагировании на них</span><span class="sxs-lookup"><span data-stu-id="4dbe4-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="4dbe4-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4dbe4-106">**Applies to:**</span></span>
- <span data-ttu-id="4dbe4-107">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="4dbe4-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4dbe4-108">Если функции автоматического исследования и [реагирования (AIR) в Office 365](automated-investigation-response-office.md) пропущены или неправильно обнаружены какие-либо действия, ваша группа по работе с безопасностью может предпринять необходимые действия, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-108">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="4dbe4-109">К таким действиям относятся:</span><span class="sxs-lookup"><span data-stu-id="4dbe4-109">Such actions include:</span></span>

- <span data-ttu-id="4dbe4-110">[Сообщение о ложных срабатываах или отрицательных результатах в Корпорацию Майкрософт;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="4dbe4-110">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="4dbe4-111">[Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); и</span><span class="sxs-lookup"><span data-stu-id="4dbe4-111">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="4dbe4-112">[Отмена принятых действий по исправлению.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="4dbe4-112">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="4dbe4-113">Используйте эту статью в качестве руководства.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-113">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="4dbe4-114">Сообщение о ложном срабатывии или отрицательных результатах в корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="4dbe4-114">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="4dbe4-115">Если AIR в Microsoft Defender для Office 365 пропустил сообщение электронной почты, вложение электронной почты, URL-адрес в сообщении электронной почты или URL-адрес в файле Office, вы можете отправить подозрительный спам, фишинг, URL-адреса и файлы в корпорацию Майкрософт для сканирования [Office 365.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="4dbe4-115">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="4dbe4-116">Вы также можете [отправить файл в корпорацию Майкрософт для анализа вредоносных программ.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="4dbe4-116">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="4dbe4-117">Настройка оповещения, чтобы предотвратить повторение ложных срабатывающих</span><span class="sxs-lookup"><span data-stu-id="4dbe4-117">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="4dbe4-118">Если оповещение инициируется законным использованием или оповещение неточно, вы можете управлять оповещениями на портале [Cloud App Security.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="4dbe4-118">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="4dbe4-119">Если ваша организация использует [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) для конечной точки в дополнение к Office 365, а файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносная программа на устройстве, хотя это безопасно, вы можете создать настраиваемый индикатор с действием ["Разрешить"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)для вашего устройства.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-119">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="4dbe4-120">Отмена действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="4dbe4-120">Undo a remediation action</span></span>

<span data-ttu-id="4dbe4-121">В большинстве случаев, если для сообщения электронной почты, вложения электронной почты или URL-адреса было предприняно действие по исправлению и элемент фактически не представляет угрозы, ваша группа по работе с безопасностью может отменить действие по исправлению и принять меры, чтобы предотвратить повторение ложного срабатывания.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-121">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="4dbe4-122">Для отмены действия можно использовать [обозреватель угроз](#undo-an-action-using-threat-explorer) или вкладку ["Действия".](#undo-an-action-in-the-action-center)</span><span class="sxs-lookup"><span data-stu-id="4dbe4-122">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4dbe4-123">Перед выполнением следующих задач убедитесь, что у вас есть необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-123">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="4dbe4-124">Отмена действия с помощью обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="4dbe4-124">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="4dbe4-125">С помощью обозревателя угроз группа операций безопасности может найти сообщение электронной почты, на которое влияет действие, и, возможно, отменить действие.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-125">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="4dbe4-126">Сценарий</span><span class="sxs-lookup"><span data-stu-id="4dbe4-126">Scenario</span></span>|<span data-ttu-id="4dbe4-127">Параметры отмены</span><span class="sxs-lookup"><span data-stu-id="4dbe4-127">Undo Options</span></span>|<span data-ttu-id="4dbe4-128">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4dbe4-128">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="4dbe4-129">Сообщение электронной почты было отправлено в папку нежелательной почты пользователя</span><span class="sxs-lookup"><span data-stu-id="4dbe4-129">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="4dbe4-130">- Переместить сообщение в папку пользователя "Удаленные"</span><span class="sxs-lookup"><span data-stu-id="4dbe4-130">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="4dbe4-131">- Переместить сообщение в почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="4dbe4-131">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="4dbe4-132">- Удалить сообщение</span><span class="sxs-lookup"><span data-stu-id="4dbe4-132">- Delete the message</span></span>|[<span data-ttu-id="4dbe4-133">Поиск и изучение вредоносной электронной почты, доставленной в Office 365</span><span class="sxs-lookup"><span data-stu-id="4dbe4-133">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="4dbe4-134">Сообщение электронной почты или файл были отправлены на карантин</span><span class="sxs-lookup"><span data-stu-id="4dbe4-134">An email message or a file was quarantined</span></span>|<span data-ttu-id="4dbe4-135">- Освободить сообщение электронной почты или файл</span><span class="sxs-lookup"><span data-stu-id="4dbe4-135">- Release the email or file</span></span><br/><span data-ttu-id="4dbe4-136">- Удалить сообщение электронной почты или файл</span><span class="sxs-lookup"><span data-stu-id="4dbe4-136">- Delete the email or file</span></span>|[<span data-ttu-id="4dbe4-137">Управление сообщениями на карантине от имени администратора</span><span class="sxs-lookup"><span data-stu-id="4dbe4-137">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="4dbe4-138">Отмена действия в центре действий</span><span class="sxs-lookup"><span data-stu-id="4dbe4-138">Undo an action in the Action center</span></span>

<span data-ttu-id="4dbe4-139">В центре действий можно увидеть действия по исправлению, которые были предприняты, и, возможно, отменить это действие.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-139">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="4dbe4-140">Перейдите в Центр безопасности Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).</span><span class="sxs-lookup"><span data-stu-id="4dbe4-140">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="4dbe4-141">В области навигации выберите **"Центр действий".**</span><span class="sxs-lookup"><span data-stu-id="4dbe4-141">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="4dbe4-142">Выберите **вкладку "История",** чтобы просмотреть список завершенных действий.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-142">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="4dbe4-143">Выберите элемент.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-143">Select an item.</span></span> <span data-ttu-id="4dbe4-144">Откроется его вылетная области.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-144">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="4dbe4-145">Во flyout pane, select **Undo**.</span><span class="sxs-lookup"><span data-stu-id="4dbe4-145">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="4dbe4-146">(Только действия, которые можно отменить, будут иметь кнопку **"Отменить".)**</span><span class="sxs-lookup"><span data-stu-id="4dbe4-146">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="4dbe4-147">См. также</span><span class="sxs-lookup"><span data-stu-id="4dbe4-147">See also</span></span>

- [<span data-ttu-id="4dbe4-148">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="4dbe4-148">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="4dbe4-149">Автоматизированные исследования в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="4dbe4-149">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
