---
title: Мониторинг устройств и создание отчетов в центре безопасности Майкрософт 365
description: В этой статье рассказывается о том, как можно хранить ваши устройства в надежном, актуальном и плашечных угрозах в Организации.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, устройства
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 149b3ab2f30d2387165dd98c0ba21eeac0fc8728
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910477"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="859d1-104">Мониторинг устройств и создание отчетов в центре безопасности Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="859d1-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="859d1-105">Обеспечьте безопасность и актуальность ваших устройств, а также возможность выявления потенциальных угроз в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="859d1-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="859d1-106">Просмотр оповещений устройства</span><span class="sxs-lookup"><span data-stu-id="859d1-106">View device alerts</span></span>

<span data-ttu-id="859d1-107">Получение обновленных предупреждений о действиях с нарушениями появления и других угрозах на устройствах из пакета ATP для Microsoft Defender (доступно с помощью лицензии "по").</span><span class="sxs-lookup"><span data-stu-id="859d1-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="859d1-108">Центр безопасности Microsoft 365 эффективно отслеживает эти оповещения на высоком уровне с помощью предпочтительного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="859d1-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="859d1-109">Отслеживание оповещений о высокой степени влияния</span><span class="sxs-lookup"><span data-stu-id="859d1-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="859d1-110">Каждое оповещение для защитника Microsoft Defender имеет соответствующее серьезность, среднюю, низкую или информационную, которая указывает на потенциальное влияние на сеть, если оно не указано в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="859d1-110">Each Microsoft Defender ATP alert has a corresponding severity�high, medium, low, or informational�that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="859d1-111">Используйте карточку **серьезности оповещений для устройств** , чтобы сосредоточиться на более серьезных оповещениях и может требовать немедленный отклик.</span><span class="sxs-lookup"><span data-stu-id="859d1-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="859d1-112">С помощью этой карточки вы можете просмотреть дополнительные сведения на портале Центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="859d1-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Карточка серьезности оповещений устройств](../images/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="859d1-114">Общие сведения об источниках оповещений</span><span class="sxs-lookup"><span data-stu-id="859d1-114">Understand sources of alerts</span></span>

<span data-ttu-id="859d1-115">Защитник Майкрософт использует данные из широкого спектра датчиков безопасности и источников аналитики для создания оповещений.</span><span class="sxs-lookup"><span data-stu-id="859d1-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="859d1-116">Например, он может использовать сведения об обнаружении антивирусной программы "Защитник Windows" и стороннего антивредоносного по, а также собственную логику, предоставляемую через API веб-службы.</span><span class="sxs-lookup"><span data-stu-id="859d1-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="859d1-117">В карточке источников **обнаружения оповещений для устройств** показано распределение оповещений по источнику.</span><span class="sxs-lookup"><span data-stu-id="859d1-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="859d1-118">С помощью этой карточки можно отслеживать действия, связанные с определенными источниками, в частности настраиваемые источники.</span><span class="sxs-lookup"><span data-stu-id="859d1-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="859d1-119">Кроме того, вы можете сосредоточиться на оповещениях, поступающих от датчиков, которые не настроены для автоматической блокировки вредоносных действий или компонентов.</span><span class="sxs-lookup"><span data-stu-id="859d1-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![Карточка источников обнаружения оповещений для устройств](../images/device-alert-detection-sources.png)

<span data-ttu-id="859d1-121">С помощью этой карточки вы можете просмотреть дополнительные сведения на портале Центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="859d1-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="859d1-122">Сведения о типах угроз, инициирующих оповещения</span><span class="sxs-lookup"><span data-stu-id="859d1-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="859d1-123">Защитник Майкрософт сортирует каждое оповещение в категории, представляющей определенный этап в цепочке атак, или тип компонента угрозы.</span><span class="sxs-lookup"><span data-stu-id="859d1-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="859d1-124">Например, обнаруженные действия по угрозе могут быть отнесены к Латерал перемещению, чтобы показать, что действие приводило к попытке получить доступ к другим устройствам в сети и, вероятно, произошло после того, как злоумышленник получит первоначальный фусолд.</span><span class="sxs-lookup"><span data-stu-id="859d1-124">For example, detected threat activity might be categorized into �lateral movement� to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="859d1-125">При обнаружении компонент для работы с угрозой может быть классифицирован в широком смысле как вредоносное или более конкретное, например, Кража учетных данных или другие типы вредоносных или нежелательных программ.</span><span class="sxs-lookup"><span data-stu-id="859d1-125">When detected, a threat component might either be classified broadly as �malware� or more specifically as �ransomware�, �credential stealing� or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="859d1-126">В карточке **категории угроз для устройств** показано распределение оповещений по этим категориям.</span><span class="sxs-lookup"><span data-stu-id="859d1-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="859d1-127">Эти сведения можно использовать для определения действий по угрозам, например попыток кражи учетных данных, которые могут значительно повлиять на появление попыток социального проектирования, например.</span><span class="sxs-lookup"><span data-stu-id="859d1-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="859d1-128">Кроме того, вы можете использовать эту возможность для отслеживания потенциально необратимых угроз, таких как шантажистом.</span><span class="sxs-lookup"><span data-stu-id="859d1-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![Карточка категорий угроз для устройств](../images/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="859d1-130">Отслеживание активных оповещений</span><span class="sxs-lookup"><span data-stu-id="859d1-130">Monitor active alerts</span></span>

<span data-ttu-id="859d1-131">Карточка **состояния оповещения для устройства** указывает количество оповещений, которые не были разрешены и могут потребовать внимания.</span><span class="sxs-lookup"><span data-stu-id="859d1-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="859d1-132">С помощью этой карточки вы можете просмотреть дополнительные сведения на портале Центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="859d1-132">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Карточка состояния оповещения для устройства](../images/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="859d1-134">Отслеживание классификации разрешенных оповещений</span><span class="sxs-lookup"><span data-stu-id="859d1-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="859d1-135">При разрешении оповещения Microsoft Defender ATP сотрудники могут указать, было ли оповещение проверено следующим образом:</span><span class="sxs-lookup"><span data-stu-id="859d1-135">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="859d1-136">Истинное оповещение, идентифицирующее реальные действия или компоненты угроз</span><span class="sxs-lookup"><span data-stu-id="859d1-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="859d1-137">Ложное оповещение, которое неправильно определило нормальные действия</span><span class="sxs-lookup"><span data-stu-id="859d1-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="859d1-138">На карточке **классификация оповещений устройств** показано, были ли разрешенные оповещения классифицированы как "истина" или "ложные".</span><span class="sxs-lookup"><span data-stu-id="859d1-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="859d1-139">С помощью этой карточки вы можете просмотреть дополнительные сведения на портале Центра безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="859d1-139">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="859d1-140">Примечание. в некоторых случаях сведения об классификации недоступны для определенных оповещений.</span><span class="sxs-lookup"><span data-stu-id="859d1-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Карточка классификации оповещений для устройств](../images/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="859d1-142">Отслеживание определения разрешенных оповещений</span><span class="sxs-lookup"><span data-stu-id="859d1-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="859d1-143">В дополнение к классификации того, является ли оповещение истинным или ложным во время разрешения, персонал по обеспечению безопасности может определить тип обычной или вредоносной активности, обнаруженной при проверке оповещения.</span><span class="sxs-lookup"><span data-stu-id="859d1-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="859d1-144">На карточке **определения оповещения для устройства** отображается определение, предоставленное для каждого оповещения, а именно:</span><span class="sxs-lookup"><span data-stu-id="859d1-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="859d1-145">**Апт** Advanced persistent Threat угроза, указывающая на то, что обнаруженное действие или компонент угроз является частью сложного нарушения безопасности, разработанного для получения фусолд в сети.</span><span class="sxs-lookup"><span data-stu-id="859d1-145">**APT** � advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="859d1-146">Вредоносный файл вредоносных **программ** или код</span><span class="sxs-lookup"><span data-stu-id="859d1-146">**Malware** � malicious file or code</span></span>
* <span data-ttu-id="859d1-147">**Нормальная работа персонала безопасности,** выполняемая сотрудниками по безопасности</span><span class="sxs-lookup"><span data-stu-id="859d1-147">**Security personnel** � normal activity performed by security staff</span></span>
* <span data-ttu-id="859d1-148">Действия по **тестированию системы безопасности** или компоненты, предназначенные для моделирования фактических угроз и ожидаемые для запуска датчиков безопасности и создания оповещений</span><span class="sxs-lookup"><span data-stu-id="859d1-148">**Security testing** � activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="859d1-149">**Нежелательные программные** приложения и другое программное обеспечение, которые не являются вредоносными, но в противном случае нарушают политику или допустимые стандарты использования</span><span class="sxs-lookup"><span data-stu-id="859d1-149">**Unwanted software** � apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="859d1-150">**Другие определения** , не попадающие в указанные типы</span><span class="sxs-lookup"><span data-stu-id="859d1-150">**Others** � any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="859d1-151">Из этой карточки вы можете просмотреть дополнительные сведения в центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="859d1-151">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Карточка определения оповещения для устройства](../images/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="859d1-153">Сведения о том, какие устройства подвержены риску</span><span class="sxs-lookup"><span data-stu-id="859d1-153">Understand which devices are at risk</span></span>

<span data-ttu-id="859d1-154">**Защита устройства** показывает уровень риска для устройств.</span><span class="sxs-lookup"><span data-stu-id="859d1-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="859d1-155">Уровень риска зависит от таких факторов, как тип и серьезность оповещений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="859d1-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Карта защиты устройства](../images/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="859d1-157">Отслеживание и отправка отчетов о состоянии устройств, управляемых Intune</span><span class="sxs-lookup"><span data-stu-id="859d1-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="859d1-158">Следующие отчеты содержат данные от устройств, зарегистрированных в Intune.</span><span class="sxs-lookup"><span data-stu-id="859d1-158">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="859d1-159">Данные из незарегистрированных устройств не входят в состав.</span><span class="sxs-lookup"><span data-stu-id="859d1-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="859d1-160">Просматривать эти карты могут только глобальные администраторы.</span><span class="sxs-lookup"><span data-stu-id="859d1-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="859d1-161">Данные устройства, зарегистрированные в Intune, включают:</span><span class="sxs-lookup"><span data-stu-id="859d1-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="859d1-162">Соответствие устройства требованиям</span><span class="sxs-lookup"><span data-stu-id="859d1-162">Device compliance</span></span>
* <span data-ttu-id="859d1-163">Устройства с активным вредоносным по</span><span class="sxs-lookup"><span data-stu-id="859d1-163">Devices with active malware</span></span>
* <span data-ttu-id="859d1-164">Типы вредоносных программ на устройствах</span><span class="sxs-lookup"><span data-stu-id="859d1-164">Types of malware on devices</span></span>
* <span data-ttu-id="859d1-165">Вредоносные программы на устройствах</span><span class="sxs-lookup"><span data-stu-id="859d1-165">Malware on devices</span></span>
* <span data-ttu-id="859d1-166">Устройства с обнаружением вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="859d1-166">Devices with malware detections</span></span>
* <span data-ttu-id="859d1-167">Пользователи с обнаружением вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="859d1-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="859d1-168">Отслеживание соответствия устройства требованиям</span><span class="sxs-lookup"><span data-stu-id="859d1-168">Monitor device compliance</span></span>

<span data-ttu-id="859d1-169">**Соответствие требованиям устройства** показывает, сколько устройств, зарегистрированных в Intune, соответствуют политикам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="859d1-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Карта соответствия требованиям устройств](../images/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="859d1-171">Обнаружение устройств с обнаружением вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="859d1-171">Discover devices with malware detections</span></span>

<span data-ttu-id="859d1-172">**Обнаружение вредоносных программ для устройств** предоставляет количество устройств, зарегистрированных в Intune, с вредоносными программами, которые не были полностью устранены в связи с ожидающими действиями перезапуска, полным сканированием или ручными действиями пользователя или в случае, если действие по исправлению не было выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="859d1-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions�a restart, a full scan or manual user actions�or if the remediation action did not complete successfully.</span></span>

![Карточка обнаружения вредоносных программ для устройств](../images/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="859d1-174">Сведения о типах обнаруженных вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="859d1-174">Understand the types of malware detected</span></span>

<span data-ttu-id="859d1-175">**Типы вредоносных программ на устройствах** показывают различные виды вредоносных программ, обнаруженных на устройствах, зарегистрированных в Intune.</span><span class="sxs-lookup"><span data-stu-id="859d1-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="859d1-176">Вы можете исследовать каждый тип в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="859d1-176">You can investigate each type in the Microsoft 365 security center.</span></span>

![Тип карты вредоносных программ на устройствах](../images/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="859d1-178">Общие сведения об определенных вредоносных программах, обнаруженных на устройствах</span><span class="sxs-lookup"><span data-stu-id="859d1-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="859d1-179">**Вредоносные программы на устройствах** предоставляет список определенных вредоносных программ, обнаруженных на устройствах.</span><span class="sxs-lookup"><span data-stu-id="859d1-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Карта вредоносных программ на устройствах](../images/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="859d1-181">Сведения о том, какие устройства имеют большинство вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="859d1-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="859d1-182">**Устройства с обнаружением вредоносных программ** показывают, какие устройства имеют большинство обнаружений вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="859d1-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="859d1-183">в центре безопасности Майкрософт 365 вы можете проверить, активна ли вредоносная программа, кто использует устройство и его состояние управления в Intune.</span><span class="sxs-lookup"><span data-stu-id="859d1-183">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Карточка с устройствами с обнаружением вредоносных программ](../images/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="859d1-185">Сведения о том, какие пользователи имеют устройства с большинством вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="859d1-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="859d1-186">**Пользователи с обнаружением вредоносных программ** показывают пользователей с устройствами, которые использовались с большинством обнаруженных вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="859d1-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="859d1-187">в центре безопасности Майкрософт 365 вы можете узнать, сколько устройств назначено каждому пользователю, и дополнительные сведения о каждом устройстве и о типе вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="859d1-187">in the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Пользователи с картой обнаружения вредоносных программ](../images/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="859d1-189">Мониторинг развертывания и обнаружения правил ASR и управление ими</span><span class="sxs-lookup"><span data-stu-id="859d1-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="859d1-190">[Правила предотвращения снижения уязвимости (ASR)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) помогают предотвратить действия и приложения, которые обычно используются вредоносной программой для проникновения устройств.</span><span class="sxs-lookup"><span data-stu-id="859d1-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="859d1-191">Эти правила определяют, когда и как запускаются исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="859d1-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="859d1-192">Например, вы можете предотвратить запуск загруженного исполняемого файла в JavaScript или VBScript, блокировать вызовы Win32 API из макросов Office или блокировать процессы, которые выполняются с USB-накопителей.</span><span class="sxs-lookup"><span data-stu-id="859d1-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Карточка о снижении уязвимости](../images/attack-surface-reduction-rules.png)

<span data-ttu-id="859d1-194">На карточке **Правила сокращения направлений атак** приведены общие сведения о развертывании правил на устройствах.</span><span class="sxs-lookup"><span data-stu-id="859d1-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="859d1-195">В верхнем столбце на этой карточке показано общее количество устройств, которые находятся в следующих режимах развертывания:</span><span class="sxs-lookup"><span data-stu-id="859d1-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="859d1-196">**Блочные** устройства с как минимум одним правилом, настроенными для блокирования обнаруженных действий</span><span class="sxs-lookup"><span data-stu-id="859d1-196">**Block mode** � devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="859d1-197">Устройства **режима аудита** без набора правил, блокирующие обнаруженные действия, но имеющие по крайней мере один набор правил для аудита обнаруженных действий</span><span class="sxs-lookup"><span data-stu-id="859d1-197">**Audit mode** � devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="859d1-198">**Отключение** устройств, для которых отключены все правила ASR</span><span class="sxs-lookup"><span data-stu-id="859d1-198">**Off** � devices with all ASR rules turned off</span></span>

<span data-ttu-id="859d1-199">В нижней части этой карточки приведены параметры всех устройств, отсортированные по правилам.</span><span class="sxs-lookup"><span data-stu-id="859d1-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="859d1-200">В каждом столбце указано количество устройств, для которых либо настроена блокировка или аудит обнаруженных действий, либо полностью отключено соответствующее правило.</span><span class="sxs-lookup"><span data-stu-id="859d1-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="859d1-201">Просмотр обнаруженных аварийных ASR</span><span class="sxs-lookup"><span data-stu-id="859d1-201">View ASR detections</span></span>

<span data-ttu-id="859d1-202">Чтобы просмотреть подробные сведения об обнаружении правил ASR в сети, выберите **Просмотр обнаружений** в карточке **правила уменьшения уязвимой зоны** .</span><span class="sxs-lookup"><span data-stu-id="859d1-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="859d1-203">Откроется вкладка **обнаружения** на странице подробный отчет.</span><span class="sxs-lookup"><span data-stu-id="859d1-203">The **Detections** tab in the detailed report page will open.</span></span>

![Вкладка "обнаружения"](../images/detections-tab.png)

<span data-ttu-id="859d1-205">На диаграмме, расположенной в верхней части страницы, показано обнаружение с обнаружением стеков по времени, которые были заблокированы или проверены.</span><span class="sxs-lookup"><span data-stu-id="859d1-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="859d1-206">В таблице внизу перечислены последние обнаруженные действия.</span><span class="sxs-lookup"><span data-stu-id="859d1-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="859d1-207">Чтобы понять, в чем заключаются обнаруженные действия, используйте следующие сведения в таблице:</span><span class="sxs-lookup"><span data-stu-id="859d1-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="859d1-208">**Обнаруженный файл** файл (как правило, сценарий или документ), содержимое которого активировало вероятные действия по атакам</span><span class="sxs-lookup"><span data-stu-id="859d1-208">**Detected file** � the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="859d1-209">Имя **правила** , описывающее действия, которые разрабатываются правилом для перехвата.</span><span class="sxs-lookup"><span data-stu-id="859d1-209">**Rule** � name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="859d1-210">Сведения о существующих правилах ASR</span><span class="sxs-lookup"><span data-stu-id="859d1-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="859d1-211">**Исходное приложение** приложение, которое загрузило или выполнило содержимое, вызывающее вероятные действия по атакам.</span><span class="sxs-lookup"><span data-stu-id="859d1-211">**Source app** � the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="859d1-212">Это может быть легальное приложение, например веб-браузер, приложение Office или системное средство, например PowerShell.</span><span class="sxs-lookup"><span data-stu-id="859d1-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="859d1-213">**Publisher** — поставщик, который освободил исходное приложение</span><span class="sxs-lookup"><span data-stu-id="859d1-213">**Publisher** � the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="859d1-214">Проверка параметров правил для устройства ASR</span><span class="sxs-lookup"><span data-stu-id="859d1-214">Review device ASR rule settings</span></span>

<span data-ttu-id="859d1-215">На странице отчета " **правила снижения уязвимости** " перейдите на вкладку **Конфигурация** , чтобы просмотреть параметры правил для отдельных устройств.</span><span class="sxs-lookup"><span data-stu-id="859d1-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="859d1-216">Выберите устройство, чтобы получить подробные сведения о том, находится ли каждое правило в режиме блокировки, режиме аудита или полном отключении.</span><span class="sxs-lookup"><span data-stu-id="859d1-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Вкладка "Конфигурация"](../images/configuration-tab.png)

<span data-ttu-id="859d1-218">Microsoft Intune предоставляет функции управления для правил ASR.</span><span class="sxs-lookup"><span data-stu-id="859d1-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="859d1-219">Если вы хотите обновить параметры, выберите **начать работу** в разделе **Настройка устройств** на вкладке, чтобы открыть компонент "Управление устройствами в Intune".</span><span class="sxs-lookup"><span data-stu-id="859d1-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="859d1-220">Исключение файлов из правил ASR</span><span class="sxs-lookup"><span data-stu-id="859d1-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="859d1-221">Центр безопасности Microsoft 365 собирает имена [файлов, которые могут потребоваться исключить](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) из обнаруженных правил по снижению уязвимости.</span><span class="sxs-lookup"><span data-stu-id="859d1-221">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="859d1-222">За счет исключения файлов можно сократить количество ложных срабатываний и более уверенно развернуть правила уменьшения уязвимой зоны в режиме блокировки.</span><span class="sxs-lookup"><span data-stu-id="859d1-222">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="859d1-223">Исключения управляются в Microsoft Intune, но центр обеспечения безопасности Microsoft 365 предоставляет средство анализа, помогающее ознакомиться с файлами.</span><span class="sxs-lookup"><span data-stu-id="859d1-223">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="859d1-224">Чтобы начать сбор файлов для исключения, перейдите на вкладку " **Добавление исключений** " на странице отчета " **правила уменьшения уязвимой зоны** ".</span><span class="sxs-lookup"><span data-stu-id="859d1-224">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="859d1-225">Средство анализирует обнаружение по всем правилам сокращения направлений атак, но [только некоторые правила поддерживают исключения](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="859d1-225">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).</span></span>

![Вкладка "Добавление исключений"](../images/add-exclusions-tab.png)

<span data-ttu-id="859d1-227">В таблице перечислены все имена файлов, обнаруженные правилами сокращения для атак на уязвимую зону.</span><span class="sxs-lookup"><span data-stu-id="859d1-227">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="859d1-228">Вы можете выбрать файлы, чтобы проанализировать последствия их исключения:</span><span class="sxs-lookup"><span data-stu-id="859d1-228">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="859d1-229">Сколько меньше обнаруженных обнаружений</span><span class="sxs-lookup"><span data-stu-id="859d1-229">How many fewer detections</span></span>
* <span data-ttu-id="859d1-230">Сколько устройств сообщает об обнаружении</span><span class="sxs-lookup"><span data-stu-id="859d1-230">How many fewer devices report the detections</span></span>

<span data-ttu-id="859d1-231">Чтобы получить список выбранных файлов с полными путями для исключения, выберите пункт **Получение путей исключения**.</span><span class="sxs-lookup"><span data-stu-id="859d1-231">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="859d1-232">Журналы для **переноса учетных данных блока правил ASR из подсистемы Windows Local Security Authority (LSASS. exe)** захватывает исходное приложение **LSASS. exe**, обычный системный файл, как обнаруженный файл.</span><span class="sxs-lookup"><span data-stu-id="859d1-232">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="859d1-233">В результате созданный список исключаемых путей будет содержать этот файл.</span><span class="sxs-lookup"><span data-stu-id="859d1-233">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="859d1-234">Чтобы исключить файл, который инициировал это правило, а не **LSASS. exe**, используйте путь к исходному приложению, а не к обнаруженному файлу.</span><span class="sxs-lookup"><span data-stu-id="859d1-234">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="859d1-235">Чтобы найти исходное приложение, выполните следующий [Расширенный запрос поиска](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) для этого конкретного правила (определяемого с помощью идентификатора правила 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="859d1-235">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="859d1-236">Проверка файлов для исключения</span><span class="sxs-lookup"><span data-stu-id="859d1-236">Check files for exclusion</span></span>
<span data-ttu-id="859d1-237">Перед исключением файла из ASR рекомендуется проверить его, чтобы определить, не является ли он вредоносным.</span><span class="sxs-lookup"><span data-stu-id="859d1-237">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="859d1-238">Чтобы просмотреть файл, используйте [страницу сведений о файле](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) в центре безопасности защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="859d1-238">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="859d1-239">На странице предоставляются сведения о распространении, а также степень обнаружения антивирусной программы Вирустотал.</span><span class="sxs-lookup"><span data-stu-id="859d1-239">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="859d1-240">Вы также можете использовать эту страницу для передачи файла для детального анализа.</span><span class="sxs-lookup"><span data-stu-id="859d1-240">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="859d1-241">Чтобы найти обнаруженный файл в центре безопасности защитника Майкрософт, выполните поиск всех обнаружений ASR, используя следующий Расширенный запрос поиска:</span><span class="sxs-lookup"><span data-stu-id="859d1-241">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="859d1-242">Используйте **SHA1** или **InitiatingProcessSHA1** в результатах поиска файла с помощью универсальной панели поиска в центре безопасности защитника Microsoft.</span><span class="sxs-lookup"><span data-stu-id="859d1-242">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>