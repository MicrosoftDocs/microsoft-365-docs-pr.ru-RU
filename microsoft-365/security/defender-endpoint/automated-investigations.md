---
title: Использование автоматизированных расследований для расследования и устранения угроз
description: Понимание потока автоматического расследования в Microsoft Defender для конечной точки.
keywords: автоматизированная, следствие, обнаружение, защита atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: d2effb44c145a4fbf1006446685dbcd703754e6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166213"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="96b45-104">Обзор автоматизированных расследований</span><span class="sxs-lookup"><span data-stu-id="96b45-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="96b45-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="96b45-105">**Applies to:**</span></span>
- [<span data-ttu-id="96b45-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="96b45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96b45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96b45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="96b45-108">Хотите узнать, как это работает?</span><span class="sxs-lookup"><span data-stu-id="96b45-108">Want to see how it works?</span></span> <span data-ttu-id="96b45-109">Просмотрите следующее видео:</span><span class="sxs-lookup"><span data-stu-id="96b45-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="96b45-110">Технология автоматического расследования использует различные алгоритмы проверки и основана на процессах, используемых аналитиками безопасности.</span><span class="sxs-lookup"><span data-stu-id="96b45-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="96b45-111">Возможности AIR предназначены для проверки оповещений и принятия незамедлительных действий для устранения нарушений.</span><span class="sxs-lookup"><span data-stu-id="96b45-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="96b45-112">Возможности AIR значительно уменьшают объем оповещений, что позволяет операциям безопасности сосредоточиться на более сложных угрозах и других важных инициативах.</span><span class="sxs-lookup"><span data-stu-id="96b45-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="96b45-113">Все действия по исправлению, отложенные или завершенные, отслеживаются в [центре действий.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="96b45-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="96b45-114">В центре действий отложенные действия одобряются (или отклоняется), а завершенные действия при необходимости могут быть отменены.</span><span class="sxs-lookup"><span data-stu-id="96b45-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="96b45-115">В этой статье представлен обзор air и ссылки на последующие действия и дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="96b45-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="96b45-116">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="96b45-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="96b45-117">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="96b45-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="96b45-118">Начало автоматического расследования</span><span class="sxs-lookup"><span data-stu-id="96b45-118">How the automated investigation starts</span></span>

<span data-ttu-id="96b45-119">Автоматическое расследование может начаться, когда срабатывает оповещение или когда оператор безопасности инициирует расследование.</span><span class="sxs-lookup"><span data-stu-id="96b45-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="96b45-120">Ситуация</span><span class="sxs-lookup"><span data-stu-id="96b45-120">Situation</span></span>  |<span data-ttu-id="96b45-121">Что происходит</span><span class="sxs-lookup"><span data-stu-id="96b45-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="96b45-122">Срабатывает оповещение</span><span class="sxs-lookup"><span data-stu-id="96b45-122">An alert is triggered</span></span>     | <span data-ttu-id="96b45-123">Как правило, автоматическое расследование начинается, [когда](review-alerts.md) запускается оповещение и [создается](view-incidents-queue.md) инцидент.</span><span class="sxs-lookup"><span data-stu-id="96b45-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="96b45-124">Например, предположим, что вредоносный файл находится на устройстве.</span><span class="sxs-lookup"><span data-stu-id="96b45-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="96b45-125">При обнаружении этого файла запускается оповещение и создается инцидент.</span><span class="sxs-lookup"><span data-stu-id="96b45-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="96b45-126">На устройстве начинается процесс автоматического расследования.</span><span class="sxs-lookup"><span data-stu-id="96b45-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="96b45-127">Так как другие оповещения создаются из-за того же файла на других устройствах, они добавляются к связанному инциденту и автоматическому расследованию.</span><span class="sxs-lookup"><span data-stu-id="96b45-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="96b45-128">Расследование начинается вручную</span><span class="sxs-lookup"><span data-stu-id="96b45-128">An investigation is started manually</span></span>     | <span data-ttu-id="96b45-129">Автоматизированное расследование может быть начато вручную вашей командой операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="96b45-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="96b45-130">Например, предположим, что оператор безопасности просматривает список устройств и замечает, что устройство имеет высокий уровень риска.</span><span class="sxs-lookup"><span data-stu-id="96b45-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="96b45-131">Оператор безопасности может выбрать устройство в списке, чтобы открыть его вылет, а затем выбрать **инициировать автоматическое расследование.**</span><span class="sxs-lookup"><span data-stu-id="96b45-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="96b45-132">Расширение области автоматизированного расследования</span><span class="sxs-lookup"><span data-stu-id="96b45-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="96b45-133">В ходе расследования все другие оповещения, созданные с устройства, добавляются в непрерывное автоматическое расследование до завершения этого расследования.</span><span class="sxs-lookup"><span data-stu-id="96b45-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="96b45-134">Кроме того, если такая же угроза видна на других устройствах, эти устройства добавляются в исследование.</span><span class="sxs-lookup"><span data-stu-id="96b45-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="96b45-135">Если инкриминированная сущность видна на другом устройстве, процесс автоматического расследования расширяет его область, включив это устройство, и на этом устройстве начинается общебезопасная книга.</span><span class="sxs-lookup"><span data-stu-id="96b45-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="96b45-136">Если в ходе этого процесса расширения из одной и той же сущности находятся 10 или более устройств, то это действие расширения требует утверждения и отображается на вкладке **Ожидающих** действий.</span><span class="sxs-lookup"><span data-stu-id="96b45-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="96b45-137">Устранение угроз</span><span class="sxs-lookup"><span data-stu-id="96b45-137">How threats are remediated</span></span>

<span data-ttu-id="96b45-138">По мере запуска оповещений и запуска автоматического расследования для каждого исследуемого доказательства создается вердикт.</span><span class="sxs-lookup"><span data-stu-id="96b45-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="96b45-139">Вердикты могут быть</span><span class="sxs-lookup"><span data-stu-id="96b45-139">Verdicts can be</span></span> 
- <span data-ttu-id="96b45-140">*Вредоносный;*</span><span class="sxs-lookup"><span data-stu-id="96b45-140">*Malicious*;</span></span>
- <span data-ttu-id="96b45-141">*Подозрительный;* или</span><span class="sxs-lookup"><span data-stu-id="96b45-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="96b45-142">*Угрозы не найдены.*</span><span class="sxs-lookup"><span data-stu-id="96b45-142">*No threats found*.</span></span> 

<span data-ttu-id="96b45-143">По мере вынесения вердиктов автоматические расследования могут привести к одному или более действиям по исправлению.</span><span class="sxs-lookup"><span data-stu-id="96b45-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="96b45-144">Примеры действий по исправлению включают отправку файла на карантин, остановку службы, удаление запланированной задачи и другие.</span><span class="sxs-lookup"><span data-stu-id="96b45-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="96b45-145">Дополнительные дополнительные ссылки см. [в дополнительных действиях по исправлению.](manage-auto-investigation.md#remediation-actions)</span><span class="sxs-lookup"><span data-stu-id="96b45-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="96b45-146">В зависимости [](automation-levels.md) от уровня автоматизации, установленного для вашей организации, а также других параметров безопасности, действия по исправлению могут происходить автоматически или только после утверждения вашей командой операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="96b45-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="96b45-147">Дополнительные параметры безопасности, которые могут повлиять на автоматическое исправление, включают защиту от потенциально [нежелательных](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) приложений (PUA).</span><span class="sxs-lookup"><span data-stu-id="96b45-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="96b45-148">Все действия по исправлению, отложенные или завершенные, отслеживаются в [центре действий.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="96b45-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="96b45-149">При необходимости группа операций безопасности может отменить действие по исправлению.</span><span class="sxs-lookup"><span data-stu-id="96b45-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="96b45-150">Дополнительные дополнительные ссылки см. в [обзоре и утверждении](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)действий по исправлению после автоматического расследования.</span><span class="sxs-lookup"><span data-stu-id="96b45-150">To learn more, see [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="96b45-151">Ознакомьтесь с новой единой страницей расследования в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96b45-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="96b45-152">Дополнительные дополнительные возможности см. [в (NEW!) Страница Единое исследование](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span><span class="sxs-lookup"><span data-stu-id="96b45-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="96b45-153">Требования к AIR</span><span class="sxs-lookup"><span data-stu-id="96b45-153">Requirements for AIR</span></span>

<span data-ttu-id="96b45-154">В организации должен быть защитник для конечной точки (см. минимальные требования [к Microsoft Defender для конечной точки).](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="96b45-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="96b45-155">В настоящее время AIR поддерживает только следующие версии ОС:</span><span class="sxs-lookup"><span data-stu-id="96b45-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="96b45-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="96b45-156">Windows Server 2019</span></span>
- <span data-ttu-id="96b45-157">Windows 10, версия 1709 (сборка ОС 16299.1085 с [KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="96b45-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="96b45-158">Windows 10, версия 1803 (сборка ОС 17134.704 с [KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="96b45-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="96b45-159">Windows 10, версия [1803 или](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) более поздней версии</span><span class="sxs-lookup"><span data-stu-id="96b45-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="96b45-160">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="96b45-160">Next steps</span></span>

- [<span data-ttu-id="96b45-161">Дополнительные статьи об уровнях автоматизации</span><span class="sxs-lookup"><span data-stu-id="96b45-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="96b45-162">См. интерактивное руководство: изучение и устранение угроз с помощью Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="96b45-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="96b45-163">Настройка возможностей автоматического расследования и исправлений в Microsoft Defender для endpoint</span><span class="sxs-lookup"><span data-stu-id="96b45-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="96b45-164">См. также</span><span class="sxs-lookup"><span data-stu-id="96b45-164">See also</span></span>

- [<span data-ttu-id="96b45-165">Защита PUA</span><span class="sxs-lookup"><span data-stu-id="96b45-165">PUA protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="96b45-166">Автоматическое расследование и ответ в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="96b45-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-air)
- [<span data-ttu-id="96b45-167">Автоматическое исследование и ответ в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96b45-167">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
