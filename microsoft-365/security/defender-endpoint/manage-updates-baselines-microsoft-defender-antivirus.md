---
title: Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей
description: Управление получением антивирусная программа в Microsoft Defender защиты и обновлений продуктов.
keywords: обновления, базовые показатели безопасности, защита, обновления расписания, обновления сил, обновления мобильных устройств, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/04/2021
ms.openlocfilehash: 264a3b7a4a24c446048d6cfc6863f1ae9765566f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789187"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="690ba-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="690ba-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="690ba-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="690ba-105">**Applies to:**</span></span>

- [<span data-ttu-id="690ba-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="690ba-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="690ba-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="690ba-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="690ba-108">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="690ba-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="690ba-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="690ba-109">Security intelligence updates</span></span>
- <span data-ttu-id="690ba-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="690ba-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="690ba-111">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="690ba-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="690ba-112">Не забудьте обновить антивирусную защиту, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="690ba-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="690ba-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="690ba-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="690ba-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="690ba-114">Security intelligence updates</span></span>

<span data-ttu-id="690ba-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="690ba-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="690ba-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="690ba-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="690ba-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="690ba-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="690ba-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="690ba-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="690ba-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="690ba-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="690ba-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="690ba-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="690ba-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="690ba-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="690ba-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="690ba-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="690ba-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="690ba-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="690ba-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="690ba-124">Product updates</span></span>

<span data-ttu-id="690ba-125">антивирусная программа в Microsoft Defender требует ежемесячных обновлений [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (известный как обновления платформы) и будет получать основные обновления функций наряду с Windows 10 выпусками.</span><span class="sxs-lookup"><span data-stu-id="690ba-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="690ba-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="690ba-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="690ba-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="690ba-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="690ba-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="690ba-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="690ba-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="690ba-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="690ba-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="690ba-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="690ba-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="690ba-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="690ba-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="690ba-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="690ba-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="690ba-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="690ba-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="690ba-134">All our updates contain</span></span> 
- <span data-ttu-id="690ba-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="690ba-135">performance improvements;</span></span>
- <span data-ttu-id="690ba-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="690ba-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="690ba-137">улучшения интеграции (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="690ba-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="690ba-138">Май-2021 (платформа: 4.18.2105.4 | Двигатель: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="690ba-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="690ba-139">&ensp;Версия обновления аналитики безопасности: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="690ba-140">&ensp;Выпущено: **4 июня 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="690ba-141">&ensp;Платформа: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="690ba-142">&ensp;Двигатель: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="690ba-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="690ba-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-144">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-144">What's new</span></span>
- <span data-ttu-id="690ba-145">Улучшения мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="690ba-145">Improvements to behavior monitoring</span></span> 

### <a name="known-issues"></a><span data-ttu-id="690ba-146">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-146">Known Issues</span></span>
<span data-ttu-id="690ba-147">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-147">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="690ba-148">Апрель-2021 (платформа: 4.18.2104.14 | Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="690ba-148">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="690ba-149">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-149">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="690ba-150">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-150">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="690ba-151">&ensp;Платформа: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="690ba-151">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="690ba-152">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="690ba-153">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="690ba-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-154">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-154">What's new</span></span>
- <span data-ttu-id="690ba-155">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="690ba-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="690ba-156">Улучшенное обнаружение кейлоггера режима ядра</span><span class="sxs-lookup"><span data-stu-id="690ba-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-157">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-157">Known Issues</span></span>
<span data-ttu-id="690ba-158">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="690ba-159">Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="690ba-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="690ba-160">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="690ba-161">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-161">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="690ba-162">&ensp;Платформа: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="690ba-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="690ba-163">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="690ba-164">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="690ba-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-165">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-165">What's new</span></span>

- <span data-ttu-id="690ba-166">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="690ba-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="690ba-167">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="690ba-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="690ba-168">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="690ba-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-169">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-169">Known Issues</span></span>
<span data-ttu-id="690ba-170">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="690ba-171">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="690ba-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="690ba-172">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="690ba-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="690ba-173">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="690ba-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="690ba-174">Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="690ba-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="690ba-175">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="690ba-176">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="690ba-177">&ensp;Платформа: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="690ba-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="690ba-178">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="690ba-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="690ba-179">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-180">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-180">What's new</span></span>

- <span data-ttu-id="690ba-181">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="690ba-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="690ba-182">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="690ba-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-183">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-183">Known Issues</span></span>
<span data-ttu-id="690ba-184">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="690ba-185">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="690ba-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="690ba-186">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="690ba-187">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="690ba-188">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="690ba-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="690ba-189">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="690ba-190">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-191">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-191">What's new</span></span>

- <span data-ttu-id="690ba-192">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="690ba-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="690ba-193">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="690ba-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="690ba-194">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="690ba-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="690ba-195">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="690ba-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="690ba-196">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="690ba-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-197">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-197">Known Issues</span></span>
<span data-ttu-id="690ba-198">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="690ba-199">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="690ba-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="690ba-200">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="690ba-201">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="690ba-202">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="690ba-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="690ba-203">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="690ba-204">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-205">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-205">What's new</span></span>

- <span data-ttu-id="690ba-206">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="690ba-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-207">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-207">Known Issues</span></span>
<span data-ttu-id="690ba-208">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="690ba-209">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="690ba-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="690ba-210">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="690ba-211">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="690ba-212">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="690ba-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="690ba-213">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="690ba-214">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-215">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-215">What's new</span></span>

- <span data-ttu-id="690ba-216">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="690ba-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="690ba-217">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="690ba-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="690ba-218">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="690ba-219">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="690ba-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-220">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-220">Known Issues</span></span>

<span data-ttu-id="690ba-221">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="690ba-222">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="690ba-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="690ba-223">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="690ba-224">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="690ba-225">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="690ba-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="690ba-226">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="690ba-227">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-228">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-228">What's new</span></span>

- <span data-ttu-id="690ba-229">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="690ba-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="690ba-230">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="690ba-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="690ba-231">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="690ba-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="690ba-232">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="690ba-232">New management interfaces for:</span></span>
   - <span data-ttu-id="690ba-233">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="690ba-233">UDP Inspection</span></span>
   - <span data-ttu-id="690ba-234">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="690ba-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="690ba-235">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="690ba-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="690ba-236">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="690ba-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="690ba-237">Улучшенное сканирование Office VBA</span><span class="sxs-lookup"><span data-stu-id="690ba-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-238">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-238">Known Issues</span></span>

<span data-ttu-id="690ba-239">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="690ba-240">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="690ba-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="690ba-241">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="690ba-242">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="690ba-243">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="690ba-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="690ba-244">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="690ba-245">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="690ba-246">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-246">What's new</span></span>

- <span data-ttu-id="690ba-247">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="690ba-247">Add more telemetry events</span></span>
- <span data-ttu-id="690ba-248">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="690ba-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="690ba-249">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="690ba-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="690ba-250">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="690ba-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="690ba-251">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="690ba-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="690ba-252">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="690ba-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="690ba-253">антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="690ba-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="690ba-254">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-254">Known Issues</span></span>
<span data-ttu-id="690ba-255">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="690ba-256">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="690ba-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="690ba-257">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="690ba-258">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="690ba-259">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="690ba-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="690ba-260">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="690ba-261">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-262">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-262">What's new</span></span>

- <span data-ttu-id="690ba-263">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="690ba-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="690ba-264">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="690ba-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-265">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-265">Known Issues</span></span>
<span data-ttu-id="690ba-266">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="690ba-267">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="690ba-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="690ba-268">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="690ba-269">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="690ba-270">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="690ba-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="690ba-271">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="690ba-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="690ba-272">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-273">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-273">What's new</span></span>

- <span data-ttu-id="690ba-274">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="690ba-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="690ba-275">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="690ba-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="690ba-276">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="690ba-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="690ba-277">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="690ba-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="690ba-278">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="690ba-278">Fixed registry query</span></span> 
- <span data-ttu-id="690ba-279">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="690ba-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-280">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-280">Known Issues</span></span>
<span data-ttu-id="690ba-281">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="690ba-282">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="690ba-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="690ba-283">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="690ba-284">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="690ba-285">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="690ba-286">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="690ba-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="690ba-287">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-288">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-288">What's new</span></span>

- <span data-ttu-id="690ba-289">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="690ba-289">Improved logging for scan events</span></span>
- <span data-ttu-id="690ba-290">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="690ba-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="690ba-291">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="690ba-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="690ba-292">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="690ba-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="690ba-293">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="690ba-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="690ba-294">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="690ba-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-295">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-295">Known Issues</span></span>
<span data-ttu-id="690ba-296">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="690ba-297">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="690ba-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="690ba-298">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="690ba-299">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="690ba-300">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="690ba-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="690ba-301">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="690ba-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="690ba-302">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-303">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-303">What's new</span></span>
- <span data-ttu-id="690ba-304">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="690ba-304">WDfilter improvements</span></span>
- <span data-ttu-id="690ba-305">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="690ba-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="690ba-306">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="690ba-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="690ba-307">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="690ba-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="690ba-308">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="690ba-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="690ba-309">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="690ba-309">UEFI scan capability</span></span>
- <span data-ttu-id="690ba-310">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="690ba-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="690ba-311">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-311">Known Issues</span></span>
<span data-ttu-id="690ba-312">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="690ba-313">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="690ba-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="690ba-314">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="690ba-315">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="690ba-316">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="690ba-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="690ba-317">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="690ba-318">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="690ba-319">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-319">What's new</span></span>

- <span data-ttu-id="690ba-320">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="690ba-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="690ba-321">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="690ba-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="690ba-322">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="690ba-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="690ba-323">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="690ba-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="690ba-324">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="690ba-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="690ba-325">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-325">Known Issues</span></span>
<span data-ttu-id="690ba-326">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="690ba-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="690ba-327">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="690ba-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="690ba-328">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="690ba-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="690ba-329">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="690ba-330">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="690ba-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="690ba-331">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="690ba-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="690ba-332">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="690ba-333">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="690ba-334">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-334">Known Issues</span></span>
<span data-ttu-id="690ba-335">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="690ba-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="690ba-336">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="690ba-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="690ba-337">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="690ba-338">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="690ba-339">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="690ba-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="690ba-340">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="690ba-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="690ba-341">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="690ba-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="690ba-342">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-342">What's new</span></span>

- <span data-ttu-id="690ba-343">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="690ba-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="690ba-344">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="690ba-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="690ba-345">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="690ba-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="690ba-346">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="690ba-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="690ba-347">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="690ba-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="690ba-348">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-348">Known Issues</span></span>

<span data-ttu-id="690ba-349">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="690ba-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="690ba-350">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="690ba-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="690ba-351">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="690ba-351">This update is:</span></span>
> - <span data-ttu-id="690ba-352">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="690ba-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="690ba-353">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="690ba-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="690ba-354">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="690ba-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="690ba-355">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="690ba-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="690ba-356">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="690ba-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="690ba-357">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="690ba-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="690ba-358">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="690ba-359">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="690ba-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="690ba-360">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="690ba-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="690ba-361">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="690ba-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="690ba-362">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="690ba-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="690ba-363">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="690ba-363">What's new</span></span>

- <span data-ttu-id="690ba-364">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="690ba-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="690ba-365">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="690ba-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="690ba-366">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="690ba-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="690ba-367">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="690ba-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="690ba-368">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="690ba-368">Known Issues</span></span>
<span data-ttu-id="690ba-369">При установке этого обновления устройству требуется пакет скачок 4.10.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="690ba-369">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="690ba-370">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="690ba-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="690ba-371">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="690ba-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="690ba-372">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="690ba-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="690ba-373">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="690ba-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="690ba-374">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="690ba-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="690ba-375">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="690ba-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="690ba-376">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="690ba-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="690ba-377">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="690ba-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="690ba-378">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="690ba-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="690ba-379">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="690ba-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="690ba-380">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="690ba-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="690ba-381">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="690ba-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="690ba-382">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="690ba-382">Windows 10 release</span></span>  |<span data-ttu-id="690ba-383">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="690ba-383">Platform version</span></span>  |<span data-ttu-id="690ba-384">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="690ba-384">Engine version</span></span> |<span data-ttu-id="690ba-385">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="690ba-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="690ba-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="690ba-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="690ba-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="690ba-387">4.18.1909.6</span></span> |<span data-ttu-id="690ba-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="690ba-388">1.1.17000.2</span></span> | <span data-ttu-id="690ba-389">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="690ba-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="690ba-390">1909  (19H2)</span></span> |<span data-ttu-id="690ba-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="690ba-391">4.18.1902.5</span></span> |<span data-ttu-id="690ba-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="690ba-392">1.1.16700.3</span></span> | <span data-ttu-id="690ba-393">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="690ba-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="690ba-394">1903  (19H1)</span></span> |<span data-ttu-id="690ba-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="690ba-395">4.18.1902.5</span></span> |<span data-ttu-id="690ba-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="690ba-396">1.1.15600.4</span></span> | <span data-ttu-id="690ba-397">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="690ba-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="690ba-398">1809  (RS5)</span></span> |<span data-ttu-id="690ba-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="690ba-399">4.18.1807.18075</span></span> |<span data-ttu-id="690ba-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="690ba-400">1.1.15000.2</span></span> | <span data-ttu-id="690ba-401">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="690ba-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="690ba-402">1803  (RS4)</span></span> |<span data-ttu-id="690ba-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="690ba-403">4.13.17134.1</span></span> |<span data-ttu-id="690ba-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="690ba-404">1.1.14600.4</span></span> | <span data-ttu-id="690ba-405">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="690ba-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="690ba-406">1709  (RS3)</span></span> |<span data-ttu-id="690ba-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="690ba-407">4.12.16299.15</span></span> |<span data-ttu-id="690ba-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="690ba-408">1.1.14104.0</span></span> | <span data-ttu-id="690ba-409">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="690ba-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="690ba-410">1703  (RS2)</span></span> |<span data-ttu-id="690ba-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="690ba-411">4.11.15603.2</span></span> |<span data-ttu-id="690ba-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="690ba-412">1.1.13504.0</span></span> | <span data-ttu-id="690ba-413">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="690ba-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="690ba-414">1607 (RS1)</span></span> |<span data-ttu-id="690ba-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="690ba-415">4.10.14393.3683</span></span> |<span data-ttu-id="690ba-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="690ba-416">1.1.12805.0</span></span> | <span data-ttu-id="690ba-417">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="690ba-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="690ba-418">Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="690ba-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="690ba-419">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="690ba-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="690ba-420">Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="690ba-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="690ba-421">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="690ba-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="690ba-422">Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="690ba-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="690ba-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="690ba-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="690ba-424">&ensp;Версия пакета: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="690ba-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="690ba-425">&ensp;Версия платформы: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="690ba-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="690ba-426">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="690ba-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="690ba-427">&ensp;Версия подписи: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-428">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-428">Fixes</span></span>
- <span data-ttu-id="690ba-429">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-430">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-430">Additional information</span></span>
- <span data-ttu-id="690ba-431">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="690ba-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="690ba-433">&ensp;Версия пакета: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="690ba-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="690ba-434">&ensp;Версия платформы: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="690ba-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="690ba-435">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="690ba-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="690ba-436">&ensp;Версия подписи: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-437">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-437">Fixes</span></span>
- <span data-ttu-id="690ba-438">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-439">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-439">Additional information</span></span>
- <span data-ttu-id="690ba-440">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="690ba-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="690ba-442">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="690ba-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="690ba-443">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="690ba-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="690ba-444">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="690ba-445">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-446">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-446">Fixes</span></span>
- <span data-ttu-id="690ba-447">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-448">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-448">Additional information</span></span>
- <span data-ttu-id="690ba-449">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="690ba-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="690ba-451">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="690ba-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="690ba-452">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="690ba-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="690ba-453">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="690ba-454">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-455">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-455">Fixes</span></span>
- <span data-ttu-id="690ba-456">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-457">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-457">Additional information</span></span>
- <span data-ttu-id="690ba-458">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="690ba-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="690ba-460">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="690ba-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="690ba-461">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="690ba-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="690ba-462">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="690ba-463">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-464">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-464">Fixes</span></span>
- <span data-ttu-id="690ba-465">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-466">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-466">Additional information</span></span>
- <span data-ttu-id="690ba-467">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="690ba-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="690ba-469">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="690ba-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="690ba-470">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="690ba-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="690ba-471">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="690ba-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="690ba-472">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-473">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-473">Fixes</span></span>
- <span data-ttu-id="690ba-474">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-475">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-475">Additional information</span></span>
- <span data-ttu-id="690ba-476">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="690ba-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="690ba-478">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="690ba-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="690ba-479">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="690ba-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="690ba-480">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="690ba-481">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-482">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-482">Fixes</span></span>
- <span data-ttu-id="690ba-483">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-484">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-484">Additional information</span></span>
- <span data-ttu-id="690ba-485">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="690ba-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="690ba-487">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="690ba-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="690ba-488">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="690ba-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="690ba-489">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="690ba-490">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-491">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-491">Fixes</span></span>
- <span data-ttu-id="690ba-492">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-493">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-493">Additional information</span></span>
- <span data-ttu-id="690ba-494">Обновленные антивирусная программа в Microsoft Defender подписи</span><span class="sxs-lookup"><span data-stu-id="690ba-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="690ba-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="690ba-496">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="690ba-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="690ba-497">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="690ba-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="690ba-498">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="690ba-499">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-500">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-500">Fixes</span></span>
- <span data-ttu-id="690ba-501">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-502">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-502">Additional information</span></span>
- <span data-ttu-id="690ba-503">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="690ba-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="690ba-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="690ba-505">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="690ba-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="690ba-506">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="690ba-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="690ba-507">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="690ba-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="690ba-508">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="690ba-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="690ba-509">Исправления</span><span class="sxs-lookup"><span data-stu-id="690ba-509">Fixes</span></span>
- <span data-ttu-id="690ba-510">Нет</span><span class="sxs-lookup"><span data-stu-id="690ba-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="690ba-511">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="690ba-511">Additional information</span></span>
- <span data-ttu-id="690ba-512">Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.</span><span class="sxs-lookup"><span data-stu-id="690ba-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="690ba-513">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="690ba-513">Additional resources</span></span>

| <span data-ttu-id="690ba-514">Статья</span><span class="sxs-lookup"><span data-stu-id="690ba-514">Article</span></span> | <span data-ttu-id="690ba-515">Описание</span><span class="sxs-lookup"><span data-stu-id="690ba-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="690ba-516">Обновление Microsoft Defender для Windows изображений установки операционной системы</span><span class="sxs-lookup"><span data-stu-id="690ba-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="690ba-517">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="690ba-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="690ba-518">Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.</span><span class="sxs-lookup"><span data-stu-id="690ba-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="690ba-519">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="690ba-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="690ba-520">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="690ba-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="690ba-521">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="690ba-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="690ba-522">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="690ba-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="690ba-523">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="690ba-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="690ba-524">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="690ba-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="690ba-525">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="690ba-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="690ba-526">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="690ba-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="690ba-527">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="690ba-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="690ba-528">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="690ba-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
