---
title: Сообщение о ложных срабатывах или ложных отрицательных результатах после автоматического расследования в Microsoft Defender для Office 365
description: Было ли что-то пропущено или неправильно обнаружено air в Microsoft Defender для Office 365? Узнайте, как отправить ложные срабатыва или ложные отрицательные результаты в Корпорацию Майкрософт для анализа.
keywords: автоматическое, исследование, оповещение, триггер, действие, исправление, ложное срабатывательство, ложный отрицательный
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
ms.openlocfilehash: 8a91a55d9598b5e780474315ddf1f7019e593fed
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406166"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="24b9b-105">Как сообщать о ложных срабатывах и отрицательных результатах в возможностях автоматического расследования и ответа</span><span class="sxs-lookup"><span data-stu-id="24b9b-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="24b9b-106">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="24b9b-106">**Applies to**</span></span>
- [<span data-ttu-id="24b9b-107">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="24b9b-107">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="24b9b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24b9b-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="24b9b-109">Если функции автоматического расследования [и реагирования (AIR) в Office 365](automated-investigation-response-office.md) что-то пропустили или неправильно обнаружили, для исправления этого могут предпринять действия, которые может предпринять ваша группа по работе с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="24b9b-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="24b9b-110">Такие действия включают:</span><span class="sxs-lookup"><span data-stu-id="24b9b-110">Such actions include:</span></span>

- <span data-ttu-id="24b9b-111">[Сообщение о ложном срабатыве или отрицательном срабатывии в Корпорации Майкрософт;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="24b9b-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="24b9b-112">[Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); и</span><span class="sxs-lookup"><span data-stu-id="24b9b-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="24b9b-113">[Отмена принятых действий по исправлению.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="24b9b-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="24b9b-114">Используйте эту статью в качестве руководства.</span><span class="sxs-lookup"><span data-stu-id="24b9b-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="24b9b-115">Сообщение о ложном срабатыве или отрицательном сообщении в Корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="24b9b-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="24b9b-116">Если AIR в Microsoft Defender для Office 365 пропустил сообщение электронной почты, вложение электронной почты, URL-адрес в сообщении электронной почты или URL-адрес в файле Office, вы можете отправить подозрительный спам, фишинг, URL-адреса и файлы в Microsoft для сканирования [Office 365](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="24b9b-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="24b9b-117">Вы также можете [отправить файл в Корпорацию Майкрософт для анализа вредоносных программ.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="24b9b-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="24b9b-118">Настройка оповещений, чтобы предотвратить повторение ложных срабатыва</span><span class="sxs-lookup"><span data-stu-id="24b9b-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="24b9b-119">Если оповещение вызывается законным использованием или оповещение является неточным, вы можете управлять оповещениями на портале [безопасности облачных приложений.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="24b9b-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="24b9b-120">Если ваша организация использует [Microsoft Defender для](https://docs.microsoft.com/windows/security/threat-protection) конечной точки в дополнение к Office 365, а файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносные программы на устройстве, даже если это безопасно, вы можете создать настраиваемый индикатор с действием ["Разрешить"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)для вашего устройства .</span><span class="sxs-lookup"><span data-stu-id="24b9b-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="24b9b-121">Отмена действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="24b9b-121">Undo a remediation action</span></span>

<span data-ttu-id="24b9b-122">В большинстве случаев, если в сообщении электронной почты, вложении электронной почты или URL-адресе было предприняно действие по исправлению, и этот элемент фактически не представляет угрозы, группа операций безопасности может отменить действие по исправлению и принять меры, чтобы предотвратить повторение ложного срабатывания.</span><span class="sxs-lookup"><span data-stu-id="24b9b-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="24b9b-123">Для отмены действия можно использовать [обозреватель угроз](#undo-an-action-using-threat-explorer) или вкладку [Действия](#undo-an-action-in-the-action-center) для расследования.</span><span class="sxs-lookup"><span data-stu-id="24b9b-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24b9b-124">Убедитесь, что у вас есть необходимые разрешения перед выполнением следующих задач.</span><span class="sxs-lookup"><span data-stu-id="24b9b-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="24b9b-125">Отмена действия с помощью обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="24b9b-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="24b9b-126">С помощью обозревателя угроз группа операций безопасности может найти электронное сообщение, затрагиваемую действием, и, возможно, отменить действие.</span><span class="sxs-lookup"><span data-stu-id="24b9b-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="24b9b-127">Сценарий</span><span class="sxs-lookup"><span data-stu-id="24b9b-127">Scenario</span></span>|<span data-ttu-id="24b9b-128">Отмена параметров</span><span class="sxs-lookup"><span data-stu-id="24b9b-128">Undo Options</span></span>|<span data-ttu-id="24b9b-129">Подробнее</span><span class="sxs-lookup"><span data-stu-id="24b9b-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="24b9b-130">Сообщение электронной почты было отправлено в папку нежелательной почты пользователя</span><span class="sxs-lookup"><span data-stu-id="24b9b-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="24b9b-131">- Перемещение сообщения в папку удаленных элементов пользователя</span><span class="sxs-lookup"><span data-stu-id="24b9b-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="24b9b-132">- Перемещение сообщения в почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="24b9b-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="24b9b-133">- Удаление сообщения</span><span class="sxs-lookup"><span data-stu-id="24b9b-133">- Delete the message</span></span>|[<span data-ttu-id="24b9b-134">Поиск и расследование вредоносной электронной почты, доставленной в Office 365</span><span class="sxs-lookup"><span data-stu-id="24b9b-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="24b9b-135">Сообщение электронной почты или файл были на карантине</span><span class="sxs-lookup"><span data-stu-id="24b9b-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="24b9b-136">- Освобождение электронной почты или файла</span><span class="sxs-lookup"><span data-stu-id="24b9b-136">- Release the email or file</span></span><br/><span data-ttu-id="24b9b-137">- Удаление электронной почты или файла</span><span class="sxs-lookup"><span data-stu-id="24b9b-137">- Delete the email or file</span></span>|[<span data-ttu-id="24b9b-138">Управление карантинными сообщениями в качестве администратора</span><span class="sxs-lookup"><span data-stu-id="24b9b-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="24b9b-139">Отмена действия в центре действий</span><span class="sxs-lookup"><span data-stu-id="24b9b-139">Undo an action in the Action center</span></span>

<span data-ttu-id="24b9b-140">В центре действий можно увидеть действия по исправлению, которые были приняты и потенциально отменяют действие.</span><span class="sxs-lookup"><span data-stu-id="24b9b-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="24b9b-141">Перейдите в центр безопасности Microsoft 365 ( <https://security.microsoft.com> ).</span><span class="sxs-lookup"><span data-stu-id="24b9b-141">Go to the Microsoft 365 security center (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="24b9b-142">В области навигации выберите **Центр действий.**</span><span class="sxs-lookup"><span data-stu-id="24b9b-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="24b9b-143">Выберите **вкладку История,** чтобы просмотреть список завершенных действий.</span><span class="sxs-lookup"><span data-stu-id="24b9b-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="24b9b-144">Выберите элемент.</span><span class="sxs-lookup"><span data-stu-id="24b9b-144">Select an item.</span></span> <span data-ttu-id="24b9b-145">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="24b9b-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="24b9b-146">В области вылетов выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="24b9b-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="24b9b-147">(Только действия, которые можно отменить, будут иметь кнопку **Undo.)**</span><span class="sxs-lookup"><span data-stu-id="24b9b-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="24b9b-148">См. также</span><span class="sxs-lookup"><span data-stu-id="24b9b-148">See also</span></span>

- [<span data-ttu-id="24b9b-149">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="24b9b-149">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="24b9b-150">Автоматизированные расследования в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="24b9b-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
