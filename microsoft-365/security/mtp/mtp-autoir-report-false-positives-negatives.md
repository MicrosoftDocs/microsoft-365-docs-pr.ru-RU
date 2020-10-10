---
title: Обработка ложных срабатываний или ложных отрицательных результатов в ПОТОКе защиты от угроз Майкрософт
description: Было ли что-то пошло не так, как было обнаружено ВОЗДУХом в защите от угроз Майкрософт? Сведения о том, как передавать ложные срабатывания или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
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
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: f8d741cbc7215c18d096573fe6555dfe7709c58b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413642"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="648fc-105">Обработка ложных срабатываний/отрицательных результатов в автоматизированном расследовании и возможностях реагирования</span><span class="sxs-lookup"><span data-stu-id="648fc-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="648fc-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="648fc-106">**Applies to:**</span></span>
- <span data-ttu-id="648fc-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="648fc-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="648fc-108">Выполнялось ли [автоматизированное исследование и возможности реагирования](mtp-autoir.md) в целях защиты от угроз Майкрософт или неправильно обнаруживают что-либо?</span><span class="sxs-lookup"><span data-stu-id="648fc-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="648fc-109">Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="648fc-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="648fc-110">Вы можете выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="648fc-110">You can:</span></span>

- <span data-ttu-id="648fc-111">[Сообщить о ложных положительных и отрицательных значениях корпорации Майкрософт](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="648fc-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="648fc-112">[Настройте оповещения](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); с</span><span class="sxs-lookup"><span data-stu-id="648fc-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="648fc-113">[Отмена действий по исправлению, сделанных на устройствах](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="648fc-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="648fc-114">Используйте эту статью в качестве руководства.</span><span class="sxs-lookup"><span data-stu-id="648fc-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="648fc-115">Сообщить о ложном положительном/отрицательном виде в корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="648fc-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="648fc-116">Элемент пропущен или неправильно обнаружен</span><span class="sxs-lookup"><span data-stu-id="648fc-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="648fc-117">Служба</span><span class="sxs-lookup"><span data-stu-id="648fc-117">Service</span></span>  |<span data-ttu-id="648fc-118">Действия</span><span class="sxs-lookup"><span data-stu-id="648fc-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="648fc-119">— Сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="648fc-119">- Email message</span></span> <br/><span data-ttu-id="648fc-120">— Вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="648fc-120">- Email attachment</span></span> <br/><span data-ttu-id="648fc-121">-URL в сообщении электронной почты</span><span class="sxs-lookup"><span data-stu-id="648fc-121">- URL in an email message</span></span><br/><span data-ttu-id="648fc-122">-URL в файле Office</span><span class="sxs-lookup"><span data-stu-id="648fc-122">- URL in an Office file</span></span>      |[<span data-ttu-id="648fc-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="648fc-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="648fc-124">Отправлять сообщения о нежелательной почте, фишинге, URL-адресах и файлах в корпорацию Майкрософт для сканирования</span><span class="sxs-lookup"><span data-stu-id="648fc-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="648fc-125">Файл или приложение на устройстве</span><span class="sxs-lookup"><span data-stu-id="648fc-125">File or app on a device</span></span>    |[<span data-ttu-id="648fc-126">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="648fc-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="648fc-127">Передача файла в корпорацию Майкрософт для анализа вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="648fc-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="648fc-128">Настройка оповещения для предотвращения повторения ложных срабатываний</span><span class="sxs-lookup"><span data-stu-id="648fc-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="648fc-129">Сценарий</span><span class="sxs-lookup"><span data-stu-id="648fc-129">Scenario</span></span> |<span data-ttu-id="648fc-130">Служба</span><span class="sxs-lookup"><span data-stu-id="648fc-130">Service</span></span> |<span data-ttu-id="648fc-131">Действия</span><span class="sxs-lookup"><span data-stu-id="648fc-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="648fc-132">— Оповещение инициировано законным использованием</span><span class="sxs-lookup"><span data-stu-id="648fc-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="648fc-133">— Неточное оповещение</span><span class="sxs-lookup"><span data-stu-id="648fc-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="648fc-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="648fc-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="648fc-135">или</span><span class="sxs-lookup"><span data-stu-id="648fc-135">or</span></span> <br/>[<span data-ttu-id="648fc-136">Расширенная угроза обнаружения угроз Azure</span><span class="sxs-lookup"><span data-stu-id="648fc-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="648fc-137">Управление оповещениями на портале Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="648fc-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="648fc-138">Файл, IP-адрес, URL-адрес или домен считается вредоносным по на устройстве, даже если он является безопасным</span><span class="sxs-lookup"><span data-stu-id="648fc-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="648fc-139">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="648fc-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="648fc-140">Создание настраиваемого индикатора с действием "разрешить"</span><span class="sxs-lookup"><span data-stu-id="648fc-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="648fc-141">Отмена действия по исправлению, сделанного на устройстве</span><span class="sxs-lookup"><span data-stu-id="648fc-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="648fc-142">Если действие по исправлению было выполнено на устройстве (например, на устройстве с Windows 10), а элемент на самом деле не является угрозой, Группа "операции по обеспечению безопасности" может отменить действие "Устранение неполадок" в [центре уведомлений](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="648fc-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="648fc-143">Перед попыткой выполнения следующей задачи убедитесь, что у вас есть [необходимые разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks) .</span><span class="sxs-lookup"><span data-stu-id="648fc-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="648fc-144">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="648fc-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="648fc-145">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="648fc-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="648fc-146">На вкладке **Журнал** выберите действие, которое необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="648fc-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="648fc-147">Откроется всплывающее окно.</span><span class="sxs-lookup"><span data-stu-id="648fc-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="648fc-148">Используйте фильтры для сужения списка результатов.</span><span class="sxs-lookup"><span data-stu-id="648fc-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="648fc-149">В всплывающем меню для выбранного элемента выберите **открыть страницу расследования**.</span><span class="sxs-lookup"><span data-stu-id="648fc-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="648fc-150">В представлении сведения об расследовании перейдите на вкладку **действия** .</span><span class="sxs-lookup"><span data-stu-id="648fc-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="648fc-151">Выберите элемент с состоянием " **завершено**" и найдите ссылку, например " **утверждено**", в столбце " **решения** ".</span><span class="sxs-lookup"><span data-stu-id="648fc-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="648fc-152">Откроется всплывающее окно с дополнительными сведениями о действии.</span><span class="sxs-lookup"><span data-stu-id="648fc-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="648fc-153">Чтобы отменить действие, выберите **Удалить исправление**.</span><span class="sxs-lookup"><span data-stu-id="648fc-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="648fc-154">См. также</span><span class="sxs-lookup"><span data-stu-id="648fc-154">See also</span></span>

- [<span data-ttu-id="648fc-155">Просмотр сведений и результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="648fc-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="648fc-156">Защита от угроз (Майкрософт) позволяет осуществлять их расширенное выслеживание на профилактической основе</span><span class="sxs-lookup"><span data-stu-id="648fc-156">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
