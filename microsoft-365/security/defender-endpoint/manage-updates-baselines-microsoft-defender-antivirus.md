---
title: Управление обновлениями антивируса Microsoft Defender и применение базовых показателей
description: Управление тем, как антивирус Microsoft Defender получает защиту и обновления продуктов.
keywords: обновления, базовые показатели безопасности, защита, обновления расписания, обновления сил, обновления мобильных устройств, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690979"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="13416-104">Управление обновлениями антивируса Microsoft Defender и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="13416-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="13416-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="13416-105">**Applies to:**</span></span>

- [<span data-ttu-id="13416-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="13416-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="13416-107">Антивирус Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="13416-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="13416-108">Существует два типа обновлений, связанных с обновлением антивируса Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="13416-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="13416-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="13416-109">Security intelligence updates</span></span>
- <span data-ttu-id="13416-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="13416-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13416-111">Обновление антивируса Microsoft Defender имеет решающее значение для обеспечения того, чтобы устройства были оснащены новейшими технологиями и функциями, необходимыми для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="13416-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="13416-112">Не забудьте обновить антивирусную защиту, даже если антивирус Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="13416-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="13416-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивируса Microsoft Defender и других [антивирусных программ Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="13416-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="13416-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="13416-114">Security intelligence updates</span></span>

<span data-ttu-id="13416-115">Антивирус Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="13416-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="13416-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="13416-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="13416-117">Антивирус Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="13416-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="13416-118">Защита конечных точек центра системы: KB2461484</span><span class="sxs-lookup"><span data-stu-id="13416-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="13416-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="13416-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="13416-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="13416-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="13416-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13416-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="13416-122">Список последних обновлений разведки безопасности см. в перечне обновлений службы безопасности для [антивируса Microsoft Defender и](https://www.microsoft.com/en-us/wdsi/defenderupdates)других антивирусных программ Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="13416-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="13416-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="13416-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="13416-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="13416-124">Product updates</span></span>

<span data-ttu-id="13416-125">Антивирус Microsoft Defender требует ежемесячных обновлений [(KB4052623) (известный](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) как обновления платформы) и будет получать основные обновления функций наряду с выпусками Windows 10. </span><span class="sxs-lookup"><span data-stu-id="13416-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="13416-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="13416-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="13416-127">Служба обновления Windows Server (WSUS)</span><span class="sxs-lookup"><span data-stu-id="13416-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="13416-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="13416-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="13416-129">Обычный метод, который используется для развертывания обновлений Microsoft и Windows в конечных точках сети.</span><span class="sxs-lookup"><span data-stu-id="13416-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="13416-130">Дополнительные сведения см. в [ссылке Управление источниками обновлений антивирусной](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)защиты Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="13416-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="13416-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="13416-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="13416-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="13416-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="13416-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="13416-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="13416-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="13416-134">All our updates contain</span></span> 
- <span data-ttu-id="13416-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="13416-135">performance improvements;</span></span>
- <span data-ttu-id="13416-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="13416-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="13416-137">улучшения интеграции (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="13416-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="13416-138">Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="13416-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="13416-139">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="13416-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="13416-140">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="13416-141">&ensp;Платформа: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="13416-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="13416-142">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="13416-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="13416-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="13416-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-144">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-144">What's new</span></span>

- <span data-ttu-id="13416-145">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="13416-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="13416-146">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="13416-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="13416-147">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="13416-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-148">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-148">Known Issues</span></span>
<span data-ttu-id="13416-149">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="13416-150">Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="13416-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="13416-151">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="13416-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="13416-152">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="13416-153">&ensp;Платформа: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="13416-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="13416-154">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="13416-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="13416-155">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="13416-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-156">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-156">What's new</span></span>

- <span data-ttu-id="13416-157">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="13416-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="13416-158">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="13416-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-159">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-159">Known Issues</span></span>
<span data-ttu-id="13416-160">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="13416-161">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="13416-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="13416-162">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="13416-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="13416-163">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="13416-164">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="13416-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="13416-165">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="13416-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="13416-166">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="13416-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-167">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-167">What's new</span></span>

- <span data-ttu-id="13416-168">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="13416-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="13416-169">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="13416-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="13416-170">Улучшения функций по борьбе с вирусами в антивирусных службах Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="13416-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="13416-171">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="13416-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="13416-172">Исправление: уведомление блока EDR остается в истории угроз после обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="13416-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-173">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-173">Known Issues</span></span>
<span data-ttu-id="13416-174">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="13416-175">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="13416-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="13416-176">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="13416-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="13416-177">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="13416-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="13416-178">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="13416-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="13416-179">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="13416-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="13416-180">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="13416-181">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="13416-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="13416-182">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="13416-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="13416-183">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="13416-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-184">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-184">What's new</span></span>

- <span data-ttu-id="13416-185">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="13416-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-186">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-186">Known Issues</span></span>
<span data-ttu-id="13416-187">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="13416-188">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="13416-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="13416-189">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="13416-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="13416-190">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="13416-191">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="13416-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="13416-192">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="13416-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="13416-193">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="13416-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-194">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-194">What's new</span></span>

- <span data-ttu-id="13416-195">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="13416-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="13416-196">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="13416-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="13416-197">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="13416-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="13416-198">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="13416-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-199">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-199">Known Issues</span></span>

<span data-ttu-id="13416-200">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="13416-201">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="13416-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="13416-202">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="13416-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="13416-203">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="13416-204">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="13416-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="13416-205">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="13416-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="13416-206">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-207">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-207">What's new</span></span>

- <span data-ttu-id="13416-208">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="13416-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="13416-209">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="13416-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="13416-210">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="13416-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="13416-211">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="13416-211">New management interfaces for:</span></span>
   - <span data-ttu-id="13416-212">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="13416-212">UDP Inspection</span></span>
   - <span data-ttu-id="13416-213">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="13416-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="13416-214">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="13416-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="13416-215">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="13416-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="13416-216">Улучшенное сканирование модулей VBA Office</span><span class="sxs-lookup"><span data-stu-id="13416-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-217">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-217">Known Issues</span></span>

<span data-ttu-id="13416-218">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="13416-219">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="13416-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="13416-220">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="13416-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="13416-221">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="13416-222">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="13416-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="13416-223">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="13416-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="13416-224">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="13416-225">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-225">What's new</span></span>

- <span data-ttu-id="13416-226">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="13416-226">Add more telemetry events</span></span>
- <span data-ttu-id="13416-227">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="13416-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="13416-228">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="13416-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="13416-229">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="13416-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="13416-230">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="13416-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="13416-231">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="13416-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="13416-232">Антивирус Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="13416-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="13416-233">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-233">Known Issues</span></span>
<span data-ttu-id="13416-234">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="13416-235">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="13416-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="13416-236">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="13416-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="13416-237">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="13416-238">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="13416-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="13416-239">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="13416-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="13416-240">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-241">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-241">What's new</span></span>

- <span data-ttu-id="13416-242">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="13416-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="13416-243">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="13416-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-244">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-244">Known Issues</span></span>
<span data-ttu-id="13416-245">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="13416-246">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="13416-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="13416-247">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="13416-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="13416-248">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="13416-249">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="13416-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="13416-250">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="13416-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="13416-251">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-252">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-252">What's new</span></span>

- <span data-ttu-id="13416-253">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="13416-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="13416-254">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="13416-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="13416-255">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="13416-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="13416-256">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="13416-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="13416-257">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="13416-257">Fixed registry query</span></span> 
- <span data-ttu-id="13416-258">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="13416-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-259">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-259">Known Issues</span></span>
<span data-ttu-id="13416-260">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="13416-261">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="13416-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="13416-262">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="13416-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="13416-263">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="13416-264">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="13416-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="13416-265">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="13416-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="13416-266">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-267">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-267">What's new</span></span>

- <span data-ttu-id="13416-268">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="13416-268">Improved logging for scan events</span></span>
- <span data-ttu-id="13416-269">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="13416-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="13416-270">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="13416-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="13416-271">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="13416-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="13416-272">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="13416-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="13416-273">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="13416-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-274">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-274">Known Issues</span></span>
<span data-ttu-id="13416-275">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="13416-276">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="13416-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="13416-277">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="13416-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="13416-278">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="13416-279">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="13416-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="13416-280">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="13416-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="13416-281">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-282">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-282">What's new</span></span>
- <span data-ttu-id="13416-283">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="13416-283">WDfilter improvements</span></span>
- <span data-ttu-id="13416-284">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="13416-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="13416-285">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="13416-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="13416-286">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="13416-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="13416-287">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="13416-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="13416-288">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="13416-288">UEFI scan capability</span></span>
- <span data-ttu-id="13416-289">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="13416-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="13416-290">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-290">Known Issues</span></span>
<span data-ttu-id="13416-291">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="13416-292">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="13416-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="13416-293">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="13416-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="13416-294">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="13416-295">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="13416-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="13416-296">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="13416-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="13416-297">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="13416-298">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-298">What's new</span></span>

- <span data-ttu-id="13416-299">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13416-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="13416-300">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="13416-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="13416-301">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="13416-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="13416-302">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="13416-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="13416-303">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="13416-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="13416-304">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-304">Known Issues</span></span>
<span data-ttu-id="13416-305">**[Исправлено]** Антивирус Microsoft Defender пропускает файлы при проверке.</span><span class="sxs-lookup"><span data-stu-id="13416-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="13416-306">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="13416-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="13416-307">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="13416-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="13416-308">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="13416-309">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="13416-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="13416-310">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="13416-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="13416-311">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="13416-312">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="13416-313">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-313">Known Issues</span></span>
<span data-ttu-id="13416-314">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="13416-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="13416-315">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="13416-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="13416-316">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="13416-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="13416-317">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="13416-318">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="13416-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="13416-319">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="13416-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="13416-320">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="13416-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="13416-321">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-321">What's new</span></span>

- <span data-ttu-id="13416-322">Исправленная BSOD на WS2016 с помощью Exchange</span><span class="sxs-lookup"><span data-stu-id="13416-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="13416-323">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="13416-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="13416-324">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="13416-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="13416-325">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="13416-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="13416-326">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="13416-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="13416-327">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-327">Known Issues</span></span>

<span data-ttu-id="13416-328">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="13416-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="13416-329">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="13416-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="13416-330">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="13416-330">This update is:</span></span>
> - <span data-ttu-id="13416-331">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="13416-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="13416-332">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="13416-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="13416-333">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="13416-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="13416-334">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="13416-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="13416-335">предлагается только с [обновлением Windows.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="13416-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="13416-336">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="13416-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="13416-337">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="13416-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="13416-338">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="13416-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="13416-339">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="13416-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="13416-340">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="13416-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="13416-341">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="13416-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="13416-342">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="13416-342">What's new</span></span>

- <span data-ttu-id="13416-343">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="13416-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="13416-344">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="13416-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="13416-345">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="13416-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="13416-346">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="13416-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="13416-347">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="13416-347">Known Issues</span></span>
<span data-ttu-id="13416-348">При установке этого обновления устройству требуется пакет скачок 4.10.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="13416-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="13416-349">Поддержка антивирусной платформы Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="13416-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="13416-350">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="13416-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="13416-351">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="13416-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="13416-352">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="13416-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="13416-353">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="13416-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="13416-354">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="13416-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="13416-355">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="13416-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="13416-356">\* Будет по-прежнему предоставляться техническая поддержка обновлений из версии выпуска Windows 10 (см. версию Platform, включенную в [выпуски Windows 10)](#platform-version-included-with-windows-10-releases)до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="13416-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="13416-357">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="13416-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="13416-358">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="13416-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="13416-359">Версия платформы, включенная в выпуски Windows 10</span><span class="sxs-lookup"><span data-stu-id="13416-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="13416-360">В приведенной ниже таблице приведены антивирусная платформа и версии двигателей Microsoft Defender, которые поставляются с последними версиями Windows 10:</span><span class="sxs-lookup"><span data-stu-id="13416-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="13416-361">Выпуск Windows 10</span><span class="sxs-lookup"><span data-stu-id="13416-361">Windows 10 release</span></span>  |<span data-ttu-id="13416-362">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="13416-362">Platform version</span></span>  |<span data-ttu-id="13416-363">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="13416-363">Engine version</span></span> |<span data-ttu-id="13416-364">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="13416-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="13416-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="13416-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="13416-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="13416-366">4.18.1909.6</span></span> |<span data-ttu-id="13416-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="13416-367">1.1.17000.2</span></span> | <span data-ttu-id="13416-368">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="13416-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="13416-369">1909  (19H2)</span></span> |<span data-ttu-id="13416-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="13416-370">4.18.1902.5</span></span> |<span data-ttu-id="13416-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="13416-371">1.1.16700.3</span></span> | <span data-ttu-id="13416-372">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="13416-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="13416-373">1903  (19H1)</span></span> |<span data-ttu-id="13416-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="13416-374">4.18.1902.5</span></span> |<span data-ttu-id="13416-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="13416-375">1.1.15600.4</span></span> | <span data-ttu-id="13416-376">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="13416-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="13416-377">1809  (RS5)</span></span> |<span data-ttu-id="13416-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="13416-378">4.18.1807.18075</span></span> |<span data-ttu-id="13416-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="13416-379">1.1.15000.2</span></span> | <span data-ttu-id="13416-380">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="13416-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="13416-381">1803  (RS4)</span></span> |<span data-ttu-id="13416-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="13416-382">4.13.17134.1</span></span> |<span data-ttu-id="13416-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="13416-383">1.1.14600.4</span></span> | <span data-ttu-id="13416-384">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="13416-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="13416-385">1709  (RS3)</span></span> |<span data-ttu-id="13416-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="13416-386">4.12.16299.15</span></span> |<span data-ttu-id="13416-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="13416-387">1.1.14104.0</span></span> | <span data-ttu-id="13416-388">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="13416-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="13416-389">1703  (RS2)</span></span> |<span data-ttu-id="13416-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="13416-390">4.11.15603.2</span></span> |<span data-ttu-id="13416-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="13416-391">1.1.13504.0</span></span> | <span data-ttu-id="13416-392">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="13416-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="13416-393">1607 (RS1)</span></span> |<span data-ttu-id="13416-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="13416-394">4.10.14393.3683</span></span> |<span data-ttu-id="13416-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="13416-395">1.1.12805.0</span></span> | <span data-ttu-id="13416-396">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="13416-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="13416-397">Сведения о выпуске Windows 10 см. в листе фактов [жизненного цикла Windows.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="13416-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="13416-398">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="13416-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="13416-399">Рекомендуется обновить изображения установки Windows 10 (корпоративные, профессиональные и домашние выпуски), Windows Server 2019 и Windows Server 2016 с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="13416-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="13416-400">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="13416-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="13416-401">Дополнительные сведения см. в [обновлении Microsoft Defender для изображений установки операционной системы Windows.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="13416-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="13416-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="13416-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="13416-403">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="13416-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="13416-404">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="13416-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="13416-405">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="13416-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="13416-406">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="13416-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-407">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-407">Fixes</span></span>
- <span data-ttu-id="13416-408">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-409">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-409">Additional information</span></span>
- <span data-ttu-id="13416-410">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="13416-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="13416-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="13416-412">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="13416-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="13416-413">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="13416-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="13416-414">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="13416-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="13416-415">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="13416-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-416">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-416">Fixes</span></span>
- <span data-ttu-id="13416-417">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-418">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-418">Additional information</span></span>
- <span data-ttu-id="13416-419">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="13416-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="13416-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="13416-421">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="13416-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="13416-422">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="13416-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="13416-423">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="13416-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="13416-424">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="13416-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-425">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-425">Fixes</span></span>
- <span data-ttu-id="13416-426">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-427">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-427">Additional information</span></span>
- <span data-ttu-id="13416-428">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="13416-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="13416-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="13416-430">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="13416-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="13416-431">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="13416-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="13416-432">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="13416-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="13416-433">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="13416-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-434">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-434">Fixes</span></span>
- <span data-ttu-id="13416-435">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-436">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-436">Additional information</span></span>
- <span data-ttu-id="13416-437">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="13416-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="13416-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="13416-439">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="13416-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="13416-440">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="13416-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="13416-441">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="13416-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="13416-442">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="13416-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-443">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-443">Fixes</span></span>
- <span data-ttu-id="13416-444">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-445">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-445">Additional information</span></span>
- <span data-ttu-id="13416-446">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="13416-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="13416-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="13416-448">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="13416-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="13416-449">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="13416-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="13416-450">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="13416-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="13416-451">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="13416-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-452">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-452">Fixes</span></span>
- <span data-ttu-id="13416-453">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-454">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-454">Additional information</span></span>
- <span data-ttu-id="13416-455">Обновленные антивирусные подписи Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="13416-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="13416-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="13416-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="13416-457">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="13416-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="13416-458">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="13416-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="13416-459">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="13416-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="13416-460">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="13416-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-461">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-461">Fixes</span></span>
- <span data-ttu-id="13416-462">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-463">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-463">Additional information</span></span>
- <span data-ttu-id="13416-464">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="13416-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="13416-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="13416-466">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="13416-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="13416-467">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="13416-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="13416-468">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="13416-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="13416-469">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="13416-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="13416-470">Исправления</span><span class="sxs-lookup"><span data-stu-id="13416-470">Fixes</span></span>
- <span data-ttu-id="13416-471">Нет</span><span class="sxs-lookup"><span data-stu-id="13416-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="13416-472">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="13416-472">Additional information</span></span>
- <span data-ttu-id="13416-473">Добавлена поддержка для Windows 10 RS1 или более поздней осмии установки изображений.</span><span class="sxs-lookup"><span data-stu-id="13416-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="13416-474">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="13416-474">Additional resources</span></span>

| <span data-ttu-id="13416-475">Статья</span><span class="sxs-lookup"><span data-stu-id="13416-475">Article</span></span> | <span data-ttu-id="13416-476">Описание</span><span class="sxs-lookup"><span data-stu-id="13416-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="13416-477">Обновление Microsoft Defender для изображений установки операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="13416-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="13416-478">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="13416-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="13416-479">Получите антивирусные обновления Microsoft Defender для Windows 10 (корпоративные, профессиональные и домашние выпуски), Windows Server 2019 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="13416-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="13416-480">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="13416-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="13416-481">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="13416-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="13416-482">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="13416-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="13416-483">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="13416-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="13416-484">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="13416-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="13416-485">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="13416-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="13416-486">Управление вынужденными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="13416-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="13416-487">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="13416-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="13416-488">Управление обновлениями для мобильных устройств и виртуальных машин (виртуальных машин)</span><span class="sxs-lookup"><span data-stu-id="13416-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="13416-489">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="13416-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
