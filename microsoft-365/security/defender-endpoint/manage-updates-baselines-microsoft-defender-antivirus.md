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
ms.date: 06/03/2021
ms.openlocfilehash: e67f783552cca5cc36c1563f5e5557796028ea18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772021"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="f6682-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="f6682-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="f6682-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f6682-105">**Applies to:**</span></span>

- [<span data-ttu-id="f6682-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f6682-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="f6682-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f6682-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="f6682-108">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="f6682-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="f6682-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="f6682-109">Security intelligence updates</span></span>
- <span data-ttu-id="f6682-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="f6682-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6682-111">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="f6682-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="f6682-112">Не забудьте обновить антивирусную защиту, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="f6682-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="f6682-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f6682-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="f6682-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="f6682-114">Security intelligence updates</span></span>

<span data-ttu-id="f6682-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="f6682-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="f6682-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="f6682-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="f6682-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="f6682-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="f6682-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="f6682-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="f6682-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="f6682-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="f6682-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="f6682-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="f6682-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f6682-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="f6682-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f6682-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="f6682-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="f6682-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="f6682-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="f6682-124">Product updates</span></span>

<span data-ttu-id="f6682-125">антивирусная программа в Microsoft Defender требует ежемесячных обновлений [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (известный как обновления платформы) и будет получать основные обновления функций наряду с Windows 10 выпусками.</span><span class="sxs-lookup"><span data-stu-id="f6682-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="f6682-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="f6682-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="f6682-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="f6682-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="f6682-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6682-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="f6682-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="f6682-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="f6682-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="f6682-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="f6682-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="f6682-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="f6682-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="f6682-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="f6682-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="f6682-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="f6682-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="f6682-134">All our updates contain</span></span> 
- <span data-ttu-id="f6682-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="f6682-135">performance improvements;</span></span>
- <span data-ttu-id="f6682-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="f6682-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="f6682-137">улучшения интеграции (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="f6682-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="f6682-138">Апрель-2021 (платформа: 4.18.2104.14 | Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="f6682-138">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="f6682-139">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="f6682-140">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="f6682-141">&ensp;Платформа: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="f6682-141">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="f6682-142">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="f6682-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="f6682-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-144">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-144">What's new</span></span>
- <span data-ttu-id="f6682-145">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="f6682-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="f6682-146">Улучшенное обнаружение кейлоггера режима ядра</span><span class="sxs-lookup"><span data-stu-id="f6682-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-147">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-147">Known Issues</span></span>
<span data-ttu-id="f6682-148">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-149">Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="f6682-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="f6682-150">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="f6682-151">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="f6682-152">&ensp;Платформа: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="f6682-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="f6682-153">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="f6682-154">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="f6682-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-155">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-155">What's new</span></span>

- <span data-ttu-id="f6682-156">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="f6682-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="f6682-157">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="f6682-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="f6682-158">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f6682-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-159">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-159">Known Issues</span></span>
<span data-ttu-id="f6682-160">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f6682-161">Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="f6682-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="f6682-162">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="f6682-163">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="f6682-164">&ensp;Платформа: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="f6682-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="f6682-165">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="f6682-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="f6682-166">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="f6682-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-167">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-167">What's new</span></span>

- <span data-ttu-id="f6682-168">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f6682-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="f6682-169">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="f6682-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-170">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-170">Known Issues</span></span>
<span data-ttu-id="f6682-171">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="f6682-172">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="f6682-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="f6682-173">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="f6682-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="f6682-174">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="f6682-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="f6682-175">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="f6682-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="f6682-176">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f6682-177">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="f6682-178">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="f6682-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="f6682-179">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="f6682-180">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-181">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-181">What's new</span></span>

- <span data-ttu-id="f6682-182">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="f6682-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="f6682-183">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="f6682-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="f6682-184">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="f6682-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="f6682-185">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="f6682-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="f6682-186">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="f6682-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-187">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-187">Known Issues</span></span>
<span data-ttu-id="f6682-188">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f6682-189">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="f6682-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="f6682-190">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f6682-191">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="f6682-192">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="f6682-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="f6682-193">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f6682-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="f6682-194">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-195">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-195">What's new</span></span>

- <span data-ttu-id="f6682-196">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="f6682-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-197">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-197">Known Issues</span></span>
<span data-ttu-id="f6682-198">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f6682-199">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="f6682-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="f6682-200">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="f6682-201">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="f6682-202">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="f6682-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="f6682-203">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="f6682-204">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-205">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-205">What's new</span></span>

- <span data-ttu-id="f6682-206">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="f6682-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="f6682-207">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="f6682-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="f6682-208">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="f6682-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="f6682-209">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="f6682-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-210">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-210">Known Issues</span></span>

<span data-ttu-id="f6682-211">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f6682-212">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="f6682-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="f6682-213">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="f6682-214">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="f6682-215">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f6682-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="f6682-216">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="f6682-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="f6682-217">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-218">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-218">What's new</span></span>

- <span data-ttu-id="f6682-219">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="f6682-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="f6682-220">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="f6682-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="f6682-221">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="f6682-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="f6682-222">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="f6682-222">New management interfaces for:</span></span>
   - <span data-ttu-id="f6682-223">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="f6682-223">UDP Inspection</span></span>
   - <span data-ttu-id="f6682-224">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="f6682-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="f6682-225">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="f6682-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="f6682-226">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="f6682-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="f6682-227">Улучшенное сканирование Office VBA</span><span class="sxs-lookup"><span data-stu-id="f6682-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-228">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-228">Known Issues</span></span>

<span data-ttu-id="f6682-229">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="f6682-230">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="f6682-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="f6682-231">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="f6682-232">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="f6682-233">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="f6682-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="f6682-234">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="f6682-235">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="f6682-236">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-236">What's new</span></span>

- <span data-ttu-id="f6682-237">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="f6682-237">Add more telemetry events</span></span>
- <span data-ttu-id="f6682-238">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="f6682-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="f6682-239">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="f6682-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="f6682-240">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="f6682-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="f6682-241">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6682-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="f6682-242">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="f6682-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="f6682-243">антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="f6682-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="f6682-244">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-244">Known Issues</span></span>
<span data-ttu-id="f6682-245">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-246">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="f6682-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="f6682-247">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="f6682-248">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="f6682-249">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="f6682-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="f6682-250">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="f6682-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="f6682-251">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-252">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-252">What's new</span></span>

- <span data-ttu-id="f6682-253">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="f6682-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="f6682-254">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="f6682-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-255">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-255">Known Issues</span></span>
<span data-ttu-id="f6682-256">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-257">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="f6682-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="f6682-258">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="f6682-259">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="f6682-260">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="f6682-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="f6682-261">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="f6682-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="f6682-262">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-263">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-263">What's new</span></span>

- <span data-ttu-id="f6682-264">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="f6682-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="f6682-265">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="f6682-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="f6682-266">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="f6682-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="f6682-267">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="f6682-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="f6682-268">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="f6682-268">Fixed registry query</span></span> 
- <span data-ttu-id="f6682-269">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="f6682-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-270">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-270">Known Issues</span></span>
<span data-ttu-id="f6682-271">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-272">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="f6682-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="f6682-273">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="f6682-274">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="f6682-275">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="f6682-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="f6682-276">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="f6682-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="f6682-277">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-278">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-278">What's new</span></span>

- <span data-ttu-id="f6682-279">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="f6682-279">Improved logging for scan events</span></span>
- <span data-ttu-id="f6682-280">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6682-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="f6682-281">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="f6682-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="f6682-282">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="f6682-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="f6682-283">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="f6682-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="f6682-284">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="f6682-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-285">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-285">Known Issues</span></span>
<span data-ttu-id="f6682-286">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-287">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="f6682-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="f6682-288">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="f6682-289">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="f6682-290">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="f6682-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="f6682-291">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="f6682-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="f6682-292">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-293">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-293">What's new</span></span>
- <span data-ttu-id="f6682-294">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="f6682-294">WDfilter improvements</span></span>
- <span data-ttu-id="f6682-295">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="f6682-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="f6682-296">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="f6682-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="f6682-297">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="f6682-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="f6682-298">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="f6682-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="f6682-299">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="f6682-299">UEFI scan capability</span></span>
- <span data-ttu-id="f6682-300">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="f6682-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="f6682-301">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-301">Known Issues</span></span>
<span data-ttu-id="f6682-302">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-303">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="f6682-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="f6682-304">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="f6682-305">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="f6682-306">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="f6682-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="f6682-307">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="f6682-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="f6682-308">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f6682-309">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-309">What's new</span></span>

- <span data-ttu-id="f6682-310">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f6682-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="f6682-311">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="f6682-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="f6682-312">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="f6682-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="f6682-313">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="f6682-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="f6682-314">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="f6682-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f6682-315">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-315">Known Issues</span></span>
<span data-ttu-id="f6682-316">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="f6682-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="f6682-317">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="f6682-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="f6682-318">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="f6682-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="f6682-319">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="f6682-320">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="f6682-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="f6682-321">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="f6682-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="f6682-322">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f6682-323">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="f6682-324">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-324">Known Issues</span></span>
<span data-ttu-id="f6682-325">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="f6682-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-326">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="f6682-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="f6682-327">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="f6682-328">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="f6682-329">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="f6682-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="f6682-330">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="f6682-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="f6682-331">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="f6682-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f6682-332">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-332">What's new</span></span>

- <span data-ttu-id="f6682-333">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="f6682-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="f6682-334">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="f6682-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="f6682-335">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f6682-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="f6682-336">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="f6682-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="f6682-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="f6682-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f6682-338">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-338">Known Issues</span></span>

<span data-ttu-id="f6682-339">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="f6682-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="f6682-340">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f6682-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="f6682-341">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="f6682-341">This update is:</span></span>
> - <span data-ttu-id="f6682-342">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="f6682-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="f6682-343">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="f6682-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="f6682-344">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="f6682-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="f6682-345">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="f6682-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="f6682-346">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="f6682-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f6682-347">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="f6682-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="f6682-348">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="f6682-349">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="f6682-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="f6682-350">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="f6682-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="f6682-351">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="f6682-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="f6682-352">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="f6682-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="f6682-353">Что нового</span><span class="sxs-lookup"><span data-stu-id="f6682-353">What's new</span></span>

- <span data-ttu-id="f6682-354">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="f6682-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="f6682-355">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="f6682-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="f6682-356">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="f6682-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="f6682-357">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="f6682-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f6682-358">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="f6682-358">Known Issues</span></span>
<span data-ttu-id="f6682-359">При установке этого обновления устройству требуется пакет скачок 4.10.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="f6682-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="f6682-360">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="f6682-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="f6682-361">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="f6682-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="f6682-362">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="f6682-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="f6682-363">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="f6682-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="f6682-364">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="f6682-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="f6682-365">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="f6682-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="f6682-366">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="f6682-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="f6682-367">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="f6682-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="f6682-368">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="f6682-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="f6682-369">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="f6682-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="f6682-370">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="f6682-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="f6682-371">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="f6682-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="f6682-372">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="f6682-372">Windows 10 release</span></span>  |<span data-ttu-id="f6682-373">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="f6682-373">Platform version</span></span>  |<span data-ttu-id="f6682-374">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="f6682-374">Engine version</span></span> |<span data-ttu-id="f6682-375">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="f6682-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="f6682-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="f6682-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="f6682-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="f6682-377">4.18.1909.6</span></span> |<span data-ttu-id="f6682-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="f6682-378">1.1.17000.2</span></span> | <span data-ttu-id="f6682-379">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f6682-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="f6682-380">1909  (19H2)</span></span> |<span data-ttu-id="f6682-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f6682-381">4.18.1902.5</span></span> |<span data-ttu-id="f6682-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="f6682-382">1.1.16700.3</span></span> | <span data-ttu-id="f6682-383">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f6682-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="f6682-384">1903  (19H1)</span></span> |<span data-ttu-id="f6682-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f6682-385">4.18.1902.5</span></span> |<span data-ttu-id="f6682-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="f6682-386">1.1.15600.4</span></span> | <span data-ttu-id="f6682-387">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f6682-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="f6682-388">1809  (RS5)</span></span> |<span data-ttu-id="f6682-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="f6682-389">4.18.1807.18075</span></span> |<span data-ttu-id="f6682-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="f6682-390">1.1.15000.2</span></span> | <span data-ttu-id="f6682-391">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f6682-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="f6682-392">1803  (RS4)</span></span> |<span data-ttu-id="f6682-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="f6682-393">4.13.17134.1</span></span> |<span data-ttu-id="f6682-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="f6682-394">1.1.14600.4</span></span> | <span data-ttu-id="f6682-395">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f6682-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="f6682-396">1709  (RS3)</span></span> |<span data-ttu-id="f6682-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="f6682-397">4.12.16299.15</span></span> |<span data-ttu-id="f6682-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="f6682-398">1.1.14104.0</span></span> | <span data-ttu-id="f6682-399">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f6682-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="f6682-400">1703  (RS2)</span></span> |<span data-ttu-id="f6682-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="f6682-401">4.11.15603.2</span></span> |<span data-ttu-id="f6682-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="f6682-402">1.1.13504.0</span></span> | <span data-ttu-id="f6682-403">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f6682-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="f6682-404">1607 (RS1)</span></span> |<span data-ttu-id="f6682-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="f6682-405">4.10.14393.3683</span></span> |<span data-ttu-id="f6682-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="f6682-406">1.1.12805.0</span></span> | <span data-ttu-id="f6682-407">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="f6682-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="f6682-408">Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="f6682-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="f6682-409">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="f6682-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="f6682-410">Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="f6682-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="f6682-411">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="f6682-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="f6682-412">Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="f6682-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="f6682-413">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="f6682-413">1.1.2106.01</span></span></summary>

<span data-ttu-id="f6682-414">&ensp;Версия пакета: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="f6682-414">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="f6682-415">&ensp;Версия платформы: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="f6682-415">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="f6682-416">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="f6682-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="f6682-417">&ensp;Версия подписи: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-417">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-418">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-418">Fixes</span></span>
- <span data-ttu-id="f6682-419">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-420">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-420">Additional information</span></span>
- <span data-ttu-id="f6682-421">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-422">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="f6682-422">1.1.2105.01</span></span></summary>

<span data-ttu-id="f6682-423">&ensp;Версия пакета: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="f6682-423">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="f6682-424">&ensp;Версия платформы: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="f6682-424">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="f6682-425">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="f6682-425">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="f6682-426">&ensp;Версия подписи: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-426">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-427">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-427">Fixes</span></span>
- <span data-ttu-id="f6682-428">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-429">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-429">Additional information</span></span>
- <span data-ttu-id="f6682-430">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-431">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="f6682-431">1.1.2104.01</span></span></summary>

<span data-ttu-id="f6682-432">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="f6682-432">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="f6682-433">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="f6682-433">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="f6682-434">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-434">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="f6682-435">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-435">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-436">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-436">Fixes</span></span>
- <span data-ttu-id="f6682-437">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-438">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-438">Additional information</span></span>
- <span data-ttu-id="f6682-439">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-440">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="f6682-440">1.1.2103.01</span></span></summary>

<span data-ttu-id="f6682-441">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="f6682-441">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="f6682-442">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="f6682-442">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="f6682-443">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f6682-444">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-444">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-445">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-445">Fixes</span></span>
- <span data-ttu-id="f6682-446">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-447">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-447">Additional information</span></span>
- <span data-ttu-id="f6682-448">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-449">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="f6682-449">1.1.2102.03</span></span></summary>

<span data-ttu-id="f6682-450">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="f6682-450">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="f6682-451">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f6682-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f6682-452">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-452">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f6682-453">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-453">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-454">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-454">Fixes</span></span>
- <span data-ttu-id="f6682-455">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-456">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-456">Additional information</span></span>
- <span data-ttu-id="f6682-457">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-458">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="f6682-458">1.1.2101.02</span></span></summary>

<span data-ttu-id="f6682-459">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="f6682-459">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="f6682-460">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f6682-460">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f6682-461">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f6682-461">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="f6682-462">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-462">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-463">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-463">Fixes</span></span>
- <span data-ttu-id="f6682-464">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-465">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-465">Additional information</span></span>
- <span data-ttu-id="f6682-466">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-467">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="f6682-467">1.1.2012.01</span></span></summary>

<span data-ttu-id="f6682-468">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="f6682-468">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="f6682-469">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f6682-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f6682-470">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f6682-471">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-471">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-472">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-472">Fixes</span></span>
- <span data-ttu-id="f6682-473">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-474">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-474">Additional information</span></span>
- <span data-ttu-id="f6682-475">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-476">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="f6682-476">1.1.2011.02</span></span></summary>

<span data-ttu-id="f6682-477">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="f6682-477">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="f6682-478">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f6682-478">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f6682-479">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f6682-480">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-480">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-481">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-481">Fixes</span></span>
- <span data-ttu-id="f6682-482">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-483">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-483">Additional information</span></span>
- <span data-ttu-id="f6682-484">Обновленные антивирусная программа в Microsoft Defender подписи</span><span class="sxs-lookup"><span data-stu-id="f6682-484">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-485">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="f6682-485">1.1.2011.01</span></span></summary>

<span data-ttu-id="f6682-486">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f6682-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f6682-487">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f6682-487">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="f6682-488">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-488">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f6682-489">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-489">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-490">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-490">Fixes</span></span>
- <span data-ttu-id="f6682-491">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-492">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-492">Additional information</span></span>
- <span data-ttu-id="f6682-493">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-493">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f6682-494">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="f6682-494">1.1.2009.10</span></span></summary>

<span data-ttu-id="f6682-495">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f6682-495">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f6682-496">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="f6682-496">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="f6682-497">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f6682-497">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="f6682-498">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="f6682-498">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f6682-499">Исправления</span><span class="sxs-lookup"><span data-stu-id="f6682-499">Fixes</span></span>
- <span data-ttu-id="f6682-500">Нет</span><span class="sxs-lookup"><span data-stu-id="f6682-500">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f6682-501">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f6682-501">Additional information</span></span>
- <span data-ttu-id="f6682-502">Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.</span><span class="sxs-lookup"><span data-stu-id="f6682-502">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="f6682-503">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f6682-503">Additional resources</span></span>

| <span data-ttu-id="f6682-504">Статья</span><span class="sxs-lookup"><span data-stu-id="f6682-504">Article</span></span> | <span data-ttu-id="f6682-505">Описание</span><span class="sxs-lookup"><span data-stu-id="f6682-505">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="f6682-506">Обновление Microsoft Defender для Windows изображений установки операционной системы</span><span class="sxs-lookup"><span data-stu-id="f6682-506">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="f6682-507">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="f6682-507">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="f6682-508">Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.</span><span class="sxs-lookup"><span data-stu-id="f6682-508">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="f6682-509">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="f6682-509">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f6682-510">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="f6682-510">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="f6682-511">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="f6682-511">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="f6682-512">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="f6682-512">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="f6682-513">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="f6682-513">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="f6682-514">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6682-514">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="f6682-515">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="f6682-515">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f6682-516">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="f6682-516">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="f6682-517">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="f6682-517">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="f6682-518">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="f6682-518">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
