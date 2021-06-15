---
title: Управление получением антивирусная программа в Microsoft Defender и получением обновлений
description: Управление порядком отката для получения обновлений антивирусная программа в Microsoft Defender защиты.
keywords: обновления, базовые показатели безопасности, защита, порядок отката, ADL, MMPC, UNC, путь к файлу, share, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 35873b371e773e793ae966a338150e2e5e256a42
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926035"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a><span data-ttu-id="ef82f-104">Управление источниками обновлений антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ef82f-104">Manage the sources for Microsoft Defender Antivirus protection updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ef82f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ef82f-105">**Applies to:**</span></span>

- [<span data-ttu-id="ef82f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ef82f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

<span data-ttu-id="ef82f-107">Важно поддерживать антивирусную защиту в соответствии с данными.</span><span class="sxs-lookup"><span data-stu-id="ef82f-107">Keeping your antivirus protection up to date is critical.</span></span> <span data-ttu-id="ef82f-108">Существует два компонента управления обновлениями защиты для антивирусная программа в Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="ef82f-108">There are two components to managing protection updates for Microsoft Defender Antivirus:</span></span> 
- <span data-ttu-id="ef82f-109">*Загрузка* обновлений; и</span><span class="sxs-lookup"><span data-stu-id="ef82f-109">*Where* the updates are downloaded from; and</span></span> 
- <span data-ttu-id="ef82f-110">*При* загрузке и применении обновлений.</span><span class="sxs-lookup"><span data-stu-id="ef82f-110">*When* updates are downloaded and applied.</span></span> 

<span data-ttu-id="ef82f-111">В этой статье описывается, как указать, откуда должны загружаться обновления (это также называется заказом на откат).</span><span class="sxs-lookup"><span data-stu-id="ef82f-111">This article describes how to specify from where updates should be downloaded (this is also known as the fallback order).</span></span> <span data-ttu-id="ef82f-112">См. [антивирусная программа в Microsoft Defender](manage-updates-baselines-microsoft-defender-antivirus.md) управление обновлениями и применение базовых версий для обзора работы обновлений и настройки других аспектов обновлений (например, планирования обновлений).</span><span class="sxs-lookup"><span data-stu-id="ef82f-112">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef82f-113">антивирусная программа в Microsoft Defender Обновления разведки безопасности доставляются через Windows обновления и начиная с понедельника, 21 октября 2019 г., все обновления разведки безопасности будут подписаны исключительно sha-2.</span><span class="sxs-lookup"><span data-stu-id="ef82f-113">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update and starting Monday, October 21, 2019, all security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="ef82f-114">Чтобы обновить сведения о безопасности, необходимо обновить устройства для поддержки SHA-2.</span><span class="sxs-lookup"><span data-stu-id="ef82f-114">Your devices must be updated to support SHA-2 in order to update your security intelligence.</span></span> <span data-ttu-id="ef82f-115">Дополнительные дополнительные новости см. в [2019 г. В sha-2 Code Signing Support requirement for Windows и WSUS.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)</span><span class="sxs-lookup"><span data-stu-id="ef82f-115">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>  


<a id="fallback-order"></a>

## <a name="fallback-order"></a><span data-ttu-id="ef82f-116">Порядок отката</span><span class="sxs-lookup"><span data-stu-id="ef82f-116">Fallback order</span></span>

<span data-ttu-id="ef82f-117">Обычно конечные точки настраиваются для индивидуальной загрузки обновлений из основного источника, а затем из других источников в порядке приоритета в зависимости от конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="ef82f-117">Typically, you configure endpoints to individually download updates from a primary source followed by other sources in order of priority, based on your network configuration.</span></span> <span data-ttu-id="ef82f-118">Обновления получаются из источников в порядке, который вы указываете.</span><span class="sxs-lookup"><span data-stu-id="ef82f-118">Updates are obtained from sources in the order you specify.</span></span> <span data-ttu-id="ef82f-119">Если источник не доступен, следующий источник в списке используется немедленно.</span><span class="sxs-lookup"><span data-stu-id="ef82f-119">If a source is not available, the next source in the list is used immediately.</span></span>

<span data-ttu-id="ef82f-120">При публикации обновлений применяется какая-то логика, чтобы свести к минимуму размер обновления.</span><span class="sxs-lookup"><span data-stu-id="ef82f-120">When updates are published, some logic is applied to minimize the size of the update.</span></span> <span data-ttu-id="ef82f-121">В большинстве случаев на устройстве загружаются и применяются только различия между последним обновлением и установленным в настоящее время обновлением (это называется дельта).</span><span class="sxs-lookup"><span data-stu-id="ef82f-121">In most cases, only the differences between the latest update and the update that is currently installed (this is referred to as the delta) on the device is downloaded and applied.</span></span> <span data-ttu-id="ef82f-122">Однако размер дельты зависит от двух основных факторов:</span><span class="sxs-lookup"><span data-stu-id="ef82f-122">However, the size of the delta depends on two main factors:</span></span>
- <span data-ttu-id="ef82f-123">Возраст последнего обновления на устройстве; и</span><span class="sxs-lookup"><span data-stu-id="ef82f-123">The age of the last update on the device; and</span></span> 
- <span data-ttu-id="ef82f-124">Источник, используемый для скачивания и применения обновлений.</span><span class="sxs-lookup"><span data-stu-id="ef82f-124">The source used to download and apply updates.</span></span> 

<span data-ttu-id="ef82f-125">Чем старше будут обновления на конечной точке, тем больше будет скачивание.</span><span class="sxs-lookup"><span data-stu-id="ef82f-125">The older the updates on an endpoint, the larger the download will be.</span></span> <span data-ttu-id="ef82f-126">Однако необходимо также учитывать частоту скачивания.</span><span class="sxs-lookup"><span data-stu-id="ef82f-126">However, you must also consider download frequency as well.</span></span> <span data-ttu-id="ef82f-127">Более частое расписание обновлений может привести к большему использованию сети, в то время как менее частое расписание может привести к большим размерам файлов для загрузки.</span><span class="sxs-lookup"><span data-stu-id="ef82f-127">A more frequent update schedule can result in more network usage, whereas a less-frequent schedule can result in larger file sizes per download.</span></span> 

<span data-ttu-id="ef82f-128">Существует пять местоположений, в которых можно указать, где конечная точка должна получать обновления:</span><span class="sxs-lookup"><span data-stu-id="ef82f-128">There are five locations where you can specify where an endpoint should obtain updates:</span></span> 

- [<span data-ttu-id="ef82f-129">Центр обновления Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ef82f-129">Microsoft Update</span></span>](https://support.microsoft.com/help/12373/windows-update-faq)
- [<span data-ttu-id="ef82f-130">Windows Служба обновления сервера</span><span class="sxs-lookup"><span data-stu-id="ef82f-130">Windows Server Update Service</span></span>](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [<span data-ttu-id="ef82f-131">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ef82f-131">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/core/servers/manage/updates)
- [<span data-ttu-id="ef82f-132">Доля сетевых файлов</span><span class="sxs-lookup"><span data-stu-id="ef82f-132">Network file share</span></span>](#unc-share)
- <span data-ttu-id="ef82f-133">[Обновления аналитики](https://www.microsoft.com/en-us/wdsi/defenderupdates) безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ Майкрософт (ваша политика и реестр могут иметь этот список как Центр Майкрософт по защите от вредоносных программ (MMPC) и его прежнее имя.)</span><span class="sxs-lookup"><span data-stu-id="ef82f-133">[Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Your policy and registry might have this listed as Microsoft Malware Protection Center (MMPC) security intelligence, its former name.)</span></span>

<span data-ttu-id="ef82f-134">Чтобы обеспечить наилучший уровень защиты, Microsoft Update позволяет быстро выпускать, что означает частые скачивания.</span><span class="sxs-lookup"><span data-stu-id="ef82f-134">To ensure the best level of protection, Microsoft Update allows for rapid releases, which means smaller downloads on a frequent basis.</span></span> <span data-ttu-id="ef82f-135">Источники Windows обновления серверов, Microsoft Endpoint Configuration Manager и microsoft security updates обеспечивают менее частые обновления.</span><span class="sxs-lookup"><span data-stu-id="ef82f-135">The Windows Server Update Service, Microsoft Endpoint Configuration Manager, and Microsoft security intelligence updates sources deliver less frequent updates.</span></span> <span data-ttu-id="ef82f-136">Таким образом, дельта может быть больше, что приводит к большим загрузкам.</span><span class="sxs-lookup"><span data-stu-id="ef82f-136">Thus, the delta can be larger, resulting in larger downloads.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ef82f-137">Если после Windows службы обновления серверов или обновления Microsoft Update вы задаете обновления страницы разведки Microsoft [Security](https://www.microsoft.com/security/portal/definitions/adl.aspx) в качестве источника отката, обновления загружаются только из обновлений разведки безопасности, если текущее обновление считается устарелым.</span><span class="sxs-lookup"><span data-stu-id="ef82f-137">If you have set [Microsoft Security intelligence page](https://www.microsoft.com/security/portal/definitions/adl.aspx) updates as a fallback source after Windows Server Update Service or Microsoft Update, updates are only downloaded from security intelligence updates when the current update is considered out-of-date.</span></span> <span data-ttu-id="ef82f-138">(По умолчанию это семь дней подряд, когда не удалось применить обновления из службы обновления Windows сервера или службы обновления Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="ef82f-138">(By default, this is seven consecutive days of not being able to apply updates from the Windows Server Update Service or Microsoft Update services).</span></span>
> <span data-ttu-id="ef82f-139">Однако можно установить количество дней до того, как защита будет отчитаться о том, что она [устарела.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)</span><span class="sxs-lookup"><span data-stu-id="ef82f-139">You can, however, [set the number of days before protection is reported as out-of-date](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span><p>
> <span data-ttu-id="ef82f-140">Начиная с понедельника, 21 октября 2019 г., обновления аналитики безопасности будут подписывался исключительно sha-2.</span><span class="sxs-lookup"><span data-stu-id="ef82f-140">Starting Monday, October 21, 2019, security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="ef82f-141">Устройства должны обновляться для поддержки SHA-2 для получения последних обновлений разведки безопасности.</span><span class="sxs-lookup"><span data-stu-id="ef82f-141">Devices must be updated to support SHA-2 in order to get the latest security intelligence updates.</span></span> <span data-ttu-id="ef82f-142">Дополнительные дополнительные новости см. в [2019 г. В sha-2 Code Signing Support requirement for Windows и WSUS.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)</span><span class="sxs-lookup"><span data-stu-id="ef82f-142">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>

<span data-ttu-id="ef82f-143">Каждый источник имеет типичные сценарии, которые зависят от настройки сети, а также от того, как часто они публикуют обновления, как описано в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="ef82f-143">Each source has typical scenarios that depend on how your network is configured, in addition to how often they publish updates, as described in the following table:</span></span>

|<span data-ttu-id="ef82f-144">Местоположение</span><span class="sxs-lookup"><span data-stu-id="ef82f-144">Location</span></span> | <span data-ttu-id="ef82f-145">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="ef82f-145">Sample scenario</span></span> |
|---|---|
|<span data-ttu-id="ef82f-146">Windows Служба обновления сервера</span><span class="sxs-lookup"><span data-stu-id="ef82f-146">Windows Server Update Service</span></span> | <span data-ttu-id="ef82f-147">Вы используете службу Windows сервера для управления обновлениями для вашей сети.</span><span class="sxs-lookup"><span data-stu-id="ef82f-147">You are using Windows Server Update Service to manage updates for your network.</span></span>|
|<span data-ttu-id="ef82f-148">Центр обновления Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ef82f-148">Microsoft Update</span></span> | <span data-ttu-id="ef82f-149">Вы хотите, чтобы конечные точки подключались непосредственно к Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="ef82f-149">You want your endpoints to connect directly to Microsoft Update.</span></span> <span data-ttu-id="ef82f-150">Это может быть полезно для конечных точек, которые нерегулярно подключаются к корпоративной сети, или если вы не используете службу обновления Windows сервера для управления обновлениями.</span><span class="sxs-lookup"><span data-stu-id="ef82f-150">This can be useful for endpoints that irregularly connect to your enterprise network, or if you do not use Windows Server Update Service to manage your updates.</span></span>|
|<span data-ttu-id="ef82f-151">Файловый ресурс</span><span class="sxs-lookup"><span data-stu-id="ef82f-151">File share</span></span> | <span data-ttu-id="ef82f-152">У вас есть устройства, не подключенные к Интернету (например, VMs).</span><span class="sxs-lookup"><span data-stu-id="ef82f-152">You have non-Internet-connected devices (such as VMs).</span></span> <span data-ttu-id="ef82f-153">Вы можете использовать подключенный к Интернету VM-хост для скачивания обновлений в сеть, из которой VMs могут получать обновления.</span><span class="sxs-lookup"><span data-stu-id="ef82f-153">You can use your Internet-connected VM host to download the updates to a network share, from which the VMs can obtain the updates.</span></span> <span data-ttu-id="ef82f-154">См. руководство по развертыванию [VDI](deployment-vdi-microsoft-defender-antivirus.md) для использования файловых акций в средах виртуальной инфраструктуры настольных компьютеров (VDI).</span><span class="sxs-lookup"><span data-stu-id="ef82f-154">See the [VDI deployment guide](deployment-vdi-microsoft-defender-antivirus.md) for how file shares can be used in virtual desktop infrastructure (VDI) environments.</span></span>|
|<span data-ttu-id="ef82f-155">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ef82f-155">Microsoft Endpoint Manager</span></span> | <span data-ttu-id="ef82f-156">Вы используете Microsoft Endpoint Manager для обновления конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ef82f-156">You are using Microsoft Endpoint Manager to update your endpoints.</span></span>|
|<span data-ttu-id="ef82f-157">Обновления аналитики безопасности для антивирусная программа в Microsoft Defender и других антивирусных программ Майкрософт (ранее именуемой MMPC)</span><span class="sxs-lookup"><span data-stu-id="ef82f-157">Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware (formerly referred to as MMPC)</span></span> |<span data-ttu-id="ef82f-158">[Убедитесь, что ваши устройства обновляются для поддержки SHA-2.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)</span><span class="sxs-lookup"><span data-stu-id="ef82f-158">[Make sure your devices are updated to support SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span> <span data-ttu-id="ef82f-159">антивирусная программа в Microsoft Defender Обновления разведки безопасности доставляются через Windows Update, и начиная с понедельника 21 октября 2019 г. обновления сведении о безопасности будут подписываться исключительно на SHA-2.</span><span class="sxs-lookup"><span data-stu-id="ef82f-159">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update, and starting Monday October 21, 2019 security intelligence updates will be SHA-2 signed exclusively.</span></span> <br/><span data-ttu-id="ef82f-160">Скачайте последние обновления защиты из-за недавней инфекции или чтобы помочь в предоставлении сильного базового изображения для [развертывания VDI.](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ef82f-160">Download the latest protection updates because of a recent infection or to help provision a strong, base image for [VDI deployment](deployment-vdi-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="ef82f-161">Обычно этот параметр следует использовать только в качестве конечного источника отката, а не основного источника.</span><span class="sxs-lookup"><span data-stu-id="ef82f-161">This option should generally be used only as a final fallback source, and not the primary source.</span></span> <span data-ttu-id="ef82f-162">Он будет использоваться только в том случае, если обновления не могут быть загружены Windows службы обновления сервера или Обновления Майкрософт в течение определенного числа [дней.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)</span><span class="sxs-lookup"><span data-stu-id="ef82f-162">It will only be used if updates cannot be downloaded from Windows Server Update Service or Microsoft Update for [a specified number of days](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span>|

<span data-ttu-id="ef82f-163">Вы можете управлять порядком, в котором источники обновления используются с помощью групповых политик, Microsoft Endpoint Configuration Manager, powerShell и WMI.</span><span class="sxs-lookup"><span data-stu-id="ef82f-163">You can manage the order in which update sources are used with Group Policy, Microsoft Endpoint Configuration Manager, PowerShell cmdlets, and WMI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef82f-164">Если вы Windows службу обновления сервера в качестве расположения загрузки, необходимо утвердить обновления независимо от средства управления, используемого для указания местоположения.</span><span class="sxs-lookup"><span data-stu-id="ef82f-164">If you set Windows Server Update Service as a download location, you must approve the updates, regardless of the management tool you use to specify the location.</span></span> <span data-ttu-id="ef82f-165">Вы можете настроить автоматическое правило утверждения с Windows службой обновления сервера, которое может быть полезно по мере поступления обновлений по крайней мере один раз в день.</span><span class="sxs-lookup"><span data-stu-id="ef82f-165">You can set up an automatic approval rule with Windows Server Update Service, which might be useful as updates arrive at least once a day.</span></span> <span data-ttu-id="ef82f-166">Дополнительные данные см. в том, как синхронизировать обновления защиты конечной точки в автономных [Windows службе обновления сервера.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="ef82f-166">To learn more, see [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

<span data-ttu-id="ef82f-167">Процедуры в этой статье сначала описывают, как настроить порядок, а затем настроить параметр **Share File,** если он включен.</span><span class="sxs-lookup"><span data-stu-id="ef82f-167">The procedures in this article first describe how to set the order, and then how to set up the **File share** option if you have enabled it.</span></span>

## <a name="use-group-policy-to-manage-the-update-location"></a><span data-ttu-id="ef82f-168">Использование групповой политики для управления расположением обновления</span><span class="sxs-lookup"><span data-stu-id="ef82f-168">Use Group Policy to manage the update location</span></span>

1. <span data-ttu-id="ef82f-169">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-169">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="ef82f-170">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="ef82f-170">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="ef82f-171">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-171">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="ef82f-172">Расширь **дерево, Windows компоненты > Защитник Windows > Подписи** и настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ef82f-172">Expand the tree to **Windows components > Windows Defender > Signature updates** and configure the following settings:</span></span>

   1.  <span data-ttu-id="ef82f-173">Дважды щелкните **кнопку Определить порядок источников** для скачивания параметров обновлений разведки безопасности и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-173">Double-click the **Define the order of sources for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   2.  <span data-ttu-id="ef82f-174">Введите порядок источников, разделенных одной трубой, например: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , как показано на следующем скриншоте.</span><span class="sxs-lookup"><span data-stu-id="ef82f-174">Enter the order of sources, separated by a single pipe, for example: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, as shown in the following screenshot.</span></span>

   ![Снимок экрана настройки групповой политики с перечислением порядка источников](images/defender/wdav-order-update-sources.png)

   3. <span data-ttu-id="ef82f-176">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-176">Click **OK**.</span></span> <span data-ttu-id="ef82f-177">При этом будет установлен порядок источников обновления защиты.</span><span class="sxs-lookup"><span data-stu-id="ef82f-177">This will set the order of protection update sources.</span></span>

   4. <span data-ttu-id="ef82f-178">Дважды щелкните **файл Define shares для скачивания** параметра обновлений разведки безопасности и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-178">Double-click the **Define file shares for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   5. <span data-ttu-id="ef82f-179">Введите источник файловой папки.</span><span class="sxs-lookup"><span data-stu-id="ef82f-179">Enter the file share source.</span></span> <span data-ttu-id="ef82f-180">Если у вас несколько источников, введите каждый источник в том порядке, в который они должны использоваться, разделенные одной трубой.</span><span class="sxs-lookup"><span data-stu-id="ef82f-180">If you have multiple sources, enter each source in the order they should be used, separated by a single pipe.</span></span> <span data-ttu-id="ef82f-181">Используйте [стандартную нотацию UNC](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) для обозначания пути, например: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .</span><span class="sxs-lookup"><span data-stu-id="ef82f-181">Use [standard UNC notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) for denoting the path, for example: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`.</span></span>  <span data-ttu-id="ef82f-182">Если вы не введите какие-либо пути, этот источник будет пропущен при загрузке обновлений VM.</span><span class="sxs-lookup"><span data-stu-id="ef82f-182">If you do not enter any paths, then this source will be skipped when the VM downloads updates.</span></span>

   6. <span data-ttu-id="ef82f-183">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-183">Click **OK**.</span></span> <span data-ttu-id="ef82f-184">При этом будет задат порядок файловых акций при ссылке на этот источник в параметре **Определить порядок источников...**</span><span class="sxs-lookup"><span data-stu-id="ef82f-184">This will set the order of file shares when that source is referenced in the **Define the order of sources...** group policy setting.</span></span>

> [!NOTE]
> <span data-ttu-id="ef82f-185">Для Windows 10 версии 1703 до 1809 года путь политики Windows компоненты **> антивирусная программа в Microsoft Defender >** Обновления подписи для Windows 10 версии 1903, путь политики — Windows **Компоненты > антивирусная программа в Microsoft Defender >** Обновления разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="ef82f-185">For Windows 10, versions 1703 up to and including 1809, the policy path is **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is **Windows Components > Microsoft Defender Antivirus > Security Intelligence Updates**</span></span>

## <a name="use-configuration-manager-to-manage-the-update-location"></a><span data-ttu-id="ef82f-186">Использование диспетчера конфигурации для управления расположением обновления</span><span class="sxs-lookup"><span data-stu-id="ef82f-186">Use Configuration Manager to manage the update location</span></span>

<span data-ttu-id="ef82f-187">Сведения [о настройке](/configmgr/protect/deploy-use/endpoint-definition-updates) Endpoint Protection безопасности см. в Microsoft Endpoint Manager (текущая ветвь).</span><span class="sxs-lookup"><span data-stu-id="ef82f-187">See [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a><span data-ttu-id="ef82f-188">Чтобы управлять расположением обновления, используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef82f-188">Use PowerShell cmdlets to manage the update location</span></span>

<span data-ttu-id="ef82f-189">Чтобы установить порядок обновления, используйте следующие cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef82f-189">Use the following PowerShell cmdlets to set the update order.</span></span>

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
<span data-ttu-id="ef82f-190">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ef82f-190">See the following articles for more information:</span></span>
- [<span data-ttu-id="ef82f-191">Set-MpPreference -SignatureFallbackOrder</span><span class="sxs-lookup"><span data-stu-id="ef82f-191">Set-MpPreference -SignatureFallbackOrder</span></span>](/powershell/module/defender/set-mppreference)
- [<span data-ttu-id="ef82f-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span><span class="sxs-lookup"><span data-stu-id="ef82f-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span></span>](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [<span data-ttu-id="ef82f-193">Для настройки и запуска антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ef82f-193">Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ef82f-194">Cmdlets Defender</span><span class="sxs-lookup"><span data-stu-id="ef82f-194">Defender cmdlets</span></span>](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a><span data-ttu-id="ef82f-195">Используйте Windows управления (WMI) для управления расположением обновления</span><span class="sxs-lookup"><span data-stu-id="ef82f-195">Use Windows Management Instruction (WMI) to manage the update location</span></span>

<span data-ttu-id="ef82f-196">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="ef82f-196">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

<span data-ttu-id="ef82f-197">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ef82f-197">See the following articles for more information:</span></span>
- [<span data-ttu-id="ef82f-198">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="ef82f-198">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a><span data-ttu-id="ef82f-199">Управление мобильными устройствами (MDM) для управления расположением обновления</span><span class="sxs-lookup"><span data-stu-id="ef82f-199">Use Mobile Device Management (MDM) to manage the update location</span></span>

<span data-ttu-id="ef82f-200">Сведения о настройке MDM см. в материале [Policy CSP - Defender/SignatureUpdateFallbackOrder.](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)</span><span class="sxs-lookup"><span data-stu-id="ef82f-200">See [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) for details on configuring MDM.</span></span>

## <a name="what-if-were-using-a-third-party-vendor"></a><span data-ttu-id="ef82f-201">Что делать, если мы используем сторонного поставщика?</span><span class="sxs-lookup"><span data-stu-id="ef82f-201">What if we're using a third-party vendor?</span></span>

<span data-ttu-id="ef82f-202">В этой статье описывается настройка и управление обновлениями для антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ef82f-202">This article describes how to configure and manage updates for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="ef82f-203">Однако для выполнения этих задач можно использовать сторонних поставщиков.</span><span class="sxs-lookup"><span data-stu-id="ef82f-203">However, third-party vendors can be used to perform these tasks.</span></span> 

<span data-ttu-id="ef82f-204">Например, предположим, что Contoso нанял Fabrikam для управления решением безопасности, которое включает антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ef82f-204">For example, suppose that Contoso has hired Fabrikam to manage their security solution, which includes Microsoft Defender Antivirus.</span></span> <span data-ttu-id="ef82f-205">Fabrikam обычно использует [Windows](./use-wmi-microsoft-defender-antivirus.md)инструментов управления, командлеты [PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md) [](./command-line-arguments-microsoft-defender-antivirus.md) или Windows командной строки для развертывания исправлений и обновлений.</span><span class="sxs-lookup"><span data-stu-id="ef82f-205">Fabrikam typically uses [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md), [PowerShell cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md), or [Windows command-line](./command-line-arguments-microsoft-defender-antivirus.md) to deploy patches and updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="ef82f-206">Корпорация Майкрософт не тестировать сторонние решения для управления антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ef82f-206">Microsoft does not test third-party solutions for managing Microsoft Defender Antivirus.</span></span>

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a><span data-ttu-id="ef82f-207">Создание доли UNC для обновлений сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="ef82f-207">Create a UNC share for security intelligence updates</span></span>

<span data-ttu-id="ef82f-208">Настройка доли сетевых файлов (unC/mapped drive) для загрузки обновлений аналитики безопасности с сайта MMPC с помощью запланированной задачи.</span><span class="sxs-lookup"><span data-stu-id="ef82f-208">Set up a network file share (UNC/mapped drive) to download security intelligence updates from the MMPC site by using a scheduled task.</span></span>

1. <span data-ttu-id="ef82f-209">В системе, в которой необходимо создать долю и скачать обновления, создайте папку, в которой будет сохраняться скрипт.</span><span class="sxs-lookup"><span data-stu-id="ef82f-209">On the system on which you want to provision the share and download the updates, create a folder to which you will save the script.</span></span>
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. <span data-ttu-id="ef82f-210">Создайте папку, в которой будут сохраняться обновления подписей.</span><span class="sxs-lookup"><span data-stu-id="ef82f-210">Create the folder to which you will save the signature updates.</span></span>
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. <span data-ttu-id="ef82f-211">Скачайте сценарий PowerShell из [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span><span class="sxs-lookup"><span data-stu-id="ef82f-211">Download the PowerShell script from [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span></span>

4. <span data-ttu-id="ef82f-212">Нажмите **кнопку Ручная загрузка**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-212">Click **Manual Download**.</span></span>

5. <span data-ttu-id="ef82f-213">Нажмите **кнопку Скачать необработанные файлы nupkg**.</span><span class="sxs-lookup"><span data-stu-id="ef82f-213">Click **Download the raw nupkg file**.</span></span>

6. <span data-ttu-id="ef82f-214">Извлечение файла.</span><span class="sxs-lookup"><span data-stu-id="ef82f-214">Extract the file.</span></span>

7. <span data-ttu-id="ef82f-215">Скопируйте файл SignatureDownloadCustomTask.ps1 в ранее созданную папку C:\Tool\PS-Scripts\.</span><span class="sxs-lookup"><span data-stu-id="ef82f-215">Copy the file SignatureDownloadCustomTask.ps1 to the folder you previously created, C:\Tool\PS-Scripts\ .</span></span>

8. <span data-ttu-id="ef82f-216">Чтобы настроить запланированную задачу, используйте командную строку.</span><span class="sxs-lookup"><span data-stu-id="ef82f-216">Use the command line to set up the scheduled task.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ef82f-217">Существует два типа обновлений: полный и дельта.</span><span class="sxs-lookup"><span data-stu-id="ef82f-217">There are two types of updates: full and delta.</span></span>
   - <span data-ttu-id="ef82f-218">Для дельты x64:</span><span class="sxs-lookup"><span data-stu-id="ef82f-218">For x64 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="ef82f-219">Для полного x64:</span><span class="sxs-lookup"><span data-stu-id="ef82f-219">For x64 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="ef82f-220">Для дельты x86:</span><span class="sxs-lookup"><span data-stu-id="ef82f-220">For x86 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="ef82f-221">Для полного x86:</span><span class="sxs-lookup"><span data-stu-id="ef82f-221">For x86 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > <span data-ttu-id="ef82f-222">После создания запланированных задач их можно найти в план-графике задач в Microsoft\Windows\Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="ef82f-222">When the scheduled tasks are created, you can find these in the Task Scheduler under Microsoft\Windows\Windows Defender</span></span>
9. <span data-ttu-id="ef82f-223">Запустите каждую задачу вручную и убедитесь, что у вас есть данные (mpam-d.exe, mpam-fe.exe и nis_full.exe) в следующих папках (возможно, вы выбрали различные расположения):</span><span class="sxs-lookup"><span data-stu-id="ef82f-223">Run each task manually and verify that you have data (mpam-d.exe, mpam-fe.exe, and nis_full.exe) in the following folders (you might have chosen different locations):</span></span>

   - <span data-ttu-id="ef82f-224">C:\Temp\TempSigs\x86</span><span class="sxs-lookup"><span data-stu-id="ef82f-224">C:\Temp\TempSigs\x86</span></span>
   - <span data-ttu-id="ef82f-225">C:\Temp\TempSigs\x64</span><span class="sxs-lookup"><span data-stu-id="ef82f-225">C:\Temp\TempSigs\x64</span></span>

   <span data-ttu-id="ef82f-226">Если запланированная задача сбой, запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="ef82f-226">If the scheduled task fails, run the following commands:</span></span>

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > <span data-ttu-id="ef82f-227">Проблемы также могут быть вызваны политикой выполнения.</span><span class="sxs-lookup"><span data-stu-id="ef82f-227">Issues could also be due to execution policy.</span></span>
    
10. <span data-ttu-id="ef82f-228">Создайте акцию, указывав на C:\Temp\TempSigs (например, \\ сервер\обновления).</span><span class="sxs-lookup"><span data-stu-id="ef82f-228">Create a share pointing to C:\Temp\TempSigs (e.g. \\server\updates).</span></span>
    > [!NOTE]
    > <span data-ttu-id="ef82f-229">По крайней мере, пользователи с проверкой подлинности должны иметь доступ к "Чтение".</span><span class="sxs-lookup"><span data-stu-id="ef82f-229">At a minimum, authenticated users must have "Read" access.</span></span>
11. <span data-ttu-id="ef82f-230">Установите расположение доли в политике для этой доли.</span><span class="sxs-lookup"><span data-stu-id="ef82f-230">Set the share location in the policy to the share.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef82f-231">Не добавляйте папку x64 (или x86) в путь.</span><span class="sxs-lookup"><span data-stu-id="ef82f-231">Do not add the x64 (or x86) folder in the path.</span></span> <span data-ttu-id="ef82f-232">Процесс mpcmdrun.exe добавляет его автоматически.</span><span class="sxs-lookup"><span data-stu-id="ef82f-232">The mpcmdrun.exe process adds it automatically.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ef82f-233">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ef82f-233">Related articles</span></span>

- [<span data-ttu-id="ef82f-234">Развертывание антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ef82f-234">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ef82f-235">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="ef82f-235">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ef82f-236">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="ef82f-236">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ef82f-237">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="ef82f-237">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ef82f-238">Управление обновлениями для мобильных устройств и VMs</span><span class="sxs-lookup"><span data-stu-id="ef82f-238">Manage updates for mobile devices and VMs</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ef82f-239">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="ef82f-239">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
