---
title: Обработка ложных срабатывавай или ложных отрицательных результатов в AIR в Защитнике Microsoft 365
description: Было ли обнаружено что-то пропущенное или неправильное с помощью AIR в Защитнике Microsoft 365? Узнайте, как отправлять ложные срабатываия или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
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
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930358"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="f2d99-105">Обработка ложных срабатывавай и отрицательных результатов в автоматизированном расследовании и реагировании на них</span><span class="sxs-lookup"><span data-stu-id="f2d99-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f2d99-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f2d99-106">**Applies to:**</span></span>
- <span data-ttu-id="f2d99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2d99-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="f2d99-108">Не [пропустили ли автоматизированные возможности](mtp-autoir.md) исследования и реагирования в Microsoft 365 Defender или неправильно обнаружили что-то?</span><span class="sxs-lookup"><span data-stu-id="f2d99-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="f2d99-109">Чтобы устранить эту проблему, необходимо предпринять несколько действий.</span><span class="sxs-lookup"><span data-stu-id="f2d99-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="f2d99-110">Вы можете выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f2d99-110">You can:</span></span>

- <span data-ttu-id="f2d99-111">[Сообщить о ложном срабатывии или отрицательных результатах в Корпорацию Майкрософт;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="f2d99-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="f2d99-112">[Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); и</span><span class="sxs-lookup"><span data-stu-id="f2d99-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="f2d99-113">[Отмена действий по исправлению, которые были предприняты на устройствах.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="f2d99-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="f2d99-114">Используйте эту статью в качестве руководства.</span><span class="sxs-lookup"><span data-stu-id="f2d99-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="f2d99-115">Отчет о ложном срабатывии или отрицательном срабатывии корпорации Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="f2d99-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="f2d99-116">Элемент пропущен или неправильно обнаружен</span><span class="sxs-lookup"><span data-stu-id="f2d99-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="f2d99-117">Служба</span><span class="sxs-lookup"><span data-stu-id="f2d99-117">Service</span></span>  |<span data-ttu-id="f2d99-118">Действия</span><span class="sxs-lookup"><span data-stu-id="f2d99-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f2d99-119">- Сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="f2d99-119">- Email message</span></span> <br/><span data-ttu-id="f2d99-120">- Вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="f2d99-120">- Email attachment</span></span> <br/><span data-ttu-id="f2d99-121">- URL-адрес в сообщении электронной почты</span><span class="sxs-lookup"><span data-stu-id="f2d99-121">- URL in an email message</span></span><br/><span data-ttu-id="f2d99-122">- URL-адрес в файле Office</span><span class="sxs-lookup"><span data-stu-id="f2d99-122">- URL in an Office file</span></span>      |[<span data-ttu-id="f2d99-123">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f2d99-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="f2d99-124">Отправка подозрительной нежелательной почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт для проверки</span><span class="sxs-lookup"><span data-stu-id="f2d99-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="f2d99-125">Файл или приложение на устройстве</span><span class="sxs-lookup"><span data-stu-id="f2d99-125">File or app on a device</span></span>    |[<span data-ttu-id="f2d99-126">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f2d99-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="f2d99-127">Отправка файла в корпорацию Майкрософт для анализа вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="f2d99-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="f2d99-128">Настройка оповещения, чтобы предотвратить повторение ложных срабатывающих</span><span class="sxs-lookup"><span data-stu-id="f2d99-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="f2d99-129">Сценарий</span><span class="sxs-lookup"><span data-stu-id="f2d99-129">Scenario</span></span> |<span data-ttu-id="f2d99-130">Служба</span><span class="sxs-lookup"><span data-stu-id="f2d99-130">Service</span></span> |<span data-ttu-id="f2d99-131">Действия</span><span class="sxs-lookup"><span data-stu-id="f2d99-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="f2d99-132">- Оповещение инициируется при законных основаниях.</span><span class="sxs-lookup"><span data-stu-id="f2d99-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="f2d99-133">- Оповещение неточно</span><span class="sxs-lookup"><span data-stu-id="f2d99-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="f2d99-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2d99-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="f2d99-135">или</span><span class="sxs-lookup"><span data-stu-id="f2d99-135">or</span></span> <br/>[<span data-ttu-id="f2d99-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="f2d99-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="f2d99-137">Управление оповещениями на портале Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2d99-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="f2d99-138">Файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносные программы на устройстве, хотя это безопасно</span><span class="sxs-lookup"><span data-stu-id="f2d99-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="f2d99-139">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f2d99-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="f2d99-140">Создание пользовательского индикатора с действием "Разрешить"</span><span class="sxs-lookup"><span data-stu-id="f2d99-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="f2d99-141">Отмена действия по исправлению, которое было принято на устройстве</span><span class="sxs-lookup"><span data-stu-id="f2d99-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="f2d99-142">Если действие по исправлению было принято на устройстве (например, на устройстве с Windows 10) и элемент фактически не является угрозой, группа операций безопасности может отменить действие по исправлению в Центре [действий.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="f2d99-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2d99-143">Перед выполнением [следующей](mtp-action-center.md#required-permissions-for-action-center-tasks) задачи убедитесь, что у вас есть необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="f2d99-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="f2d99-144">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="f2d99-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="f2d99-145">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="f2d99-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="f2d99-146">На **вкладке "История"** выберите действие, которое нужно отменить.</span><span class="sxs-lookup"><span data-stu-id="f2d99-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="f2d99-147">Откроется flyout.</span><span class="sxs-lookup"><span data-stu-id="f2d99-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="f2d99-148">Используйте фильтры, чтобы сузить список результатов.</span><span class="sxs-lookup"><span data-stu-id="f2d99-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="f2d99-149">Во flyout для выбранного элемента выберите страницу **"Открыть исследование".**</span><span class="sxs-lookup"><span data-stu-id="f2d99-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="f2d99-150">В представлении сведений об исследованиях выберите вкладку **"Действия".**</span><span class="sxs-lookup"><span data-stu-id="f2d99-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="f2d99-151">Выберите элемент с состоянием **"Завершено"** и наберись ссылки, например "Утверждено", в столбце **"Решения".**</span><span class="sxs-lookup"><span data-stu-id="f2d99-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="f2d99-152">Откроется flyout с дополнительными сведениями о действии.</span><span class="sxs-lookup"><span data-stu-id="f2d99-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="f2d99-153">Чтобы отменить действие, выберите **"Удалить исправление".**</span><span class="sxs-lookup"><span data-stu-id="f2d99-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2d99-154">См. также</span><span class="sxs-lookup"><span data-stu-id="f2d99-154">See also</span></span>

- [<span data-ttu-id="f2d99-155">Просмотр сведений и результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="f2d99-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="f2d99-156">Упреждающий поиск угроз с помощью расширенных поисков в Защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f2d99-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
