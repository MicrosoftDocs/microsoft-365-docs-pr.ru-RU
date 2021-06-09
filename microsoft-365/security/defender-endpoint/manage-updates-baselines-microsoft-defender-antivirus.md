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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822278"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="a3da4-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="a3da4-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="a3da4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a3da4-105">**Applies to:**</span></span>

- [<span data-ttu-id="a3da4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a3da4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="a3da4-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a3da4-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="a3da4-108">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="a3da4-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="a3da4-109">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="a3da4-109">Security intelligence updates</span></span>
- <span data-ttu-id="a3da4-110">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="a3da4-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3da4-111">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="a3da4-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="a3da4-112">Не забудьте обновить антивирусную защиту, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="a3da4-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="a3da4-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="a3da4-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="a3da4-114">Security intelligence updates</span></span>

<span data-ttu-id="a3da4-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="a3da4-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da4-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="a3da4-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="a3da4-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="a3da4-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="a3da4-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="a3da4-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="a3da4-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="a3da4-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="a3da4-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="a3da4-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="a3da4-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="a3da4-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="a3da4-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="a3da4-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="a3da4-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="a3da4-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="a3da4-124">Product updates</span></span>

<span data-ttu-id="a3da4-125">антивирусная программа в Microsoft Defender требует ежемесячных обновлений [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (известный как обновления платформы) и будет получать основные обновления функций наряду с Windows 10 выпусками.</span><span class="sxs-lookup"><span data-stu-id="a3da4-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="a3da4-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="a3da4-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="a3da4-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="a3da4-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="a3da4-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a3da4-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="a3da4-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="a3da4-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="a3da4-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="a3da4-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="a3da4-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="a3da4-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="a3da4-132">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="a3da4-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="a3da4-133">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="a3da4-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="a3da4-134">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="a3da4-134">All our updates contain</span></span> 
- <span data-ttu-id="a3da4-135">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="a3da4-135">performance improvements;</span></span>
- <span data-ttu-id="a3da4-136">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="a3da4-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="a3da4-137">улучшения интеграции (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="a3da4-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="a3da4-138">Май-2021 (платформа: 4.18.2105.4 | Двигатель: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="a3da4-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="a3da4-139">&ensp;Версия обновления аналитики безопасности: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="a3da4-140">&ensp;Выпущено: **4 июня 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="a3da4-141">&ensp;Платформа: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="a3da4-142">&ensp;Двигатель: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="a3da4-143">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="a3da4-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-144">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-144">What's new</span></span>
- <span data-ttu-id="a3da4-145">Улучшения мониторинга [поведения](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="a3da4-146">Функция [фильтрации уведомлений о](network-protection.md) фиксированной защите сети</span><span class="sxs-lookup"><span data-stu-id="a3da4-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-147">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-147">Known Issues</span></span>
<span data-ttu-id="a3da4-148">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="a3da4-149">Апрель-2021 (платформа: 4.18.2104.14 | Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="a3da4-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="a3da4-150">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="a3da4-151">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="a3da4-152">&ensp;Платформа: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="a3da4-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="a3da4-153">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="a3da4-154">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="a3da4-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-155">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-155">What's new</span></span>
- <span data-ttu-id="a3da4-156">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="a3da4-157">Улучшенное обнаружение кейлоггера режима ядра</span><span class="sxs-lookup"><span data-stu-id="a3da4-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="a3da4-158">Добавлены новые элементы управления для управления постепенным процессом выкатки обновлений [Microsoft Defender](updates.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-159">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-159">Known Issues</span></span>
<span data-ttu-id="a3da4-160">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="a3da4-161">Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="a3da4-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="a3da4-162">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="a3da4-163">&ensp;Выпущено: **1 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="a3da4-164">&ensp;Платформа: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="a3da4-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="a3da4-165">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="a3da4-166">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="a3da4-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-167">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-167">What's new</span></span>

- <span data-ttu-id="a3da4-168">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="a3da4-169">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="a3da4-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="a3da4-170">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-171">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-171">Known Issues</span></span>
<span data-ttu-id="a3da4-172">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="a3da4-173">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="a3da4-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="a3da4-174">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="a3da4-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="a3da4-175">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="a3da4-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="a3da4-176">Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="a3da4-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="a3da4-177">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="a3da4-178">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="a3da4-179">&ensp;Платформа: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="a3da4-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="a3da4-180">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="a3da4-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="a3da4-181">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-182">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-182">What's new</span></span>

- <span data-ttu-id="a3da4-183">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="a3da4-184">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="a3da4-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-185">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-185">Known Issues</span></span>
<span data-ttu-id="a3da4-186">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="a3da4-187">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="a3da4-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="a3da4-188">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="a3da4-189">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="a3da4-190">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="a3da4-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="a3da4-191">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="a3da4-192">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-193">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-193">What's new</span></span>

- <span data-ttu-id="a3da4-194">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="a3da4-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="a3da4-195">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="a3da4-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="a3da4-196">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="a3da4-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="a3da4-197">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="a3da4-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="a3da4-198">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="a3da4-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-199">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-199">Known Issues</span></span>
<span data-ttu-id="a3da4-200">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="a3da4-201">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="a3da4-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="a3da4-202">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="a3da4-203">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="a3da4-204">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="a3da4-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="a3da4-205">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="a3da4-206">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-207">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-207">What's new</span></span>

- <span data-ttu-id="a3da4-208">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="a3da4-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-209">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-209">Known Issues</span></span>
<span data-ttu-id="a3da4-210">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="a3da4-211">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="a3da4-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="a3da4-212">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="a3da4-213">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="a3da4-214">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="a3da4-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="a3da4-215">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="a3da4-216">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-217">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-217">What's new</span></span>

- <span data-ttu-id="a3da4-218">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="a3da4-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="a3da4-219">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="a3da4-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="a3da4-220">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="a3da4-221">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="a3da4-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-222">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-222">Known Issues</span></span>

<span data-ttu-id="a3da4-223">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="a3da4-224">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="a3da4-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="a3da4-225">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="a3da4-226">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="a3da4-227">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="a3da4-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="a3da4-228">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="a3da4-229">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-230">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-230">What's new</span></span>

- <span data-ttu-id="a3da4-231">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="a3da4-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="a3da4-232">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="a3da4-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="a3da4-233">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="a3da4-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="a3da4-234">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="a3da4-234">New management interfaces for:</span></span>
   - <span data-ttu-id="a3da4-235">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="a3da4-235">UDP Inspection</span></span>
   - <span data-ttu-id="a3da4-236">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="a3da4-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="a3da4-237">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="a3da4-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="a3da4-238">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="a3da4-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="a3da4-239">Улучшенное сканирование Office VBA</span><span class="sxs-lookup"><span data-stu-id="a3da4-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-240">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-240">Known Issues</span></span>

<span data-ttu-id="a3da4-241">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="a3da4-242">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="a3da4-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="a3da4-243">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="a3da4-244">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="a3da4-245">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="a3da4-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="a3da4-246">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="a3da4-247">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="a3da4-248">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-248">What's new</span></span>

- <span data-ttu-id="a3da4-249">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="a3da4-249">Add more telemetry events</span></span>
- <span data-ttu-id="a3da4-250">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="a3da4-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="a3da4-251">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="a3da4-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="a3da4-252">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="a3da4-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="a3da4-253">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3da4-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="a3da4-254">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="a3da4-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="a3da4-255">антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="a3da4-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="a3da4-256">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-256">Known Issues</span></span>
<span data-ttu-id="a3da4-257">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="a3da4-258">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="a3da4-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="a3da4-259">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="a3da4-260">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="a3da4-261">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="a3da4-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="a3da4-262">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="a3da4-263">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-264">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-264">What's new</span></span>

- <span data-ttu-id="a3da4-265">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="a3da4-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="a3da4-266">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="a3da4-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-267">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-267">Known Issues</span></span>
<span data-ttu-id="a3da4-268">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="a3da4-269">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="a3da4-270">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="a3da4-271">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="a3da4-272">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="a3da4-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="a3da4-273">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="a3da4-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="a3da4-274">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-275">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-275">What's new</span></span>

- <span data-ttu-id="a3da4-276">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="a3da4-277">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="a3da4-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="a3da4-278">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="a3da4-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="a3da4-279">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="a3da4-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="a3da4-280">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="a3da4-280">Fixed registry query</span></span> 
- <span data-ttu-id="a3da4-281">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="a3da4-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-282">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-282">Known Issues</span></span>
<span data-ttu-id="a3da4-283">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="a3da4-284">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="a3da4-285">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="a3da4-286">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="a3da4-287">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="a3da4-288">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="a3da4-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="a3da4-289">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-290">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-290">What's new</span></span>

- <span data-ttu-id="a3da4-291">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="a3da4-291">Improved logging for scan events</span></span>
- <span data-ttu-id="a3da4-292">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3da4-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="a3da4-293">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="a3da4-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="a3da4-294">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="a3da4-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="a3da4-295">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="a3da4-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="a3da4-296">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="a3da4-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-297">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-297">Known Issues</span></span>
<span data-ttu-id="a3da4-298">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="a3da4-299">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="a3da4-300">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="a3da4-301">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="a3da4-302">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="a3da4-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="a3da4-303">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="a3da4-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="a3da4-304">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-305">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-305">What's new</span></span>
- <span data-ttu-id="a3da4-306">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="a3da4-306">WDfilter improvements</span></span>
- <span data-ttu-id="a3da4-307">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="a3da4-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="a3da4-308">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="a3da4-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="a3da4-309">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="a3da4-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="a3da4-310">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="a3da4-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="a3da4-311">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="a3da4-311">UEFI scan capability</span></span>
- <span data-ttu-id="a3da4-312">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="a3da4-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="a3da4-313">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-313">Known Issues</span></span>
<span data-ttu-id="a3da4-314">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="a3da4-315">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="a3da4-316">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="a3da4-317">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="a3da4-318">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="a3da4-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="a3da4-319">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="a3da4-320">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="a3da4-321">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-321">What's new</span></span>

- <span data-ttu-id="a3da4-322">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="a3da4-323">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="a3da4-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="a3da4-324">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="a3da4-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="a3da4-325">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="a3da4-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="a3da4-326">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="a3da4-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="a3da4-327">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-327">Known Issues</span></span>
<span data-ttu-id="a3da4-328">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="a3da4-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="a3da4-329">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="a3da4-330">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="a3da4-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="a3da4-331">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="a3da4-332">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="a3da4-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="a3da4-333">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="a3da4-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="a3da4-334">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="a3da4-335">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="a3da4-336">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-336">Known Issues</span></span>
<span data-ttu-id="a3da4-337">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="a3da4-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="a3da4-338">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="a3da4-339">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="a3da4-340">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="a3da4-341">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="a3da4-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="a3da4-342">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="a3da4-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="a3da4-343">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="a3da4-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="a3da4-344">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-344">What's new</span></span>

- <span data-ttu-id="a3da4-345">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="a3da4-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="a3da4-346">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="a3da4-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="a3da4-347">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="a3da4-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="a3da4-348">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="a3da4-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="a3da4-349">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="a3da4-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="a3da4-350">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-350">Known Issues</span></span>

<span data-ttu-id="a3da4-351">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="a3da4-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="a3da4-352">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a3da4-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="a3da4-353">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="a3da4-353">This update is:</span></span>
> - <span data-ttu-id="a3da4-354">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="a3da4-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="a3da4-355">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="a3da4-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="a3da4-356">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="a3da4-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="a3da4-357">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="a3da4-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="a3da4-358">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="a3da4-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="a3da4-359">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="a3da4-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="a3da4-360">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="a3da4-361">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="a3da4-362">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="a3da4-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="a3da4-363">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="a3da4-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="a3da4-364">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="a3da4-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="a3da4-365">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="a3da4-365">What's new</span></span>

- <span data-ttu-id="a3da4-366">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="a3da4-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="a3da4-367">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="a3da4-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="a3da4-368">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="a3da4-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="a3da4-369">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="a3da4-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="a3da4-370">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a3da4-370">Known Issues</span></span>
<span data-ttu-id="a3da4-371">При установке этого обновления устройству требуется пакет скачок 4.18.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="a3da4-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="a3da4-372">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="a3da4-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="a3da4-373">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="a3da4-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="a3da4-374">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="a3da4-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="a3da4-375">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="a3da4-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="a3da4-376">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="a3da4-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="a3da4-377">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="a3da4-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="a3da4-378">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="a3da4-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="a3da4-379">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="a3da4-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="a3da4-380">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="a3da4-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="a3da4-381">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="a3da4-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="a3da4-382">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="a3da4-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="a3da4-383">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="a3da4-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="a3da4-384">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="a3da4-384">Windows 10 release</span></span>  |<span data-ttu-id="a3da4-385">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="a3da4-385">Platform version</span></span>  |<span data-ttu-id="a3da4-386">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="a3da4-386">Engine version</span></span> |<span data-ttu-id="a3da4-387">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="a3da4-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="a3da4-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="a3da4-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="a3da4-389">4.18.1909.6</span></span> |<span data-ttu-id="a3da4-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="a3da4-390">1.1.17000.2</span></span> | <span data-ttu-id="a3da4-391">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="a3da4-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-392">1909  (19H2)</span></span> |<span data-ttu-id="a3da4-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="a3da4-393">4.18.1902.5</span></span> |<span data-ttu-id="a3da4-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="a3da4-394">1.1.16700.3</span></span> | <span data-ttu-id="a3da4-395">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="a3da4-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="a3da4-396">1903  (19H1)</span></span> |<span data-ttu-id="a3da4-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="a3da4-397">4.18.1902.5</span></span> |<span data-ttu-id="a3da4-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="a3da4-398">1.1.15600.4</span></span> | <span data-ttu-id="a3da4-399">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="a3da4-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="a3da4-400">1809  (RS5)</span></span> |<span data-ttu-id="a3da4-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="a3da4-401">4.18.1807.18075</span></span> |<span data-ttu-id="a3da4-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="a3da4-402">1.1.15000.2</span></span> | <span data-ttu-id="a3da4-403">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="a3da4-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="a3da4-404">1803  (RS4)</span></span> |<span data-ttu-id="a3da4-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="a3da4-405">4.13.17134.1</span></span> |<span data-ttu-id="a3da4-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="a3da4-406">1.1.14600.4</span></span> | <span data-ttu-id="a3da4-407">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="a3da4-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="a3da4-408">1709  (RS3)</span></span> |<span data-ttu-id="a3da4-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="a3da4-409">4.12.16299.15</span></span> |<span data-ttu-id="a3da4-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="a3da4-410">1.1.14104.0</span></span> | <span data-ttu-id="a3da4-411">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="a3da4-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="a3da4-412">1703  (RS2)</span></span> |<span data-ttu-id="a3da4-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="a3da4-413">4.11.15603.2</span></span> |<span data-ttu-id="a3da4-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="a3da4-414">1.1.13504.0</span></span> | <span data-ttu-id="a3da4-415">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="a3da4-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="a3da4-416">1607 (RS1)</span></span> |<span data-ttu-id="a3da4-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="a3da4-417">4.10.14393.3683</span></span> |<span data-ttu-id="a3da4-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="a3da4-418">1.1.12805.0</span></span> | <span data-ttu-id="a3da4-419">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="a3da4-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="a3da4-420">Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="a3da4-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="a3da4-421">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="a3da4-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="a3da4-422">Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="a3da4-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="a3da4-423">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="a3da4-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="a3da4-424">Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="a3da4-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="a3da4-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="a3da4-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="a3da4-426">&ensp;Версия пакета: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="a3da4-427">&ensp;Версия платформы: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="a3da4-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="a3da4-428">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="a3da4-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="a3da4-429">&ensp;Версия подписи: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-430">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-430">Fixes</span></span>
- <span data-ttu-id="a3da4-431">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-432">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-432">Additional information</span></span>
- <span data-ttu-id="a3da4-433">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="a3da4-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="a3da4-435">&ensp;Версия пакета: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="a3da4-436">&ensp;Версия платформы: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="a3da4-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="a3da4-437">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="a3da4-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="a3da4-438">&ensp;Версия подписи: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-439">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-439">Fixes</span></span>
- <span data-ttu-id="a3da4-440">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-441">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-441">Additional information</span></span>
- <span data-ttu-id="a3da4-442">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="a3da4-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="a3da4-444">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="a3da4-445">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="a3da4-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="a3da4-446">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="a3da4-447">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-448">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-448">Fixes</span></span>
- <span data-ttu-id="a3da4-449">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-450">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-450">Additional information</span></span>
- <span data-ttu-id="a3da4-451">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="a3da4-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="a3da4-453">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="a3da4-454">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="a3da4-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="a3da4-455">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="a3da4-456">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-457">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-457">Fixes</span></span>
- <span data-ttu-id="a3da4-458">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-459">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-459">Additional information</span></span>
- <span data-ttu-id="a3da4-460">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="a3da4-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="a3da4-462">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="a3da4-463">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="a3da4-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="a3da4-464">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="a3da4-465">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-466">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-466">Fixes</span></span>
- <span data-ttu-id="a3da4-467">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-468">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-468">Additional information</span></span>
- <span data-ttu-id="a3da4-469">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="a3da4-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="a3da4-471">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="a3da4-472">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="a3da4-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="a3da4-473">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="a3da4-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="a3da4-474">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-475">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-475">Fixes</span></span>
- <span data-ttu-id="a3da4-476">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-477">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-477">Additional information</span></span>
- <span data-ttu-id="a3da4-478">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="a3da4-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="a3da4-480">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="a3da4-481">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="a3da4-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="a3da4-482">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="a3da4-483">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-484">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-484">Fixes</span></span>
- <span data-ttu-id="a3da4-485">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-486">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-486">Additional information</span></span>
- <span data-ttu-id="a3da4-487">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="a3da4-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="a3da4-489">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="a3da4-490">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="a3da4-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="a3da4-491">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="a3da4-492">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-493">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-493">Fixes</span></span>
- <span data-ttu-id="a3da4-494">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-495">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-495">Additional information</span></span>
- <span data-ttu-id="a3da4-496">Обновленные антивирусная программа в Microsoft Defender подписи</span><span class="sxs-lookup"><span data-stu-id="a3da4-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="a3da4-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="a3da4-498">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="a3da4-499">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="a3da4-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="a3da4-500">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="a3da4-501">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-502">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-502">Fixes</span></span>
- <span data-ttu-id="a3da4-503">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-504">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-504">Additional information</span></span>
- <span data-ttu-id="a3da4-505">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="a3da4-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="a3da4-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="a3da4-507">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="a3da4-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="a3da4-508">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="a3da4-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="a3da4-509">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="a3da4-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="a3da4-510">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="a3da4-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="a3da4-511">Исправления</span><span class="sxs-lookup"><span data-stu-id="a3da4-511">Fixes</span></span>
- <span data-ttu-id="a3da4-512">Нет</span><span class="sxs-lookup"><span data-stu-id="a3da4-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="a3da4-513">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3da4-513">Additional information</span></span>
- <span data-ttu-id="a3da4-514">Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.</span><span class="sxs-lookup"><span data-stu-id="a3da4-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="a3da4-515">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="a3da4-515">Additional resources</span></span>

| <span data-ttu-id="a3da4-516">Статья</span><span class="sxs-lookup"><span data-stu-id="a3da4-516">Article</span></span> | <span data-ttu-id="a3da4-517">Описание</span><span class="sxs-lookup"><span data-stu-id="a3da4-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="a3da4-518">Обновление Microsoft Defender для Windows изображений установки операционной системы</span><span class="sxs-lookup"><span data-stu-id="a3da4-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="a3da4-519">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="a3da4-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="a3da4-520">Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.</span><span class="sxs-lookup"><span data-stu-id="a3da4-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="a3da4-521">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a3da4-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="a3da4-522">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="a3da4-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="a3da4-523">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a3da4-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="a3da4-524">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="a3da4-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="a3da4-525">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="a3da4-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="a3da4-526">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3da4-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="a3da4-527">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="a3da4-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="a3da4-528">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="a3da4-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="a3da4-529">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="a3da4-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="a3da4-530">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="a3da4-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
