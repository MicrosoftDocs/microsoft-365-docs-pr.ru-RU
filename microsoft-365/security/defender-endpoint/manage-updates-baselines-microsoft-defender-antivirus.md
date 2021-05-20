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
ms.date: 05/13/2021
ms.openlocfilehash: 17a76b39b51293de82cf9b3e5f0e323ec3d28844
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538043"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="ad1e1-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="ad1e1-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="ad1e1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-105">**Applies to:**</span></span>

- [<span data-ttu-id="ad1e1-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ad1e1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="ad1e1-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ad1e1-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="ad1e1-108">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="ad1e1-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="ad1e1-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-109">Security intelligence updates</span></span>
- <span data-ttu-id="ad1e1-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="ad1e1-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad1e1-111">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="ad1e1-112">Не забудьте обновить антивирусную защиту, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="ad1e1-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="ad1e1-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-114">Security intelligence updates</span></span>

<span data-ttu-id="ad1e1-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="ad1e1-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="ad1e1-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="ad1e1-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="ad1e1-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="ad1e1-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="ad1e1-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="ad1e1-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="ad1e1-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="ad1e1-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="ad1e1-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="ad1e1-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="ad1e1-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="ad1e1-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="ad1e1-124">Product updates</span></span>

<span data-ttu-id="ad1e1-125">антивирусная программа в Microsoft Defender требует ежемесячных обновлений [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (известный как обновления платформы) и будет получать основные обновления функций наряду с Windows 10 выпусками.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="ad1e1-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="ad1e1-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="ad1e1-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="ad1e1-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ad1e1-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="ad1e1-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="ad1e1-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="ad1e1-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="ad1e1-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="ad1e1-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="ad1e1-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="ad1e1-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="ad1e1-134">All our updates contain</span></span> 
- <span data-ttu-id="ad1e1-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="ad1e1-135">performance improvements;</span></span>
- <span data-ttu-id="ad1e1-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="ad1e1-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="ad1e1-137">улучшения интеграции (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="ad1e1-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="ad1e1-138">Апрель-2021 (платформа: 4.18.2104.14 | Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-138">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="ad1e1-139">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="ad1e1-140">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ad1e1-141">&ensp;Платформа: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-141">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="ad1e1-142">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="ad1e1-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-144">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-144">What's new</span></span>
- <span data-ttu-id="ad1e1-145">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="ad1e1-146">Улучшенное обнаружение кейлоггера режима ядра</span><span class="sxs-lookup"><span data-stu-id="ad1e1-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-147">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-147">Known Issues</span></span>
<span data-ttu-id="ad1e1-148">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-149">Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="ad1e1-150">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="ad1e1-151">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ad1e1-152">&ensp;Платформа: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="ad1e1-153">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="ad1e1-154">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-155">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-155">What's new</span></span>

- <span data-ttu-id="ad1e1-156">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="ad1e1-157">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="ad1e1-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="ad1e1-158">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-159">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-159">Known Issues</span></span>
<span data-ttu-id="ad1e1-160">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ad1e1-161">Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="ad1e1-162">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="ad1e1-163">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="ad1e1-164">&ensp;Платформа: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="ad1e1-165">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="ad1e1-166">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-167">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-167">What's new</span></span>

- <span data-ttu-id="ad1e1-168">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="ad1e1-169">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="ad1e1-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-170">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-170">Known Issues</span></span>
<span data-ttu-id="ad1e1-171">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="ad1e1-172">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="ad1e1-173">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="ad1e1-174">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="ad1e1-175">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="ad1e1-176">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ad1e1-177">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="ad1e1-178">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="ad1e1-179">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="ad1e1-180">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-181">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-181">What's new</span></span>

- <span data-ttu-id="ad1e1-182">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="ad1e1-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="ad1e1-183">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="ad1e1-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="ad1e1-184">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="ad1e1-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="ad1e1-185">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="ad1e1-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="ad1e1-186">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="ad1e1-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-187">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-187">Known Issues</span></span>
<span data-ttu-id="ad1e1-188">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ad1e1-189">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="ad1e1-190">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ad1e1-191">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="ad1e1-192">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="ad1e1-193">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="ad1e1-194">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-195">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-195">What's new</span></span>

- <span data-ttu-id="ad1e1-196">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-197">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-197">Known Issues</span></span>
<span data-ttu-id="ad1e1-198">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ad1e1-199">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="ad1e1-200">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="ad1e1-201">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="ad1e1-202">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="ad1e1-203">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="ad1e1-204">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-205">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-205">What's new</span></span>

- <span data-ttu-id="ad1e1-206">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="ad1e1-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="ad1e1-207">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="ad1e1-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="ad1e1-208">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="ad1e1-209">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="ad1e1-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-210">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-210">Known Issues</span></span>

<span data-ttu-id="ad1e1-211">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ad1e1-212">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="ad1e1-213">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="ad1e1-214">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="ad1e1-215">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="ad1e1-216">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="ad1e1-217">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-218">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-218">What's new</span></span>

- <span data-ttu-id="ad1e1-219">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="ad1e1-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="ad1e1-220">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="ad1e1-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="ad1e1-221">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="ad1e1-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="ad1e1-222">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="ad1e1-222">New management interfaces for:</span></span>
   - <span data-ttu-id="ad1e1-223">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="ad1e1-223">UDP Inspection</span></span>
   - <span data-ttu-id="ad1e1-224">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="ad1e1-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="ad1e1-225">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="ad1e1-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="ad1e1-226">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="ad1e1-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="ad1e1-227">Улучшенное сканирование Office VBA</span><span class="sxs-lookup"><span data-stu-id="ad1e1-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-228">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-228">Known Issues</span></span>

<span data-ttu-id="ad1e1-229">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="ad1e1-230">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="ad1e1-231">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="ad1e1-232">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="ad1e1-233">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="ad1e1-234">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="ad1e1-235">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="ad1e1-236">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-236">What's new</span></span>

- <span data-ttu-id="ad1e1-237">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="ad1e1-237">Add more telemetry events</span></span>
- <span data-ttu-id="ad1e1-238">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="ad1e1-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="ad1e1-239">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="ad1e1-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="ad1e1-240">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="ad1e1-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="ad1e1-241">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad1e1-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="ad1e1-242">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="ad1e1-243">антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="ad1e1-244">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-244">Known Issues</span></span>
<span data-ttu-id="ad1e1-245">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-246">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="ad1e1-247">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="ad1e1-248">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="ad1e1-249">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="ad1e1-250">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="ad1e1-251">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-252">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-252">What's new</span></span>

- <span data-ttu-id="ad1e1-253">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="ad1e1-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="ad1e1-254">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="ad1e1-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-255">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-255">Known Issues</span></span>
<span data-ttu-id="ad1e1-256">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-257">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="ad1e1-258">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="ad1e1-259">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="ad1e1-260">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="ad1e1-261">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="ad1e1-262">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-263">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-263">What's new</span></span>

- <span data-ttu-id="ad1e1-264">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="ad1e1-265">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="ad1e1-266">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="ad1e1-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="ad1e1-267">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="ad1e1-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="ad1e1-268">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="ad1e1-268">Fixed registry query</span></span> 
- <span data-ttu-id="ad1e1-269">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="ad1e1-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-270">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-270">Known Issues</span></span>
<span data-ttu-id="ad1e1-271">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-272">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="ad1e1-273">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="ad1e1-274">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="ad1e1-275">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="ad1e1-276">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="ad1e1-277">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-278">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-278">What's new</span></span>

- <span data-ttu-id="ad1e1-279">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="ad1e1-279">Improved logging for scan events</span></span>
- <span data-ttu-id="ad1e1-280">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="ad1e1-281">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="ad1e1-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="ad1e1-282">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="ad1e1-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="ad1e1-283">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="ad1e1-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="ad1e1-284">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-285">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-285">Known Issues</span></span>
<span data-ttu-id="ad1e1-286">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-287">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="ad1e1-288">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="ad1e1-289">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="ad1e1-290">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="ad1e1-291">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="ad1e1-292">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-293">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-293">What's new</span></span>
- <span data-ttu-id="ad1e1-294">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="ad1e1-294">WDfilter improvements</span></span>
- <span data-ttu-id="ad1e1-295">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="ad1e1-296">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="ad1e1-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="ad1e1-297">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="ad1e1-298">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="ad1e1-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="ad1e1-299">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="ad1e1-299">UEFI scan capability</span></span>
- <span data-ttu-id="ad1e1-300">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="ad1e1-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="ad1e1-301">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-301">Known Issues</span></span>
<span data-ttu-id="ad1e1-302">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-303">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="ad1e1-304">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="ad1e1-305">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="ad1e1-306">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="ad1e1-307">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="ad1e1-308">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ad1e1-309">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-309">What's new</span></span>

- <span data-ttu-id="ad1e1-310">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="ad1e1-311">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="ad1e1-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="ad1e1-312">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="ad1e1-313">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="ad1e1-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="ad1e1-314">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="ad1e1-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ad1e1-315">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-315">Known Issues</span></span>
<span data-ttu-id="ad1e1-316">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="ad1e1-317">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="ad1e1-318">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="ad1e1-319">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="ad1e1-320">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="ad1e1-321">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="ad1e1-322">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ad1e1-323">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="ad1e1-324">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-324">Known Issues</span></span>
<span data-ttu-id="ad1e1-325">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="ad1e1-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-326">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="ad1e1-327">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="ad1e1-328">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="ad1e1-329">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="ad1e1-330">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="ad1e1-331">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ad1e1-332">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-332">What's new</span></span>

- <span data-ttu-id="ad1e1-333">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="ad1e1-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="ad1e1-334">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="ad1e1-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="ad1e1-335">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="ad1e1-336">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="ad1e1-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="ad1e1-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ad1e1-338">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-338">Known Issues</span></span>

<span data-ttu-id="ad1e1-339">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="ad1e1-340">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="ad1e1-341">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="ad1e1-341">This update is:</span></span>
> - <span data-ttu-id="ad1e1-342">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="ad1e1-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="ad1e1-343">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="ad1e1-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="ad1e1-344">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="ad1e1-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="ad1e1-345">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="ad1e1-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="ad1e1-346">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="ad1e1-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ad1e1-347">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="ad1e1-348">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="ad1e1-349">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="ad1e1-350">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="ad1e1-351">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="ad1e1-352">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="ad1e1-353">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ad1e1-353">What's new</span></span>

- <span data-ttu-id="ad1e1-354">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="ad1e1-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="ad1e1-355">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="ad1e1-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="ad1e1-356">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="ad1e1-357">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="ad1e1-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ad1e1-358">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-358">Known Issues</span></span>
<span data-ttu-id="ad1e1-359">При установке этого обновления устройству требуется пакет скачок 4.10.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="ad1e1-360">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="ad1e1-361">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="ad1e1-362">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="ad1e1-363">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="ad1e1-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="ad1e1-364">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="ad1e1-365">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="ad1e1-366">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="ad1e1-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="ad1e1-367">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="ad1e1-368">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="ad1e1-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="ad1e1-369">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="ad1e1-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="ad1e1-370">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="ad1e1-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="ad1e1-371">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="ad1e1-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="ad1e1-372">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="ad1e1-372">Windows 10 release</span></span>  |<span data-ttu-id="ad1e1-373">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-373">Platform version</span></span>  |<span data-ttu-id="ad1e1-374">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="ad1e1-374">Engine version</span></span> |<span data-ttu-id="ad1e1-375">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="ad1e1-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="ad1e1-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="ad1e1-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="ad1e1-377">4.18.1909.6</span></span> |<span data-ttu-id="ad1e1-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="ad1e1-378">1.1.17000.2</span></span> | <span data-ttu-id="ad1e1-379">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ad1e1-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-380">1909  (19H2)</span></span> |<span data-ttu-id="ad1e1-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ad1e1-381">4.18.1902.5</span></span> |<span data-ttu-id="ad1e1-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="ad1e1-382">1.1.16700.3</span></span> | <span data-ttu-id="ad1e1-383">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ad1e1-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-384">1903  (19H1)</span></span> |<span data-ttu-id="ad1e1-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ad1e1-385">4.18.1902.5</span></span> |<span data-ttu-id="ad1e1-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="ad1e1-386">1.1.15600.4</span></span> | <span data-ttu-id="ad1e1-387">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ad1e1-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-388">1809  (RS5)</span></span> |<span data-ttu-id="ad1e1-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="ad1e1-389">4.18.1807.18075</span></span> |<span data-ttu-id="ad1e1-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="ad1e1-390">1.1.15000.2</span></span> | <span data-ttu-id="ad1e1-391">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ad1e1-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-392">1803  (RS4)</span></span> |<span data-ttu-id="ad1e1-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="ad1e1-393">4.13.17134.1</span></span> |<span data-ttu-id="ad1e1-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="ad1e1-394">1.1.14600.4</span></span> | <span data-ttu-id="ad1e1-395">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ad1e1-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-396">1709  (RS3)</span></span> |<span data-ttu-id="ad1e1-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="ad1e1-397">4.12.16299.15</span></span> |<span data-ttu-id="ad1e1-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="ad1e1-398">1.1.14104.0</span></span> | <span data-ttu-id="ad1e1-399">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ad1e1-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-400">1703  (RS2)</span></span> |<span data-ttu-id="ad1e1-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="ad1e1-401">4.11.15603.2</span></span> |<span data-ttu-id="ad1e1-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="ad1e1-402">1.1.13504.0</span></span> | <span data-ttu-id="ad1e1-403">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ad1e1-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-404">1607 (RS1)</span></span> |<span data-ttu-id="ad1e1-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="ad1e1-405">4.10.14393.3683</span></span> |<span data-ttu-id="ad1e1-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="ad1e1-406">1.1.12805.0</span></span> | <span data-ttu-id="ad1e1-407">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="ad1e1-408">Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="ad1e1-409">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="ad1e1-410">Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="ad1e1-411">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="ad1e1-412">Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="ad1e1-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="ad1e1-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="ad1e1-414">&ensp;Версия пакета: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="ad1e1-415">&ensp;Версия платформы: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="ad1e1-416">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ad1e1-417">&ensp;Версия подписи: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-418">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-418">Fixes</span></span>
- <span data-ttu-id="ad1e1-419">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-420">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-420">Additional information</span></span>
- <span data-ttu-id="ad1e1-421">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="ad1e1-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="ad1e1-423">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="ad1e1-424">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="ad1e1-425">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="ad1e1-426">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-427">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-427">Fixes</span></span>
- <span data-ttu-id="ad1e1-428">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-429">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-429">Additional information</span></span>
- <span data-ttu-id="ad1e1-430">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="ad1e1-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="ad1e1-432">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="ad1e1-433">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="ad1e1-434">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ad1e1-435">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-436">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-436">Fixes</span></span>
- <span data-ttu-id="ad1e1-437">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-438">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-438">Additional information</span></span>
- <span data-ttu-id="ad1e1-439">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="ad1e1-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="ad1e1-441">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="ad1e1-442">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ad1e1-443">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ad1e1-444">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-445">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-445">Fixes</span></span>
- <span data-ttu-id="ad1e1-446">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-447">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-447">Additional information</span></span>
- <span data-ttu-id="ad1e1-448">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="ad1e1-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="ad1e1-450">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="ad1e1-451">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ad1e1-452">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="ad1e1-453">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-454">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-454">Fixes</span></span>
- <span data-ttu-id="ad1e1-455">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-456">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-456">Additional information</span></span>
- <span data-ttu-id="ad1e1-457">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="ad1e1-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="ad1e1-459">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="ad1e1-460">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ad1e1-461">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ad1e1-462">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-463">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-463">Fixes</span></span>
- <span data-ttu-id="ad1e1-464">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-465">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-465">Additional information</span></span>
- <span data-ttu-id="ad1e1-466">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="ad1e1-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="ad1e1-468">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="ad1e1-469">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ad1e1-470">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ad1e1-471">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-472">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-472">Fixes</span></span>
- <span data-ttu-id="ad1e1-473">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-474">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-474">Additional information</span></span>
- <span data-ttu-id="ad1e1-475">Обновленные антивирусная программа в Microsoft Defender подписи</span><span class="sxs-lookup"><span data-stu-id="ad1e1-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="ad1e1-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="ad1e1-477">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ad1e1-478">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="ad1e1-479">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ad1e1-480">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-481">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-481">Fixes</span></span>
- <span data-ttu-id="ad1e1-482">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-483">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-483">Additional information</span></span>
- <span data-ttu-id="ad1e1-484">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ad1e1-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="ad1e1-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="ad1e1-486">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ad1e1-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ad1e1-487">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="ad1e1-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="ad1e1-488">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="ad1e1-489">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="ad1e1-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ad1e1-490">Исправления</span><span class="sxs-lookup"><span data-stu-id="ad1e1-490">Fixes</span></span>
- <span data-ttu-id="ad1e1-491">Нет</span><span class="sxs-lookup"><span data-stu-id="ad1e1-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ad1e1-492">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad1e1-492">Additional information</span></span>
- <span data-ttu-id="ad1e1-493">Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="ad1e1-494">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-494">Additional resources</span></span>

| <span data-ttu-id="ad1e1-495">Статья</span><span class="sxs-lookup"><span data-stu-id="ad1e1-495">Article</span></span> | <span data-ttu-id="ad1e1-496">Описание</span><span class="sxs-lookup"><span data-stu-id="ad1e1-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="ad1e1-497">Обновление Microsoft Defender для Windows изображений установки операционной системы</span><span class="sxs-lookup"><span data-stu-id="ad1e1-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="ad1e1-498">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="ad1e1-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="ad1e1-499">Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="ad1e1-500">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="ad1e1-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ad1e1-501">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="ad1e1-502">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="ad1e1-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="ad1e1-503">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="ad1e1-504">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="ad1e1-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="ad1e1-505">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="ad1e1-506">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="ad1e1-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ad1e1-507">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="ad1e1-508">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="ad1e1-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="ad1e1-509">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="ad1e1-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
