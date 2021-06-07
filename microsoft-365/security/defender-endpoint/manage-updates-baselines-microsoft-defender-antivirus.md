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
ms.openlocfilehash: a1b7891e9e397e7345eb73a94d6298a9da781d98
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795986"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="c9e07-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="c9e07-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="c9e07-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c9e07-105">**Applies to:**</span></span>

- [<span data-ttu-id="c9e07-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c9e07-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="c9e07-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c9e07-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="c9e07-108">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="c9e07-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="c9e07-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="c9e07-109">Security intelligence updates</span></span>
- <span data-ttu-id="c9e07-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="c9e07-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9e07-111">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="c9e07-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="c9e07-112">Не забудьте обновить антивирусную защиту, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="c9e07-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c9e07-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="c9e07-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="c9e07-114">Security intelligence updates</span></span>

<span data-ttu-id="c9e07-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="c9e07-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="c9e07-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="c9e07-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="c9e07-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="c9e07-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="c9e07-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="c9e07-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="c9e07-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="c9e07-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="c9e07-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="c9e07-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="c9e07-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="c9e07-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c9e07-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="c9e07-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="c9e07-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="c9e07-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="c9e07-124">Product updates</span></span>

<span data-ttu-id="c9e07-125">антивирусная программа в Microsoft Defender требует ежемесячных обновлений [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (известный как обновления платформы) и будет получать основные обновления функций наряду с Windows 10 выпусками.</span><span class="sxs-lookup"><span data-stu-id="c9e07-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="c9e07-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="c9e07-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="c9e07-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="c9e07-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="c9e07-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c9e07-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="c9e07-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="c9e07-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="c9e07-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="c9e07-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="c9e07-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="c9e07-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="c9e07-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="c9e07-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="c9e07-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="c9e07-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="c9e07-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="c9e07-134">All our updates contain</span></span> 
- <span data-ttu-id="c9e07-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="c9e07-135">performance improvements;</span></span>
- <span data-ttu-id="c9e07-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="c9e07-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="c9e07-137">улучшения интеграции (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="c9e07-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="c9e07-138">Май-2021 (платформа: 4.18.2105.4 | Двигатель: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="c9e07-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="c9e07-139">&ensp;Версия обновления аналитики безопасности: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="c9e07-140">&ensp;Выпущено: **4 июня 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="c9e07-141">&ensp;Платформа: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="c9e07-142">&ensp;Двигатель: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="c9e07-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="c9e07-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-144">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-144">What's new</span></span>
- <span data-ttu-id="c9e07-145">Улучшения мониторинга [поведения](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="c9e07-146">Функция [фильтрации уведомлений о](network-protection.md) фиксированной защите сети</span><span class="sxs-lookup"><span data-stu-id="c9e07-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-147">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-147">Known Issues</span></span>
<span data-ttu-id="c9e07-148">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c9e07-149">Апрель-2021 (платформа: 4.18.2104.14 | Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="c9e07-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="c9e07-150">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="c9e07-151">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="c9e07-152">&ensp;Платформа: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="c9e07-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="c9e07-153">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="c9e07-154">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="c9e07-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-155">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-155">What's new</span></span>
- <span data-ttu-id="c9e07-156">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="c9e07-157">Улучшенное обнаружение кейлоггера режима ядра</span><span class="sxs-lookup"><span data-stu-id="c9e07-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-158">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-158">Known Issues</span></span>
<span data-ttu-id="c9e07-159">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c9e07-160">Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="c9e07-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="c9e07-161">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="c9e07-162">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="c9e07-163">&ensp;Платформа: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="c9e07-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="c9e07-164">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="c9e07-165">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="c9e07-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-166">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-166">What's new</span></span>

- <span data-ttu-id="c9e07-167">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="c9e07-168">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="c9e07-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="c9e07-169">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-170">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-170">Known Issues</span></span>
<span data-ttu-id="c9e07-171">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="c9e07-172">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="c9e07-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="c9e07-173">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="c9e07-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="c9e07-174">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="c9e07-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="c9e07-175">Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="c9e07-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="c9e07-176">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="c9e07-177">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="c9e07-178">&ensp;Платформа: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="c9e07-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="c9e07-179">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="c9e07-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="c9e07-180">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-181">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-181">What's new</span></span>

- <span data-ttu-id="c9e07-182">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="c9e07-183">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="c9e07-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-184">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-184">Known Issues</span></span>
<span data-ttu-id="c9e07-185">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c9e07-186">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="c9e07-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="c9e07-187">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c9e07-188">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="c9e07-189">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="c9e07-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="c9e07-190">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="c9e07-191">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-192">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-192">What's new</span></span>

- <span data-ttu-id="c9e07-193">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="c9e07-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="c9e07-194">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="c9e07-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="c9e07-195">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="c9e07-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="c9e07-196">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="c9e07-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="c9e07-197">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="c9e07-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-198">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-198">Known Issues</span></span>
<span data-ttu-id="c9e07-199">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c9e07-200">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="c9e07-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="c9e07-201">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c9e07-202">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="c9e07-203">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="c9e07-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="c9e07-204">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="c9e07-205">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-206">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-206">What's new</span></span>

- <span data-ttu-id="c9e07-207">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="c9e07-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-208">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-208">Known Issues</span></span>
<span data-ttu-id="c9e07-209">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c9e07-210">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="c9e07-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="c9e07-211">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="c9e07-212">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="c9e07-213">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="c9e07-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="c9e07-214">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="c9e07-215">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-216">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-216">What's new</span></span>

- <span data-ttu-id="c9e07-217">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="c9e07-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="c9e07-218">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="c9e07-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="c9e07-219">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="c9e07-220">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="c9e07-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-221">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-221">Known Issues</span></span>

<span data-ttu-id="c9e07-222">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c9e07-223">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="c9e07-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="c9e07-224">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="c9e07-225">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="c9e07-226">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c9e07-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="c9e07-227">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="c9e07-228">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-229">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-229">What's new</span></span>

- <span data-ttu-id="c9e07-230">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="c9e07-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="c9e07-231">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="c9e07-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="c9e07-232">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="c9e07-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="c9e07-233">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="c9e07-233">New management interfaces for:</span></span>
   - <span data-ttu-id="c9e07-234">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="c9e07-234">UDP Inspection</span></span>
   - <span data-ttu-id="c9e07-235">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="c9e07-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="c9e07-236">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="c9e07-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="c9e07-237">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="c9e07-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="c9e07-238">Улучшенное сканирование Office VBA</span><span class="sxs-lookup"><span data-stu-id="c9e07-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-239">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-239">Known Issues</span></span>

<span data-ttu-id="c9e07-240">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="c9e07-241">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="c9e07-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="c9e07-242">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="c9e07-243">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="c9e07-244">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="c9e07-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="c9e07-245">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="c9e07-246">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="c9e07-247">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-247">What's new</span></span>

- <span data-ttu-id="c9e07-248">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="c9e07-248">Add more telemetry events</span></span>
- <span data-ttu-id="c9e07-249">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="c9e07-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="c9e07-250">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="c9e07-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="c9e07-251">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="c9e07-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="c9e07-252">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9e07-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="c9e07-253">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c9e07-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="c9e07-254">антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="c9e07-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="c9e07-255">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-255">Known Issues</span></span>
<span data-ttu-id="c9e07-256">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c9e07-257">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="c9e07-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="c9e07-258">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="c9e07-259">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="c9e07-260">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="c9e07-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="c9e07-261">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="c9e07-262">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-263">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-263">What's new</span></span>

- <span data-ttu-id="c9e07-264">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="c9e07-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="c9e07-265">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="c9e07-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-266">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-266">Known Issues</span></span>
<span data-ttu-id="c9e07-267">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c9e07-268">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="c9e07-269">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="c9e07-270">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="c9e07-271">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="c9e07-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="c9e07-272">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="c9e07-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="c9e07-273">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-274">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-274">What's new</span></span>

- <span data-ttu-id="c9e07-275">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="c9e07-276">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="c9e07-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="c9e07-277">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="c9e07-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="c9e07-278">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="c9e07-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="c9e07-279">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="c9e07-279">Fixed registry query</span></span> 
- <span data-ttu-id="c9e07-280">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="c9e07-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-281">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-281">Known Issues</span></span>
<span data-ttu-id="c9e07-282">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c9e07-283">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="c9e07-284">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="c9e07-285">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="c9e07-286">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="c9e07-287">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="c9e07-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="c9e07-288">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-289">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-289">What's new</span></span>

- <span data-ttu-id="c9e07-290">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="c9e07-290">Improved logging for scan events</span></span>
- <span data-ttu-id="c9e07-291">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="c9e07-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="c9e07-292">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="c9e07-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="c9e07-293">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="c9e07-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="c9e07-294">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="c9e07-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="c9e07-295">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="c9e07-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-296">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-296">Known Issues</span></span>
<span data-ttu-id="c9e07-297">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c9e07-298">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="c9e07-299">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="c9e07-300">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="c9e07-301">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="c9e07-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="c9e07-302">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="c9e07-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="c9e07-303">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-304">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-304">What's new</span></span>
- <span data-ttu-id="c9e07-305">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="c9e07-305">WDfilter improvements</span></span>
- <span data-ttu-id="c9e07-306">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="c9e07-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="c9e07-307">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="c9e07-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="c9e07-308">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="c9e07-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="c9e07-309">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="c9e07-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="c9e07-310">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="c9e07-310">UEFI scan capability</span></span>
- <span data-ttu-id="c9e07-311">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="c9e07-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="c9e07-312">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-312">Known Issues</span></span>
<span data-ttu-id="c9e07-313">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c9e07-314">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="c9e07-315">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="c9e07-316">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="c9e07-317">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="c9e07-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="c9e07-318">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="c9e07-319">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c9e07-320">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-320">What's new</span></span>

- <span data-ttu-id="c9e07-321">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="c9e07-322">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="c9e07-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="c9e07-323">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="c9e07-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="c9e07-324">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="c9e07-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="c9e07-325">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="c9e07-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c9e07-326">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-326">Known Issues</span></span>
<span data-ttu-id="c9e07-327">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="c9e07-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="c9e07-328">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="c9e07-329">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="c9e07-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="c9e07-330">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="c9e07-331">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="c9e07-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="c9e07-332">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="c9e07-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="c9e07-333">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c9e07-334">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="c9e07-335">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-335">Known Issues</span></span>
<span data-ttu-id="c9e07-336">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c9e07-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c9e07-337">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="c9e07-338">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="c9e07-339">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="c9e07-340">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="c9e07-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="c9e07-341">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="c9e07-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="c9e07-342">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c9e07-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c9e07-343">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-343">What's new</span></span>

- <span data-ttu-id="c9e07-344">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="c9e07-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="c9e07-345">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="c9e07-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="c9e07-346">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c9e07-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="c9e07-347">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="c9e07-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="c9e07-348">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="c9e07-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c9e07-349">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-349">Known Issues</span></span>

<span data-ttu-id="c9e07-350">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="c9e07-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="c9e07-351">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c9e07-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="c9e07-352">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="c9e07-352">This update is:</span></span>
> - <span data-ttu-id="c9e07-353">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="c9e07-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="c9e07-354">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="c9e07-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="c9e07-355">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="c9e07-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="c9e07-356">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="c9e07-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="c9e07-357">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="c9e07-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c9e07-358">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="c9e07-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="c9e07-359">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="c9e07-360">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="c9e07-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="c9e07-361">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="c9e07-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="c9e07-362">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="c9e07-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="c9e07-363">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="c9e07-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="c9e07-364">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c9e07-364">What's new</span></span>

- <span data-ttu-id="c9e07-365">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="c9e07-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="c9e07-366">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="c9e07-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="c9e07-367">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="c9e07-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="c9e07-368">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="c9e07-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c9e07-369">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c9e07-369">Known Issues</span></span>
<span data-ttu-id="c9e07-370">При установке этого обновления устройству требуется пакет скачок 4.10.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="c9e07-370">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="c9e07-371">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="c9e07-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="c9e07-372">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="c9e07-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="c9e07-373">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="c9e07-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="c9e07-374">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="c9e07-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="c9e07-375">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="c9e07-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="c9e07-376">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="c9e07-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="c9e07-377">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="c9e07-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="c9e07-378">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="c9e07-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="c9e07-379">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="c9e07-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="c9e07-380">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="c9e07-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="c9e07-381">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="c9e07-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="c9e07-382">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="c9e07-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="c9e07-383">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="c9e07-383">Windows 10 release</span></span>  |<span data-ttu-id="c9e07-384">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="c9e07-384">Platform version</span></span>  |<span data-ttu-id="c9e07-385">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="c9e07-385">Engine version</span></span> |<span data-ttu-id="c9e07-386">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="c9e07-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="c9e07-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="c9e07-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="c9e07-388">4.18.1909.6</span></span> |<span data-ttu-id="c9e07-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="c9e07-389">1.1.17000.2</span></span> | <span data-ttu-id="c9e07-390">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c9e07-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-391">1909  (19H2)</span></span> |<span data-ttu-id="c9e07-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c9e07-392">4.18.1902.5</span></span> |<span data-ttu-id="c9e07-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="c9e07-393">1.1.16700.3</span></span> | <span data-ttu-id="c9e07-394">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c9e07-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="c9e07-395">1903  (19H1)</span></span> |<span data-ttu-id="c9e07-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c9e07-396">4.18.1902.5</span></span> |<span data-ttu-id="c9e07-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="c9e07-397">1.1.15600.4</span></span> | <span data-ttu-id="c9e07-398">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c9e07-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="c9e07-399">1809  (RS5)</span></span> |<span data-ttu-id="c9e07-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="c9e07-400">4.18.1807.18075</span></span> |<span data-ttu-id="c9e07-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="c9e07-401">1.1.15000.2</span></span> | <span data-ttu-id="c9e07-402">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c9e07-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="c9e07-403">1803  (RS4)</span></span> |<span data-ttu-id="c9e07-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="c9e07-404">4.13.17134.1</span></span> |<span data-ttu-id="c9e07-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="c9e07-405">1.1.14600.4</span></span> | <span data-ttu-id="c9e07-406">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c9e07-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="c9e07-407">1709  (RS3)</span></span> |<span data-ttu-id="c9e07-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="c9e07-408">4.12.16299.15</span></span> |<span data-ttu-id="c9e07-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="c9e07-409">1.1.14104.0</span></span> | <span data-ttu-id="c9e07-410">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c9e07-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="c9e07-411">1703  (RS2)</span></span> |<span data-ttu-id="c9e07-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="c9e07-412">4.11.15603.2</span></span> |<span data-ttu-id="c9e07-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="c9e07-413">1.1.13504.0</span></span> | <span data-ttu-id="c9e07-414">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c9e07-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="c9e07-415">1607 (RS1)</span></span> |<span data-ttu-id="c9e07-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="c9e07-416">4.10.14393.3683</span></span> |<span data-ttu-id="c9e07-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="c9e07-417">1.1.12805.0</span></span> | <span data-ttu-id="c9e07-418">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c9e07-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="c9e07-419">Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="c9e07-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="c9e07-420">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="c9e07-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="c9e07-421">Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="c9e07-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="c9e07-422">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="c9e07-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="c9e07-423">Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="c9e07-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="c9e07-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="c9e07-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="c9e07-425">&ensp;Версия пакета: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="c9e07-426">&ensp;Версия платформы: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="c9e07-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="c9e07-427">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="c9e07-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="c9e07-428">&ensp;Версия подписи: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-429">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-429">Fixes</span></span>
- <span data-ttu-id="c9e07-430">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-431">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-431">Additional information</span></span>
- <span data-ttu-id="c9e07-432">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="c9e07-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="c9e07-434">&ensp;Версия пакета: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="c9e07-435">&ensp;Версия платформы: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="c9e07-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="c9e07-436">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="c9e07-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="c9e07-437">&ensp;Версия подписи: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-438">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-438">Fixes</span></span>
- <span data-ttu-id="c9e07-439">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-440">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-440">Additional information</span></span>
- <span data-ttu-id="c9e07-441">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="c9e07-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="c9e07-443">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="c9e07-444">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="c9e07-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="c9e07-445">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="c9e07-446">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-447">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-447">Fixes</span></span>
- <span data-ttu-id="c9e07-448">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-449">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-449">Additional information</span></span>
- <span data-ttu-id="c9e07-450">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="c9e07-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="c9e07-452">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="c9e07-453">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="c9e07-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="c9e07-454">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c9e07-455">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-456">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-456">Fixes</span></span>
- <span data-ttu-id="c9e07-457">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-458">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-458">Additional information</span></span>
- <span data-ttu-id="c9e07-459">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="c9e07-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="c9e07-461">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="c9e07-462">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c9e07-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c9e07-463">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c9e07-464">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-465">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-465">Fixes</span></span>
- <span data-ttu-id="c9e07-466">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-467">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-467">Additional information</span></span>
- <span data-ttu-id="c9e07-468">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="c9e07-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="c9e07-470">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="c9e07-471">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c9e07-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c9e07-472">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c9e07-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="c9e07-473">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-474">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-474">Fixes</span></span>
- <span data-ttu-id="c9e07-475">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-476">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-476">Additional information</span></span>
- <span data-ttu-id="c9e07-477">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="c9e07-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="c9e07-479">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="c9e07-480">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c9e07-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c9e07-481">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c9e07-482">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-483">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-483">Fixes</span></span>
- <span data-ttu-id="c9e07-484">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-485">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-485">Additional information</span></span>
- <span data-ttu-id="c9e07-486">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="c9e07-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="c9e07-488">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="c9e07-489">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c9e07-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c9e07-490">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c9e07-491">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-492">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-492">Fixes</span></span>
- <span data-ttu-id="c9e07-493">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-494">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-494">Additional information</span></span>
- <span data-ttu-id="c9e07-495">Обновленные антивирусная программа в Microsoft Defender подписи</span><span class="sxs-lookup"><span data-stu-id="c9e07-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="c9e07-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="c9e07-497">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c9e07-498">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c9e07-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="c9e07-499">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c9e07-500">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-501">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-501">Fixes</span></span>
- <span data-ttu-id="c9e07-502">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-503">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-503">Additional information</span></span>
- <span data-ttu-id="c9e07-504">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c9e07-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="c9e07-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="c9e07-506">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c9e07-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c9e07-507">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="c9e07-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="c9e07-508">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c9e07-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="c9e07-509">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="c9e07-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c9e07-510">Исправления</span><span class="sxs-lookup"><span data-stu-id="c9e07-510">Fixes</span></span>
- <span data-ttu-id="c9e07-511">Нет</span><span class="sxs-lookup"><span data-stu-id="c9e07-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c9e07-512">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c9e07-512">Additional information</span></span>
- <span data-ttu-id="c9e07-513">Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.</span><span class="sxs-lookup"><span data-stu-id="c9e07-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="c9e07-514">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="c9e07-514">Additional resources</span></span>

| <span data-ttu-id="c9e07-515">Статья</span><span class="sxs-lookup"><span data-stu-id="c9e07-515">Article</span></span> | <span data-ttu-id="c9e07-516">Описание</span><span class="sxs-lookup"><span data-stu-id="c9e07-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="c9e07-517">Обновление Microsoft Defender для Windows изображений установки операционной системы</span><span class="sxs-lookup"><span data-stu-id="c9e07-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="c9e07-518">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="c9e07-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="c9e07-519">Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.</span><span class="sxs-lookup"><span data-stu-id="c9e07-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="c9e07-520">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="c9e07-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c9e07-521">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="c9e07-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="c9e07-522">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="c9e07-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="c9e07-523">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="c9e07-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="c9e07-524">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="c9e07-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="c9e07-525">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="c9e07-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="c9e07-526">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="c9e07-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c9e07-527">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="c9e07-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="c9e07-528">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="c9e07-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="c9e07-529">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="c9e07-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
