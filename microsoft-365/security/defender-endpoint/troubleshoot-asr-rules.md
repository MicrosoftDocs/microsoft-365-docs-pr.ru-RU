---
title: Отчет и устранение неполадок в Microsoft Defender для правил ASR конечной точки
description: В этом разделе описаны отчеты и устранение неполадок Microsoft Defender для правил ASR конечной точки
keywords: Правила уменьшения поверхности атаки, asr, hips, система предотвращения вторжения хостов, правила защиты, антиэкспозиция, антиэкспозит, эксплойт, профилактика инфекций, защитник Майкрософт для конечной точки
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246257"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="f108b-104">Отчет и устранение неполадок Microsoft Defender для правил ASR ATP</span><span class="sxs-lookup"><span data-stu-id="f108b-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f108b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f108b-105">**Applies to:**</span></span>

- [<span data-ttu-id="f108b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f108b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f108b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f108b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f108b-108">Центр Microsoft 365 безопасности — это новый интерфейс для мониторинга и управления безопасностью в идентификаторах, данных, устройствах, приложениях и инфраструктуре Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f108b-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="f108b-109">Здесь можно просмотреть сведения о работоспособности системы безопасности вашей организации, настроить устройства, пользователей и приложения, а также проверить оповещения о подозрительных действиях.</span><span class="sxs-lookup"><span data-stu-id="f108b-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="f108b-110">Центр безопасности Microsoft 365 создан для того чтобы администраторы безопасности и группы операций безопасности могли лучше управлять вашей организацией и защищать ее.</span><span class="sxs-lookup"><span data-stu-id="f108b-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="f108b-111">Посетите центр Microsoft 365 безопасности на https://security.microsoft.com сайте .</span><span class="sxs-lookup"><span data-stu-id="f108b-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="f108b-112">В Microsoft 365 центре безопасности мы предлагаем вам полный взгляд на текущую конфигурацию правил ASR и события в вашем имении.</span><span class="sxs-lookup"><span data-stu-id="f108b-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="f108b-113">Обратите внимание, что для заполнения этих отчетов необходимо ввести устройства в службу Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f108b-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="f108b-114">Вот снимок экрана из центра безопасности Microsoft 365 (в статье **Reports**  >  **Devices**  >  **Attack surface reduction).**</span><span class="sxs-lookup"><span data-stu-id="f108b-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="f108b-115">На уровне устройства выберите **Конфигурация** из области правил уменьшения поверхности **Attack.**</span><span class="sxs-lookup"><span data-stu-id="f108b-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="f108b-116">Отображается следующий экран, на котором можно выбрать определенное устройство и проверить его индивидуальную конфигурацию правил ASR.</span><span class="sxs-lookup"><span data-stu-id="f108b-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="Экран правил ASR":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="f108b-118">Microsoft Defender для конечной точки — расширенный поиск</span><span class="sxs-lookup"><span data-stu-id="f108b-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="f108b-119">Одна из самых мощных функций Microsoft Defender для конечной точки — это продвинутая охота.</span><span class="sxs-lookup"><span data-stu-id="f108b-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="f108b-120">Если вы не знакомы с развитой охотой, обратитесь к активной охоте на угрозы [с помощью расширенных охоты.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f108b-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="f108b-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span><span class="sxs-lookup"><span data-stu-id="f108b-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="f108b-122">С помощью продвинутой охоты можно активно проверять события, чтобы найти интересные индикаторы и объекты.</span><span class="sxs-lookup"><span data-stu-id="f108b-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="f108b-123">Гибкий доступ к данным помогает безудержно искать как известные, так и потенциальные угрозы.</span><span class="sxs-lookup"><span data-stu-id="f108b-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="f108b-124">С помощью продвинутой охоты можно извлечь сведения о правилах ASR, создавать отчеты и получать углубленные сведения о контексте данного аудита или события блокировки правил ASR.</span><span class="sxs-lookup"><span data-stu-id="f108b-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="f108b-125">События правил ASR доступны для запроса из таблицы DeviceEvents в разделе расширенный раздел Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f108b-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f108b-126">Например, простой запрос, например ниже, может сообщать о всех событиях, которые имеют правила ASR в качестве источника данных, за последние 30 дней и суммировать их по подсчету ActionType, что в этом случае это будет фактическое кодовое имя правила ASR.</span><span class="sxs-lookup"><span data-stu-id="f108b-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Расширенный запрос на охоту":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="расширенный экран охоты":::

<span data-ttu-id="f108b-129">С помощью продвинутой охоты вы можете формировать запросы по своему вкусу, чтобы вы могли видеть, что происходит, независимо от того, хотите ли вы что-то определить на отдельной машине, или вы хотите извлечь сведения из всей среды.</span><span class="sxs-lookup"><span data-stu-id="f108b-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="f108b-130">Шкала microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f108b-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="f108b-131">Альтернативой передовой охоте, но с более узкой областью, является временная шкала машины Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f108b-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="f108b-132">Вы можете просмотреть все собранные события устройства за последние шесть месяцев в Центр безопасности в Microsoft Defender, переехав в список Машин, выберите заданную машину и нажмите на вкладку Timeline.</span><span class="sxs-lookup"><span data-stu-id="f108b-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="f108b-133">На рисунке ниже приведен снимок экрана представления Временной шкалы этих событий на данной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="f108b-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="f108b-134">Из этого представления можно отфильтровать список событий на основе любой из групп событий на правой стороне области.</span><span class="sxs-lookup"><span data-stu-id="f108b-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="f108b-135">Вы также можете включить или отключить события с флагом и вербозией во время просмотра оповещений и прокрутки по исторической шкале.</span><span class="sxs-lookup"><span data-stu-id="f108b-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Хронология центра безопасности защитника Майкрософт":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="f108b-137">Устранение неполадок в правилах ASR?</span><span class="sxs-lookup"><span data-stu-id="f108b-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="f108b-138">Первый и самый непосредственный способ — проверить локально на устройстве Windows, в котором включены правила ASR (и их конфигурация) с помощью cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f108b-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="f108b-139">Вот несколько других источников информации, которые Windows, чтобы устранить влияние и работу правил ASR.</span><span class="sxs-lookup"><span data-stu-id="f108b-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="f108b-140">Запрашивание активных правил</span><span class="sxs-lookup"><span data-stu-id="f108b-140">Querying which rules are active</span></span>
<span data-ttu-id="f108b-141">Один из самых простых способов определить, включены ли правила ASR, — и с помощью комлета PowerShell Get-MpPreference.</span><span class="sxs-lookup"><span data-stu-id="f108b-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="f108b-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="f108b-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="получить сценарий mppreference":::

<span data-ttu-id="f108b-144">Существует несколько активных правил ASR с различными настроенными действиями.</span><span class="sxs-lookup"><span data-stu-id="f108b-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="f108b-145">Чтобы расширить вышеуказанные сведения о правилах ASR, можно использовать свойства AttackSurfaceReductionRules_Ids  **и/или AttackSurfaceReductionRules_Actions.**</span><span class="sxs-lookup"><span data-stu-id="f108b-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="f108b-146">Пример.</span><span class="sxs-lookup"><span data-stu-id="f108b-146">Example:</span></span>

<span data-ttu-id="f108b-147">*Get-MPPreference | Select-Object-ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="f108b-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="пример mpreference":::

<span data-ttu-id="f108b-149">Выше показаны все ID-данные для правил ASR, которые имеют параметр, отличаемый от 0 (Не настроен).</span><span class="sxs-lookup"><span data-stu-id="f108b-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="f108b-150">Затем необходимо перечислить фактические действия (блок или аудит), с помощью которых настраивается каждое правило.</span><span class="sxs-lookup"><span data-stu-id="f108b-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="f108b-151">*Get-MPPreference | Select-Object-ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="f108b-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="f108b-153">Запрос событий блокировки и аудита</span><span class="sxs-lookup"><span data-stu-id="f108b-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="f108b-154">События правил ASR можно просмотреть в журнале Защитник Windows.</span><span class="sxs-lookup"><span data-stu-id="f108b-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="f108b-155">Чтобы получить к нему доступ, откройте Windows для просмотра событий и просмотрите журналы приложений и служб  >  **Microsoft**  >  **Windows**  >  **Защитник Windows**  >  **operational**.</span><span class="sxs-lookup"><span data-stu-id="f108b-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="SCR просмотра событий":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="f108b-157">Журналы защиты от вредоносных программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f108b-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="f108b-158">Вы также можете просматривать события правил с помощью антивирусная программа в Microsoft Defender средства командной строки, называемого , который можно использовать для управления и настройки и автоматизации задач, если `*mpcmdrun.exe*` это необходимо.</span><span class="sxs-lookup"><span data-stu-id="f108b-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="f108b-159">Эту утилиту можно найти в *%ProgramFiles%\Windows Defender\MpCmdRun.exe.*</span><span class="sxs-lookup"><span data-stu-id="f108b-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="f108b-160">Вы должны запустить его из команды с повышенным запросом (то есть выполнить в качестве администратора).</span><span class="sxs-lookup"><span data-stu-id="f108b-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="f108b-161">Чтобы создать сведения о поддержке, *введитеMpCmdRun.exe -getfiles*.</span><span class="sxs-lookup"><span data-stu-id="f108b-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="f108b-162">Через некоторое время несколько журналов будут упакованы в архив (MpSupportFiles.cab) и доступны в *C:\ProgramData\Microsoft\Защитник Windows\Support*.</span><span class="sxs-lookup"><span data-stu-id="f108b-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="журналы защиты от вредоносных программ":::

<span data-ttu-id="f108b-164">Извлекать этот архив, и у вас будет много файлов, доступных для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="f108b-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="f108b-165">Наиболее релевантные файлы:</span><span class="sxs-lookup"><span data-stu-id="f108b-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="f108b-166">**MPOperationalEvents.txt** - Этот файл содержит тот же уровень сведений, что и в Защитник Windows журнала операционной службы.</span><span class="sxs-lookup"><span data-stu-id="f108b-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="f108b-167">**MPRegistry.txt** — В этом файле вы сможете проанализировать все текущие конфигурации Защитник Windows с момента захвата журналов поддержки.</span><span class="sxs-lookup"><span data-stu-id="f108b-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="f108b-168">**MPLog.txt** — Этот журнал содержит более подробные сведения обо всех действиях и операциях Защитник Windows.</span><span class="sxs-lookup"><span data-stu-id="f108b-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
