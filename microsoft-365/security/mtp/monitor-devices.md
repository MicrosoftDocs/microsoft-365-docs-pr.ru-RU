---
title: Отчеты & мониторинга устройств — Центр безопасности
description: В этой статье описано, как обеспечить безопасность, защиту, защиту и защиту от потенциальных угроз в организации.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Центр безопасности, монитор, отчет, устройства
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930502"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="1087b-104">Мониторинг устройств и отчетность в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1087b-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1087b-105">Сохраняйте безопасность, последние и сохраняйте потенциальные угрозы на своих устройствах в Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1087b-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="1087b-106">Просмотр оповещений устройств</span><span class="sxs-lookup"><span data-stu-id="1087b-106">View device alerts</span></span>

<span data-ttu-id="1087b-107">Получать оповещения о нарушении безопасности и других угрозах на устройствах из Microsoft Defender для конечной точки (доступно с лицензией E5).</span><span class="sxs-lookup"><span data-stu-id="1087b-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="1087b-108">Центр безопасности Microsoft 365 эффективно отслеживает эти оповещения на высоком уровне с помощью предпочитаемого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1087b-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="1087b-109">Отслеживание оповещений с высоким уровнем воздействия</span><span class="sxs-lookup"><span data-stu-id="1087b-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="1087b-110">Каждому оповещению Microsoft Defender для конечной точки соответствует степень серьезности (высокая, средняя, низкая или информационная).</span><span class="sxs-lookup"><span data-stu-id="1087b-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="1087b-111">Это указывает на потенциальное влияние на сеть, если оставить ее безотвратно.</span><span class="sxs-lookup"><span data-stu-id="1087b-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="1087b-112">Используйте **карточку серьезности** оповещений устройства, чтобы сосредоточиться на более строгих оповещениях, которые могут требовать немедленного реагирования.</span><span class="sxs-lookup"><span data-stu-id="1087b-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="1087b-113">С этой карточки можно просмотреть дополнительные сведения на портале Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1087b-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Карточка серьезности оповещений устройства](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="1087b-115">Понимание источников оповещений</span><span class="sxs-lookup"><span data-stu-id="1087b-115">Understand sources of alerts</span></span>

<span data-ttu-id="1087b-116">Microsoft Defender для конечной точки использует данные из широкого диапазона датчиков безопасности и источников аналитики для создания оповещений.</span><span class="sxs-lookup"><span data-stu-id="1087b-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="1087b-117">Например, он может использовать сведения об обнаружении из антивирусной программы "Microsoft Defender" и сторонняя защита от вирусов.</span><span class="sxs-lookup"><span data-stu-id="1087b-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="1087b-118">Он также может использовать собственную настраиваемую аналитику угроз, предоставляемую через API веб-службы.</span><span class="sxs-lookup"><span data-stu-id="1087b-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="1087b-119">Карточка **источников обнаружения оповещений** устройства показывает распределение оповещений по источнику.</span><span class="sxs-lookup"><span data-stu-id="1087b-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="1087b-120">Отслеживание действий, связанных с определенными источниками, особенно настраиваемые источники.</span><span class="sxs-lookup"><span data-stu-id="1087b-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="1087b-121">Вы также можете использовать карточку, чтобы сосредоточиться на оповещениях от датчиков, которые не настроены для автоматического блокировки вредоносных действий или компонентов.</span><span class="sxs-lookup"><span data-stu-id="1087b-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![Карточка источников обнаружения оповещений устройства](../../media/device-alert-detection-sources.png)

<span data-ttu-id="1087b-123">С этой карточки можно просмотреть дополнительные сведения на портале Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1087b-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="1087b-124">Типы угроз, которые вызывают оповещения</span><span class="sxs-lookup"><span data-stu-id="1087b-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="1087b-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span><span class="sxs-lookup"><span data-stu-id="1087b-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="1087b-126">Например, обнаруженное действие с угрозой может быть классифицироваться как "другое перемещение", чтобы указать на то, что была предпринята попытка связаться с другими устройствами в сети.</span><span class="sxs-lookup"><span data-stu-id="1087b-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="1087b-127">Действие, скорее всего, произошло после того, как злоумышленники получили начальный foothold.</span><span class="sxs-lookup"><span data-stu-id="1087b-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="1087b-128">При обнаружении компонент угрозы может широко классифицироваться как вредоносная программа или, в частности, как определенный тип угрозы.</span><span class="sxs-lookup"><span data-stu-id="1087b-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="1087b-129">К ним относятся программы-вымогателя, кража учетных данных и другие типы вредоносных или нежелательных программ.</span><span class="sxs-lookup"><span data-stu-id="1087b-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="1087b-130">На **карточке категорий угроз устройства** показано распределение оповещений по этим категориям.</span><span class="sxs-lookup"><span data-stu-id="1087b-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="1087b-131">Используйте эту информацию для определения действий с угрозами, например попыток кражи учетных данных, которые обычно имеют большее влияние, чем попытки социальной инженерии.</span><span class="sxs-lookup"><span data-stu-id="1087b-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="1087b-132">Вы также можете отслеживать потенциально деструктивные угрозы, такие как программы-вымогателя.</span><span class="sxs-lookup"><span data-stu-id="1087b-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![Карточка категорий угроз устройств](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="1087b-134">Отслеживание активных оповещений</span><span class="sxs-lookup"><span data-stu-id="1087b-134">Monitor active alerts</span></span>

<span data-ttu-id="1087b-135">Карточка **состояния оповещений** устройства указывает количество оповещений, которые не были разрешены и могут требовать внимания.</span><span class="sxs-lookup"><span data-stu-id="1087b-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="1087b-136">С этой карточки можно просмотреть дополнительные сведения на портале Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1087b-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Карточка состояния оповещений устройства](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="1087b-138">Мониторинг классификации разрешенных оповещений</span><span class="sxs-lookup"><span data-stu-id="1087b-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="1087b-139">При разрешении оповещений в Microsoft Defender для конечной точки сотрудники службы безопасности могут указать, проверено ли оповещение как:</span><span class="sxs-lookup"><span data-stu-id="1087b-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="1087b-140">Настоящее оповещение, которое определяет фактические действия по нарушению безопасности или компоненты угроз</span><span class="sxs-lookup"><span data-stu-id="1087b-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="1087b-141">Ложное оповещение, которое неправильно обнаружило обычную активность</span><span class="sxs-lookup"><span data-stu-id="1087b-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="1087b-142">На **карточке классификации** оповещений устройства показано, были ли разрешенные оповещения классифицированы как истинные или ложные.</span><span class="sxs-lookup"><span data-stu-id="1087b-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="1087b-143">С этой карточки можно просмотреть дополнительные сведения на портале Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1087b-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="1087b-144">Примечание. В некоторых случаях сведения о классификации недоступны для определенных оповещений.</span><span class="sxs-lookup"><span data-stu-id="1087b-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Карточка классификации оповещений устройства](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="1087b-146">Отслеживание определения разрешенных оповещений</span><span class="sxs-lookup"><span data-stu-id="1087b-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="1087b-147">Помимо классификации того, является ли оповещение истинным или ложным при разрешении, сотрудники службы безопасности могут предоставить определение.</span><span class="sxs-lookup"><span data-stu-id="1087b-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="1087b-148">Определение указывает тип обычной или вредоносной активности, обнаруженной при проверке оповещения.</span><span class="sxs-lookup"><span data-stu-id="1087b-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="1087b-149">На **карточке определения оповещений** устройства показано определение, предоставленное для каждого оповещения.</span><span class="sxs-lookup"><span data-stu-id="1087b-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="1087b-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span><span class="sxs-lookup"><span data-stu-id="1087b-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="1087b-151">**Вредоносная** программа: вредоносный файл или код</span><span class="sxs-lookup"><span data-stu-id="1087b-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="1087b-152">**Персонал безопасности:** обычная активность, выполняемая сотрудниками службы безопасности</span><span class="sxs-lookup"><span data-stu-id="1087b-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="1087b-153">**Тестирование безопасности**: действия или компоненты, предназначенные для имитации фактических угроз и предназначенные для запуска датчиков безопасности и создания оповещений</span><span class="sxs-lookup"><span data-stu-id="1087b-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="1087b-154">**Нежелательное программное обеспечение:** приложения и другое программное обеспечение, которые не считаются вредоносными, но в противном случае нарушают политику или допустимые стандарты использования</span><span class="sxs-lookup"><span data-stu-id="1087b-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="1087b-155">**Others**: any other determination that doesn't fall under the provided types</span><span class="sxs-lookup"><span data-stu-id="1087b-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="1087b-156">На этой карточке можно просмотреть дополнительные сведения в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1087b-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Карточка определения оповещений устройства](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="1087b-158">Понять, какие устройства находятся под угрозой</span><span class="sxs-lookup"><span data-stu-id="1087b-158">Understand which devices are at risk</span></span>

<span data-ttu-id="1087b-159">**Защита устройств** показывает уровень риска для устройств.</span><span class="sxs-lookup"><span data-stu-id="1087b-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="1087b-160">Уровень риска зависит от таких факторов, как тип и серьезность оповещений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="1087b-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Карточка защиты устройств](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="1087b-162">Мониторинг и отчет о состоянии устройств, управляемых Intune</span><span class="sxs-lookup"><span data-stu-id="1087b-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="1087b-163">В следующих отчетах содержатся данные с устройств, зарегистрированных в Intune.</span><span class="sxs-lookup"><span data-stu-id="1087b-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="1087b-164">Данные с устройств, не включенных в нее, не включаются.</span><span class="sxs-lookup"><span data-stu-id="1087b-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="1087b-165">Только глобальные администраторы могут просматривать эти карточки.</span><span class="sxs-lookup"><span data-stu-id="1087b-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="1087b-166">Данные зарегистрированных устройств в Intune включают:</span><span class="sxs-lookup"><span data-stu-id="1087b-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="1087b-167">Соответствие устройства требованиям</span><span class="sxs-lookup"><span data-stu-id="1087b-167">Device compliance</span></span>
* <span data-ttu-id="1087b-168">Устройства с активным вредоносным ПО</span><span class="sxs-lookup"><span data-stu-id="1087b-168">Devices with active malware</span></span>
* <span data-ttu-id="1087b-169">Типы вредоносных программ на устройствах</span><span class="sxs-lookup"><span data-stu-id="1087b-169">Types of malware on devices</span></span>
* <span data-ttu-id="1087b-170">Вредоносные программы на устройствах</span><span class="sxs-lookup"><span data-stu-id="1087b-170">Malware on devices</span></span>
* <span data-ttu-id="1087b-171">Устройства с обнаружением вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="1087b-171">Devices with malware detections</span></span>
* <span data-ttu-id="1087b-172">Пользователи с обнаружением вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="1087b-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="1087b-173">Отслеживание соответствия устройств требованиям</span><span class="sxs-lookup"><span data-stu-id="1087b-173">Monitor device compliance</span></span>

<span data-ttu-id="1087b-174">**Соответствие устройств** требованиям показывает, сколько устройств, зарегистрированных в Intune, соответствуют политикам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1087b-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Карточка соответствия устройств требованиям](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="1087b-176">Обнаружение устройств с обнаружением вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="1087b-176">Discover devices with malware detections</span></span>

<span data-ttu-id="1087b-177">**Обнаружение вредоносных программ на** устройствах предоставляет количество зарегистрированных в Intune устройств с вредоносными программами, которые не были полностью разрешены.</span><span class="sxs-lookup"><span data-stu-id="1087b-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="1087b-178">Отсутствие разрешения может быть из-за ожидающих действий, перезагрузки, полной проверки, действий пользователя вручную или из-за того, что действие по исправлению не было успешно завершено.</span><span class="sxs-lookup"><span data-stu-id="1087b-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![Карта обнаружения вредоносных программ на устройстве](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="1087b-180">Понять, какие типы вредоносных программ обнаружены</span><span class="sxs-lookup"><span data-stu-id="1087b-180">Understand the types of malware detected</span></span>

<span data-ttu-id="1087b-181">**Типы вредоносных программ на устройствах** показывают различные виды вредоносных программ, обнаруженных на устройствах, зарегистрированных в Intune.</span><span class="sxs-lookup"><span data-stu-id="1087b-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="1087b-182">Вы можете изучить каждый тип в Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1087b-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![Типы вредоносных программ на карточках устройств](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="1087b-184">Понять, какие вредоносные программы обнаружены на ваших устройствах</span><span class="sxs-lookup"><span data-stu-id="1087b-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="1087b-185">**Вредоносные программы на устройствах** предоставляют список определенных вредоносных программ, обнаруженных на ваших устройствах.</span><span class="sxs-lookup"><span data-stu-id="1087b-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Карта вредоносного ПО на устройствах](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="1087b-187">Понять, на каких устройствах больше всего вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="1087b-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="1087b-188">**Устройства с обнаружением вредоносных программ** показывают, на каких устройствах обнаружено больше всего вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="1087b-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="1087b-189">В Центре безопасности Microsoft 365 вы можете выяснить, активна ли вредоносная программа, кто использует устройство, и состояние управления в Intune.</span><span class="sxs-lookup"><span data-stu-id="1087b-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Устройства с картой обнаружения вредоносных программ](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="1087b-191">Понять, какие пользователи имеют устройства с самыми вредоносными программами</span><span class="sxs-lookup"><span data-stu-id="1087b-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="1087b-192">**Пользователи с обнаружением вредоносных программ показывают** пользователей с устройствами, на которые было обнаружено больше всего вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="1087b-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="1087b-193">В Центре безопасности Microsoft 365 вы можете узнать, сколько устройств назначено каждому пользователю, а также дополнительные сведения о каждом устройстве и типе вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="1087b-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Пользователи с картой обнаружения вредоносных программ](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="1087b-195">Мониторинг и управление развертыванием и обнаружением правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="1087b-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="1087b-196">[Правила уменьшения уязвимости (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) помогают предотвратить заражение устройств действиями и приложениями, которые обычно используются вредоносными программами, которые ищут эксплойт.</span><span class="sxs-lookup"><span data-stu-id="1087b-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="1087b-197">Эти правила определяют, когда и как запускаются исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="1087b-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="1087b-198">Например, вы можете предотвратить запуск загруженного исполняемого файла в JavaScript или VBScript, блокировать вызовы Win32 API из макросов Office или блокировать процессы, которые выполняются с USB-накопителей.</span><span class="sxs-lookup"><span data-stu-id="1087b-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Карта уменьшения поверхности атаки](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="1087b-200">На карточке **Правила сокращения направлений атак** приведены общие сведения о развертывании правил на устройствах.</span><span class="sxs-lookup"><span data-stu-id="1087b-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="1087b-201">В верхнем столбце на этой карточке показано общее количество устройств, которые находятся в следующих режимах развертывания:</span><span class="sxs-lookup"><span data-stu-id="1087b-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="1087b-202">**Режим блокировки:** устройства с по крайней мере одним правилом, настроенным для блокировки обнаруженной активности</span><span class="sxs-lookup"><span data-stu-id="1087b-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="1087b-203">**Режим аудита:** устройства без правил, блокируют обнаруженную активность, но хотя бы одно правило настроено для аудита обнаруженной активности</span><span class="sxs-lookup"><span data-stu-id="1087b-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="1087b-204">**Off**: devices with all ASR rules turned off</span><span class="sxs-lookup"><span data-stu-id="1087b-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="1087b-205">В нижней части этой карточки приведены параметры всех устройств, отсортированные по правилам.</span><span class="sxs-lookup"><span data-stu-id="1087b-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="1087b-206">На каждой панели указывается количество устройств, для которых настроено блокировка, обнаружение аудита или отключение правила полностью.</span><span class="sxs-lookup"><span data-stu-id="1087b-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="1087b-207">Просмотр обнаружений ASR</span><span class="sxs-lookup"><span data-stu-id="1087b-207">View ASR detections</span></span>

<span data-ttu-id="1087b-208">Чтобы просмотреть подробные сведения об обнаружении  правил ASR в сети, выберите "Просмотр обнаружений на карточке правил уменьшения поверхности **атаки".**</span><span class="sxs-lookup"><span data-stu-id="1087b-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="1087b-209">Откроется **вкладка "Обнаружения"** на странице подробного отчета.</span><span class="sxs-lookup"><span data-stu-id="1087b-209">The **Detections** tab in the detailed report page will open.</span></span>

![Вкладка "Обнаружения"](../../media/detections-tab.png)

<span data-ttu-id="1087b-211">На диаграмме в верхней части страницы показаны обнаружения с течением времени стека, которые были либо заблокированы, либо были аудитом.</span><span class="sxs-lookup"><span data-stu-id="1087b-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="1087b-212">В таблице внизу перечислены последние обнаруженные действия.</span><span class="sxs-lookup"><span data-stu-id="1087b-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="1087b-213">Чтобы понять, в чем заключаются обнаруженные действия, используйте следующие сведения в таблице:</span><span class="sxs-lookup"><span data-stu-id="1087b-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="1087b-214">**Обнаруженный файл**: файл, как правило, сценарий или документ, содержимое которого вызвало подозрительное действие атаки</span><span class="sxs-lookup"><span data-stu-id="1087b-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="1087b-215">**Rule**: name describing the attack activities the rule is designed to catch.</span><span class="sxs-lookup"><span data-stu-id="1087b-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="1087b-216">Ознакомьтесь с существующими правилами ASR</span><span class="sxs-lookup"><span data-stu-id="1087b-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="1087b-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span><span class="sxs-lookup"><span data-stu-id="1087b-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="1087b-218">Это может быть законное приложение, например веб-браузер, приложение Office или системное средство, например PowerShell</span><span class="sxs-lookup"><span data-stu-id="1087b-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="1087b-219">**Publisher**: поставщик, который выпустил исходный приложение</span><span class="sxs-lookup"><span data-stu-id="1087b-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="1087b-220">Просмотр параметров правил ASR устройства</span><span class="sxs-lookup"><span data-stu-id="1087b-220">Review device ASR rule settings</span></span>

<span data-ttu-id="1087b-221">На странице **отчета о правилах уменьшения** поверхности атаки перейдите на вкладку "Конфигурация", чтобы просмотреть параметры правил для отдельных устройств. </span><span class="sxs-lookup"><span data-stu-id="1087b-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="1087b-222">Выберите устройство, чтобы получить подробные сведения о том, находится ли каждое правило в режиме блокировки, режиме аудита или полностью отключено.</span><span class="sxs-lookup"><span data-stu-id="1087b-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Вкладка "Конфигурация"](../../media/configuration-tab.png)

<span data-ttu-id="1087b-224">Microsoft Intune предоставляет функции управления для правил ASR.</span><span class="sxs-lookup"><span data-stu-id="1087b-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="1087b-225">Если вы хотите обновить параметры, выберите  "Начало работы" в области "Настройка устройств" на вкладке, чтобы открыть управление устройствами в Intune. </span><span class="sxs-lookup"><span data-stu-id="1087b-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="1087b-226">Исключение файлов из правил ASR</span><span class="sxs-lookup"><span data-stu-id="1087b-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="1087b-227">Центр безопасности Microsoft 365 собирает [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) имена файлов, которые можно исключить из обнаружения с помощью правил уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="1087b-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="1087b-228">За исключением файлов можно уменьшить количество обнаружений ложных срабатывавай и более уверенно развертывать правила уменьшения направлений атаки в режиме блокировки.</span><span class="sxs-lookup"><span data-stu-id="1087b-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="1087b-229">Исключениями можно управлять в Microsoft Intune, но Центр безопасности Microsoft 365 предоставляет средство анализа, помогая понять файлы.</span><span class="sxs-lookup"><span data-stu-id="1087b-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="1087b-230">Чтобы начать сбор файлов для исключения, перейдите на вкладку **"Добавление** исключений" на странице отчета о правилах **уменьшения** поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="1087b-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="1087b-231">Средство анализирует обнаружение всех правил уменьшения поверхности атаки, но только некоторые правила [поддерживают исключения.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)</span><span class="sxs-lookup"><span data-stu-id="1087b-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Вкладка "Добавление исключений"](../../media/add-exclusions-tab.png)

<span data-ttu-id="1087b-233">В таблице перечислены все имена файлов, обнаруженные правилами уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="1087b-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="1087b-234">Вы можете выбрать файлы, чтобы просмотреть влияние их исключения:</span><span class="sxs-lookup"><span data-stu-id="1087b-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="1087b-235">Сколько меньше обнаружений</span><span class="sxs-lookup"><span data-stu-id="1087b-235">How many fewer detections</span></span>
* <span data-ttu-id="1087b-236">Сколько устройств сообщает об обнаружении</span><span class="sxs-lookup"><span data-stu-id="1087b-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="1087b-237">Чтобы получить список выбранных файлов с полными путями для исключения, выберите **"Получить пути исключения".**</span><span class="sxs-lookup"><span data-stu-id="1087b-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="1087b-238">Журналы для правила ASR Блокируют кражу учетных данных из подсистемы локального органа безопасности **Windows (lsass.exe)** и захватывают исходный код **lsass.exe.**</span><span class="sxs-lookup"><span data-stu-id="1087b-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="1087b-239">Это обычный системный файл, который захватывается как обнаруженный файл.</span><span class="sxs-lookup"><span data-stu-id="1087b-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="1087b-240">В результате в созданный список путей исключения будет включен этот файл.</span><span class="sxs-lookup"><span data-stu-id="1087b-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="1087b-241">Чтобы исключить файл, который инициирует это правило, **lsass.exe,** используйте путь к приложению-источнику вместо обнаруженного файла.</span><span class="sxs-lookup"><span data-stu-id="1087b-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="1087b-242">Чтобы найти исходные приложения, [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) запустите следующий запрос на расширенный поиск для этого правила (определенного по коду правила 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="1087b-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="1087b-243">Проверка файлов на исключение</span><span class="sxs-lookup"><span data-stu-id="1087b-243">Check files for exclusion</span></span>

<span data-ttu-id="1087b-244">Перед исключением файла из ASR рекомендуется проверить файл, чтобы определить, действительно ли он не является вредоносным.</span><span class="sxs-lookup"><span data-stu-id="1087b-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="1087b-245">Чтобы просмотреть файл, используйте страницу сведений о [файле](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1087b-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="1087b-246">На странице приводится информация о преобладание и коэффициент обнаружения вирусов VirusTotal.</span><span class="sxs-lookup"><span data-stu-id="1087b-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="1087b-247">Вы также можете использовать страницу для отправки файла для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="1087b-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="1087b-248">Чтобы найти обнаруженный файл в Центре безопасности Microsoft Defender, найдите все обнаружения ASR с помощью следующего запроса на расширенный поиск:</span><span class="sxs-lookup"><span data-stu-id="1087b-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="1087b-249">Используйте **SHA1** или **InitiatingProcessSHA1** в результатах для поиска файла с помощью универсальной панели поиска в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1087b-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
