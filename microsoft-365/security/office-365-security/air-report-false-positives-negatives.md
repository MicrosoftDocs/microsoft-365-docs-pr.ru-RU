---
title: Составление отчетов о ложных срабатываниях и ложных отрицательных отрицательных результатов в Office 365 автоматизированное исследование и отклик
description: Было ли что-то пошло или неправильно обнаружено в Office 365 Advanced Threat protection? Сведения о том, как передавать ложные срабатывания или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 837232550ca392a364b9842f64a1c3f0d790a502
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520162"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="972ee-105">Составление отчетов о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования</span><span class="sxs-lookup"><span data-stu-id="972ee-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="972ee-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="972ee-106">**Applies to:**</span></span>
- <span data-ttu-id="972ee-107">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="972ee-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="972ee-108">Были ли [автоматизированные функции расследования и реагирования (AIR) в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) пропустили или ошибочно обнаружить что-то?</span><span class="sxs-lookup"><span data-stu-id="972ee-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="972ee-109">Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="972ee-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="972ee-110">Варианты действий:</span><span class="sxs-lookup"><span data-stu-id="972ee-110">You can:</span></span>
- <span data-ttu-id="972ee-111">[Сообщить о ложных положительных и отрицательных значениях корпорации Майкрософт](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="972ee-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="972ee-112">[Настройте оповещения](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); с</span><span class="sxs-lookup"><span data-stu-id="972ee-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="972ee-113">[Отмена выполненных действий по исправлению](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="972ee-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="972ee-114">Используйте эту статью в качестве руководства.</span><span class="sxs-lookup"><span data-stu-id="972ee-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="972ee-115">Сообщить о ложном положительном/отрицательном виде в корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="972ee-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="972ee-116">Если в Office 365 воздух пропустил сообщение электронной почты, вложение электронной почты, URL-адрес в сообщении электронной почты или URL-адрес в файле Office, вы можете [отправлять сообщения о подозрениях, фишинг, URL-адреса и файлы в корпорацию Майкрософт для сканирования в office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="972ee-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="972ee-117">Вы также можете [передать файл в корпорацию Майкрософт для анализа вредоносных программ](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="972ee-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="972ee-118">Настройка оповещения для предотвращения повторения ложных срабатываний</span><span class="sxs-lookup"><span data-stu-id="972ee-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="972ee-119">Если оповещение инициировано законным использованием или оповещение неточны, вы можете [управлять оповещениями на портале Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="972ee-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="972ee-120">Если в организации используется [Advanced Threat protection (Майкрософт](https://docs.microsoft.com/windows/security/threat-protection) ) в дополнение к Office 365, а файл, IP-адрес, URL-адрес или домен считаются вредоносными программами на устройстве, даже если это безопасно, можно [создать настраиваемый индикатор с действием "разрешить" для вашего устройства](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="972ee-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="972ee-121">Отмена действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="972ee-121">Undo a remediation action</span></span>

<span data-ttu-id="972ee-122">В большинстве случаев, если действие по исправлению было выполнено над сообщением электронной почты, вложением электронной почты или URL-адресом, а на самом деле это не угроза, Группа "операции по обеспечению безопасности" может отменить действие по исправлению и предпринять меры по предотвращению ложного срабатывания.</span><span class="sxs-lookup"><span data-stu-id="972ee-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="972ee-123">Для отмены действия можно использовать [Обозреватель угроз](#undo-an-action-using-threat-explorer) или [вкладку действия для исследования](#undo-an-action-using-the-actions-tab-for-an-investigation) .</span><span class="sxs-lookup"><span data-stu-id="972ee-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="972ee-124">Перед попыткой выполнения следующих задач убедитесь, что у вас есть необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="972ee-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="972ee-125">Отмена действия с помощью обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="972ee-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="972ee-126">В обозревателе угроз группа "операции безопасности" может найти сообщение электронной почты, затронутое действием, и, возможно, отменить действие.</span><span class="sxs-lookup"><span data-stu-id="972ee-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="972ee-127">Сценарий</span><span class="sxs-lookup"><span data-stu-id="972ee-127">Scenario</span></span>  |<span data-ttu-id="972ee-128">Параметры отмены</span><span class="sxs-lookup"><span data-stu-id="972ee-128">Undo Options</span></span>  |<span data-ttu-id="972ee-129">Подробнее</span><span class="sxs-lookup"><span data-stu-id="972ee-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="972ee-130">Сообщение электронной почты было перенаправлено в папку нежелательной почты пользователя</span><span class="sxs-lookup"><span data-stu-id="972ee-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="972ee-131">— Переместить сообщение в папку "Удаленные" пользователя.</span><span class="sxs-lookup"><span data-stu-id="972ee-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="972ee-132">— Переместить сообщение в папку "Входящие" пользователя</span><span class="sxs-lookup"><span data-stu-id="972ee-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="972ee-133">— Удалить сообщение.</span><span class="sxs-lookup"><span data-stu-id="972ee-133">- Delete the message</span></span>          |[<span data-ttu-id="972ee-134">Поиск и исследование вредоносных сообщений электронной почты, которые были доставлены в Office 365</span><span class="sxs-lookup"><span data-stu-id="972ee-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="972ee-135">Сообщение электронной почты или файл помещено в карантин</span><span class="sxs-lookup"><span data-stu-id="972ee-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="972ee-136">— Освободите электронную почту или файл.</span><span class="sxs-lookup"><span data-stu-id="972ee-136">- Release the email or file</span></span> <br/><span data-ttu-id="972ee-137">— Удаление электронной почты или файла</span><span class="sxs-lookup"><span data-stu-id="972ee-137">- Delete the email or file</span></span>         |[<span data-ttu-id="972ee-138">Управление сообщениями, помещенными в карантин, и файлами в качестве администратора в Office 365</span><span class="sxs-lookup"><span data-stu-id="972ee-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="972ee-139">Отмена действия с помощью вкладки "действия" для исследования</span><span class="sxs-lookup"><span data-stu-id="972ee-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="972ee-140">В центре уведомлений вы можете просмотреть принятые действия по исправлению и потенциально отменить действие.</span><span class="sxs-lookup"><span data-stu-id="972ee-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="972ee-141">Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="972ee-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="972ee-142">Откроется Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="972ee-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="972ee-143">Перейдите на страницу расследования по **управлению угрозами**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="972ee-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="972ee-144">В списке исследований выберите значок **Открыть в новом окне** рядом с идентификатором элемента.</span><span class="sxs-lookup"><span data-stu-id="972ee-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="972ee-145">Перейдите на вкладку **действия** .</span><span class="sxs-lookup"><span data-stu-id="972ee-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="972ee-146">Выберите элемент с состоянием " **завершено**" и найдите ссылку, например " **утверждено**", в столбце " **решение** ".</span><span class="sxs-lookup"><span data-stu-id="972ee-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="972ee-147">Откроется всплывающее окно с дополнительными сведениями о действии.</span><span class="sxs-lookup"><span data-stu-id="972ee-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="972ee-148">Чтобы отменить действие, выберите **Удалить исправление**.</span><span class="sxs-lookup"><span data-stu-id="972ee-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="972ee-149">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="972ee-149">Related articles</span></span>

[<span data-ttu-id="972ee-150">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="972ee-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="972ee-151">Начало работы с автоматизированным исследованием и откликом (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="972ee-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)
