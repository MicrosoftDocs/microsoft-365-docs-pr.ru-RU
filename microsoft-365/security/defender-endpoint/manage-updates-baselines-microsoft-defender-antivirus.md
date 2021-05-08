---
title: Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей
description: Управление получением антивирусная программа в Microsoft Defender защиты и обновлений продуктов.
keywords: обновления, базовые показатели безопасности, защита, обновления расписания, обновления сил, обновления мобильных устройств, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 92f903f750ea5e7f2cb971b535c50bfecced65a2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242316"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="54854-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="54854-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="54854-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="54854-105">**Applies to:**</span></span>

- [<span data-ttu-id="54854-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="54854-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="54854-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54854-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="54854-108">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="54854-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="54854-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="54854-109">Security intelligence updates</span></span>
- <span data-ttu-id="54854-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="54854-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54854-111">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="54854-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="54854-112">Не забудьте обновить антивирусную защиту, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="54854-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="54854-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="54854-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="54854-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="54854-114">Security intelligence updates</span></span>

<span data-ttu-id="54854-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="54854-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="54854-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="54854-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="54854-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="54854-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="54854-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="54854-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="54854-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="54854-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="54854-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="54854-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="54854-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="54854-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="54854-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="54854-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="54854-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="54854-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="54854-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="54854-124">Product updates</span></span>

<span data-ttu-id="54854-125">антивирусная программа в Microsoft Defender требует ежемесячных обновлений [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (известный как обновления платформы) и будет получать основные обновления функций наряду с Windows 10 выпусками.</span><span class="sxs-lookup"><span data-stu-id="54854-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="54854-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="54854-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="54854-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="54854-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="54854-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="54854-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="54854-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="54854-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="54854-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="54854-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="54854-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="54854-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="54854-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="54854-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="54854-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="54854-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="54854-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="54854-134">All our updates contain</span></span> 
- <span data-ttu-id="54854-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="54854-135">performance improvements;</span></span>
- <span data-ttu-id="54854-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="54854-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="54854-137">улучшения интеграции (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="54854-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="54854-138">Апрель-2021 (платформа: 4.19.2104.9| Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="54854-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="54854-139">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="54854-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="54854-140">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="54854-141">&ensp;Платформа: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="54854-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="54854-142">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="54854-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="54854-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="54854-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-144">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-144">What's new</span></span>
- <span data-ttu-id="54854-145">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="54854-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="54854-146">Улучшенное обнаружение кейлоггера режима ядра</span><span class="sxs-lookup"><span data-stu-id="54854-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-147">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-147">Known Issues</span></span>
<span data-ttu-id="54854-148">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-149">Март-2021 (платформа: 4.19.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="54854-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="54854-150">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="54854-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="54854-151">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="54854-152">&ensp;Платформа: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="54854-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="54854-153">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="54854-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="54854-154">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="54854-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-155">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-155">What's new</span></span>

- <span data-ttu-id="54854-156">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="54854-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="54854-157">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="54854-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="54854-158">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="54854-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-159">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-159">Known Issues</span></span>
<span data-ttu-id="54854-160">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="54854-161">Февраль-2021 (платформа: 4.19.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="54854-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="54854-162">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="54854-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="54854-163">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="54854-164">&ensp;Платформа: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="54854-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="54854-165">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="54854-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="54854-166">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="54854-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-167">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-167">What's new</span></span>

- <span data-ttu-id="54854-168">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="54854-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="54854-169">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="54854-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-170">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-170">Known Issues</span></span>
<span data-ttu-id="54854-171">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="54854-172">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="54854-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="54854-173">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="54854-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="54854-174">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="54854-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="54854-175">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="54854-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="54854-176">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="54854-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="54854-177">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="54854-178">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="54854-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="54854-179">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="54854-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="54854-180">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-181">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-181">What's new</span></span>

- <span data-ttu-id="54854-182">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="54854-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="54854-183">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="54854-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="54854-184">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="54854-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="54854-185">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="54854-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="54854-186">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="54854-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-187">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-187">Known Issues</span></span>
<span data-ttu-id="54854-188">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="54854-189">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="54854-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="54854-190">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="54854-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="54854-191">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="54854-192">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="54854-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="54854-193">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="54854-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="54854-194">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-195">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-195">What's new</span></span>

- <span data-ttu-id="54854-196">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="54854-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-197">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-197">Known Issues</span></span>
<span data-ttu-id="54854-198">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="54854-199">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="54854-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="54854-200">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="54854-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="54854-201">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="54854-202">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="54854-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="54854-203">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="54854-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="54854-204">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-205">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-205">What's new</span></span>

- <span data-ttu-id="54854-206">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="54854-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="54854-207">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="54854-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="54854-208">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="54854-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="54854-209">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="54854-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-210">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-210">Known Issues</span></span>

<span data-ttu-id="54854-211">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="54854-212">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="54854-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="54854-213">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="54854-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="54854-214">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="54854-215">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="54854-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="54854-216">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="54854-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="54854-217">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-218">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-218">What's new</span></span>

- <span data-ttu-id="54854-219">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="54854-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="54854-220">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="54854-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="54854-221">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="54854-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="54854-222">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="54854-222">New management interfaces for:</span></span>
   - <span data-ttu-id="54854-223">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="54854-223">UDP Inspection</span></span>
   - <span data-ttu-id="54854-224">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="54854-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="54854-225">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="54854-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="54854-226">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="54854-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="54854-227">Улучшенное сканирование Office VBA</span><span class="sxs-lookup"><span data-stu-id="54854-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-228">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-228">Known Issues</span></span>

<span data-ttu-id="54854-229">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="54854-230">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="54854-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="54854-231">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="54854-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="54854-232">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="54854-233">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="54854-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="54854-234">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="54854-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="54854-235">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="54854-236">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-236">What's new</span></span>

- <span data-ttu-id="54854-237">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="54854-237">Add more telemetry events</span></span>
- <span data-ttu-id="54854-238">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="54854-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="54854-239">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="54854-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="54854-240">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="54854-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="54854-241">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="54854-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="54854-242">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="54854-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="54854-243">антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="54854-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="54854-244">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-244">Known Issues</span></span>
<span data-ttu-id="54854-245">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-246">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="54854-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="54854-247">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="54854-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="54854-248">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="54854-249">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="54854-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="54854-250">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="54854-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="54854-251">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-252">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-252">What's new</span></span>

- <span data-ttu-id="54854-253">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="54854-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="54854-254">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="54854-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-255">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-255">Known Issues</span></span>
<span data-ttu-id="54854-256">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-257">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="54854-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="54854-258">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="54854-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="54854-259">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="54854-260">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="54854-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="54854-261">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="54854-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="54854-262">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-263">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-263">What's new</span></span>

- <span data-ttu-id="54854-264">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="54854-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="54854-265">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="54854-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="54854-266">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="54854-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="54854-267">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="54854-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="54854-268">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="54854-268">Fixed registry query</span></span> 
- <span data-ttu-id="54854-269">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="54854-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-270">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-270">Known Issues</span></span>
<span data-ttu-id="54854-271">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-272">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="54854-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="54854-273">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="54854-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="54854-274">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="54854-275">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="54854-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="54854-276">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="54854-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="54854-277">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-278">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-278">What's new</span></span>

- <span data-ttu-id="54854-279">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="54854-279">Improved logging for scan events</span></span>
- <span data-ttu-id="54854-280">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="54854-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="54854-281">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="54854-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="54854-282">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="54854-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="54854-283">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="54854-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="54854-284">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="54854-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-285">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-285">Known Issues</span></span>
<span data-ttu-id="54854-286">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-287">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="54854-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="54854-288">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="54854-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="54854-289">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="54854-290">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="54854-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="54854-291">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="54854-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="54854-292">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-293">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-293">What's new</span></span>
- <span data-ttu-id="54854-294">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="54854-294">WDfilter improvements</span></span>
- <span data-ttu-id="54854-295">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="54854-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="54854-296">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="54854-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="54854-297">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="54854-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="54854-298">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="54854-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="54854-299">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="54854-299">UEFI scan capability</span></span>
- <span data-ttu-id="54854-300">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="54854-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="54854-301">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-301">Known Issues</span></span>
<span data-ttu-id="54854-302">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-303">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="54854-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="54854-304">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="54854-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="54854-305">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="54854-306">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="54854-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="54854-307">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="54854-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="54854-308">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="54854-309">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-309">What's new</span></span>

- <span data-ttu-id="54854-310">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="54854-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="54854-311">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="54854-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="54854-312">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="54854-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="54854-313">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="54854-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="54854-314">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="54854-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="54854-315">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-315">Known Issues</span></span>
<span data-ttu-id="54854-316">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="54854-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="54854-317">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="54854-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="54854-318">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="54854-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="54854-319">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="54854-320">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="54854-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="54854-321">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="54854-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="54854-322">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="54854-323">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="54854-324">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-324">Known Issues</span></span>
<span data-ttu-id="54854-325">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="54854-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-326">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="54854-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="54854-327">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="54854-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="54854-328">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="54854-329">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="54854-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="54854-330">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="54854-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="54854-331">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="54854-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="54854-332">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-332">What's new</span></span>

- <span data-ttu-id="54854-333">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="54854-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="54854-334">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="54854-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="54854-335">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="54854-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="54854-336">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="54854-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="54854-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="54854-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="54854-338">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-338">Known Issues</span></span>

<span data-ttu-id="54854-339">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="54854-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="54854-340">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="54854-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="54854-341">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="54854-341">This update is:</span></span>
> - <span data-ttu-id="54854-342">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="54854-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="54854-343">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="54854-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="54854-344">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="54854-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="54854-345">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="54854-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="54854-346">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="54854-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="54854-347">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="54854-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="54854-348">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="54854-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="54854-349">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="54854-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="54854-350">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="54854-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="54854-351">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="54854-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="54854-352">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="54854-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="54854-353">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="54854-353">What's new</span></span>

- <span data-ttu-id="54854-354">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="54854-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="54854-355">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="54854-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="54854-356">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="54854-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="54854-357">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="54854-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="54854-358">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="54854-358">Known Issues</span></span>
<span data-ttu-id="54854-359">При установке этого обновления устройству требуется пакет скачок 4.10.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="54854-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="54854-360">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="54854-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="54854-361">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="54854-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="54854-362">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="54854-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="54854-363">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="54854-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="54854-364">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="54854-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="54854-365">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="54854-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="54854-366">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="54854-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="54854-367">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="54854-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="54854-368">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="54854-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="54854-369">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="54854-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="54854-370">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="54854-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="54854-371">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="54854-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="54854-372">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="54854-372">Windows 10 release</span></span>  |<span data-ttu-id="54854-373">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="54854-373">Platform version</span></span>  |<span data-ttu-id="54854-374">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="54854-374">Engine version</span></span> |<span data-ttu-id="54854-375">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="54854-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="54854-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="54854-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="54854-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="54854-377">4.18.1909.6</span></span> |<span data-ttu-id="54854-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="54854-378">1.1.17000.2</span></span> | <span data-ttu-id="54854-379">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="54854-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="54854-380">1909  (19H2)</span></span> |<span data-ttu-id="54854-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="54854-381">4.18.1902.5</span></span> |<span data-ttu-id="54854-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="54854-382">1.1.16700.3</span></span> | <span data-ttu-id="54854-383">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="54854-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="54854-384">1903  (19H1)</span></span> |<span data-ttu-id="54854-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="54854-385">4.18.1902.5</span></span> |<span data-ttu-id="54854-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="54854-386">1.1.15600.4</span></span> | <span data-ttu-id="54854-387">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="54854-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="54854-388">1809  (RS5)</span></span> |<span data-ttu-id="54854-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="54854-389">4.18.1807.18075</span></span> |<span data-ttu-id="54854-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="54854-390">1.1.15000.2</span></span> | <span data-ttu-id="54854-391">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="54854-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="54854-392">1803  (RS4)</span></span> |<span data-ttu-id="54854-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="54854-393">4.13.17134.1</span></span> |<span data-ttu-id="54854-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="54854-394">1.1.14600.4</span></span> | <span data-ttu-id="54854-395">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="54854-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="54854-396">1709  (RS3)</span></span> |<span data-ttu-id="54854-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="54854-397">4.12.16299.15</span></span> |<span data-ttu-id="54854-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="54854-398">1.1.14104.0</span></span> | <span data-ttu-id="54854-399">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="54854-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="54854-400">1703  (RS2)</span></span> |<span data-ttu-id="54854-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="54854-401">4.11.15603.2</span></span> |<span data-ttu-id="54854-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="54854-402">1.1.13504.0</span></span> | <span data-ttu-id="54854-403">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="54854-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="54854-404">1607 (RS1)</span></span> |<span data-ttu-id="54854-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="54854-405">4.10.14393.3683</span></span> |<span data-ttu-id="54854-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="54854-406">1.1.12805.0</span></span> | <span data-ttu-id="54854-407">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="54854-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="54854-408">Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="54854-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="54854-409">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="54854-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="54854-410">Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="54854-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="54854-411">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="54854-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="54854-412">Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="54854-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="54854-413">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="54854-413">1.1.2104.01</span></span></summary>

<span data-ttu-id="54854-414">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="54854-414">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="54854-415">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="54854-415">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="54854-416">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="54854-416">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="54854-417">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="54854-417">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-418">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-418">Fixes</span></span>
- <span data-ttu-id="54854-419">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-420">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-420">Additional information</span></span>
- <span data-ttu-id="54854-421">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="54854-422">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="54854-422">1.1.2103.01</span></span></summary>

<span data-ttu-id="54854-423">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="54854-423">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="54854-424">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="54854-424">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="54854-425">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="54854-425">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="54854-426">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="54854-426">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-427">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-427">Fixes</span></span>
- <span data-ttu-id="54854-428">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-429">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-429">Additional information</span></span>
- <span data-ttu-id="54854-430">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="54854-431">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="54854-431">1.1.2102.03</span></span></summary>

<span data-ttu-id="54854-432">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="54854-432">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="54854-433">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="54854-433">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="54854-434">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="54854-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="54854-435">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="54854-435">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-436">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-436">Fixes</span></span>
- <span data-ttu-id="54854-437">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-438">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-438">Additional information</span></span>
- <span data-ttu-id="54854-439">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="54854-440">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="54854-440">1.1.2101.02</span></span></summary>

<span data-ttu-id="54854-441">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="54854-441">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="54854-442">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="54854-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="54854-443">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="54854-443">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="54854-444">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="54854-444">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-445">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-445">Fixes</span></span>
- <span data-ttu-id="54854-446">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-447">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-447">Additional information</span></span>
- <span data-ttu-id="54854-448">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="54854-449">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="54854-449">1.1.2012.01</span></span></summary>

<span data-ttu-id="54854-450">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="54854-450">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="54854-451">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="54854-451">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="54854-452">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="54854-452">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="54854-453">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="54854-453">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-454">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-454">Fixes</span></span>
- <span data-ttu-id="54854-455">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-456">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-456">Additional information</span></span>
- <span data-ttu-id="54854-457">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="54854-458">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="54854-458">1.1.2011.02</span></span></summary>

<span data-ttu-id="54854-459">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="54854-459">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="54854-460">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="54854-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="54854-461">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="54854-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="54854-462">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="54854-462">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-463">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-463">Fixes</span></span>
- <span data-ttu-id="54854-464">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-465">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-465">Additional information</span></span>
- <span data-ttu-id="54854-466">Обновленные антивирусная программа в Microsoft Defender подписи</span><span class="sxs-lookup"><span data-stu-id="54854-466">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="54854-467">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="54854-467">1.1.2011.01</span></span></summary>

<span data-ttu-id="54854-468">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="54854-468">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="54854-469">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="54854-469">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="54854-470">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="54854-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="54854-471">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="54854-471">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-472">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-472">Fixes</span></span>
- <span data-ttu-id="54854-473">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-474">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-474">Additional information</span></span>
- <span data-ttu-id="54854-475">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="54854-476">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="54854-476">1.1.2009.10</span></span></summary>

<span data-ttu-id="54854-477">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="54854-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="54854-478">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="54854-478">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="54854-479">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="54854-479">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="54854-480">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="54854-480">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="54854-481">Исправления</span><span class="sxs-lookup"><span data-stu-id="54854-481">Fixes</span></span>
- <span data-ttu-id="54854-482">Нет</span><span class="sxs-lookup"><span data-stu-id="54854-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="54854-483">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="54854-483">Additional information</span></span>
- <span data-ttu-id="54854-484">Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.</span><span class="sxs-lookup"><span data-stu-id="54854-484">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="54854-485">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="54854-485">Additional resources</span></span>

| <span data-ttu-id="54854-486">Статья</span><span class="sxs-lookup"><span data-stu-id="54854-486">Article</span></span> | <span data-ttu-id="54854-487">Описание</span><span class="sxs-lookup"><span data-stu-id="54854-487">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="54854-488">Обновление Microsoft Defender для Windows изображений установки операционной системы</span><span class="sxs-lookup"><span data-stu-id="54854-488">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="54854-489">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="54854-489">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="54854-490">Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.</span><span class="sxs-lookup"><span data-stu-id="54854-490">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="54854-491">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="54854-491">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="54854-492">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="54854-492">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="54854-493">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="54854-493">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="54854-494">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="54854-494">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="54854-495">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="54854-495">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="54854-496">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="54854-496">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="54854-497">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="54854-497">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="54854-498">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="54854-498">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="54854-499">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="54854-499">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="54854-500">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="54854-500">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
