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
ms.date: 05/06/2021
ms.openlocfilehash: 22a173d39c3ab8d1afd91a33b05e02e58da24aaa
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274560"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="c17aa-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="c17aa-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="c17aa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c17aa-105">**Applies to:**</span></span>

- [<span data-ttu-id="c17aa-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c17aa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="c17aa-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c17aa-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="c17aa-108">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="c17aa-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="c17aa-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="c17aa-109">Security intelligence updates</span></span>
- <span data-ttu-id="c17aa-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="c17aa-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c17aa-111">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="c17aa-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="c17aa-112">Не забудьте обновить антивирусную защиту, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="c17aa-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="c17aa-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c17aa-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="c17aa-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="c17aa-114">Security intelligence updates</span></span>

<span data-ttu-id="c17aa-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="c17aa-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="c17aa-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="c17aa-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="c17aa-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="c17aa-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="c17aa-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="c17aa-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="c17aa-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="c17aa-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="c17aa-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="c17aa-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="c17aa-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c17aa-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="c17aa-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c17aa-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="c17aa-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="c17aa-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="c17aa-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="c17aa-124">Product updates</span></span>

<span data-ttu-id="c17aa-125">антивирусная программа в Microsoft Defender требует ежемесячных обновлений [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (известный как обновления платформы) и будет получать основные обновления функций наряду с Windows 10 выпусками.</span><span class="sxs-lookup"><span data-stu-id="c17aa-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="c17aa-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="c17aa-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="c17aa-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="c17aa-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="c17aa-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c17aa-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="c17aa-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="c17aa-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="c17aa-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="c17aa-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="c17aa-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="c17aa-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="c17aa-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="c17aa-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="c17aa-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="c17aa-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="c17aa-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="c17aa-134">All our updates contain</span></span> 
- <span data-ttu-id="c17aa-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="c17aa-135">performance improvements;</span></span>
- <span data-ttu-id="c17aa-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="c17aa-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="c17aa-137">улучшения интеграции (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="c17aa-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="c17aa-138">Апрель-2021 (платформа: 4.19.2104.9| Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="c17aa-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="c17aa-139">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="c17aa-140">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="c17aa-141">&ensp;Платформа: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="c17aa-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="c17aa-142">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="c17aa-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="c17aa-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-144">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-144">What's new</span></span>
- <span data-ttu-id="c17aa-145">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="c17aa-146">Улучшенное обнаружение кейлоггера режима ядра</span><span class="sxs-lookup"><span data-stu-id="c17aa-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-147">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-147">Known Issues</span></span>
<span data-ttu-id="c17aa-148">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-149">Март-2021 (платформа: 4.19.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="c17aa-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="c17aa-150">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="c17aa-151">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="c17aa-152">&ensp;Платформа: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="c17aa-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="c17aa-153">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="c17aa-154">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="c17aa-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-155">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-155">What's new</span></span>

- <span data-ttu-id="c17aa-156">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="c17aa-157">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="c17aa-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="c17aa-158">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c17aa-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-159">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-159">Known Issues</span></span>
<span data-ttu-id="c17aa-160">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c17aa-161">Февраль-2021 (платформа: 4.19.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="c17aa-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="c17aa-162">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="c17aa-163">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="c17aa-164">&ensp;Платформа: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="c17aa-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="c17aa-165">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="c17aa-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="c17aa-166">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="c17aa-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-167">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-167">What's new</span></span>

- <span data-ttu-id="c17aa-168">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c17aa-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="c17aa-169">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="c17aa-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-170">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-170">Known Issues</span></span>
<span data-ttu-id="c17aa-171">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="c17aa-172">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="c17aa-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="c17aa-173">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="c17aa-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="c17aa-174">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="c17aa-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="c17aa-175">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="c17aa-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="c17aa-176">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c17aa-177">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="c17aa-178">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="c17aa-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="c17aa-179">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="c17aa-180">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-181">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-181">What's new</span></span>

- <span data-ttu-id="c17aa-182">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="c17aa-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="c17aa-183">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="c17aa-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="c17aa-184">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="c17aa-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="c17aa-185">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="c17aa-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="c17aa-186">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="c17aa-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-187">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-187">Known Issues</span></span>
<span data-ttu-id="c17aa-188">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c17aa-189">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="c17aa-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="c17aa-190">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c17aa-191">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="c17aa-192">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="c17aa-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="c17aa-193">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c17aa-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="c17aa-194">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-195">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-195">What's new</span></span>

- <span data-ttu-id="c17aa-196">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="c17aa-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-197">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-197">Known Issues</span></span>
<span data-ttu-id="c17aa-198">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c17aa-199">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="c17aa-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="c17aa-200">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="c17aa-201">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="c17aa-202">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="c17aa-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="c17aa-203">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="c17aa-204">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-205">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-205">What's new</span></span>

- <span data-ttu-id="c17aa-206">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="c17aa-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="c17aa-207">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="c17aa-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="c17aa-208">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="c17aa-209">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="c17aa-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-210">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-210">Known Issues</span></span>

<span data-ttu-id="c17aa-211">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c17aa-212">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="c17aa-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="c17aa-213">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="c17aa-214">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="c17aa-215">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c17aa-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="c17aa-216">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="c17aa-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="c17aa-217">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-218">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-218">What's new</span></span>

- <span data-ttu-id="c17aa-219">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="c17aa-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="c17aa-220">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="c17aa-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="c17aa-221">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="c17aa-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="c17aa-222">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="c17aa-222">New management interfaces for:</span></span>
   - <span data-ttu-id="c17aa-223">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="c17aa-223">UDP Inspection</span></span>
   - <span data-ttu-id="c17aa-224">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="c17aa-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="c17aa-225">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="c17aa-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="c17aa-226">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="c17aa-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="c17aa-227">Улучшенное сканирование модулей VBA Office</span><span class="sxs-lookup"><span data-stu-id="c17aa-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-228">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-228">Known Issues</span></span>

<span data-ttu-id="c17aa-229">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="c17aa-230">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="c17aa-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="c17aa-231">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="c17aa-232">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="c17aa-233">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="c17aa-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="c17aa-234">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="c17aa-235">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="c17aa-236">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-236">What's new</span></span>

- <span data-ttu-id="c17aa-237">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="c17aa-237">Add more telemetry events</span></span>
- <span data-ttu-id="c17aa-238">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="c17aa-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="c17aa-239">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="c17aa-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="c17aa-240">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="c17aa-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="c17aa-241">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="c17aa-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="c17aa-242">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c17aa-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="c17aa-243">Антивирус Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="c17aa-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="c17aa-244">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-244">Known Issues</span></span>
<span data-ttu-id="c17aa-245">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-246">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="c17aa-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="c17aa-247">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="c17aa-248">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="c17aa-249">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="c17aa-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="c17aa-250">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="c17aa-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="c17aa-251">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-252">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-252">What's new</span></span>

- <span data-ttu-id="c17aa-253">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="c17aa-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="c17aa-254">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="c17aa-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-255">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-255">Known Issues</span></span>
<span data-ttu-id="c17aa-256">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-257">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="c17aa-258">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="c17aa-259">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="c17aa-260">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="c17aa-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="c17aa-261">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="c17aa-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="c17aa-262">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-263">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-263">What's new</span></span>

- <span data-ttu-id="c17aa-264">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="c17aa-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="c17aa-265">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="c17aa-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="c17aa-266">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="c17aa-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="c17aa-267">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="c17aa-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="c17aa-268">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="c17aa-268">Fixed registry query</span></span> 
- <span data-ttu-id="c17aa-269">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="c17aa-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-270">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-270">Known Issues</span></span>
<span data-ttu-id="c17aa-271">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-272">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="c17aa-273">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="c17aa-274">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="c17aa-275">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="c17aa-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="c17aa-276">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="c17aa-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="c17aa-277">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-278">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-278">What's new</span></span>

- <span data-ttu-id="c17aa-279">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="c17aa-279">Improved logging for scan events</span></span>
- <span data-ttu-id="c17aa-280">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="c17aa-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="c17aa-281">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="c17aa-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="c17aa-282">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="c17aa-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="c17aa-283">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="c17aa-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="c17aa-284">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="c17aa-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-285">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-285">Known Issues</span></span>
<span data-ttu-id="c17aa-286">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-287">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="c17aa-288">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="c17aa-289">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="c17aa-290">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="c17aa-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="c17aa-291">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="c17aa-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="c17aa-292">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-293">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-293">What's new</span></span>
- <span data-ttu-id="c17aa-294">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="c17aa-294">WDfilter improvements</span></span>
- <span data-ttu-id="c17aa-295">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="c17aa-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="c17aa-296">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="c17aa-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="c17aa-297">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="c17aa-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="c17aa-298">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="c17aa-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="c17aa-299">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="c17aa-299">UEFI scan capability</span></span>
- <span data-ttu-id="c17aa-300">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="c17aa-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="c17aa-301">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-301">Known Issues</span></span>
<span data-ttu-id="c17aa-302">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-303">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="c17aa-304">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="c17aa-305">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="c17aa-306">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="c17aa-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="c17aa-307">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="c17aa-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="c17aa-308">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c17aa-309">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-309">What's new</span></span>

- <span data-ttu-id="c17aa-310">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c17aa-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="c17aa-311">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="c17aa-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="c17aa-312">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="c17aa-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="c17aa-313">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="c17aa-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="c17aa-314">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="c17aa-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c17aa-315">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-315">Known Issues</span></span>
<span data-ttu-id="c17aa-316">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="c17aa-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="c17aa-317">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="c17aa-318">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="c17aa-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="c17aa-319">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="c17aa-320">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="c17aa-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="c17aa-321">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="c17aa-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="c17aa-322">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c17aa-323">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="c17aa-324">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-324">Known Issues</span></span>
<span data-ttu-id="c17aa-325">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="c17aa-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-326">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="c17aa-327">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="c17aa-328">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="c17aa-329">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="c17aa-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="c17aa-330">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="c17aa-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="c17aa-331">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="c17aa-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c17aa-332">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-332">What's new</span></span>

- <span data-ttu-id="c17aa-333">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="c17aa-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="c17aa-334">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="c17aa-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="c17aa-335">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c17aa-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="c17aa-336">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="c17aa-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="c17aa-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="c17aa-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c17aa-338">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-338">Known Issues</span></span>

<span data-ttu-id="c17aa-339">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="c17aa-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="c17aa-340">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c17aa-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="c17aa-341">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="c17aa-341">This update is:</span></span>
> - <span data-ttu-id="c17aa-342">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="c17aa-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="c17aa-343">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="c17aa-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="c17aa-344">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="c17aa-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="c17aa-345">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="c17aa-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="c17aa-346">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="c17aa-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c17aa-347">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="c17aa-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="c17aa-348">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="c17aa-349">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="c17aa-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="c17aa-350">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="c17aa-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="c17aa-351">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="c17aa-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="c17aa-352">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="c17aa-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="c17aa-353">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="c17aa-353">What's new</span></span>

- <span data-ttu-id="c17aa-354">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="c17aa-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="c17aa-355">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="c17aa-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="c17aa-356">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="c17aa-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="c17aa-357">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="c17aa-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c17aa-358">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="c17aa-358">Known Issues</span></span>
<span data-ttu-id="c17aa-359">При установке этого обновления устройству требуется пакет скачок 4.10.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="c17aa-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="c17aa-360">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="c17aa-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="c17aa-361">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="c17aa-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="c17aa-362">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="c17aa-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="c17aa-363">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="c17aa-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="c17aa-364">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="c17aa-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="c17aa-365">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="c17aa-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="c17aa-366">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="c17aa-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="c17aa-367">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="c17aa-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="c17aa-368">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="c17aa-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="c17aa-369">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="c17aa-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="c17aa-370">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="c17aa-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="c17aa-371">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="c17aa-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="c17aa-372">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="c17aa-372">Windows 10 release</span></span>  |<span data-ttu-id="c17aa-373">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="c17aa-373">Platform version</span></span>  |<span data-ttu-id="c17aa-374">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="c17aa-374">Engine version</span></span> |<span data-ttu-id="c17aa-375">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="c17aa-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="c17aa-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="c17aa-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="c17aa-377">4.18.1909.6</span></span> |<span data-ttu-id="c17aa-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="c17aa-378">1.1.17000.2</span></span> | <span data-ttu-id="c17aa-379">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c17aa-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-380">1909  (19H2)</span></span> |<span data-ttu-id="c17aa-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c17aa-381">4.18.1902.5</span></span> |<span data-ttu-id="c17aa-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="c17aa-382">1.1.16700.3</span></span> | <span data-ttu-id="c17aa-383">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c17aa-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="c17aa-384">1903  (19H1)</span></span> |<span data-ttu-id="c17aa-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c17aa-385">4.18.1902.5</span></span> |<span data-ttu-id="c17aa-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="c17aa-386">1.1.15600.4</span></span> | <span data-ttu-id="c17aa-387">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c17aa-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="c17aa-388">1809  (RS5)</span></span> |<span data-ttu-id="c17aa-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="c17aa-389">4.18.1807.18075</span></span> |<span data-ttu-id="c17aa-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="c17aa-390">1.1.15000.2</span></span> | <span data-ttu-id="c17aa-391">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c17aa-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="c17aa-392">1803  (RS4)</span></span> |<span data-ttu-id="c17aa-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="c17aa-393">4.13.17134.1</span></span> |<span data-ttu-id="c17aa-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="c17aa-394">1.1.14600.4</span></span> | <span data-ttu-id="c17aa-395">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c17aa-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="c17aa-396">1709  (RS3)</span></span> |<span data-ttu-id="c17aa-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="c17aa-397">4.12.16299.15</span></span> |<span data-ttu-id="c17aa-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="c17aa-398">1.1.14104.0</span></span> | <span data-ttu-id="c17aa-399">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c17aa-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="c17aa-400">1703  (RS2)</span></span> |<span data-ttu-id="c17aa-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="c17aa-401">4.11.15603.2</span></span> |<span data-ttu-id="c17aa-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="c17aa-402">1.1.13504.0</span></span> | <span data-ttu-id="c17aa-403">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c17aa-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="c17aa-404">1607 (RS1)</span></span> |<span data-ttu-id="c17aa-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="c17aa-405">4.10.14393.3683</span></span> |<span data-ttu-id="c17aa-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="c17aa-406">1.1.12805.0</span></span> | <span data-ttu-id="c17aa-407">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="c17aa-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="c17aa-408">Сведения о выпуске Windows 10 см. в листе фактов [жизненного цикла Windows.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="c17aa-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="c17aa-409">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="c17aa-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="c17aa-410">Рекомендуется обновить изображения установки Windows 10 (корпоративные, профессиональные и домашние выпуски), Windows Server 2019 и Windows Server 2016 с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="c17aa-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="c17aa-411">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="c17aa-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="c17aa-412">Дополнительные сведения см. в [обновлении Microsoft Defender для изображений установки операционной системы Windows.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="c17aa-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="c17aa-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="c17aa-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="c17aa-414">&ensp;Версия пакета: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="c17aa-415">&ensp;Версия платформы: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="c17aa-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="c17aa-416">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="c17aa-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="c17aa-417">&ensp;Версия подписи: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-418">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-418">Fixes</span></span>
- <span data-ttu-id="c17aa-419">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-420">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-420">Additional information</span></span>
- <span data-ttu-id="c17aa-421">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="c17aa-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="c17aa-423">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="c17aa-424">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="c17aa-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="c17aa-425">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="c17aa-426">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-427">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-427">Fixes</span></span>
- <span data-ttu-id="c17aa-428">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-429">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-429">Additional information</span></span>
- <span data-ttu-id="c17aa-430">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="c17aa-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="c17aa-432">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="c17aa-433">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="c17aa-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="c17aa-434">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c17aa-435">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-436">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-436">Fixes</span></span>
- <span data-ttu-id="c17aa-437">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-438">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-438">Additional information</span></span>
- <span data-ttu-id="c17aa-439">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="c17aa-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="c17aa-441">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="c17aa-442">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c17aa-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c17aa-443">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c17aa-444">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-445">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-445">Fixes</span></span>
- <span data-ttu-id="c17aa-446">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-447">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-447">Additional information</span></span>
- <span data-ttu-id="c17aa-448">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="c17aa-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="c17aa-450">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="c17aa-451">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c17aa-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c17aa-452">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c17aa-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="c17aa-453">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-454">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-454">Fixes</span></span>
- <span data-ttu-id="c17aa-455">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-456">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-456">Additional information</span></span>
- <span data-ttu-id="c17aa-457">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="c17aa-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="c17aa-459">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="c17aa-460">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c17aa-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c17aa-461">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c17aa-462">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-463">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-463">Fixes</span></span>
- <span data-ttu-id="c17aa-464">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-465">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-465">Additional information</span></span>
- <span data-ttu-id="c17aa-466">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="c17aa-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="c17aa-468">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="c17aa-469">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c17aa-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c17aa-470">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c17aa-471">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-472">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-472">Fixes</span></span>
- <span data-ttu-id="c17aa-473">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-474">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-474">Additional information</span></span>
- <span data-ttu-id="c17aa-475">Обновленные антивирусные подписи Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c17aa-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="c17aa-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="c17aa-477">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c17aa-478">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c17aa-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="c17aa-479">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c17aa-480">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-481">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-481">Fixes</span></span>
- <span data-ttu-id="c17aa-482">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-483">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-483">Additional information</span></span>
- <span data-ttu-id="c17aa-484">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c17aa-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="c17aa-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="c17aa-486">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c17aa-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c17aa-487">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="c17aa-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="c17aa-488">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c17aa-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="c17aa-489">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="c17aa-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c17aa-490">Исправления</span><span class="sxs-lookup"><span data-stu-id="c17aa-490">Fixes</span></span>
- <span data-ttu-id="c17aa-491">Нет</span><span class="sxs-lookup"><span data-stu-id="c17aa-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c17aa-492">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c17aa-492">Additional information</span></span>
- <span data-ttu-id="c17aa-493">Добавлена поддержка для Windows 10 RS1 или более поздней осмии установки изображений.</span><span class="sxs-lookup"><span data-stu-id="c17aa-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="c17aa-494">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="c17aa-494">Additional resources</span></span>

| <span data-ttu-id="c17aa-495">Статья</span><span class="sxs-lookup"><span data-stu-id="c17aa-495">Article</span></span> | <span data-ttu-id="c17aa-496">Описание</span><span class="sxs-lookup"><span data-stu-id="c17aa-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="c17aa-497">Обновление Microsoft Defender для изображений установки операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="c17aa-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="c17aa-498">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="c17aa-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="c17aa-499">Получите антивирусные обновления Microsoft Defender для Windows 10 (корпоративные, профессиональные и домашние выпуски), Windows Server 2019 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c17aa-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="c17aa-500">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="c17aa-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c17aa-501">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="c17aa-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="c17aa-502">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="c17aa-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="c17aa-503">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="c17aa-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="c17aa-504">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="c17aa-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="c17aa-505">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="c17aa-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="c17aa-506">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="c17aa-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c17aa-507">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="c17aa-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="c17aa-508">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="c17aa-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="c17aa-509">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="c17aa-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
