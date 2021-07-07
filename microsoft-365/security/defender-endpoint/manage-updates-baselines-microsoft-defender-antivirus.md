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
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: f64c71501a550aabdf16b9de2d7a5db93e48caef
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314468"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="3ee49-104">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="3ee49-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="3ee49-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3ee49-105">**Applies to:**</span></span>

- [<span data-ttu-id="3ee49-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3ee49-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="3ee49-107">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3ee49-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="3ee49-108">Важно антивирусная программа в Microsoft Defender, чтобы убедиться, что устройства имеют новейшие технологии и функции, необходимые для защиты от новых вредоносных программ и методов атак.</span><span class="sxs-lookup"><span data-stu-id="3ee49-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="3ee49-109">Убедитесь в обновлении антивирусной защиты, даже если антивирусная программа в Microsoft Defender работает в [пассивном режиме.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="3ee49-110">Существует два типа обновлений, связанных с антивирусная программа в Microsoft Defender обновлениями:</span><span class="sxs-lookup"><span data-stu-id="3ee49-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="3ee49-111">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="3ee49-111">Security intelligence updates</span></span>
- <span data-ttu-id="3ee49-112">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="3ee49-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="3ee49-113">Чтобы увидеть наиболее актуальные даты движка, платформы и подписи, посетите обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ [Майкрософт](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="3ee49-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="3ee49-114">Обновления аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="3ee49-114">Security intelligence updates</span></span>

<span data-ttu-id="3ee49-115">антивирусная программа в Microsoft Defender использует облачную защиту [(также](cloud-protection-microsoft-defender-antivirus.md) называемую службой защиты Microsoft Advanced Protection Service или MAPS) и периодически загружает обновления разведки безопасности для обеспечения защиты.</span><span class="sxs-lookup"><span data-stu-id="3ee49-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="3ee49-116">Обновления выпускаются под номерами ниже KB:</span><span class="sxs-lookup"><span data-stu-id="3ee49-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="3ee49-117">антивирусная программа в Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="3ee49-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="3ee49-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="3ee49-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="3ee49-119">Защита с облачной доставкой всегда работает и требует активного подключения к Интернету для работы.</span><span class="sxs-lookup"><span data-stu-id="3ee49-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="3ee49-120">Обновления сведении безопасности происходят в запланированной каденции (настраиваемой с помощью политики).</span><span class="sxs-lookup"><span data-stu-id="3ee49-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="3ee49-121">Дополнительные сведения см. в [веб-сайте Use Microsoft cloud-provided protection in антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="3ee49-122">Список последних обновлений разведки безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="3ee49-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="3ee49-123">Обновления двигателя включаются с обновлениями аналитики безопасности и выпускаются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="3ee49-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="3ee49-124">Обновления продукта</span><span class="sxs-lookup"><span data-stu-id="3ee49-124">Product updates</span></span>

<span data-ttu-id="3ee49-125">антивирусная программа в Microsoft Defender требует [ежемесячных обновлений (KB4052623),](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) известных как *обновления платформы.*</span><span class="sxs-lookup"><span data-stu-id="3ee49-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="3ee49-126">Вы можете управлять распространением обновлений с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="3ee49-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="3ee49-127">Windows Служба обновления сервера (WSUS)</span><span class="sxs-lookup"><span data-stu-id="3ee49-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="3ee49-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3ee49-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="3ee49-129">Обычный метод, который используется для развертывания microsoft и Windows обновлений конечных точек в сети.</span><span class="sxs-lookup"><span data-stu-id="3ee49-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="3ee49-130">Дополнительные сведения см. [в ссылке Управление источниками обновлений антивирусная программа в Microsoft Defender защиты.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="3ee49-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="3ee49-131">Ежемесячные обновления выпускаются поэтапно, в результате чего в службах обновления window Server отображается несколько [пакетов.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="3ee49-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="3ee49-132">В этой статье перечислены изменения, включенные в широкий канал выпуска.</span><span class="sxs-lookup"><span data-stu-id="3ee49-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="3ee49-133">[Последние выпуски широкого канала см. здесь.](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)</span><span class="sxs-lookup"><span data-stu-id="3ee49-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="3ee49-134">Дополнительные сведения о постепенном процессе выкатки и дополнительные сведения о следующем выпуске см. в руб. Управление процессом постепенного выката обновлений [Microsoft Defender.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="3ee49-135">Дополнительные сведения об обновлениях сведений о безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах [Майкрософт.](https://www.microsoft.com/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="3ee49-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="3ee49-136">Ежемесячные версии платформы и двигателя</span><span class="sxs-lookup"><span data-stu-id="3ee49-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="3ee49-137">Сведения об обновлении или установке обновления платформы см. в Защитник Windows [update for Защитник Windows.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="3ee49-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="3ee49-138">Все обновления содержат</span><span class="sxs-lookup"><span data-stu-id="3ee49-138">All our updates contain</span></span> 
- <span data-ttu-id="3ee49-139">улучшения производительности;</span><span class="sxs-lookup"><span data-stu-id="3ee49-139">performance improvements;</span></span>
- <span data-ttu-id="3ee49-140">улучшения в обслуживании; и</span><span class="sxs-lookup"><span data-stu-id="3ee49-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="3ee49-141">улучшения интеграции (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="3ee49-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="3ee49-142">Июнь-2021 (платформа: 4.18.2106.5 | Двигатель: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="3ee49-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="3ee49-143">&ensp;Версия обновления аналитики безопасности: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="3ee49-144">&ensp;Выпущено: **28 июня 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="3ee49-145">&ensp;Платформа: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="3ee49-146">&ensp;Двигатель: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="3ee49-147">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="3ee49-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-148">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-148">What's new</span></span>
- <span data-ttu-id="3ee49-149">Новые элементы управления процессом постепенного выкатки обновлений Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3ee49-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="3ee49-150">См. [в рубке Управление постепенным процессом выкатки обновлений Microsoft Defender.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="3ee49-151">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="3ee49-152">Улучшения в октановке определений противомалярийных программ</span><span class="sxs-lookup"><span data-stu-id="3ee49-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="3ee49-153">Расширенные проверки сетевых событий Edge</span><span class="sxs-lookup"><span data-stu-id="3ee49-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-154">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-154">Known Issues</span></span>
<span data-ttu-id="3ee49-155">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3ee49-156">Май-2021 (платформа: 4.18.2105.4 | Двигатель: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="3ee49-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="3ee49-157">&ensp;Версия обновления аналитики безопасности: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="3ee49-158">&ensp;Выпущено: **3 июня 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="3ee49-159">&ensp;Платформа: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="3ee49-160">&ensp;Двигатель: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="3ee49-161">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="3ee49-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-162">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-162">What's new</span></span>
- <span data-ttu-id="3ee49-163">Улучшения мониторинга [поведения](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="3ee49-164">Функция [фильтрации уведомлений о](network-protection.md) фиксированной защите сети</span><span class="sxs-lookup"><span data-stu-id="3ee49-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-165">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-165">Known Issues</span></span>
<span data-ttu-id="3ee49-166">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3ee49-167">Апрель-2021 (платформа: 4.18.2104.14 | Двигатель: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="3ee49-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="3ee49-168">&ensp;Версия обновления аналитики безопасности: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="3ee49-169">&ensp;Выпущено: **26 апреля 2021**  г. (Двигатель: 1.1.18100.6 выпущен 5 мая 2021 г.) &ensp; Платформа: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="3ee49-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="3ee49-170">&ensp;Двигатель: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="3ee49-171">&ensp;Этап поддержки: **безопасность и критически важные обновления**</span><span class="sxs-lookup"><span data-stu-id="3ee49-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-172">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-172">What's new</span></span>
- <span data-ttu-id="3ee49-173">Дополнительная логика мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="3ee49-174">Улучшено обнаружение регистратора ключей режима ядра</span><span class="sxs-lookup"><span data-stu-id="3ee49-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="3ee49-175">Добавлены новые элементы управления для управления постепенным процессом выкатки обновлений [Microsoft Defender](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="3ee49-176">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-176">Known Issues</span></span>
<span data-ttu-id="3ee49-177">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="3ee49-178">Предыдущие обновления версий: только поддержка технического обновления</span><span class="sxs-lookup"><span data-stu-id="3ee49-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="3ee49-179">После выпуска новой версии пакета поддержка двух предыдущих версий снижается только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="3ee49-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="3ee49-180">Версии старше, чем указанные в этом разделе, и предоставляются только для технической поддержки обновления.</span><span class="sxs-lookup"><span data-stu-id="3ee49-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="3ee49-181">Март-2021 (платформа: 4.18.2103.7 | Двигатель: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="3ee49-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="3ee49-182">&ensp;Версия обновления аналитики безопасности: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="3ee49-183">&ensp;Выпущено: **2 апреля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="3ee49-184">&ensp;Платформа: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="3ee49-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="3ee49-185">&ensp;Двигатель: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="3ee49-186">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-187">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-187">What's new</span></span>

- <span data-ttu-id="3ee49-188">Улучшение движка мониторинга поведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="3ee49-189">Смягчение последствий атак с расширенной сетью brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="3ee49-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="3ee49-190">Дополнительное неудалось поколение событий попытки взлома при включенной защите [tamper](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-191">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-191">Known Issues</span></span>
<span data-ttu-id="3ee49-192">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3ee49-193">Февраль-2021 (платформа: 4.18.2102.3 | Двигатель: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="3ee49-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="3ee49-194">&ensp;Версия обновления аналитики безопасности: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="3ee49-195">&ensp;Выпущено: **9 марта 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="3ee49-196">&ensp;Платформа: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="3ee49-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="3ee49-197">&ensp;Двигатель: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="3ee49-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="3ee49-198">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-199">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-199">What's new</span></span>

- <span data-ttu-id="3ee49-200">Улучшение восстановления службы с [помощью защиты от взлома](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="3ee49-201">Расширение области защиты от взлома</span><span class="sxs-lookup"><span data-stu-id="3ee49-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-202">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-202">Known Issues</span></span>
<span data-ttu-id="3ee49-203">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3ee49-204">Январь-2021 (платформа: 4.18.2101.9 | Двигатель: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="3ee49-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="3ee49-205">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="3ee49-206">&ensp;Выпущено: **2 февраля 2021 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="3ee49-207">&ensp;Платформа: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="3ee49-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="3ee49-208">&ensp;Двигатель: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="3ee49-209">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-210">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-210">What's new</span></span>

- <span data-ttu-id="3ee49-211">Улучшения обнаружения эксплойтов Shellcode</span><span class="sxs-lookup"><span data-stu-id="3ee49-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="3ee49-212">Повышенная видимость попыток кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="3ee49-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="3ee49-213">Улучшения в области антиуставных функций в антивирусная программа в Microsoft Defender службах</span><span class="sxs-lookup"><span data-stu-id="3ee49-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="3ee49-214">Улучшенная поддержка эмуляции ARM x64</span><span class="sxs-lookup"><span data-stu-id="3ee49-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="3ee49-215">Исправление: EDR уведомление о блоке остается в истории угроз после первоначального обнаружения защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="3ee49-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-216">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-216">Known Issues</span></span>
<span data-ttu-id="3ee49-217">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3ee49-218">Ноябрь-2020 (платформа: 4.18.2011.6 | Двигатель: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="3ee49-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="3ee49-219">&ensp;Версия обновления аналитики безопасности: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="3ee49-220">&ensp;Выпущено: **03 декабря 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="3ee49-221">&ensp;Платформа: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="3ee49-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="3ee49-222">&ensp;Двигатель: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="3ee49-223">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-224">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-224">What's new</span></span>

- <span data-ttu-id="3ee49-225">Ведение журнала поддержки состояния [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="3ee49-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-226">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-226">Known Issues</span></span>
<span data-ttu-id="3ee49-227">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3ee49-228">Октябрь-2020 (платформа: 4.18.2010.7 | Двигатель: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="3ee49-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="3ee49-229">&ensp;Версия обновления аналитики безопасности: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="3ee49-230">&ensp;Выпущено: **29 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="3ee49-231">&ensp;Платформа: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="3ee49-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="3ee49-232">&ensp;Двигатель: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="3ee49-233">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-234">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-234">What's new</span></span>

- <span data-ttu-id="3ee49-235">Новые описания для специальных категорий угроз</span><span class="sxs-lookup"><span data-stu-id="3ee49-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="3ee49-236">Улучшенные возможности эмуляции</span><span class="sxs-lookup"><span data-stu-id="3ee49-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="3ee49-237">Улучшенный хост-адрес разрешить/заблокировать возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="3ee49-238">Новый параметр в CSP Defender для игнорирования объединения локальных исключений пользователей</span><span class="sxs-lookup"><span data-stu-id="3ee49-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-239">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-239">Known Issues</span></span>

<span data-ttu-id="3ee49-240">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3ee49-241">Сентябрь-2020 (платформа: 4.18.2009.7 | Двигатель: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="3ee49-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="3ee49-242">&ensp;Версия обновления аналитики безопасности: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="3ee49-243">&ensp;Выпущено: **01 октября 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="3ee49-244">&ensp;Платформа: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="3ee49-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="3ee49-245">&ensp;Двигатель: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="3ee49-246">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-247">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-247">What's new</span></span>

- <span data-ttu-id="3ee49-248">Для восстановления файлов в карантине требуются разрешения администратора</span><span class="sxs-lookup"><span data-stu-id="3ee49-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="3ee49-249">XML-форматированные события теперь поддерживаются</span><span class="sxs-lookup"><span data-stu-id="3ee49-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="3ee49-250">Поддержка CSP для игнорирования слияний исключений</span><span class="sxs-lookup"><span data-stu-id="3ee49-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="3ee49-251">Новые интерфейсы управления для:</span><span class="sxs-lookup"><span data-stu-id="3ee49-251">New management interfaces for:</span></span>
   - <span data-ttu-id="3ee49-252">Проверка UDP</span><span class="sxs-lookup"><span data-stu-id="3ee49-252">UDP Inspection</span></span>
   - <span data-ttu-id="3ee49-253">Защита сети на сервере 2019</span><span class="sxs-lookup"><span data-stu-id="3ee49-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="3ee49-254">Исключения IP-адресов для защиты сети</span><span class="sxs-lookup"><span data-stu-id="3ee49-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="3ee49-255">Улучшенная видимость измерений TPM</span><span class="sxs-lookup"><span data-stu-id="3ee49-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="3ee49-256">Улучшенное сканирование Office VBA</span><span class="sxs-lookup"><span data-stu-id="3ee49-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-257">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-257">Known Issues</span></span>

<span data-ttu-id="3ee49-258">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="3ee49-259">Август-2020 (платформа: 4.18.2008.9 | Двигатель: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="3ee49-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="3ee49-260">&ensp;Версия обновления аналитики безопасности: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="3ee49-261">&ensp;Выпущено: **27 августа 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="3ee49-262">&ensp;Платформа: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="3ee49-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="3ee49-263">&ensp;Двигатель: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="3ee49-264">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="3ee49-265">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-265">What's new</span></span>

- <span data-ttu-id="3ee49-266">Добавление дополнительных событий телеметрии</span><span class="sxs-lookup"><span data-stu-id="3ee49-266">Add more telemetry events</span></span>
- <span data-ttu-id="3ee49-267">Улучшенная телеметрия событий сканирования</span><span class="sxs-lookup"><span data-stu-id="3ee49-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="3ee49-268">Улучшенный мониторинг поведения при проверке памяти</span><span class="sxs-lookup"><span data-stu-id="3ee49-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="3ee49-269">Улучшенное сканирование макропотоков</span><span class="sxs-lookup"><span data-stu-id="3ee49-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="3ee49-270">Добавлен `AMRunningMode` в Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ee49-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="3ee49-271">[ОтключениеAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3ee49-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="3ee49-272">антивирусная программа в Microsoft Defender автоматически выключается при обнаружении другой антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="3ee49-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="3ee49-273">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-273">Known Issues</span></span>
<span data-ttu-id="3ee49-274">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3ee49-275">Июль-2020 (платформа: 4.18.2007.8 | Двигатель: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="3ee49-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="3ee49-276">&ensp;Версия обновления аналитики безопасности: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="3ee49-277">&ensp;Выпущено: **28 июля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="3ee49-278">&ensp;Платформа: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="3ee49-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="3ee49-279">&ensp;Двигатель: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="3ee49-280">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-281">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-281">What's new</span></span>

- <span data-ttu-id="3ee49-282">Улучшенная телеметрия для BITS</span><span class="sxs-lookup"><span data-stu-id="3ee49-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="3ee49-283">Улучшенная проверка сертификата подписи кода Authenticode</span><span class="sxs-lookup"><span data-stu-id="3ee49-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-284">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-284">Known Issues</span></span>
<span data-ttu-id="3ee49-285">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3ee49-286">Июнь-2020 (платформа: 4.18.2006.10 | Двигатель: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="3ee49-287">&ensp;Версия обновления аналитики безопасности: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="3ee49-288">&ensp;Выпущено: **22 июня 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="3ee49-289">&ensp;Платформа: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="3ee49-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="3ee49-290">&ensp;Двигатель: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="3ee49-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="3ee49-291">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-292">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-292">What's new</span></span>

- <span data-ttu-id="3ee49-293">Возможность указать [расположение журналов поддержки](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="3ee49-294">Пропуск агрессивной проверки догона в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="3ee49-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="3ee49-295">Разрешить Защитнику обновлять дозы подключений</span><span class="sxs-lookup"><span data-stu-id="3ee49-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="3ee49-296">Настройка фиксированной производительности при отключении кэшинга</span><span class="sxs-lookup"><span data-stu-id="3ee49-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="3ee49-297">Запрос фиксированного реестра</span><span class="sxs-lookup"><span data-stu-id="3ee49-297">Fixed registry query</span></span> 
- <span data-ttu-id="3ee49-298">Исправленная рандомизация времени сканирования в ADMX</span><span class="sxs-lookup"><span data-stu-id="3ee49-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-299">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-299">Known Issues</span></span>
<span data-ttu-id="3ee49-300">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3ee49-301">Май-2020 (платформа: 4.18.2005.4 | Двигатель: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="3ee49-302">&ensp;Версия обновления аналитики безопасности: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="3ee49-303">&ensp;Выпущено: **26 мая 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="3ee49-304">&ensp;Платформа: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="3ee49-305">&ensp;Двигатель: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="3ee49-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="3ee49-306">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-307">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-307">What's new</span></span>

- <span data-ttu-id="3ee49-308">Улучшенная ведение журнала для событий сканирования</span><span class="sxs-lookup"><span data-stu-id="3ee49-308">Improved logging for scan events</span></span>
- <span data-ttu-id="3ee49-309">Улучшенная обработка сбоя режима пользователя.</span><span class="sxs-lookup"><span data-stu-id="3ee49-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="3ee49-310">Добавлена трассировка событий для защиты Tamper</span><span class="sxs-lookup"><span data-stu-id="3ee49-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="3ee49-311">Исправленная отправка образца AMSI</span><span class="sxs-lookup"><span data-stu-id="3ee49-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="3ee49-312">Исправленная блокировка облака AMSI</span><span class="sxs-lookup"><span data-stu-id="3ee49-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="3ee49-313">Журнал установки фиксированного обновления безопасности</span><span class="sxs-lookup"><span data-stu-id="3ee49-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-314">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-314">Known Issues</span></span>
<span data-ttu-id="3ee49-315">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3ee49-316">Апрель-2020 (платформа: 4.18.2004.6 | Двигатель: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="3ee49-317">&ensp;Версия обновления аналитики безопасности: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="3ee49-318">&ensp;Выпущено: **30 апреля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="3ee49-319">&ensp;Платформа: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="3ee49-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="3ee49-320">&ensp;Двигатель: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="3ee49-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="3ee49-321">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-322">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-322">What's new</span></span>
- <span data-ttu-id="3ee49-323">Улучшения WDfilter</span><span class="sxs-lookup"><span data-stu-id="3ee49-323">WDfilter improvements</span></span>
- <span data-ttu-id="3ee49-324">Добавление дополнительных данных событий для атак на события обнаружения уменьшения поверхности</span><span class="sxs-lookup"><span data-stu-id="3ee49-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="3ee49-325">Сведения о фиксированной версии в диагностических данных и WMI</span><span class="sxs-lookup"><span data-stu-id="3ee49-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="3ee49-326">Исправлена неправильная версия платформы в пользовательском интерфейсе после обновления платформы</span><span class="sxs-lookup"><span data-stu-id="3ee49-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="3ee49-327">Динамический URL-адрес для защиты от угроз без файлов</span><span class="sxs-lookup"><span data-stu-id="3ee49-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="3ee49-328">Возможность сканирования UEFI</span><span class="sxs-lookup"><span data-stu-id="3ee49-328">UEFI scan capability</span></span>
- <span data-ttu-id="3ee49-329">Расширение ведения журнала для обновлений</span><span class="sxs-lookup"><span data-stu-id="3ee49-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="3ee49-330">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-330">Known Issues</span></span>
<span data-ttu-id="3ee49-331">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3ee49-332">Март-2020 (платформа: 4.18.2003.8 | Двигатель: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="3ee49-333">&ensp;Версия обновления аналитики безопасности: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="3ee49-334">&ensp;Выпущено: **24 марта 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="3ee49-335">&ensp;Платформа: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="3ee49-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="3ee49-336">&ensp;Двигатель: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="3ee49-337">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3ee49-338">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-338">What's new</span></span>

- <span data-ttu-id="3ee49-339">Параметр регулирования ЦП, добавленный в [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="3ee49-340">Улучшение возможностей диагностики</span><span class="sxs-lookup"><span data-stu-id="3ee49-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="3ee49-341">уменьшение времени разведданных безопасности (5 минут)</span><span class="sxs-lookup"><span data-stu-id="3ee49-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="3ee49-342">Расширение возможностей внутреннего журнала двигателя AMSI</span><span class="sxs-lookup"><span data-stu-id="3ee49-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="3ee49-343">Улучшение уведомления о блокировке процесса</span><span class="sxs-lookup"><span data-stu-id="3ee49-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="3ee49-344">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-344">Known Issues</span></span>
<span data-ttu-id="3ee49-345">**[Исправлено]** антивирусная программа в Microsoft Defender пропускает файлы при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="3ee49-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="3ee49-346">Февраль-2020 (платформа: - | Двигатель: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="3ee49-347">&ensp;Версия обновления аналитики безопасности: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="3ee49-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="3ee49-348">&ensp;Выпущено: **25 февраля 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="3ee49-349">&ensp;Платформа/клиент: **-**</span><span class="sxs-lookup"><span data-stu-id="3ee49-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="3ee49-350">&ensp;Двигатель: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="3ee49-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="3ee49-351">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="3ee49-352">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="3ee49-353">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-353">Known Issues</span></span>
<span data-ttu-id="3ee49-354">Отсутствие известных проблем</span><span class="sxs-lookup"><span data-stu-id="3ee49-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="3ee49-355">Январь-2020 (платформа: 4.18.2001.10 | Двигатель: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="3ee49-356">Версия обновления аналитики безопасности: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="3ee49-357">Выпущено: **30 января 2020 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="3ee49-358">Платформа/клиент: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="3ee49-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="3ee49-359">Двигатель: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="3ee49-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="3ee49-360">&ensp;Этап поддержки: **техническая поддержка обновления (только)**</span><span class="sxs-lookup"><span data-stu-id="3ee49-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="3ee49-361">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-361">What's new</span></span>

- <span data-ttu-id="3ee49-362">Исправлена BSOD на WS2016 с Exchange</span><span class="sxs-lookup"><span data-stu-id="3ee49-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="3ee49-363">Обновления платформы поддержки при перенаправлении TMP на сетевой путь</span><span class="sxs-lookup"><span data-stu-id="3ee49-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="3ee49-364">Версии платформы и двигателя добавляются в [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="3ee49-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="3ee49-365">расширение обновления подписи аварийной ситуации до [пассивного режима](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="3ee49-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="3ee49-366">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="3ee49-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="3ee49-367">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-367">Known Issues</span></span>

<span data-ttu-id="3ee49-368">**[Исправленные]** устройства, использующие современный режим ожидания, могут испытывать зависание с драйвером Защитник Windows фильтра, что приводит к разрыву защиты. [](/windows-hardware/design/device-experiences/modern-standby)</span><span class="sxs-lookup"><span data-stu-id="3ee49-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="3ee49-369">Затронутые компьютеры, как представляется, не обновляются до последней платформы антивирусного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="3ee49-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="3ee49-370">Это обновление:</span><span class="sxs-lookup"><span data-stu-id="3ee49-370">This update is:</span></span>
> - <span data-ttu-id="3ee49-371">для устройств RS1 с более низкой версией платформы для поддержки SHA2;</span><span class="sxs-lookup"><span data-stu-id="3ee49-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="3ee49-372">имеет флаг перезагрузки для систем с висячими вопросами;</span><span class="sxs-lookup"><span data-stu-id="3ee49-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="3ee49-373">повторно выпущен в апреле 2020 г. и не будет совмещаяся с новыми обновлениями для сохраняемой доступности в будущем;</span><span class="sxs-lookup"><span data-stu-id="3ee49-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="3ee49-374">классифицируются как обновление из-за требования перезагрузки; и</span><span class="sxs-lookup"><span data-stu-id="3ee49-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="3ee49-375">предлагается только с [Windows update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="3ee49-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="3ee49-376">Ноябрь-2019 (платформа: 4.18.1911.3 | Двигатель: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="3ee49-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="3ee49-377">Версия обновления аналитики безопасности: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="3ee49-378">Выпущено: **7 декабря 2019 г.**</span><span class="sxs-lookup"><span data-stu-id="3ee49-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="3ee49-379">Платформа: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="3ee49-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="3ee49-380">Двигатель: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="3ee49-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="3ee49-381">Этап поддержки: **поддержка не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="3ee49-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="3ee49-382">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="3ee49-382">What's new</span></span>

- <span data-ttu-id="3ee49-383">Фиксированный уровень отслеживания MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="3ee49-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="3ee49-384">Исправленная информация версии WDFilter</span><span class="sxs-lookup"><span data-stu-id="3ee49-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="3ee49-385">Улучшение уведомлений (PUA)</span><span class="sxs-lookup"><span data-stu-id="3ee49-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="3ee49-386">добавление журналов MRT для поддержки файлов</span><span class="sxs-lookup"><span data-stu-id="3ee49-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="3ee49-387">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3ee49-387">Known Issues</span></span>
<span data-ttu-id="3ee49-388">При установке этого обновления устройству требуется пакет скачок 4.18.2001.10 для обновления до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="3ee49-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="3ee49-389">антивирусная программа в Microsoft Defender поддержки платформы</span><span class="sxs-lookup"><span data-stu-id="3ee49-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="3ee49-390">Обновления платформы и двигателя предоставляются на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="3ee49-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="3ee49-391">Чтобы получить полную поддержку, следите за последними обновлениями платформы.</span><span class="sxs-lookup"><span data-stu-id="3ee49-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="3ee49-392">Наша структура поддержки динамична и развивается в два этапа в зависимости от доступности последней версии платформы:</span><span class="sxs-lookup"><span data-stu-id="3ee49-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="3ee49-393">**Этап обслуживания служб** безопасности и критически важных обновлений . При запуске последней версии платформы вы сможете получать как обновления безопасности, так и критические обновления для платформы защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="3ee49-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="3ee49-394">**Этап технической поддержки (только)** — после выпуска новой версии платформы поддержка более старых версий (N-2) будет сокращена только до технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="3ee49-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="3ee49-395">Версии платформы старше N-2 больше не будут поддерживаться.\*</span><span class="sxs-lookup"><span data-stu-id="3ee49-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="3ee49-396">\*Техническая поддержка будет по-прежнему предоставляться для обновлений из версии Windows 10 версии (см. версию [Platform,](#platform-version-included-with-windows-10-releases)включенную в Windows 10 выпусках) до последней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="3ee49-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="3ee49-397">На этапе технической поддержки (только) коммерчески обоснованные инциденты поддержки будут предоставляться через Службу поддержки клиентов Майкрософт & поддержку и управляемые предложения поддержки Майкрософт (например, Premier Support).</span><span class="sxs-lookup"><span data-stu-id="3ee49-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="3ee49-398">Если инцидент поддержки требует эскалации для разработки для получения дополнительных указаний, требует обновления без обеспечения безопасности или обновления безопасности, клиентам будет предложено обновить до последней версии платформы или промежуточного обновления (\*).</span><span class="sxs-lookup"><span data-stu-id="3ee49-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="3ee49-399">Версия платформы, включенная в Windows 10 выпусков</span><span class="sxs-lookup"><span data-stu-id="3ee49-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="3ee49-400">В приведенной ниже таблице приведены антивирусная программа в Microsoft Defender платформы и версии двигателей, которые поставляются с последними Windows 10 выпусками:</span><span class="sxs-lookup"><span data-stu-id="3ee49-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="3ee49-401">Windows 10 выпуска</span><span class="sxs-lookup"><span data-stu-id="3ee49-401">Windows 10 release</span></span>  |<span data-ttu-id="3ee49-402">Версия платформы</span><span class="sxs-lookup"><span data-stu-id="3ee49-402">Platform version</span></span>  |<span data-ttu-id="3ee49-403">Версия двигателя</span><span class="sxs-lookup"><span data-stu-id="3ee49-403">Engine version</span></span> |<span data-ttu-id="3ee49-404">Этап поддержки</span><span class="sxs-lookup"><span data-stu-id="3ee49-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="3ee49-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="3ee49-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="3ee49-406">4.18.1909.6</span></span> |<span data-ttu-id="3ee49-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="3ee49-407">1.1.17000.2</span></span> | <span data-ttu-id="3ee49-408">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3ee49-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-409">1909  (19H2)</span></span> |<span data-ttu-id="3ee49-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="3ee49-410">4.18.1902.5</span></span> |<span data-ttu-id="3ee49-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="3ee49-411">1.1.16700.3</span></span> | <span data-ttu-id="3ee49-412">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3ee49-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="3ee49-413">1903  (19H1)</span></span> |<span data-ttu-id="3ee49-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="3ee49-414">4.18.1902.5</span></span> |<span data-ttu-id="3ee49-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="3ee49-415">1.1.15600.4</span></span> | <span data-ttu-id="3ee49-416">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3ee49-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="3ee49-417">1809  (RS5)</span></span> |<span data-ttu-id="3ee49-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="3ee49-418">4.18.1807.18075</span></span> |<span data-ttu-id="3ee49-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="3ee49-419">1.1.15000.2</span></span> | <span data-ttu-id="3ee49-420">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3ee49-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="3ee49-421">1803  (RS4)</span></span> |<span data-ttu-id="3ee49-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="3ee49-422">4.13.17134.1</span></span> |<span data-ttu-id="3ee49-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="3ee49-423">1.1.14600.4</span></span> | <span data-ttu-id="3ee49-424">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3ee49-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="3ee49-425">1709  (RS3)</span></span> |<span data-ttu-id="3ee49-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="3ee49-426">4.12.16299.15</span></span> |<span data-ttu-id="3ee49-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="3ee49-427">1.1.14104.0</span></span> | <span data-ttu-id="3ee49-428">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3ee49-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="3ee49-429">1703  (RS2)</span></span> |<span data-ttu-id="3ee49-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="3ee49-430">4.11.15603.2</span></span> |<span data-ttu-id="3ee49-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="3ee49-431">1.1.13504.0</span></span> | <span data-ttu-id="3ee49-432">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3ee49-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="3ee49-433">1607 (RS1)</span></span> |<span data-ttu-id="3ee49-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="3ee49-434">4.10.14393.3683</span></span> |<span data-ttu-id="3ee49-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="3ee49-435">1.1.12805.0</span></span> | <span data-ttu-id="3ee49-436">Техническая поддержка обновления (только)</span><span class="sxs-lookup"><span data-stu-id="3ee49-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="3ee49-437">Сведения Windows 10 релиза см. в Windows [информационном листе жизненного цикла.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="3ee49-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="3ee49-438">Обновления для обслуживания и управления изображениями развертывания (DISM)</span><span class="sxs-lookup"><span data-stu-id="3ee49-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="3ee49-439">Рекомендуется обновить Windows 10 (Enterprise, Pro и Домашние выпуски), Windows Server 2019 и Windows Server 2016 изображений установки ОС с последними обновлениями антивирусных и антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="3ee49-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="3ee49-440">Сохранение изображений установки ОС в курсе данных помогает избежать пробела в защите.</span><span class="sxs-lookup"><span data-stu-id="3ee49-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="3ee49-441">Дополнительные сведения см. в [обновлении Microsoft Defender для Windows изображений установки операционной системы.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="3ee49-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="3ee49-442">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="3ee49-442">1.1.2106.01</span></span></summary>

<span data-ttu-id="3ee49-443">&ensp;Версия пакета: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-443">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="3ee49-444">&ensp;Версия платформы: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="3ee49-444">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="3ee49-445">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="3ee49-445">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="3ee49-446">&ensp;Версия подписи: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-446">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-447">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-447">Fixes</span></span>
- <span data-ttu-id="3ee49-448">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-449">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-449">Additional information</span></span>
- <span data-ttu-id="3ee49-450">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-451">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="3ee49-451">1.1.2105.01</span></span></summary>

<span data-ttu-id="3ee49-452">&ensp;Версия пакета: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-452">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="3ee49-453">&ensp;Версия платформы: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="3ee49-453">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="3ee49-454">&ensp;Версия двигателя: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="3ee49-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="3ee49-455">&ensp;Версия подписи: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-455">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-456">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-456">Fixes</span></span>
- <span data-ttu-id="3ee49-457">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-458">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-458">Additional information</span></span>
- <span data-ttu-id="3ee49-459">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-460">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="3ee49-460">1.1.2104.01</span></span></summary>

<span data-ttu-id="3ee49-461">&ensp;Версия пакета: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-461">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="3ee49-462">&ensp;Версия платформы: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="3ee49-462">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="3ee49-463">&ensp;Версия двигателя: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-463">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="3ee49-464">&ensp;Версия подписи: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-464">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-465">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-465">Fixes</span></span>
- <span data-ttu-id="3ee49-466">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-467">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-467">Additional information</span></span>
- <span data-ttu-id="3ee49-468">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-469">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="3ee49-469">1.1.2103.01</span></span></summary>

<span data-ttu-id="3ee49-470">&ensp;Версия пакета: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-470">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="3ee49-471">&ensp;Версия платформы: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="3ee49-471">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="3ee49-472">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-472">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="3ee49-473">&ensp;Версия подписи: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-473">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-474">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-474">Fixes</span></span>
- <span data-ttu-id="3ee49-475">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-476">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-476">Additional information</span></span>
- <span data-ttu-id="3ee49-477">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-478">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="3ee49-478">1.1.2102.03</span></span></summary>

<span data-ttu-id="3ee49-479">&ensp;Версия пакета: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-479">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="3ee49-480">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="3ee49-480">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="3ee49-481">&ensp;Версия двигателя: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="3ee49-482">&ensp;Версия подписи: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-482">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-483">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-483">Fixes</span></span>
- <span data-ttu-id="3ee49-484">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-485">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-485">Additional information</span></span>
- <span data-ttu-id="3ee49-486">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-487">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="3ee49-487">1.1.2101.02</span></span></summary>

<span data-ttu-id="3ee49-488">&ensp;Версия пакета: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-488">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="3ee49-489">&ensp;Версия платформы: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="3ee49-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="3ee49-490">&ensp;Версия двигателя: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="3ee49-490">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="3ee49-491">&ensp;Версия подписи: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-491">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-492">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-492">Fixes</span></span>
- <span data-ttu-id="3ee49-493">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-494">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-494">Additional information</span></span>
- <span data-ttu-id="3ee49-495">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-496">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="3ee49-496">1.1.2012.01</span></span></summary>

<span data-ttu-id="3ee49-497">&ensp;Версия пакета: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-497">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="3ee49-498">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="3ee49-498">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="3ee49-499">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="3ee49-500">&ensp;Версия для подписи: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-500">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-501">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-501">Fixes</span></span>
- <span data-ttu-id="3ee49-502">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-503">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-503">Additional information</span></span>
- <span data-ttu-id="3ee49-504">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-505">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="3ee49-505">1.1.2011.02</span></span></summary>

<span data-ttu-id="3ee49-506">&ensp;Версия пакета: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-506">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="3ee49-507">&ensp;Версия платформы: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="3ee49-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="3ee49-508">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="3ee49-509">&ensp;Версия подписи: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-509">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-510">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-510">Fixes</span></span>
- <span data-ttu-id="3ee49-511">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-512">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-512">Additional information</span></span>
- <span data-ttu-id="3ee49-513">Обновленные антивирусная программа в Microsoft Defender подписи</span><span class="sxs-lookup"><span data-stu-id="3ee49-513">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-514">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="3ee49-514">1.1.2011.01</span></span></summary>

<span data-ttu-id="3ee49-515">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-515">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="3ee49-516">&ensp;Версия платформы: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="3ee49-516">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="3ee49-517">&ensp;Версия двигателя: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="3ee49-518">&ensp;Версия подписи: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-518">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-519">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-519">Fixes</span></span>
- <span data-ttu-id="3ee49-520">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-521">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-521">Additional information</span></span>
- <span data-ttu-id="3ee49-522">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-522">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3ee49-523">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="3ee49-523">1.1.2009.10</span></span></summary>

<span data-ttu-id="3ee49-524">&ensp;Версия пакета: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="3ee49-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="3ee49-525">&ensp;Версия платформы: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="3ee49-525">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="3ee49-526">&ensp;Версия двигателя: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="3ee49-526">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="3ee49-527">&ensp;Версия для подписи: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="3ee49-527">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3ee49-528">Исправления</span><span class="sxs-lookup"><span data-stu-id="3ee49-528">Fixes</span></span>
- <span data-ttu-id="3ee49-529">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ee49-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3ee49-530">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee49-530">Additional information</span></span>
- <span data-ttu-id="3ee49-531">Добавлена поддержка Windows 10 RS1 или более поздней оси установки изображений.</span><span class="sxs-lookup"><span data-stu-id="3ee49-531">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="3ee49-532">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="3ee49-532">Additional resources</span></span>

| <span data-ttu-id="3ee49-533">Статья</span><span class="sxs-lookup"><span data-stu-id="3ee49-533">Article</span></span> | <span data-ttu-id="3ee49-534">Описание</span><span class="sxs-lookup"><span data-stu-id="3ee49-534">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="3ee49-535">Обновление Microsoft Defender для Windows изображений установки операционной системы</span><span class="sxs-lookup"><span data-stu-id="3ee49-535">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="3ee49-536">Просмотрите пакеты обновления антивирусных программ для изображений установки ОС (WIM и VHD-файлы).</span><span class="sxs-lookup"><span data-stu-id="3ee49-536">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="3ee49-537">Получите антивирусная программа в Microsoft Defender обновления для Windows 10 (Enterprise, Pro и домашних выпусков), Windows Server 2019 и Windows Server 2016 изображений установки.</span><span class="sxs-lookup"><span data-stu-id="3ee49-537">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="3ee49-538">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="3ee49-538">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="3ee49-539">Обновления защиты могут быть доставлены из многих источников.</span><span class="sxs-lookup"><span data-stu-id="3ee49-539">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="3ee49-540">Управление загрузкой и приложением обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="3ee49-540">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="3ee49-541">Можно запланировать загрузку обновлений защиты.</span><span class="sxs-lookup"><span data-stu-id="3ee49-541">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="3ee49-542">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="3ee49-542">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="3ee49-543">Если конечная точка пропустит обновление или запланированное сканирование, вы можете принудить к обновлению или сканировать при следующем взявке пользователя.</span><span class="sxs-lookup"><span data-stu-id="3ee49-543">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="3ee49-544">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="3ee49-544">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="3ee49-545">Можно установить обновления защиты для скачивания при запуске или после определенных событий защиты с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="3ee49-545">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="3ee49-546">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="3ee49-546">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="3ee49-547">Можно указать параметры, например, следует ли обновлять заряд батареи, которые особенно полезны для мобильных устройств и виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="3ee49-547">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
