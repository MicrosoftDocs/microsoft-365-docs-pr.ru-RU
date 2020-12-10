---
title: Как сообщить о ложных срабатываниях или ложных отрицательных отрицательных результатов при автоматическом расследовании в защитнике Майкрософт для Office 365
description: Было ли что-то пошло не так, как было обнаружено ВОЗДУХом в защитнике Майкрософт для Office 365? Сведения о том, как передавать ложные срабатывания или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
keywords: автоматические, исследование, оповещение, триггер, действие, исправление, ложное срабатывание, ложные отрицательные значения
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 0fe8891f5ea6af215791c5f4321a93667a9d58f0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616180"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="6439d-105">Составление отчетов о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования</span><span class="sxs-lookup"><span data-stu-id="6439d-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6439d-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6439d-106">**Applies to:**</span></span>
- <span data-ttu-id="6439d-107">Защитник Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="6439d-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6439d-108">Были ли [автоматизированные функции расследования и реагирования (AIR) в Office 365](automated-investigation-response-office.md) пропустили или ошибочно обнаружить что-то?</span><span class="sxs-lookup"><span data-stu-id="6439d-108">Did [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) miss or wrongly detect something?</span></span> <span data-ttu-id="6439d-109">Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6439d-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="6439d-110">Вы можете выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6439d-110">You can:</span></span>

- <span data-ttu-id="6439d-111">[Сообщить о ложных положительных и отрицательных значениях корпорации Майкрософт](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="6439d-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="6439d-112">[Настройте оповещения](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); с</span><span class="sxs-lookup"><span data-stu-id="6439d-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="6439d-113">[Отмена выполненных действий по исправлению](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="6439d-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="6439d-114">Используйте эту статью в качестве руководства.</span><span class="sxs-lookup"><span data-stu-id="6439d-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="6439d-115">Сообщить о ложном положительном/отрицательном виде в корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="6439d-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="6439d-116">Если воздух в защитнике Microsoft для Office 365 пропустил сообщение электронной почты, вложение электронной почты, URL-адрес в сообщении электронной почты или URL-адрес в файле Office, вы можете [отправлять сообщения о подозрениях, фишинг, URL-адреса и файлы в корпорацию Майкрософт для сканирования в office 365](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="6439d-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="6439d-117">Вы также можете [передать файл в корпорацию Майкрософт для анализа вредоносных программ](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="6439d-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="6439d-118">Настройка оповещения для предотвращения повторения ложных срабатываний</span><span class="sxs-lookup"><span data-stu-id="6439d-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="6439d-119">Если оповещение инициировано законным использованием или оповещение неточны, вы можете [управлять оповещениями на портале Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="6439d-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="6439d-120">Если в организации используется [защитник Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection) в дополнение к Office 365, а файл, IP-адрес, URL-адрес или домен считаются вредоносными программами на устройстве, даже если это безопасно, можно [создать настраиваемый индикатор с действием "разрешить" для вашего устройства](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="6439d-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="6439d-121">Отмена действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="6439d-121">Undo a remediation action</span></span>

<span data-ttu-id="6439d-122">В большинстве случаев, если действие по исправлению было выполнено над сообщением электронной почты, вложением электронной почты или URL-адресом, а на самом деле это не угроза, Группа "операции по обеспечению безопасности" может отменить действие по исправлению и предпринять меры по предотвращению ложного срабатывания.</span><span class="sxs-lookup"><span data-stu-id="6439d-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="6439d-123">Для отмены действия можно использовать [Обозреватель угроз](#undo-an-action-using-threat-explorer) или [вкладку действия для исследования](#undo-an-action-using-the-actions-tab-for-an-investigation) .</span><span class="sxs-lookup"><span data-stu-id="6439d-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6439d-124">Перед попыткой выполнения следующих задач убедитесь, что у вас есть необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="6439d-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="6439d-125">Отмена действия с помощью обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="6439d-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="6439d-126">В обозревателе угроз группа "операции безопасности" может найти сообщение электронной почты, затронутое действием, и, возможно, отменить действие.</span><span class="sxs-lookup"><span data-stu-id="6439d-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="6439d-127">Сценарий</span><span class="sxs-lookup"><span data-stu-id="6439d-127">Scenario</span></span>|<span data-ttu-id="6439d-128">Параметры отмены</span><span class="sxs-lookup"><span data-stu-id="6439d-128">Undo Options</span></span>|<span data-ttu-id="6439d-129">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6439d-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="6439d-130">Сообщение электронной почты было перенаправлено в папку нежелательной почты пользователя</span><span class="sxs-lookup"><span data-stu-id="6439d-130">An email message was routed to a user's Junk Email folder</span></span>|<ul><li><span data-ttu-id="6439d-131">Перемещение сообщения в папку "Удаленные" пользователя</span><span class="sxs-lookup"><span data-stu-id="6439d-131">Move the message to the user's Deleted Items folder</span></span></li><li><span data-ttu-id="6439d-132">Перемещение сообщения в папку "Входящие" пользователя</span><span class="sxs-lookup"><span data-stu-id="6439d-132">Move the message to the user's Inbox</span></span></li><li><span data-ttu-id="6439d-133">Удалить сообщение.</span><span class="sxs-lookup"><span data-stu-id="6439d-133">Delete the message</span></span></li></ul>|[<span data-ttu-id="6439d-134">Поиск и исследование вредоносных сообщений электронной почты, которые были доставлены в Office 365</span><span class="sxs-lookup"><span data-stu-id="6439d-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="6439d-135">Сообщение электронной почты или файл помещено в карантин</span><span class="sxs-lookup"><span data-stu-id="6439d-135">An email message or a file was quarantined</span></span>|<ul><li><span data-ttu-id="6439d-136">Освобождение электронной почты или файла</span><span class="sxs-lookup"><span data-stu-id="6439d-136">Release the email or file</span></span></li><li><span data-ttu-id="6439d-137">Удаление электронной почты или файла</span><span class="sxs-lookup"><span data-stu-id="6439d-137">Delete the email or file</span></span></li></ul>|[<span data-ttu-id="6439d-138">Управление сообщениями, помещенными в карантин, в качестве администратора</span><span class="sxs-lookup"><span data-stu-id="6439d-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="6439d-139">Отмена действия с помощью вкладки "действия" для исследования</span><span class="sxs-lookup"><span data-stu-id="6439d-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="6439d-140">В центре уведомлений вы можете просмотреть принятые действия по исправлению и потенциально отменить действие.</span><span class="sxs-lookup"><span data-stu-id="6439d-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="6439d-141">Перейдите на <https://protection.office.com> и войдите.</span><span class="sxs-lookup"><span data-stu-id="6439d-141">Go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="6439d-142">Откроется Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6439d-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="6439d-143">Перейдите на страницу расследования по **управлению угрозами** \> .</span><span class="sxs-lookup"><span data-stu-id="6439d-143">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="6439d-144">В списке исследований выберите значок **Открыть в новом окне** рядом с идентификатором элемента.</span><span class="sxs-lookup"><span data-stu-id="6439d-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="6439d-145">Перейдите на вкладку **действия** .</span><span class="sxs-lookup"><span data-stu-id="6439d-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="6439d-146">Выберите элемент с состоянием " **завершено**" и найдите ссылку, например " **утверждено**", в столбце " **решение** ".</span><span class="sxs-lookup"><span data-stu-id="6439d-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="6439d-147">Откроется всплывающее окно с дополнительными сведениями о действии.</span><span class="sxs-lookup"><span data-stu-id="6439d-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="6439d-148">Чтобы отменить действие, выберите **Удалить исправление**.</span><span class="sxs-lookup"><span data-stu-id="6439d-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6439d-149">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="6439d-149">Related articles</span></span>

[<span data-ttu-id="6439d-150">Защитник Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="6439d-150">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="6439d-151">ВОЗДУХ в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="6439d-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
