---
title: Адрес false positives or false negatives in Microsoft 365 Defender
description: Было ли что-то пропущено или неправильно обнаружено air в Microsoft 365 Defender? Узнайте, как отправить ложные срабатыва или ложные отрицательные результаты в Корпорацию Майкрософт для анализа.
keywords: автоматическое, исследование, оповещение, исправление, ложное срабатывательство, ложный отрицательный
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 3cffa97d26b2b28de8d9e45d7030e0931a7ba072
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269583"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="c9264-105">Адрес false positives or false negatives in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9264-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c9264-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c9264-106">**Applies to:**</span></span>
- <span data-ttu-id="c9264-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9264-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="c9264-108">Ложные срабатывательство или негативы могут иногда возникать с любым решением защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="c9264-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="c9264-109">Если [автоматизированные возможности](m365d-autoir.md) расследования и реагирования в Microsoft 365 Defender пропустили или неправильно обнаружили что-то, ваша группа операций безопасности может предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c9264-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="c9264-110">Сообщение о ложном срабатыве или отрицательном срабатывии в Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9264-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="c9264-111">[Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="c9264-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="c9264-112">Отмена действий по исправлению, принятых на устройствах</span><span class="sxs-lookup"><span data-stu-id="c9264-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="c9264-113">В следующих разделах описано, как выполнять эти задачи.</span><span class="sxs-lookup"><span data-stu-id="c9264-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="c9264-114">Сообщение о ложном срабатыве или отрицательном сообщении в Корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="c9264-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="c9264-115">Элемент, пропущенный или неправильно обнаруженный</span><span class="sxs-lookup"><span data-stu-id="c9264-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="c9264-116">Служба</span><span class="sxs-lookup"><span data-stu-id="c9264-116">Service</span></span>  |<span data-ttu-id="c9264-117">Действия</span><span class="sxs-lookup"><span data-stu-id="c9264-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c9264-118">- Сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="c9264-118">- Email message</span></span> <br/><span data-ttu-id="c9264-119">- Вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="c9264-119">- Email attachment</span></span> <br/><span data-ttu-id="c9264-120">- URL-адрес в сообщении электронной почты</span><span class="sxs-lookup"><span data-stu-id="c9264-120">- URL in an email message</span></span><br/><span data-ttu-id="c9264-121">- URL-адрес в файле Office</span><span class="sxs-lookup"><span data-stu-id="c9264-121">- URL in an Office file</span></span>      |[<span data-ttu-id="c9264-122">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="c9264-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="c9264-123">Отправка подозрительных спама, фишинга, URL-адресов и файлов в Корпорацию Майкрософт для сканирования</span><span class="sxs-lookup"><span data-stu-id="c9264-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="c9264-124">Файл или приложение на устройстве</span><span class="sxs-lookup"><span data-stu-id="c9264-124">File or app on a device</span></span>    |[<span data-ttu-id="c9264-125">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c9264-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="c9264-126">Отправка файла в Корпорацию Майкрософт для анализа вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="c9264-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="c9264-127">Настройка оповещений, чтобы предотвратить повторение ложных срабатыва</span><span class="sxs-lookup"><span data-stu-id="c9264-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="c9264-128">Сценарий</span><span class="sxs-lookup"><span data-stu-id="c9264-128">Scenario</span></span> |<span data-ttu-id="c9264-129">Служба</span><span class="sxs-lookup"><span data-stu-id="c9264-129">Service</span></span> |<span data-ttu-id="c9264-130">Действия</span><span class="sxs-lookup"><span data-stu-id="c9264-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="c9264-131">- Оповещение вызывается законным использованием</span><span class="sxs-lookup"><span data-stu-id="c9264-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="c9264-132">- Оповещение является неточным</span><span class="sxs-lookup"><span data-stu-id="c9264-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="c9264-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c9264-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="c9264-134">или</span><span class="sxs-lookup"><span data-stu-id="c9264-134">or</span></span> <br/>[<span data-ttu-id="c9264-135">Защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="c9264-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="c9264-136">Управление оповещениями на портале безопасности облачных приложений</span><span class="sxs-lookup"><span data-stu-id="c9264-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="c9264-137">Файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносные программы на устройстве, даже если это безопасно</span><span class="sxs-lookup"><span data-stu-id="c9264-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="c9264-138">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c9264-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="c9264-139">Создание настраиваемой индикаторной области с помощью действия "Разрешить"</span><span class="sxs-lookup"><span data-stu-id="c9264-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="c9264-140">Отмена действия по исправлению, которое было принято на устройстве</span><span class="sxs-lookup"><span data-stu-id="c9264-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="c9264-141">Если для объекта (например, устройства или сообщения электронной почты) было принято действие по исправлению, и затрагиваемая сущность на самом [](m365d-action-center.md)деле не представляет угрозы, ваша группа операций безопасности может отменить действие по исправлению в центре действий.</span><span class="sxs-lookup"><span data-stu-id="c9264-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="c9264-142">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="c9264-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="c9264-143">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="c9264-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="c9264-144">На **вкладке История** выберите действие, которое необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="c9264-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="c9264-145">Откроется его поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="c9264-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="c9264-146">В области вылетов выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="c9264-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="c9264-147">См. [действия отмены завершенных действий.](m365d-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="c9264-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9264-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c9264-148">See also</span></span>

- [<span data-ttu-id="c9264-149">Просмотр сведений и результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="c9264-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="c9264-150">Активная охота на угрозы с расширенным поиском в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9264-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c9264-151">Устранение ложных положительных/отрицательных срабатываний в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c9264-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)