---
title: Коды событий и коды ошибок Microsoft Defender AV
description: Поиск причин и решений для ID и ошибок антивирусных событий Microsoft Defender
keywords: событие, код ошибки, siem, ведение журнала, устранение неполадок, wef, пересылание событий Windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f7e8d6428360e5fe45a377f3ed6611a76f0a7911
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765819"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="625d7-104">Просмотр журналов событий и кодов ошибок для устранения неполадок с антивирусной программой в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="625d7-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="625d7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="625d7-105">**Applies to:**</span></span>

- [<span data-ttu-id="625d7-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="625d7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="625d7-107">Если у вас возникла проблема с антивирусом Microsoft Defender, вы можете найти таблицы в этом разделе, чтобы найти совпадающие проблемы и потенциальное решение.</span><span class="sxs-lookup"><span data-stu-id="625d7-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="625d7-108">Список таблиц:</span><span class="sxs-lookup"><span data-stu-id="625d7-108">The tables list:</span></span>

- <span data-ttu-id="625d7-109">[ID-документы антивирусных](#windows-defender-av-ids) событий Microsoft Defender (они применяются как к Windows 10, так и к Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="625d7-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="625d7-110">Коды ошибок клиентов антивирусной программы Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="625d7-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="625d7-111">Внутренние коды ошибок клиента антивирусного защитника Майкрософт (используемые Корпорацией Майкрософт во время разработки и тестирования)</span><span class="sxs-lookup"><span data-stu-id="625d7-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="625d7-112">Вы также можете посетить веб-сайт демонстрации Microsoft Defender для конечной точки [в demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить, что работают следующие функции:</span><span class="sxs-lookup"><span data-stu-id="625d7-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="625d7-113">Защита с облачным доставкой</span><span class="sxs-lookup"><span data-stu-id="625d7-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="625d7-114">Быстрое обучение (включая блок с первого взгляда)</span><span class="sxs-lookup"><span data-stu-id="625d7-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="625d7-115">Блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="625d7-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="625d7-116">ID-ID событий антивирусного события Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="625d7-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="625d7-117">Антивирус Microsoft Defender записи событий в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="625d7-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="625d7-118">Вы можете напрямую просмотреть журнал событий, или если у вас есть сторонний инструмент управления данными безопасности и событиями (SIEM), вы также можете использовать [ID-данные](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) клиентских событий антивирусной программы Microsoft Defender для проверки определенных событий и ошибок с конечных точек.</span><span class="sxs-lookup"><span data-stu-id="625d7-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="625d7-119">В таблице в этом разделе перечислены основные ID событий антивирусного события Защитника Майкрософт и, по возможности, предлагаются предлагаемые решения для исправления или устранения ошибки.</span><span class="sxs-lookup"><span data-stu-id="625d7-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="625d7-120">Просмотр антивирусного события Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="625d7-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="625d7-121">Open **Event Viewer**.</span><span class="sxs-lookup"><span data-stu-id="625d7-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="625d7-122">В дереве консоли разойдите **журналы приложений** и **служб,** **затем Microsoft,** **затем Windows,** а затем Защитник Windows .</span><span class="sxs-lookup"><span data-stu-id="625d7-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="625d7-123">Дважды нажмите кнопку **Оперативный**.</span><span class="sxs-lookup"><span data-stu-id="625d7-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="625d7-124">В области сведений просмотреть список отдельных событий, чтобы найти событие.</span><span class="sxs-lookup"><span data-stu-id="625d7-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="625d7-125">Щелкните событие, чтобы увидеть конкретные сведения о событии в нижней области в вкладке **Общие** и **Подробные** сведения.</span><span class="sxs-lookup"><span data-stu-id="625d7-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="625d7-126">ID события: 1000</span><span class="sxs-lookup"><span data-stu-id="625d7-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-127">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="625d7-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-129">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-129">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-130">
<b>Началось сканирование антивирусного программного обеспечения. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="625d7-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="625d7-132">
<dt>Scan ID: &lt; ID-номер соответствующей &gt; проверки.</dt> 
<dt> Тип сканирования: &lt; тип &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-133">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-133">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-134">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-135">Antimalware</span></span></li>
</ul><span data-ttu-id="625d7-136">
</dt>
<dt>Параметры сканирования: &lt; параметры &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-137">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-137">Full scan</span></span></li>
<li><span data-ttu-id="625d7-138">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-138">Quick scan</span></span></li>
<li><span data-ttu-id="625d7-139">Сканирование клиентов</span><span class="sxs-lookup"><span data-stu-id="625d7-139">Customer scan</span></span></li>
</ul><span data-ttu-id="625d7-140">
</dt>
<dt>Ресурсы сканирования: &lt; Сканированные ресурсы (например, файлы/каталоги/BHO). &gt; </dt> 
<dt>Пользователь: &lt; lt &gt; \& домена; Пользователь &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-141">ID события: 1001</span><span class="sxs-lookup"><span data-stu-id="625d7-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-142">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-144">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-144">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-145">
<b>Проверка противомалярийных программ завершена.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-146">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="625d7-147">
<dt>Scan ID: &lt; ID-номер соответствующей &gt; проверки.</dt> 
<dt> Тип сканирования: &lt; тип &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-148">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-148">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-149">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-150">Antimalware</span></span></li>
</ul><span data-ttu-id="625d7-151">
</dt>
<dt>Параметры сканирования: &lt; параметры &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-152">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-152">Full scan</span></span></li>
<li><span data-ttu-id="625d7-153">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-153">Quick scan</span></span></li>
<li><span data-ttu-id="625d7-154">Сканирование клиентов</span><span class="sxs-lookup"><span data-stu-id="625d7-154">Customer scan</span></span></li>
</ul><span data-ttu-id="625d7-155">
</dt>
<dt>Пользователь: &lt; lt &gt; \& домена; Время &gt; </dt>
<dt>сканирования пользователя: &lt; продолжительность &gt; сканирования.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-156">ID события: 1002</span><span class="sxs-lookup"><span data-stu-id="625d7-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-157">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-159">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-159">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-160">
<b>Проверка противомалярийных программ была остановлена до его завершения. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-161">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="625d7-162">
<dt>Scan ID: &lt; ID-номер соответствующей &gt; проверки.</dt> 
<dt> Тип сканирования: &lt; тип &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-163">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-163">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-164">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-165">Antimalware</span></span></li>
</ul><span data-ttu-id="625d7-166">
</dt>
<dt>Параметры сканирования: &lt; параметры &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-167">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-167">Full scan</span></span></li>
<li><span data-ttu-id="625d7-168">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-168">Quick scan</span></span></li>
<li><span data-ttu-id="625d7-169">Сканирование клиентов</span><span class="sxs-lookup"><span data-stu-id="625d7-169">Customer scan</span></span></li>
</ul><span data-ttu-id="625d7-170">
</dt>
<dt>Пользователь: &lt; lt &gt; &amp; домена; Время &gt; </dt>
<dt>сканирования пользователя: &lt; продолжительность &gt; сканирования.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-171">ID события: 1003</span><span class="sxs-lookup"><span data-stu-id="625d7-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-172">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-174">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-174">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-175">
<b>Было приостановлено сканирование антивирусных программ. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-176">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="625d7-177">
<dt>Scan ID: &lt; ID-номер соответствующей &gt; проверки.</dt> 
<dt> Тип сканирования: &lt; тип &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-178">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-178">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-179">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-180">Antimalware</span></span></li>
</ul><span data-ttu-id="625d7-181">
</dt>
<dt>Параметры сканирования: &lt; параметры &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-182">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-182">Full scan</span></span></li>
<li><span data-ttu-id="625d7-183">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-183">Quick scan</span></span></li>
<li><span data-ttu-id="625d7-184">Сканирование клиентов</span><span class="sxs-lookup"><span data-stu-id="625d7-184">Customer scan</span></span></li>
</ul><span data-ttu-id="625d7-185">
</dt>
<dt>Пользователь: &lt; &gt; \& lt домена; Пользователь&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-186">ID события: 1004</span><span class="sxs-lookup"><span data-stu-id="625d7-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-187">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-189">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-189">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-190">
<b>Было возобновлено сканирование противомалярийных программ. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-191">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="625d7-192">
<dt>Scan ID: &lt; ID-номер соответствующей &gt; проверки.</dt> 
<dt> Тип сканирования: &lt; тип &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-193">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-193">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-194">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-195">Antimalware</span></span></li>
</ul><span data-ttu-id="625d7-196">
</dt>
<dt>Параметры сканирования: &lt; параметры &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-197">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-197">Full scan</span></span></li>
<li><span data-ttu-id="625d7-198">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-198">Quick scan</span></span></li>
<li><span data-ttu-id="625d7-199">Сканирование клиентов</span><span class="sxs-lookup"><span data-stu-id="625d7-199">Customer scan</span></span></li>
</ul><span data-ttu-id="625d7-200">
</dt>
<dt>Пользователь: &lt; &gt; \& lt домена; Пользователь&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-201">ID события: 1005</span><span class="sxs-lookup"><span data-stu-id="625d7-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-202">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-204">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-204">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-205">
<b>Проверка антивирусных программ не удалась. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-206">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="625d7-207">
<dt>Scan ID: &lt; ID-номер соответствующей &gt; проверки.</dt> 
<dt> Тип сканирования: &lt; тип &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-208">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-208">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-209">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-210">Antimalware</span></span></li>
</ul><span data-ttu-id="625d7-211">
</dt>
<dt>Параметры сканирования: &lt; параметры &gt; сканирования, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-212">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-212">Full scan</span></span></li>
<li><span data-ttu-id="625d7-213">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="625d7-213">Quick scan</span></span></li>
<li><span data-ttu-id="625d7-214">Сканирование клиентов</span><span class="sxs-lookup"><span data-stu-id="625d7-214">Customer scan</span></span></li>
</ul><span data-ttu-id="625d7-215">
</dt>
<dt>Пользователь: &lt; lt &gt; \& домена; Код &gt; </dt>
<dt>ошибки пользователя. &lt; Код результатов &gt; кода ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-216">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-217">Антивирусный клиент столкнулся с ошибкой, и текущее сканирование остановлено.</span><span class="sxs-lookup"><span data-stu-id="625d7-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="625d7-218">Проверка может привести к сбою из-за проблемы с клиентом.</span><span class="sxs-lookup"><span data-stu-id="625d7-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="625d7-219">Эта запись событий включает в себя код сканирования, тип сканирования (антивирус Microsoft Defender, антивирусное программное обеспечение, антивирусное программное обеспечение), параметры сканирования, пользователя, который начал проверку, код ошибки и описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="625d7-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="625d7-220">Устранение неполадок в этом событии:</span><span class="sxs-lookup"><span data-stu-id="625d7-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="625d7-221">Снова запустите сканирование.</span><span class="sxs-lookup"><span data-stu-id="625d7-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="625d7-222">Если это не удается таким же образом, перейдите на сайт <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support,</a>введите номер ошибки в поле Поиска, чтобы найти код ошибки.</span><span class="sxs-lookup"><span data-stu-id="625d7-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="625d7-223">Обратитесь в <a href="https://go.microsoft.com/fwlink/?LinkId=215491">службу поддержки Майкрософт</a>.</span><span class="sxs-lookup"><span data-stu-id="625d7-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-224">ID события: 1006</span><span class="sxs-lookup"><span data-stu-id="625d7-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-225">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-227">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-227">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-228">
<b>В антивирусном движке обнаружено вредоносное ПО или другое потенциально нежелательное программное обеспечение. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-229">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-230">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-231">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-232">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-232">Low</span></span></li>
<li><span data-ttu-id="625d7-233">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-233">Moderate</span></span></li>
<li><span data-ttu-id="625d7-234">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-234">High</span></span></li>
<li><span data-ttu-id="625d7-235">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-235">Severe</span></span></li>
</ul><span data-ttu-id="625d7-236">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Происхождение &gt; пути обнаружения</dt> 
<dt> файлов: &lt; происхождение &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-237">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="625d7-237">Unknown</span></span></li>
<li><span data-ttu-id="625d7-238">Локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="625d7-238">Local computer</span></span></li>
<li><span data-ttu-id="625d7-239">Сетевая папка</span><span class="sxs-lookup"><span data-stu-id="625d7-239">Network share</span></span></li>
<li><span data-ttu-id="625d7-240">Интернет</span><span class="sxs-lookup"><span data-stu-id="625d7-240">Internet</span></span></li>
<li><span data-ttu-id="625d7-241">Входящий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="625d7-242">Исходяющий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="625d7-243">
</dt>
<dt>Тип обнаружения: &lt; тип &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-244">Heuristics</span><span class="sxs-lookup"><span data-stu-id="625d7-244">Heuristics</span></span></li>
<li><span data-ttu-id="625d7-245">Generic</span><span class="sxs-lookup"><span data-stu-id="625d7-245">Generic</span></span></li>
<li><span data-ttu-id="625d7-246">Бетон</span><span class="sxs-lookup"><span data-stu-id="625d7-246">Concrete</span></span></li>
<li><span data-ttu-id="625d7-247">Динамическая подпись</span><span class="sxs-lookup"><span data-stu-id="625d7-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="625d7-248">
</dt>
<dt>Источник обнаружения: &lt; источник &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="625d7-249">Пользователь: инициированный пользователем</span><span class="sxs-lookup"><span data-stu-id="625d7-249">User: user initiated</span></span></li>
<li><span data-ttu-id="625d7-250">Система: инициированная система</span><span class="sxs-lookup"><span data-stu-id="625d7-250">System: system initiated</span></span></li>
<li><span data-ttu-id="625d7-251">В режиме реального времени: инициирован компонент в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="625d7-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="625d7-252">IOAV: инициированные загрузки IE и экспресс-вложения Outlook</span><span class="sxs-lookup"><span data-stu-id="625d7-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="625d7-253">NIS: система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="625d7-254">IEPROTECT: IE - IExtensionValidation; это защищает от вредоносных элементов управления веб-страницами</span><span class="sxs-lookup"><span data-stu-id="625d7-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="625d7-255">Ранний запуск антивирусных программ (ELAM).</span><span class="sxs-lookup"><span data-stu-id="625d7-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="625d7-256">Это включает вредоносные программы, обнаруженные в последовательности загрузки</span><span class="sxs-lookup"><span data-stu-id="625d7-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="625d7-257">Удаленная атестация</span><span class="sxs-lookup"><span data-stu-id="625d7-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="625d7-258">Интерфейс сканирования антивирусных программ (AMSI).</span><span class="sxs-lookup"><span data-stu-id="625d7-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="625d7-259">В основном используется для защиты скриптов (PS, VBS), хотя они могут вызываться и третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="625d7-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="625d7-260">Состояние </dt> 
<dt>UAC: &lt; пользователь &gt; </dt>
<dt>состояния: &lt; домен &gt; \& lt; Имя &gt; </dt>
<dt>процесса пользователя: &lt; процесс &gt; в версии подписи PID:</dt>
<dt> &lt; Версия &gt; </dt>двигателя версии
<dt>определения: &lt; версия движка antimalware &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-261">Идентификатор события: 1007</span><span class="sxs-lookup"><span data-stu-id="625d7-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-262">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-264">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-264">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-265">
<b>Платформа антивирусных программ выполнила действие, чтобы защитить систему от вредоносных программ или другого потенциально нежелательного программного обеспечения. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-266">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-267">Антивирус Microsoft Defender принял меры для защиты этой машины от вредоносных программ или другого потенциально нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="625d7-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="625d7-268">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-269">
<dt>Пользователь: &lt; lt &gt; \& домена; Имя &gt; </dt>
<dt>пользователя: &lt; &gt; ID имени</dt>
<dt> &lt; &gt; угрозы: Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-270">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-270">Low</span></span></li>
<li><span data-ttu-id="625d7-271">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-271">Moderate</span></span></li>
<li><span data-ttu-id="625d7-272">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-272">High</span></span></li>
<li><span data-ttu-id="625d7-273">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-273">Severe</span></span></li>
</ul><span data-ttu-id="625d7-274">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt> Действие: &lt; &gt; действие, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-275">Clean: ресурс был очищен</span><span class="sxs-lookup"><span data-stu-id="625d7-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="625d7-276">Карантин. Ресурс был карантин</span><span class="sxs-lookup"><span data-stu-id="625d7-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="625d7-277">Удаление. Ресурс был удален</span><span class="sxs-lookup"><span data-stu-id="625d7-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="625d7-278">Разрешить. Ресурс разрешено выполнять или существовать</span><span class="sxs-lookup"><span data-stu-id="625d7-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="625d7-279">Определено пользователем: обычно это действие, определенное пользователем, из этого списка действий, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="625d7-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="625d7-280">Нет действий: нет действий</span><span class="sxs-lookup"><span data-stu-id="625d7-280">No action: No action</span></span></li>
<li><span data-ttu-id="625d7-281">Блок. Ресурс был заблокирован при выполнении</span><span class="sxs-lookup"><span data-stu-id="625d7-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="625d7-282">
</dt>
<dt>Состояние: &lt; Версия &gt; подписи</dt>
<dt>состояния: &lt; Версия &gt; </dt>двигателя версии
<dt> &lt; &gt; определения: версия двигателя antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-283">Идентификатор события: 1008</span><span class="sxs-lookup"><span data-stu-id="625d7-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-284">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-286">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-286">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-287">
<b>Платформа антивирусных программ попыталась выполнить действие, чтобы защитить систему от вредоносных программ или другого потенциально нежелательного программного обеспечения, но действие не удалось.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-288">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-289">Антивирус Microsoft Defender столкнулся с ошибкой при принятии мер по вредоносным программам или другому потенциально нежелательному программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="625d7-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="625d7-290">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-291">
<dt>Пользователь: &lt; lt &gt; \& домена; Имя &gt; </dt>
<dt>пользователя: &lt; &gt; ID имени</dt>
<dt> &lt; &gt; угрозы: Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-292">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-292">Low</span></span></li>
<li><span data-ttu-id="625d7-293">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-293">Moderate</span></span></li>
<li><span data-ttu-id="625d7-294">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-294">High</span></span></li>
<li><span data-ttu-id="625d7-295">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-295">Severe</span></span></li>
</ul><span data-ttu-id="625d7-296">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Действие &gt; пути файла:</dt> 
<dt> &lt; &gt; действие, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-297">Clean: ресурс был очищен</span><span class="sxs-lookup"><span data-stu-id="625d7-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="625d7-298">Карантин. Ресурс был карантин</span><span class="sxs-lookup"><span data-stu-id="625d7-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="625d7-299">Удаление. Ресурс был удален</span><span class="sxs-lookup"><span data-stu-id="625d7-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="625d7-300">Разрешить. Ресурс разрешено выполнять или существовать</span><span class="sxs-lookup"><span data-stu-id="625d7-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="625d7-301">Определено пользователем: обычно это действие, определенное пользователем, из этого списка действий, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="625d7-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="625d7-302">Нет действий: нет действий</span><span class="sxs-lookup"><span data-stu-id="625d7-302">No action: No action</span></span></li>
<li><span data-ttu-id="625d7-303">Блок. Ресурс был заблокирован при выполнении</span><span class="sxs-lookup"><span data-stu-id="625d7-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="625d7-304">
</dt>
<dt>Код ошибки: &lt; Код кода &gt; ошибки Результат, связанный со статусом угрозы. Стандартные значения HRESULT. </dt> 
<dt>Описание ошибки. &lt; &gt; Описание ошибки.</dt> 
<dt>Состояние: &lt; Версия &gt; подписи</dt>
<dt>состояния: &lt; Версия &gt; </dt>двигателя версии
<dt> &lt; &gt; определения: версия двигателя antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-305">Идентификатор события: 1009</span><span class="sxs-lookup"><span data-stu-id="625d7-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-306">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-308">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-308">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-309">
<b>Платформа антивирусных программ восстановила элемент из карантина. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-310">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-311">Антивирус Microsoft Defender восстановил элемент из карантина.</span><span class="sxs-lookup"><span data-stu-id="625d7-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="625d7-312">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-313">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-314">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-314">Low</span></span></li>
<li><span data-ttu-id="625d7-315">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-315">Moderate</span></span></li>
<li><span data-ttu-id="625d7-316">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-316">High</span></span></li>
<li><span data-ttu-id="625d7-317">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-317">Severe</span></span></li>
</ul><span data-ttu-id="625d7-318">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Путь &gt; к</dt>
<dt>файлу: &lt; домен &gt; \& lt; Версия &gt; </dt>
<dt>подписи пользователя: &lt; Версия &gt; </dt>двигателя версии
<dt> &lt; &gt; определения: версия двигателя antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-319">Идентификатор события: 1010</span><span class="sxs-lookup"><span data-stu-id="625d7-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-320">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-322">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-322">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-323">
<b>Платформа антивирусных программ не смогла восстановить элемент из карантина. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-324">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-325">Антивирус Microsoft Defender столкнулся с ошибкой при попытке восстановить элемент из карантина.</span><span class="sxs-lookup"><span data-stu-id="625d7-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="625d7-326">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-327">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-328">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-328">Low</span></span></li>
<li><span data-ttu-id="625d7-329">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-329">Moderate</span></span></li>
<li><span data-ttu-id="625d7-330">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-330">High</span></span></li>
<li><span data-ttu-id="625d7-331">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-331">Severe</span></span></li>
</ul><span data-ttu-id="625d7-332">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Путь &gt; к</dt>
<dt>файлу: &lt; домен &gt; \& lt; Код &gt; </dt>
<dt>ошибки пользователя. &lt; Код результатов &gt; кода ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT. </dt> 
<dt>Описание ошибки. &lt; &gt; Описание ошибки.</dt> 
<dt>Версия подписи: &lt; Версия &gt; двигателя</dt>
<dt>версии определения: &lt; версия &gt; движка antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-333">ID события: 1011</span><span class="sxs-lookup"><span data-stu-id="625d7-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-334">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-336">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-336">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-337">
<b>Платформа антивирусных программ удалила элемент из карантина. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-338">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-339">Антивирус Microsoft Defender удалил элемент из карантина.</span><span class="sxs-lookup"><span data-stu-id="625d7-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="625d7-340">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-341">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-342">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-342">Low</span></span></li>
<li><span data-ttu-id="625d7-343">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-343">Moderate</span></span></li>
<li><span data-ttu-id="625d7-344">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-344">High</span></span></li>
<li><span data-ttu-id="625d7-345">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-345">Severe</span></span></li>
</ul><span data-ttu-id="625d7-346">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Путь &gt; к</dt>
<dt>файлу: &lt; домен &gt; \& lt; Версия &gt; </dt>
<dt>подписи пользователя: &lt; Версия &gt; </dt>двигателя версии
<dt> &lt; &gt; определения: версия двигателя antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-347">Идентификатор события: 1012</span><span class="sxs-lookup"><span data-stu-id="625d7-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-348">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-350">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-350">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-351">
<b>Платформа антивирусных программ не может удалить элемент из карантина.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-352">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-353">Антивирус Microsoft Defender столкнулся с ошибкой при попытке удалить элемент из карантина.</span><span class="sxs-lookup"><span data-stu-id="625d7-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="625d7-354">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-355">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-356">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-356">Low</span></span></li>
<li><span data-ttu-id="625d7-357">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-357">Moderate</span></span></li>
<li><span data-ttu-id="625d7-358">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-358">High</span></span></li>
<li><span data-ttu-id="625d7-359">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-359">Severe</span></span></li>
</ul><span data-ttu-id="625d7-360">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Путь &gt; к</dt>
<dt>файлу: &lt; домен &gt; \& lt; Код &gt; </dt>
<dt>ошибки пользователя. &lt; Код результатов &gt; кода ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT. </dt> 
<dt>Описание ошибки. &lt; &gt; Описание ошибки.</dt> 
<dt>Версия подписи: &lt; Версия &gt; двигателя</dt>
<dt>версии определения: &lt; версия &gt; движка antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-361">ID события: 1013</span><span class="sxs-lookup"><span data-stu-id="625d7-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-362">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-364">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-364">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-365">
<b>Платформа антивирусных программ удалила историю вредоносных программ и другого потенциально нежелательного программного обеспечения.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-366">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-367">Антивирус Microsoft Defender удалил историю вредоносных программ и другого потенциально нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="625d7-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="625d7-368">
<dt>Время: время, когда произошло событие, например, когда история была стерта. Этот параметр не используется в событиях угроз, чтобы не было путаницы относительно времени восстановления или времени заражения. Для них мы называем их</dt> временем действия или временем обнаружения. 
<dt>Пользователь: &lt; lt &gt; \& домена; Пользователь &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-369">ID события: 1014</span><span class="sxs-lookup"><span data-stu-id="625d7-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-370">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-372">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="625d7-373">Платформа antimalware не может удалить историю вредоносных программ и других потенциально нежелательных программ.</span><span class="sxs-lookup"><span data-stu-id="625d7-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-374">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-375">Антивирус Microsoft Defender столкнулся с ошибкой при попытке удалить историю вредоносных программ и другого потенциально нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="625d7-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="625d7-376">
<dt>Время: время, когда произошло событие, например, когда история была стерта. Этот параметр не используется в событиях угроз, чтобы не было путаницы относительно времени восстановления или времени заражения. Для них мы называем их</dt> временем действия или временем обнаружения. 
<dt>Пользователь: &lt; lt &gt; \& домена; Код &gt; </dt>
<dt>ошибки пользователя. &lt; Код результатов &gt; кода ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT. </dt> 
<dt>Описание ошибки. &lt; &gt; Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-377">ID события: 1015</span><span class="sxs-lookup"><span data-stu-id="625d7-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-378">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-380">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-380">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-381">
<b>Платформа антивирусных программ обнаружила подозрительное поведение.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-382">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-383">Антивирус Microsoft Defender обнаружил подозрительное поведение.</span><span class="sxs-lookup"><span data-stu-id="625d7-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="625d7-384">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-385">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-386">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-386">Low</span></span></li>
<li><span data-ttu-id="625d7-387">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-387">Moderate</span></span></li>
<li><span data-ttu-id="625d7-388">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-388">High</span></span></li>
<li><span data-ttu-id="625d7-389">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-389">Severe</span></span></li>
</ul><span data-ttu-id="625d7-390">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Происхождение &gt; пути обнаружения</dt> 
<dt> файлов: &lt; происхождение &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-391">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="625d7-391">Unknown</span></span></li>
<li><span data-ttu-id="625d7-392">Локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="625d7-392">Local computer</span></span></li>
<li><span data-ttu-id="625d7-393">Сетевая папка</span><span class="sxs-lookup"><span data-stu-id="625d7-393">Network share</span></span></li>
<li><span data-ttu-id="625d7-394">Интернет</span><span class="sxs-lookup"><span data-stu-id="625d7-394">Internet</span></span></li>
<li><span data-ttu-id="625d7-395">Входящий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="625d7-396">Исходяющий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="625d7-397">
</dt>
<dt>Тип обнаружения: &lt; тип &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-398">Heuristics</span><span class="sxs-lookup"><span data-stu-id="625d7-398">Heuristics</span></span></li>
<li><span data-ttu-id="625d7-399">Generic</span><span class="sxs-lookup"><span data-stu-id="625d7-399">Generic</span></span></li>
<li><span data-ttu-id="625d7-400">Бетон</span><span class="sxs-lookup"><span data-stu-id="625d7-400">Concrete</span></span></li>
<li><span data-ttu-id="625d7-401">Динамическая подпись</span><span class="sxs-lookup"><span data-stu-id="625d7-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="625d7-402">
</dt>
<dt>Источник обнаружения: &lt; источник &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="625d7-403">Пользователь: инициированный пользователем</span><span class="sxs-lookup"><span data-stu-id="625d7-403">User: user initiated</span></span></li>
<li><span data-ttu-id="625d7-404">Система: инициированная система</span><span class="sxs-lookup"><span data-stu-id="625d7-404">System: system initiated</span></span></li>
<li><span data-ttu-id="625d7-405">В режиме реального времени: инициирован компонент в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="625d7-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="625d7-406">IOAV: инициированные загрузки IE и экспресс-вложения Outlook</span><span class="sxs-lookup"><span data-stu-id="625d7-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="625d7-407">NIS: система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="625d7-408">IEPROTECT: IE - IExtensionValidation; это защищает от вредоносных элементов управления веб-страницами</span><span class="sxs-lookup"><span data-stu-id="625d7-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="625d7-409">Ранний запуск антивирусных программ (ELAM).</span><span class="sxs-lookup"><span data-stu-id="625d7-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="625d7-410">Это включает вредоносные программы, обнаруженные в последовательности загрузки</span><span class="sxs-lookup"><span data-stu-id="625d7-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="625d7-411">Удаленная атестация</span><span class="sxs-lookup"><span data-stu-id="625d7-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="625d7-412">Интерфейс сканирования антивирусных программ (AMSI).</span><span class="sxs-lookup"><span data-stu-id="625d7-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="625d7-413">В основном используется для защиты скриптов (PS, VBS), хотя они могут вызываться и третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="625d7-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="625d7-414">Состояние </dt> 
<dt>UAC: &lt; пользователь &gt; </dt>
<dt>состояния: &lt; домен &gt; \& lt; Имя &gt; </dt>
<dt>процесса пользователя. &lt; Процесс &gt; в коде PID</dt>
<dt>Signature ID: строгость переописи.</dt> 
<dt>Версия подписи: &lt; Версия &gt; двигателя</dt>версии
<dt>определения: &lt; метка &gt; fidelity версии antimalware</dt>
<dt>Engine:</dt>Target File Name: Имя файла
<dt> &lt; &gt; файла.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-415">ID события: 1116</span><span class="sxs-lookup"><span data-stu-id="625d7-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-416">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-418">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-418">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-419">
<b>Платформа антивирусных программ обнаружила вредоносные программы или другое потенциально нежелательное программное обеспечение. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-420">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-421">Антивирус Microsoft Defender обнаружил вредоносные программы или другое потенциально нежелательное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="625d7-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="625d7-422">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-423">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-424">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-424">Low</span></span></li>
<li><span data-ttu-id="625d7-425">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-425">Moderate</span></span></li>
<li><span data-ttu-id="625d7-426">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-426">High</span></span></li>
<li><span data-ttu-id="625d7-427">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-427">Severe</span></span></li>
</ul><span data-ttu-id="625d7-428">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Происхождение &gt; пути обнаружения</dt> 
<dt> файлов: &lt; происхождение &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-429">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="625d7-429">Unknown</span></span></li>
<li><span data-ttu-id="625d7-430">Локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="625d7-430">Local computer</span></span></li>
<li><span data-ttu-id="625d7-431">Сетевая папка</span><span class="sxs-lookup"><span data-stu-id="625d7-431">Network share</span></span></li>
<li><span data-ttu-id="625d7-432">Интернет</span><span class="sxs-lookup"><span data-stu-id="625d7-432">Internet</span></span></li>
<li><span data-ttu-id="625d7-433">Входящий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="625d7-434">Исходяющий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="625d7-435">
</dt>
<dt>Тип обнаружения: &lt; тип &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-436">Heuristics</span><span class="sxs-lookup"><span data-stu-id="625d7-436">Heuristics</span></span></li>
<li><span data-ttu-id="625d7-437">Generic</span><span class="sxs-lookup"><span data-stu-id="625d7-437">Generic</span></span></li>
<li><span data-ttu-id="625d7-438">Бетон</span><span class="sxs-lookup"><span data-stu-id="625d7-438">Concrete</span></span></li>
<li><span data-ttu-id="625d7-439">Динамическая подпись</span><span class="sxs-lookup"><span data-stu-id="625d7-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="625d7-440">
</dt>
<dt>Источник обнаружения: &lt; источник &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="625d7-441">Пользователь: инициированный пользователем</span><span class="sxs-lookup"><span data-stu-id="625d7-441">User: user initiated</span></span></li>
<li><span data-ttu-id="625d7-442">Система: инициированная система</span><span class="sxs-lookup"><span data-stu-id="625d7-442">System: system initiated</span></span></li>
<li><span data-ttu-id="625d7-443">В режиме реального времени: инициирован компонент в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="625d7-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="625d7-444">IOAV: инициированные загрузки IE и экспресс-вложения Outlook</span><span class="sxs-lookup"><span data-stu-id="625d7-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="625d7-445">NIS: система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="625d7-446">IEPROTECT: IE - IExtensionValidation; это защищает от вредоносных элементов управления веб-страницами</span><span class="sxs-lookup"><span data-stu-id="625d7-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="625d7-447">Ранний запуск антивирусных программ (ELAM).</span><span class="sxs-lookup"><span data-stu-id="625d7-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="625d7-448">Это включает вредоносные программы, обнаруженные в последовательности загрузки</span><span class="sxs-lookup"><span data-stu-id="625d7-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="625d7-449">Удаленная атестация</span><span class="sxs-lookup"><span data-stu-id="625d7-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="625d7-450">Интерфейс сканирования антивирусных программ (AMSI).</span><span class="sxs-lookup"><span data-stu-id="625d7-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="625d7-451">В основном используется для защиты скриптов (PS, VBS), хотя они могут вызываться и третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="625d7-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="625d7-452">Пользователь </dt> 
<dt>UAC: &lt; &gt; \& lt домена; Имя &gt; </dt>
<dt>процесса пользователя: &lt; процесс &gt; в версии подписи PID:</dt>
<dt> &lt; Версия &gt; </dt>двигателя версии
<dt>определения: &lt; версия движка antimalware &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-453">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-454">Не требуется выполнять никаких действий.</span><span class="sxs-lookup"><span data-stu-id="625d7-454">No action is required.</span></span> <span data-ttu-id="625d7-455">Антивирус Microsoft Defender может приостанавливать и принимать обычные меры по борьбе с этой угрозой.</span><span class="sxs-lookup"><span data-stu-id="625d7-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="625d7-456">Если вы хотите удалить угрозу вручную, в интерфейсе антивируса Microsoft Defender нажмите кнопку <b>Чистый компьютер</b>.</span><span class="sxs-lookup"><span data-stu-id="625d7-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-457">ID события: 1117</span><span class="sxs-lookup"><span data-stu-id="625d7-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-458">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-460">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-460">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-461">
<b>Платформа антивирусных программ выполнила действие, чтобы защитить систему от вредоносных программ или другого потенциально нежелательного программного обеспечения. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-462">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-463">Антивирус Microsoft Defender принял меры для защиты этой машины от вредоносных программ или другого потенциально нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="625d7-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="625d7-464">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-465">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-466">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-466">Low</span></span></li>
<li><span data-ttu-id="625d7-467">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-467">Moderate</span></span></li>
<li><span data-ttu-id="625d7-468">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-468">High</span></span></li>
<li><span data-ttu-id="625d7-469">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-469">Severe</span></span></li>
</ul><span data-ttu-id="625d7-470">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Происхождение &gt; пути обнаружения</dt> 
<dt> файлов: &lt; происхождение &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-471">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="625d7-471">Unknown</span></span></li>
<li><span data-ttu-id="625d7-472">Локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="625d7-472">Local computer</span></span></li>
<li><span data-ttu-id="625d7-473">Сетевая папка</span><span class="sxs-lookup"><span data-stu-id="625d7-473">Network share</span></span></li>
<li><span data-ttu-id="625d7-474">Интернет</span><span class="sxs-lookup"><span data-stu-id="625d7-474">Internet</span></span></li>
<li><span data-ttu-id="625d7-475">Входящий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="625d7-476">Исходяющий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="625d7-477">
</dt>
<dt>Тип обнаружения: &lt; тип &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-478">Heuristics</span><span class="sxs-lookup"><span data-stu-id="625d7-478">Heuristics</span></span></li>
<li><span data-ttu-id="625d7-479">Generic</span><span class="sxs-lookup"><span data-stu-id="625d7-479">Generic</span></span></li>
<li><span data-ttu-id="625d7-480">Бетон</span><span class="sxs-lookup"><span data-stu-id="625d7-480">Concrete</span></span></li>
<li><span data-ttu-id="625d7-481">Динамическая подпись</span><span class="sxs-lookup"><span data-stu-id="625d7-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="625d7-482">
</dt>
<dt>Источник обнаружения: &lt; источник &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="625d7-483">Пользователь: инициированный пользователем</span><span class="sxs-lookup"><span data-stu-id="625d7-483">User: user initiated</span></span></li>
<li><span data-ttu-id="625d7-484">Система: инициированная система</span><span class="sxs-lookup"><span data-stu-id="625d7-484">System: system initiated</span></span></li>
<li><span data-ttu-id="625d7-485">В режиме реального времени: инициирован компонент в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="625d7-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="625d7-486">IOAV: инициированные загрузки IE и экспресс-вложения Outlook</span><span class="sxs-lookup"><span data-stu-id="625d7-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="625d7-487">NIS: система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="625d7-488">IEPROTECT: IE - IExtensionValidation; это защищает от вредоносных элементов управления веб-страницами</span><span class="sxs-lookup"><span data-stu-id="625d7-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="625d7-489">Ранний запуск антивирусных программ (ELAM).</span><span class="sxs-lookup"><span data-stu-id="625d7-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="625d7-490">Это включает вредоносные программы, обнаруженные в последовательности загрузки</span><span class="sxs-lookup"><span data-stu-id="625d7-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="625d7-491">Удаленная атестация</span><span class="sxs-lookup"><span data-stu-id="625d7-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="625d7-492">Интерфейс сканирования антивирусных программ (AMSI).</span><span class="sxs-lookup"><span data-stu-id="625d7-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="625d7-493">В основном используется для защиты скриптов (PS, VBS), хотя они могут вызываться и третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="625d7-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="625d7-494">Пользователь </dt> 
<dt>UAC: &lt; &gt; \& lt домена; Имя &gt; </dt>
<dt>процесса пользователя: &lt; процесс &gt; в действии PID:</dt> 
<dt> &lt; &gt; Действие, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-495">Clean: ресурс был очищен</span><span class="sxs-lookup"><span data-stu-id="625d7-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="625d7-496">Карантин. Ресурс был карантин</span><span class="sxs-lookup"><span data-stu-id="625d7-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="625d7-497">Удаление. Ресурс был удален</span><span class="sxs-lookup"><span data-stu-id="625d7-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="625d7-498">Разрешить. Ресурс разрешено выполнять или существовать</span><span class="sxs-lookup"><span data-stu-id="625d7-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="625d7-499">Определено пользователем: обычно это действие, определенное пользователем, из этого списка действий, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="625d7-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="625d7-500">Нет действий: нет действий</span><span class="sxs-lookup"><span data-stu-id="625d7-500">No action: No action</span></span></li>
<li><span data-ttu-id="625d7-501">Блок. Ресурс был заблокирован при выполнении</span><span class="sxs-lookup"><span data-stu-id="625d7-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="625d7-502">
</dt>
<dt>Состояние действия: &lt; Описание дополнительных &gt; действий</dt>
<dt>Код ошибки: &lt; код результатов кода &gt; ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt> 
<dt>Версия подписи: &lt; &gt;</dt>Версия двигателя версии
<dt>определения. &lt; &gt; </dt> Примечание версии антивирусного двигателя: Всякий раз, когда антивирус Microsoft Defender, Microsoft Security Essentials, средство удаления вредоносного программного обеспечения или защита конечных точек System Center обнаруживает вредоносное ПО, оно восстановит следующие параметры системы и службы, которые могли изменить вредоносные программы:</span><span class="sxs-lookup"><span data-stu-id="625d7-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="625d7-503">Параметр Internet Explorer или Microsoft Edge по умолчанию</span><span class="sxs-lookup"><span data-stu-id="625d7-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="625d7-504">Параметры управления доступом пользователей</span><span class="sxs-lookup"><span data-stu-id="625d7-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="625d7-505">Параметры Chrome</span><span class="sxs-lookup"><span data-stu-id="625d7-505">Chrome settings</span></span></li>
<li><span data-ttu-id="625d7-506">Данные управления загрузкой</span><span class="sxs-lookup"><span data-stu-id="625d7-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="625d7-507">Параметры реестра Regedit и Task Manager</span><span class="sxs-lookup"><span data-stu-id="625d7-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="625d7-508">Служба вызовов windows, Background Intelligent Transfer Service и удаленной процедуры</span><span class="sxs-lookup"><span data-stu-id="625d7-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="625d7-509">Файлы операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="625d7-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="625d7-510">Вышеперечисленный контекст применим к следующим версиям клиента и сервера:</span><span class="sxs-lookup"><span data-stu-id="625d7-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="625d7-511">Операционная система</span><span class="sxs-lookup"><span data-stu-id="625d7-511">Operating system</span></span></th>
<th><span data-ttu-id="625d7-512">Версия операционной системы</span><span class="sxs-lookup"><span data-stu-id="625d7-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-513">Клиентская операционная система</span><span class="sxs-lookup"><span data-stu-id="625d7-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="625d7-514">Windows Vista (Пакет обновления 1 или Пакет обновления 2), Windows 7 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="625d7-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-515">Серверная операционная система</span><span class="sxs-lookup"><span data-stu-id="625d7-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="625d7-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 и Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="625d7-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-517">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-518">Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="625d7-518">No action is necessary.</span></span> <span data-ttu-id="625d7-519">Антивирус Microsoft Defender удален или карантин для угрозы.</span><span class="sxs-lookup"><span data-stu-id="625d7-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-520">ID события: 1118</span><span class="sxs-lookup"><span data-stu-id="625d7-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-521">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-523">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-523">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-524">
<b>Платформа антивирусных программ попыталась выполнить действие, чтобы защитить систему от вредоносных программ или другого потенциально нежелательного программного обеспечения, но действие не удалось. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-525">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-526">Антивирус Microsoft Defender столкнулся с некритичными ошибками при принятии мер по вредоносным программам или другому потенциально нежелательному программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="625d7-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="625d7-527">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-528">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-529">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-529">Low</span></span></li>
<li><span data-ttu-id="625d7-530">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-530">Moderate</span></span></li>
<li><span data-ttu-id="625d7-531">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-531">High</span></span></li>
<li><span data-ttu-id="625d7-532">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-532">Severe</span></span></li>
</ul><span data-ttu-id="625d7-533">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Происхождение &gt; пути обнаружения</dt> 
<dt> файлов: &lt; происхождение &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-534">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="625d7-534">Unknown</span></span></li>
<li><span data-ttu-id="625d7-535">Локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="625d7-535">Local computer</span></span></li>
<li><span data-ttu-id="625d7-536">Сетевая папка</span><span class="sxs-lookup"><span data-stu-id="625d7-536">Network share</span></span></li>
<li><span data-ttu-id="625d7-537">Интернет</span><span class="sxs-lookup"><span data-stu-id="625d7-537">Internet</span></span></li>
<li><span data-ttu-id="625d7-538">Входящий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="625d7-539">Исходяющий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="625d7-540">
</dt>
<dt>Тип обнаружения: &lt; тип &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-541">Heuristics</span><span class="sxs-lookup"><span data-stu-id="625d7-541">Heuristics</span></span></li>
<li><span data-ttu-id="625d7-542">Generic</span><span class="sxs-lookup"><span data-stu-id="625d7-542">Generic</span></span></li>
<li><span data-ttu-id="625d7-543">Бетон</span><span class="sxs-lookup"><span data-stu-id="625d7-543">Concrete</span></span></li>
<li><span data-ttu-id="625d7-544">Динамическая подпись</span><span class="sxs-lookup"><span data-stu-id="625d7-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="625d7-545">
</dt>
<dt>Источник обнаружения: &lt; источник &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="625d7-546">Пользователь: инициированный пользователем</span><span class="sxs-lookup"><span data-stu-id="625d7-546">User: user initiated</span></span></li>
<li><span data-ttu-id="625d7-547">Система: инициированная система</span><span class="sxs-lookup"><span data-stu-id="625d7-547">System: system initiated</span></span></li>
<li><span data-ttu-id="625d7-548">В режиме реального времени: инициирован компонент в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="625d7-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="625d7-549">IOAV: инициированные загрузки IE и экспресс-вложения Outlook</span><span class="sxs-lookup"><span data-stu-id="625d7-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="625d7-550">NIS: система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="625d7-551">IEPROTECT: IE - IExtensionValidation; это защищает от вредоносных элементов управления веб-страницами</span><span class="sxs-lookup"><span data-stu-id="625d7-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="625d7-552">Ранний запуск антивирусных программ (ELAM).</span><span class="sxs-lookup"><span data-stu-id="625d7-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="625d7-553">Это включает вредоносные программы, обнаруженные в последовательности загрузки</span><span class="sxs-lookup"><span data-stu-id="625d7-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="625d7-554">Удаленная атестация</span><span class="sxs-lookup"><span data-stu-id="625d7-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="625d7-555">Интерфейс сканирования антивирусных программ (AMSI).</span><span class="sxs-lookup"><span data-stu-id="625d7-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="625d7-556">В основном используется для защиты скриптов (PS, VBS), хотя они могут вызываться и третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="625d7-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="625d7-557">Пользователь </dt> 
<dt>UAC: &lt; &gt; \& lt домена; Имя &gt; </dt>
<dt>процесса пользователя: &lt; процесс &gt; в действии PID:</dt> 
<dt> &lt; &gt; Действие, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-558">Clean: ресурс был очищен</span><span class="sxs-lookup"><span data-stu-id="625d7-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="625d7-559">Карантин. Ресурс был карантин</span><span class="sxs-lookup"><span data-stu-id="625d7-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="625d7-560">Удаление. Ресурс был удален</span><span class="sxs-lookup"><span data-stu-id="625d7-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="625d7-561">Разрешить. Ресурс разрешено выполнять или существовать</span><span class="sxs-lookup"><span data-stu-id="625d7-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="625d7-562">Определено пользователем: обычно это действие, определенное пользователем, из этого списка действий, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="625d7-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="625d7-563">Нет действий: нет действий</span><span class="sxs-lookup"><span data-stu-id="625d7-563">No action: No action</span></span></li>
<li><span data-ttu-id="625d7-564">Блок. Ресурс был заблокирован при выполнении</span><span class="sxs-lookup"><span data-stu-id="625d7-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="625d7-565">
</dt>
<dt>Состояние действия: &lt; Описание дополнительных &gt; действий</dt>
<dt>Код ошибки: &lt; код результатов кода &gt; ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt> 
<dt>Версия подписи: &lt; Версия &gt; двигателя</dt>
<dt>версии определения: &lt; версия &gt; движка antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-566">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-567">Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="625d7-567">No action is necessary.</span></span> <span data-ttu-id="625d7-568">Антивирус Microsoft Defender не смог выполнить задачу, связанную с исправлением вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="625d7-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="625d7-569">Это не критический сбой.</span><span class="sxs-lookup"><span data-stu-id="625d7-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-570">ID события: 1119</span><span class="sxs-lookup"><span data-stu-id="625d7-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-571">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-573">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-573">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-574">
<b>Платформа антивирусных программ столкнулась с критической ошибкой при попытке действовать в отношении вредоносных программ или другого потенциально нежелательного программного обеспечения. Дополнительные сведения в сообщении события.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-575">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-576">Антивирус Microsoft Defender столкнулся с критической ошибкой при принятии мер по вредоносным программам или другому потенциально нежелательному программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="625d7-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="625d7-577">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="625d7-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="625d7-578">
<dt>Имя: &lt; ID &gt; имени</dt>
<dt>угрозы: &lt; &gt; Серьезность:</dt> 
<dt> &lt; &gt; серьезность, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-579">Низкие</span><span class="sxs-lookup"><span data-stu-id="625d7-579">Low</span></span></li>
<li><span data-ttu-id="625d7-580">Умеренно</span><span class="sxs-lookup"><span data-stu-id="625d7-580">Moderate</span></span></li>
<li><span data-ttu-id="625d7-581">Высокие</span><span class="sxs-lookup"><span data-stu-id="625d7-581">High</span></span></li>
<li><span data-ttu-id="625d7-582">Критический</span><span class="sxs-lookup"><span data-stu-id="625d7-582">Severe</span></span></li>
</ul><span data-ttu-id="625d7-583">
</dt>
<dt>Категория: &lt; Описание &gt; категории, например, любой тип угрозы или вредоносных программ.</dt> 
<dt>Путь: &lt; Происхождение &gt; пути обнаружения</dt> 
<dt> файлов: &lt; происхождение &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-584">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="625d7-584">Unknown</span></span></li>
<li><span data-ttu-id="625d7-585">Локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="625d7-585">Local computer</span></span></li>
<li><span data-ttu-id="625d7-586">Сетевая папка</span><span class="sxs-lookup"><span data-stu-id="625d7-586">Network share</span></span></li>
<li><span data-ttu-id="625d7-587">Интернет</span><span class="sxs-lookup"><span data-stu-id="625d7-587">Internet</span></span></li>
<li><span data-ttu-id="625d7-588">Входящий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="625d7-589">Исходяющий трафик</span><span class="sxs-lookup"><span data-stu-id="625d7-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="625d7-590">
</dt>
<dt>Тип обнаружения: &lt; тип &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-591">Heuristics</span><span class="sxs-lookup"><span data-stu-id="625d7-591">Heuristics</span></span></li>
<li><span data-ttu-id="625d7-592">Generic</span><span class="sxs-lookup"><span data-stu-id="625d7-592">Generic</span></span></li>
<li><span data-ttu-id="625d7-593">Бетон</span><span class="sxs-lookup"><span data-stu-id="625d7-593">Concrete</span></span></li>
<li><span data-ttu-id="625d7-594">Динамическая подпись</span><span class="sxs-lookup"><span data-stu-id="625d7-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="625d7-595">
</dt>
<dt>Источник обнаружения: &lt; источник &gt; обнаружения, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="625d7-596">Пользователь: инициированный пользователем</span><span class="sxs-lookup"><span data-stu-id="625d7-596">User: user initiated</span></span></li>
<li><span data-ttu-id="625d7-597">Система: инициированная система</span><span class="sxs-lookup"><span data-stu-id="625d7-597">System: system initiated</span></span></li>
<li><span data-ttu-id="625d7-598">В режиме реального времени: инициирован компонент в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="625d7-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="625d7-599">IOAV: инициированные загрузки IE и экспресс-вложения Outlook</span><span class="sxs-lookup"><span data-stu-id="625d7-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="625d7-600">NIS: система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="625d7-601">IEPROTECT: IE - IExtensionValidation; это защищает от вредоносных элементов управления веб-страницами</span><span class="sxs-lookup"><span data-stu-id="625d7-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="625d7-602">Ранний запуск антивирусных программ (ELAM).</span><span class="sxs-lookup"><span data-stu-id="625d7-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="625d7-603">Это включает вредоносные программы, обнаруженные в последовательности загрузки</span><span class="sxs-lookup"><span data-stu-id="625d7-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="625d7-604">Удаленная атестация</span><span class="sxs-lookup"><span data-stu-id="625d7-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="625d7-605">Интерфейс сканирования антивирусных программ (AMSI).</span><span class="sxs-lookup"><span data-stu-id="625d7-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="625d7-606">В основном используется для защиты скриптов (PS, VBS), хотя они могут вызываться и третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="625d7-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="625d7-607">Пользователь </dt> 
<dt>UAC: &lt; &gt; \& lt домена; Имя &gt; </dt>
<dt>процесса пользователя: &lt; процесс &gt; в действии PID:</dt> 
<dt> &lt; &gt; Действие, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="625d7-608">Clean: ресурс был очищен</span><span class="sxs-lookup"><span data-stu-id="625d7-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="625d7-609">Карантин. Ресурс был карантин</span><span class="sxs-lookup"><span data-stu-id="625d7-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="625d7-610">Удаление. Ресурс был удален</span><span class="sxs-lookup"><span data-stu-id="625d7-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="625d7-611">Разрешить. Ресурс разрешено выполнять или существовать</span><span class="sxs-lookup"><span data-stu-id="625d7-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="625d7-612">Определено пользователем: обычно это действие, определенное пользователем, из этого списка действий, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="625d7-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="625d7-613">Нет действий: нет действий</span><span class="sxs-lookup"><span data-stu-id="625d7-613">No action: No action</span></span></li>
<li><span data-ttu-id="625d7-614">Блок. Ресурс был заблокирован при выполнении</span><span class="sxs-lookup"><span data-stu-id="625d7-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="625d7-615">
</dt>
<dt>Состояние действия: &lt; Описание дополнительных &gt; действий</dt>
<dt>Код ошибки: &lt; код результатов кода &gt; ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt> 
<dt>Версия подписи: &lt; Версия &gt; двигателя</dt>
<dt>версии определения: &lt; версия &gt; движка antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-616">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-617">Антивирусный клиент Microsoft Defender столкнулся с этой ошибкой из-за критических проблем.</span><span class="sxs-lookup"><span data-stu-id="625d7-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="625d7-618">Конечная точка может не быть защищена.</span><span class="sxs-lookup"><span data-stu-id="625d7-618">The endpoint might not be protected.</span></span> <span data-ttu-id="625d7-619">Просмотрите описание ошибки, а затем <b>выполните</b> соответствующие действия пользователя ниже.</span><span class="sxs-lookup"><span data-stu-id="625d7-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="625d7-620">Action</span><span class="sxs-lookup"><span data-stu-id="625d7-620">Action</span></span></th>
<th><span data-ttu-id="625d7-621">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="625d7-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="625d7-622">
<b>Удаление</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="625d7-623">Обнови определения и убедитесь, что удаление было успешным.</span><span class="sxs-lookup"><span data-stu-id="625d7-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="625d7-624">
<b>Clean</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="625d7-625">Обнови определения и убедитесь, что исправление было успешным.</span><span class="sxs-lookup"><span data-stu-id="625d7-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="625d7-626">
<b>Карантин</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="625d7-627">Обнови определения и убедитесь, что у пользователя есть разрешение на доступ к необходимым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="625d7-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="625d7-628">
<b>Разрешить</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="625d7-629">Убедитесь, что у пользователя есть разрешение на доступ к необходимым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="625d7-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="625d7-630">Если это событие сохраняется:</span><span class="sxs-lookup"><span data-stu-id="625d7-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="625d7-631">Снова запустите сканирование.</span><span class="sxs-lookup"><span data-stu-id="625d7-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="625d7-632">Если это не удается таким же образом, перейдите на сайт <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support,</a>введите номер ошибки в поле Поиска, чтобы найти код ошибки.</span><span class="sxs-lookup"><span data-stu-id="625d7-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="625d7-633">Обратитесь в <a href="https://go.microsoft.com/fwlink/?LinkId=215491">службу поддержки Майкрософт</a>.</span><span class="sxs-lookup"><span data-stu-id="625d7-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-634">ID события: 1120</span><span class="sxs-lookup"><span data-stu-id="625d7-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-635">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-637">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-637">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-638">
<b>Антивирус Microsoft Defender вычли хеши для ресурса угрозы.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-639">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-640">Антивирусный клиент Microsoft Defender работает в нормальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="625d7-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="625d7-641">
<dt>Текущая версия платформы: &lt; Текущий &gt; путь</dt>
<dt>ресурсов ресурсов версии &lt; &gt; платформы:</dt>
<dt>hashes пути: &lt; hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="625d7-642"><b>Примечание. Это событие будет в журнале, только если задана следующая политика: <b>ThreatFileHashLogging без подписи.</b></span><span class="sxs-lookup"><span data-stu-id="625d7-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-643">ID события: 1150</span><span class="sxs-lookup"><span data-stu-id="625d7-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-644">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-646">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-646">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-647">
<b>Если ваша платформа антивирусных программ сообщает о состоянии платформы мониторинга, это событие указывает на то, что платформа антивирусных программ запущена и находится в нормальном состоянии. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-648">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-649">Антивирусный клиент Microsoft Defender работает в нормальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="625d7-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="625d7-650">
<dt>Версия платформы: &lt; Текущая &gt; версия версии</dt>
<dt>подписи платформы: &lt; Версия &gt; </dt>двигателя версии
<dt> &lt; &gt; определения: версия двигателя antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-651">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-652">Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="625d7-652">No action is necessary.</span></span> <span data-ttu-id="625d7-653">Антивирусный клиент Microsoft Defender находится в нормальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="625d7-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="625d7-654">Об этом событии сообщается почасовая информация.</span><span class="sxs-lookup"><span data-stu-id="625d7-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="625d7-655">ID события: 1151</span><span class="sxs-lookup"><span data-stu-id="625d7-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-656">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-658">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-658">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-659">
<b>Отчет о состоянии здоровья клиента endpoint Protection (время в UTC) </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-660">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-661">Отчет о состоянии антивирусного клиента.</span><span class="sxs-lookup"><span data-stu-id="625d7-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="625d7-662">
<dt>Версия платформы: &lt; &gt;</dt>Текущая версия версии версии двигателя
<dt>платформы: &lt; &gt; </dt>Версия двигателя антивирусной версии антивирусной версии проверки сетевого реального
<dt>времени: &lt; &gt; </dt>версия подписи антивирусной версии антивирусной подписи подписи антивирусной подписи версии антивирусной подписи.
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>Версия подписи подписи антивирусной подписи Network
<dt> &lt; &gt; Realtime</dt>Inspection Версия
<dt>RTP: состояние защиты реального времени &lt; &gt; (включено</dt>или отключено) состояние
<dt>OA: Состояние IOAV (Включено или отключено) &lt; &gt; </dt>Состояние BM для скачивания и экспресс-вложений Outlook
<dt> &lt; &gt; (включено</dt>или отключено): состояние мониторинга поведения (включено или
<dt> &lt; &gt; отключено)</dt>Возраст подписи антивируса: возраст подписи антивирусных подписей
<dt>(в &lt; &gt; днях)</dt>Возраст подписи антивируса: возраст подписи
<dt> &lt; antispyware &gt; (в днях)</dt>Последний быстрый возраст сканирования: Последний быстрый возраст сканирования
<dt>(в &lt; &gt; днях)</dt>Последний полный возраст сканирования: Последний полный возраст
<dt> &lt; &gt; проверки (в днях)</dt>Время создания подписи антивируса:
<dt>? &lt; Время создания антивирусной &gt; подписи</dt>Время создания подписи
<dt>Antispyware: ? &lt; Время создания подписи &gt; antispyware</dt>
<dt>Последнее время быстрого сканирования: ? &lt; Последнее быстрое &gt; время начала сканирования</dt>
<dt>Последнее быстрое время окончания сканирования: ? &lt; &gt;</dt>Последний быстрый конец сканирования Последний источник быстрого сканирования. Последний источник быстрого сканирования (0 = сканирование не&#39;, 1 = инициировано пользователем, 2 = инициирована
<dt> &lt; &gt; система)</dt>Последнее полное время начала
<dt>сканирования: ? &lt; Последнее полное время &gt; начала сканирования</dt>Последнее полное время
<dt>окончания сканирования: ? &lt; &gt;</dt>Последний полный источник полного сканирования. Последний источник полного сканирования (0 = проверка не&#39;, 1 = инициированный пользователем, 2 = инициированный
<dt> &lt; &gt; системой)</dt>Состояние продукта: для устранения внутренних неполадок 
<dt></span><span class="sxs-lookup"><span data-stu-id="625d7-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="625d7-663">
<th colspan="2">ID события: 2000</span><span class="sxs-lookup"><span data-stu-id="625d7-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-664">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-666">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-666">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-667">
<b>Определения противомалярийных программ успешно обновляются. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-668">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-669">Обновлена версия антивирусной подписи.</span><span class="sxs-lookup"><span data-stu-id="625d7-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="625d7-670">
<dt>Текущая версия подписи: &lt; Текущая &gt; версия подписи</dt>
<dt>Предыдущая версия подписи: &lt; &gt; Предыдущий тип</dt>подписи: Тип подписи, 
<dt> &lt; &gt; например:</span><span class="sxs-lookup"><span data-stu-id="625d7-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="625d7-671">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-671">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-672">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-673">Antimalware</span></span></li>
<li><span data-ttu-id="625d7-674">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-675">
</dt>
<dt>Тип обновления: &lt; Тип обновления &gt; , полный или дельта.</dt> 
<dt>Пользователь: &lt; lt &gt; \& домена; &gt;Текущая</dt>
<dt>версия двигателя пользователя: &lt; текущая версия &gt; двигателя</dt>
<dt>Предыдущая версия двигателя: &lt; предыдущая версия двигателя &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-676">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-677">Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="625d7-677">No action is necessary.</span></span> <span data-ttu-id="625d7-678">Антивирусный клиент Microsoft Defender находится в нормальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="625d7-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="625d7-679">Это событие сообщается при успешном обновлении подписей.</span><span class="sxs-lookup"><span data-stu-id="625d7-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-680">ID события: 2001</span><span class="sxs-lookup"><span data-stu-id="625d7-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-681">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-683">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-683">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-684">
<b>Обновление сведении безопасности не удалось. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-685">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-686">Антивирус Microsoft Defender столкнулся с ошибкой при попытке обновить подписи.</span><span class="sxs-lookup"><span data-stu-id="625d7-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="625d7-687">
<dt>Новая версия разведки безопасности: &lt; Новая версия &gt; номер</dt>
<dt>предыдущей версии аналитики безопасности: &lt; Источник &gt; </dt>обновления предыдущей 
<dt> версии: Источник &lt; &gt; обновления, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-688">Папка обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="625d7-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="625d7-689">Сервер обновления внутренней разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="625d7-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="625d7-690">Сервер обновления Майкрософт</span><span class="sxs-lookup"><span data-stu-id="625d7-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="625d7-691">Файловый ресурс</span><span class="sxs-lookup"><span data-stu-id="625d7-691">File share</span></span></li>
<li><span data-ttu-id="625d7-692">Центр Майкрософт по защите от вредоносных программ (MMPC)</span><span class="sxs-lookup"><span data-stu-id="625d7-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="625d7-693">
</dt>
<dt>Этап обновления: &lt; этап &gt; обновления, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-694">Поиск</span><span class="sxs-lookup"><span data-stu-id="625d7-694">Search</span></span></li>
<li><span data-ttu-id="625d7-695">Скачать</span><span class="sxs-lookup"><span data-stu-id="625d7-695">Download</span></span></li>
<li><span data-ttu-id="625d7-696">Установка</span><span class="sxs-lookup"><span data-stu-id="625d7-696">Install</span></span></li>
</ul><span data-ttu-id="625d7-697">
</dt>Путь к источнику: имя файла для Универсальной конвенции имен (UNC), имя сервера 
<dt>для cлужбы Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Тип подписи: &lt; тип &gt; подписи, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="625d7-698">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-698">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-699">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-700">Antimalware</span></span></li>
<li><span data-ttu-id="625d7-701">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-702">
</dt>
<dt>Тип обновления: &lt; Тип обновления &gt; , полный или дельта.</dt> 
<dt>Пользователь: &lt; lt &gt; \& домена; Текущая &gt; </dt>версия двигателя
<dt>пользователя: &lt; &gt; текущая</dt>версия двигателя Предыдущая версия
<dt>двигателя: &lt; Код &gt; </dt>ошибки предыдущей версии двигателя: код кода ошибки Результат, связанный
<dt>с &lt; &gt; состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-703">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-704">Эта ошибка возникает, когда возникают проблемы с обновлением определений.</span><span class="sxs-lookup"><span data-stu-id="625d7-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="625d7-705">Устранение неполадок в этом событии:</span><span class="sxs-lookup"><span data-stu-id="625d7-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="625d7-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Обновление определений</a> и принудительное обновление rescan непосредственно на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="625d7-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="625d7-707">Дополнительные сведения об этой ошибке просмотрите записи в файле %Windir%\WindowsUpdate.log.</span><span class="sxs-lookup"><span data-stu-id="625d7-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="625d7-708">Обратитесь в <a href="https://go.microsoft.com/fwlink/?LinkId=215491">службу поддержки Майкрософт</a>.</span><span class="sxs-lookup"><span data-stu-id="625d7-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-709">ID события: 2002</span><span class="sxs-lookup"><span data-stu-id="625d7-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-710">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-712">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-712">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-713">
<b>Движок antimalware обновлен успешно. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-714">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-715">Обновлена версия антивирусного двигателя Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="625d7-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="625d7-716">
<dt>Текущая версия двигателя: &lt; Текущая &gt; версия двигателя</dt>Предыдущая версия
<dt>двигателя: &lt; &gt; Предыдущий тип</dt>двигателя версии двигателя: тип двигателя, либо движок противомалярийных программ, либо двигатель системы проверки
<dt> &lt; &gt; сети.</dt> 
<dt>Пользователь: &lt; lt &gt; \& домена; Пользователь &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-717">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-718">Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="625d7-718">No action is necessary.</span></span> <span data-ttu-id="625d7-719">Антивирусный клиент Microsoft Defender находится в нормальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="625d7-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="625d7-720">Об этом событии сообщается при успешном обновлении антивирусного двигателя.</span><span class="sxs-lookup"><span data-stu-id="625d7-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-721">ID события: 2003</span><span class="sxs-lookup"><span data-stu-id="625d7-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-722">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-724">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-724">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-725">
<b>Обновление антивирусного двигателя не удалось. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-726">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-727">Антивирус Microsoft Defender столкнулся с ошибкой при попытке обновить двигатель.</span><span class="sxs-lookup"><span data-stu-id="625d7-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="625d7-728">
<dt>Новая версия двигателя:</dt>предыдущая версия
<dt> &lt; &gt; двигателя:</dt>тип двигателя предыдущей версии двигателя: тип двигателя, либо двигатель противомалярийного программного обеспечения, либо двигатель системы проверки
<dt> &lt; &gt; сети.</dt> 
<dt>Пользователь: &lt; lt &gt; \& домена; Код &gt; </dt>
<dt>ошибки пользователя. &lt; Код результатов &gt; кода ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-729">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-730">Обновление антивирусного клиента Microsoft Defender не удалось.</span><span class="sxs-lookup"><span data-stu-id="625d7-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="625d7-731">Это событие происходит, когда клиент не обновляется.</span><span class="sxs-lookup"><span data-stu-id="625d7-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="625d7-732">Это событие обычно происходит из-за прерывания подключения к сети во время обновления.</span><span class="sxs-lookup"><span data-stu-id="625d7-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="625d7-733">Устранение неполадок в этом событии:</span><span class="sxs-lookup"><span data-stu-id="625d7-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="625d7-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Обновление определений</a> и принудительное обновление rescan непосредственно на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="625d7-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="625d7-735">Обратитесь в <a href="https://go.microsoft.com/fwlink/?LinkId=215491">службу поддержки Майкрософт</a>.</span><span class="sxs-lookup"><span data-stu-id="625d7-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-736">ID события: 2004</span><span class="sxs-lookup"><span data-stu-id="625d7-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-737">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-739">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-739">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-740">
<b>Возникла проблема с загрузкой определений противомалярийных программ. Движок antimalware попытается загрузить последний известный хороший набор определений.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-741">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-742">Антивирус Microsoft Defender столкнулся с ошибкой при попытке загрузить подписи и будет пытаться вернуться к известному набору подписей.</span><span class="sxs-lookup"><span data-stu-id="625d7-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="625d7-743">
<dt>Сигнатуры:</dt>Код ошибки: код результатов
<dt>кода &lt; &gt; ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt> 
<dt>Версия подписи: &lt; Версия &gt; двигателя</dt>
<dt>версии определения: &lt; версия &gt; двигателя antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-744">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-745">Антивирусный клиент Microsoft Defender попытался скачать и установить последний файл определений и не удалось.</span><span class="sxs-lookup"><span data-stu-id="625d7-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="625d7-746">Эта ошибка может возникнуть, когда клиент сталкивается с ошибкой при попытке загрузить определения, или если файл поврежден.</span><span class="sxs-lookup"><span data-stu-id="625d7-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="625d7-747">Антивирус Microsoft Defender попытается вернуться к известному набору определений.</span><span class="sxs-lookup"><span data-stu-id="625d7-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="625d7-748">Устранение неполадок в этом событии:</span><span class="sxs-lookup"><span data-stu-id="625d7-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="625d7-749">Перезапустите компьютер и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="625d7-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="625d7-750">Скачайте последние определения с сайта <a href="https://aka.ms/wdsi">Microsoft Security Intelligence.</a></span><span class="sxs-lookup"><span data-stu-id="625d7-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="625d7-751">Примечание. Размер файла определений, загруженного с сайта, может превышать 60 МБ и не должен использоваться в качестве долгосрочного решения для обновления определений.</span><span class="sxs-lookup"><span data-stu-id="625d7-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="625d7-752">Обратитесь в <a href="https://go.microsoft.com/fwlink/?LinkId=215491">службу поддержки Майкрософт</a>.</span><span class="sxs-lookup"><span data-stu-id="625d7-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-753">ID события: 2005</span><span class="sxs-lookup"><span data-stu-id="625d7-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-754">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-756">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-756">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-757">
<b>Не удалось загрузить антивирусный двигатель, так как платформа антивирусных программ устарела. Платформа антивирусных программ загрузит последний известный хороший движок противомалярийных программ и попытается обновить.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-758">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-759">Антивирус Microsoft Defender не мог загрузить антивирусный двигатель, так как текущая версия платформы не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="625d7-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="625d7-760">Антивирус Microsoft Defender возвращается к последнему хорошо известному двигателю, и будет предпринята попытка обновления платформы.</span><span class="sxs-lookup"><span data-stu-id="625d7-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="625d7-761">
<dt>Текущая версия платформы: &lt; текущая версия платформы&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-762">ID события: 2006</span><span class="sxs-lookup"><span data-stu-id="625d7-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-763">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-765">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-765">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-766">
<b>Обновление платформы не удалось. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-767">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-768">Антивирус Microsoft Defender столкнулся с ошибкой при обновлении платформы.</span><span class="sxs-lookup"><span data-stu-id="625d7-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="625d7-769">
<dt>Текущая версия платформы: &lt; Код ошибки &gt; </dt>текущей версии платформы: код результатов кода
<dt> &lt; &gt; ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-770">ID события: 2007</span><span class="sxs-lookup"><span data-stu-id="625d7-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-771">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-773">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-773">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-774">
<b>Платформа скоро будет устарела. Скачайте последнюю платформу для поддержания последней защиты.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-775">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-776">Антивирус Microsoft Defender вскоре потребует более новой версии платформы для поддержки будущих версий антивирусного двигателя.</span><span class="sxs-lookup"><span data-stu-id="625d7-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="625d7-777">Скачайте последнюю антивирусную платформу Microsoft Defender для поддержания наилучшего уровня доступной защиты.</span><span class="sxs-lookup"><span data-stu-id="625d7-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="625d7-778">
<dt>Текущая версия платформы: &lt; текущая версия платформы&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-779">ID события: 2010</span><span class="sxs-lookup"><span data-stu-id="625d7-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-780">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-782">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-782">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-783">
<b>Для получения дополнительных определений движок antimalware использовал службу динамической подписи. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-784">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-785">Антивирус Microsoft Defender использовал <i>службу динамической подписи</i> для получения дополнительных подписей для защиты компьютера.</span><span class="sxs-lookup"><span data-stu-id="625d7-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="625d7-786">
<dt>Текущая версия подписи: &lt; Текущий &gt; тип подписи:</dt> 
<dt> тип &lt; &gt; подписи, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="625d7-787">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-787">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-788">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-789">Antimalware</span></span></li>
<li><span data-ttu-id="625d7-790">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-791">
</dt>
<dt>Текущая версия двигателя: &lt; Текущий &gt; тип динамической</dt>подписи версии 
<dt> двигателя: &lt; динамический тип &gt; подписи, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-792">Версия</span><span class="sxs-lookup"><span data-stu-id="625d7-792">Version</span></span></li>
<li><span data-ttu-id="625d7-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="625d7-793">Timestamp</span></span></li>
<li><span data-ttu-id="625d7-794">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="625d7-794">No limit</span></span></li>
<li><span data-ttu-id="625d7-795">Duration</span><span class="sxs-lookup"><span data-stu-id="625d7-795">Duration</span></span></li>
</ul><span data-ttu-id="625d7-796">
</dt>
<dt>Путь сохраняемости: &lt; Версия &gt; </dt>
<dt>динамической подписи пути: &lt; &gt; время</dt>компиляции динамических подписей
<dt>версии: &lt; Тип &gt; </dt>ограничения на сохранение: тип ограничения постоянства, 
<dt> &lt; &gt; например:</span><span class="sxs-lookup"><span data-stu-id="625d7-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-797">Версия VDM</span><span class="sxs-lookup"><span data-stu-id="625d7-797">VDM version</span></span></li>
<li><span data-ttu-id="625d7-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="625d7-798">Timestamp</span></span></li>
<li><span data-ttu-id="625d7-799">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="625d7-799">No limit</span></span></li>
</ul><span data-ttu-id="625d7-800">
</dt>
<dt>Ограничение сохраняемости. Ограничение постоянства подписи fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-801">Идентификатор события: 2011</span><span class="sxs-lookup"><span data-stu-id="625d7-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-802">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-804">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-804">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-805">
<b>Служба динамической подписи удалила устарели динамические определения. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-806">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-807">Антивирус Microsoft Defender использовал <i>службу динамической подписи</i> для отбраковки устаревших подписей.</span><span class="sxs-lookup"><span data-stu-id="625d7-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="625d7-808">
<dt>Текущая версия подписи: &lt; Текущий &gt; тип подписи:</dt> 
<dt> тип &lt; &gt; подписи, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="625d7-809">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-809">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-810">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-811">Antimalware</span></span></li>
<li><span data-ttu-id="625d7-812">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-813">
</dt>
<dt>Текущая версия двигателя: &lt; Текущий &gt; тип динамической</dt>подписи версии 
<dt> двигателя: &lt; динамический тип &gt; подписи, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-814">Версия</span><span class="sxs-lookup"><span data-stu-id="625d7-814">Version</span></span></li>
<li><span data-ttu-id="625d7-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="625d7-815">Timestamp</span></span></li>
<li><span data-ttu-id="625d7-816">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="625d7-816">No limit</span></span></li>
<li><span data-ttu-id="625d7-817">Duration</span><span class="sxs-lookup"><span data-stu-id="625d7-817">Duration</span></span></li>
</ul><span data-ttu-id="625d7-818">
</dt>
<dt>Путь сохраняемости: &lt; Версия &gt; </dt>
<dt>динамической &lt; &gt; подписи пути:</dt>время компиляции динамических подписей версии: Причина удаления
<dt> &lt; &gt; timestamp:</dt>Тип ограничения постоянства: тип ограничения постоянства,
<dt></dt> 
<dt> &lt; &gt; например:</span><span class="sxs-lookup"><span data-stu-id="625d7-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-819">Версия VDM</span><span class="sxs-lookup"><span data-stu-id="625d7-819">VDM version</span></span></li>
<li><span data-ttu-id="625d7-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="625d7-820">Timestamp</span></span></li>
<li><span data-ttu-id="625d7-821">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="625d7-821">No limit</span></span></li>
</ul><span data-ttu-id="625d7-822">
</dt>
<dt>Ограничение сохраняемости. Ограничение постоянства подписи fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-823">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-824">Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="625d7-824">No action is necessary.</span></span> <span data-ttu-id="625d7-825">Антивирусный клиент Microsoft Defender находится в нормальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="625d7-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="625d7-826">Это событие сообщается, когда служба динамической подписи успешно удаляет устарели динамические определения.</span><span class="sxs-lookup"><span data-stu-id="625d7-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-827">ID события: 2012</span><span class="sxs-lookup"><span data-stu-id="625d7-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-828">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-830">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-830">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-831">
<b>При попытке использования службы динамической подписи у движка антивирусных программ произошла ошибка. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-832">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-833">Антивирус Microsoft Defender столкнулся с ошибкой при попытке использования <i>службы динамической подписи.</i></span><span class="sxs-lookup"><span data-stu-id="625d7-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="625d7-834">
<dt>Текущая версия подписи: &lt; Текущий &gt; тип подписи:</dt> 
<dt> тип &lt; &gt; подписи, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="625d7-835">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="625d7-835">Antivirus</span></span></li>
<li><span data-ttu-id="625d7-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="625d7-836">Antispyware</span></span></li>
<li><span data-ttu-id="625d7-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="625d7-837">Antimalware</span></span></li>
<li><span data-ttu-id="625d7-838">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-839">
</dt>
<dt>Текущая версия двигателя: &lt; Код ошибки &gt; </dt>текущей версии
<dt>двигателя: код результатов кода &lt; &gt; ошибки, связанный с состоянием угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt> 
<dt> Динамический тип подписи: &lt; динамический &gt; тип подписи, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-840">Версия</span><span class="sxs-lookup"><span data-stu-id="625d7-840">Version</span></span></li>
<li><span data-ttu-id="625d7-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="625d7-841">Timestamp</span></span></li>
<li><span data-ttu-id="625d7-842">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="625d7-842">No limit</span></span></li>
<li><span data-ttu-id="625d7-843">Duration</span><span class="sxs-lookup"><span data-stu-id="625d7-843">Duration</span></span></li>
</ul><span data-ttu-id="625d7-844">
</dt>
<dt>Путь сохраняемости: &lt; Версия &gt; </dt>
<dt>динамической подписи пути: &lt; &gt; время</dt>компиляции динамических подписей
<dt>версии: &lt; Тип &gt; </dt>ограничения на сохранение: тип ограничения постоянства, 
<dt> &lt; &gt; например:</span><span class="sxs-lookup"><span data-stu-id="625d7-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-845">Версия VDM</span><span class="sxs-lookup"><span data-stu-id="625d7-845">VDM version</span></span></li>
<li><span data-ttu-id="625d7-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="625d7-846">Timestamp</span></span></li>
<li><span data-ttu-id="625d7-847">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="625d7-847">No limit</span></span></li>
</ul><span data-ttu-id="625d7-848">
</dt>
<dt>Ограничение сохраняемости. Ограничение постоянства подписи fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-849">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-850">Проверьте параметры подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="625d7-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-851">ID события: 2013</span><span class="sxs-lookup"><span data-stu-id="625d7-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-852">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-854">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-854">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-855">
<b>Служба динамической подписи удалила все динамические определения. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-856">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-857">Антивирус Microsoft Defender отбросил все <i>подписи службы динамической</i> подписи.</span><span class="sxs-lookup"><span data-stu-id="625d7-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="625d7-858">
<dt>Текущая версия подписи: &lt; текущая версия подписи&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-859">ID события: 2020</span><span class="sxs-lookup"><span data-stu-id="625d7-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-860">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-862">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-862">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-863">
<b>Движок antimalware скачал чистый файл. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-864">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-865">Антивирус Microsoft Defender скачал чистый файл.</span><span class="sxs-lookup"><span data-stu-id="625d7-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="625d7-866">
<dt>Имя файла: &lt; Имя &gt; файла.</dt> 
<dt>Текущая версия подписи: &lt; Текущая &gt; версия подписи</dt>
<dt>Текущая версия двигателя: &lt; текущая версия двигателя &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-867">ID события: 2021</span><span class="sxs-lookup"><span data-stu-id="625d7-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-868">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-870">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-870">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-871">
<b>Движок antimalware не смог скачать чистый файл. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-872">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-873">Антивирус Microsoft Defender столкнулся с ошибкой при попытке скачать чистый файл.</span><span class="sxs-lookup"><span data-stu-id="625d7-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="625d7-874">
<dt>Имя файла: &lt; Имя &gt; файла.</dt> 
<dt>Текущая версия подписи: &lt; Текущая &gt; версия подписи</dt>
<dt>Current Engine Version: &lt; Current engine &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-875">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-876">Проверьте параметры подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="625d7-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="625d7-877">Антивирусный клиент Microsoft Defender столкнулся с ошибкой при использовании службы динамической подписи для скачивания последних определений в определенную угрозу.</span><span class="sxs-lookup"><span data-stu-id="625d7-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="625d7-878">Эта ошибка, скорее всего, вызвана проблемой подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="625d7-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-879">ID события: 2030</span><span class="sxs-lookup"><span data-stu-id="625d7-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-880">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-882">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-882">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-883">
<b>Движок antimalware был загружен и настроен для запуска в автономном режиме при следующей перезагрузке системы.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-884">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-885">Антивирус Microsoft Defender скачал и настраивал автономный антивирус для запуска следующей перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="625d7-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-886">ID события: 2031</span><span class="sxs-lookup"><span data-stu-id="625d7-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-887">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-889">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-889">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-890">
<b>Движок antimalware не смог скачать и настроить автономное сканирование.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-891">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-892">Антивирус Microsoft Defender столкнулся с ошибкой при попытке скачать и настроить автономный антивирус.</span><span class="sxs-lookup"><span data-stu-id="625d7-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="625d7-893">
<dt>Код ошибки: &lt; Код кода &gt; ошибки Результат, связанный со статусом угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-894">ID события: 2040</span><span class="sxs-lookup"><span data-stu-id="625d7-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-895">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-897">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-897">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-898">
<b>Поддержка антивирусных программ для этой версии операционной системы скоро закончится. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-899">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-900">Поддержка операционной системы истекает в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="625d7-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="625d7-901">Запуск антивируса Microsoft Defender в операционной системе поддержки не является адекватным решением для защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="625d7-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-902">Идентификатор события: 2041</span><span class="sxs-lookup"><span data-stu-id="625d7-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-903">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-905">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-905">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-906">
<b>Поддержка антивирусных программ для этой операционной системы завершена. Для дальнейшей поддержки необходимо обновить операционную систему. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-907">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-908">Срок службы поддержки операционной системы истек.</span><span class="sxs-lookup"><span data-stu-id="625d7-908">The support for your operating system has expired.</span></span> <span data-ttu-id="625d7-909">Запуск антивируса Microsoft Defender в операционной системе поддержки не является адекватным решением для защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="625d7-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-910">ID события: 2042</span><span class="sxs-lookup"><span data-stu-id="625d7-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-911">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-913">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-913">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-914">
<b>Движок antimalware больше не поддерживает эту операционную систему и больше не защищает систему от вредоносных программ. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-915">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-916">Срок службы поддержки операционной системы истек.</span><span class="sxs-lookup"><span data-stu-id="625d7-916">The support for your operating system has expired.</span></span> <span data-ttu-id="625d7-917">Антивирус Microsoft Defender больше не поддерживается в операционной системе, перестал функционировать и не защищает от угроз вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="625d7-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-918">ID события: 3002</span><span class="sxs-lookup"><span data-stu-id="625d7-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-919">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-921">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-921">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-922">
<b>Защита в режиме реального времени столкнулась с ошибкой и сбой.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-923">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-924">Функция защиты Real-Time Microsoft Defender столкнулась с ошибкой и не справилась с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="625d7-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="625d7-925">
<dt>Функция: &lt; &gt; Функция, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-926">О доступе</span><span class="sxs-lookup"><span data-stu-id="625d7-926">On Access</span></span></li>
<li><span data-ttu-id="625d7-927">Загрузка Internet Explorer и вложения Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="625d7-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="625d7-928">Мониторинг поведения</span><span class="sxs-lookup"><span data-stu-id="625d7-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="625d7-929">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-930">
</dt>
<dt>Код ошибки: &lt; Код кода &gt; ошибки Результат, связанный со статусом угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt> Причина: причина перезапуска антивирусной защиты Microsoft Defender в режиме 
<dt>реального времени.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-931">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-932">Необходимо перезапустить систему, а затем выполнить полное сканирование, так как&#39;возможно, что система не была защищена в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="625d7-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="625d7-933">Антивирусный клиент Microsoft Defender&#39;функции защиты в режиме реального времени столкнулся с ошибкой из-за того, что одна из служб не смогла запуститься.</span><span class="sxs-lookup"><span data-stu-id="625d7-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="625d7-934">Если за ним следует ID события 3007, сбой был временным, и клиент антивирусного обеспечения восстановился после сбоя.</span><span class="sxs-lookup"><span data-stu-id="625d7-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-935">ID события: 3007</span><span class="sxs-lookup"><span data-stu-id="625d7-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-936">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-938">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-938">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-939">
<b>Защита в режиме реального времени, восстановленная после сбоя. При просмотре этой ошибки рекомендуется полное сканирование системы. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-940">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-941">Антивирус Microsoft Defender в режиме реального времени перезапустил функцию.</span><span class="sxs-lookup"><span data-stu-id="625d7-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="625d7-942">Рекомендуется выполнить полное сканирование системы для обнаружения элементов, которые могли быть пропущены во время сбития этого агента.</span><span class="sxs-lookup"><span data-stu-id="625d7-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="625d7-943">
<dt>Функция: &lt; &gt; Функция, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-944">О доступе</span><span class="sxs-lookup"><span data-stu-id="625d7-944">On Access</span></span></li>
<li><span data-ttu-id="625d7-945">Загрузка IE и вложения Outlook Express</span><span class="sxs-lookup"><span data-stu-id="625d7-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="625d7-946">Мониторинг поведения</span><span class="sxs-lookup"><span data-stu-id="625d7-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="625d7-947">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-948">
</dt>
<dt>Причина: причина перезапуска антивирусной защиты Microsoft Defender в режиме реального времени.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-949">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-950">Функция защиты в режиме реального времени перезапущена.</span><span class="sxs-lookup"><span data-stu-id="625d7-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="625d7-951">Если это событие произойдет снова, обратитесь <a href="https://go.microsoft.com/fwlink/?LinkId=215491">в службу технической поддержки Майкрософт.</a></span><span class="sxs-lookup"><span data-stu-id="625d7-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-952">ID события: 5000</span><span class="sxs-lookup"><span data-stu-id="625d7-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-953">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-955">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-955">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-956">
<b>Включена защита в режиме реального времени. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-957">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-958">Было включено сканирование антивируса Microsoft Defender в режиме реального времени для вредоносных программ и другого потенциально нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="625d7-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-959">ID события: 5001</span><span class="sxs-lookup"><span data-stu-id="625d7-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-960">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-962">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-962">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-963">
<b>Защита в режиме реального времени отключена. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-964">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-965">Проверка антивируса Microsoft Defender в режиме реального времени для вредоносных программ и другого потенциально нежелательного программного обеспечения была отключена.</span><span class="sxs-lookup"><span data-stu-id="625d7-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-966">ID события: 5004</span><span class="sxs-lookup"><span data-stu-id="625d7-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-967">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-969">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-969">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-970">
<b>Изменена конфигурация защиты в режиме реального времени. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-971">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-972">Конфигурация функции защиты антивируса Microsoft Defender в режиме реального времени изменилась.</span><span class="sxs-lookup"><span data-stu-id="625d7-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="625d7-973">
<dt>Функция: &lt; &gt; Функция, например:</span><span class="sxs-lookup"><span data-stu-id="625d7-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="625d7-974">О доступе</span><span class="sxs-lookup"><span data-stu-id="625d7-974">On Access</span></span></li>
<li><span data-ttu-id="625d7-975">Загрузка IE и вложения Outlook Express</span><span class="sxs-lookup"><span data-stu-id="625d7-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="625d7-976">Мониторинг поведения</span><span class="sxs-lookup"><span data-stu-id="625d7-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="625d7-977">Система сетевого контроля</span><span class="sxs-lookup"><span data-stu-id="625d7-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="625d7-978">
</dt>
<dt>Конфигурация: </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-979">ID события: 5007</span><span class="sxs-lookup"><span data-stu-id="625d7-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-980">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-982">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-982">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-983">
<b>Изменена конфигурация платформы антивирусного программного обеспечения.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-984">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-985">Конфигурация антивируса Microsoft Defender изменилась.</span><span class="sxs-lookup"><span data-stu-id="625d7-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="625d7-986">Если это неожиданное событие, необходимо просмотреть параметры, так как это может быть результатом вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="625d7-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="625d7-987">
<dt>Старое значение: &lt; Старое значение число &gt; Старое значение конфигурации антивируса.</dt> 
<dt>Новое значение: &lt; Новое значение число &gt; Новое значение конфигурации антивируса.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-988">ID события: 5008</span><span class="sxs-lookup"><span data-stu-id="625d7-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-989">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-991">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-991">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-992">
<b>Двигатель антивирусного обеспечения столкнулся с ошибкой и не справился с ошибкой.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-993">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-994">Антивирусный движок Microsoft Defender был прекращен из-за неожиданной ошибки.</span><span class="sxs-lookup"><span data-stu-id="625d7-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="625d7-995">
<dt>Тип отказа: &lt; Тип &gt; отказа, например: Crash или Hang</dt>Exception
<dt>Code: Error &lt; code &gt; </dt>
<dt>Resource: &lt; Resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-996">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-997">Устранение неполадок в этом событии:</span><span class="sxs-lookup"><span data-stu-id="625d7-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="625d7-998">Попробуйте перезапустить службу.</span><span class="sxs-lookup"><span data-stu-id="625d7-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="625d7-999">Для антивирусных, антивирусных и шпионских программ в командной подсказке введите <b>msmpsvc</b>с чистой остановкой, а затем введите сетевой <b>msmpsvc</b> для перезапуска двигателя противомалярийных программ.</span><span class="sxs-lookup"><span data-stu-id="625d7-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="625d7-1000">Для <i></i>системы сетевого контроля на повышенной командной подсказке введите чистый пуск <b>nissrv,</b>а затем введите чистый пуск <b>nissrv</b> для перезапуска двигателя системы проверки сети с помощью NiSSRV.exe файла. <i></i></span><span class="sxs-lookup"><span data-stu-id="625d7-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="625d7-1001">Если он не удается таким же образом, обратитесь к коду ошибки, обратившись <b></b> к сайту поддержки <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Майкрософт</a> и введите номер ошибки в поле Поиска и обратитесь в <a href="https://go.microsoft.com/fwlink/?LinkId=215491">службу технической поддержки Майкрософт.</a></span><span class="sxs-lookup"><span data-stu-id="625d7-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1002">Действие пользователя:</span><span class="sxs-lookup"><span data-stu-id="625d7-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="625d7-1003">Клиентский движок антивирусной программы Microsoft Defender остановился из-за неожиданной ошибки.</span><span class="sxs-lookup"><span data-stu-id="625d7-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="625d7-1004">Устранение неполадок в этом событии:</span><span class="sxs-lookup"><span data-stu-id="625d7-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="625d7-1005">Снова запустите сканирование.</span><span class="sxs-lookup"><span data-stu-id="625d7-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="625d7-1006">Если это не удается таким же образом, перейдите на сайт <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support,</a>введите номер ошибки в поле Поиска, чтобы найти код ошибки.</span><span class="sxs-lookup"><span data-stu-id="625d7-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="625d7-1007">Обратитесь в <a href="https://go.microsoft.com/fwlink/?LinkId=215491">службу поддержки Майкрософт</a>.</span><span class="sxs-lookup"><span data-stu-id="625d7-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1008">ID события: 5009</span><span class="sxs-lookup"><span data-stu-id="625d7-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-1009">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1011">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-1012">
<b>Включено сканирование вредоносных программ и других потенциально нежелательных программ. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1013">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-1014">Включено антивирусное сканирование Microsoft Defender для вредоносных программ и другого потенциально нежелательного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="625d7-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1015">ID события: 5010</span><span class="sxs-lookup"><span data-stu-id="625d7-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-1016">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1018">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-1019">
<b>Сканирование вредоносных программ и других потенциально нежелательных программ отключено.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1020">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-1021">Антивирусное сканирование Microsoft Defender для вредоносных программ и другого потенциально нежелательного программного обеспечения отключено.</span><span class="sxs-lookup"><span data-stu-id="625d7-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1022">ID события: 5011</span><span class="sxs-lookup"><span data-stu-id="625d7-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-1023">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1025">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-1026">
<b>Сканирование для вирусов включено.</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1027">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-1028">Включено антивирусное сканирование microsoft Defender для вирусов.</span><span class="sxs-lookup"><span data-stu-id="625d7-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1029">ID события: 5012</span><span class="sxs-lookup"><span data-stu-id="625d7-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-1030">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1032">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-1033">
<b>Сканирование для вирусов отключено. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1034">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-1035">Антивирусное сканирование Microsoft Defender для вирусов отключено.</span><span class="sxs-lookup"><span data-stu-id="625d7-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1036">ID события: 5100</span><span class="sxs-lookup"><span data-stu-id="625d7-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-1037">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1039">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-1040">
<b>В ближайшее время срок действия платформы антивирусного обеспечения истекает. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1041">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-1042">Антивирус Microsoft Defender вступил в льготный период и скоро истечет.</span><span class="sxs-lookup"><span data-stu-id="625d7-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="625d7-1043">По истечении срока действия эта программа отключит защиту от вирусов, программ-шпионов и других потенциально нежелательных программ.</span><span class="sxs-lookup"><span data-stu-id="625d7-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="625d7-1044">
<dt>Причина истечения срока действия: истекает срок</dt> действия антивируса Microsoft Defender. 
<dt>Срок действия: срок действия антивируса Microsoft Defender истекает.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1045">ID события: 5101</span><span class="sxs-lookup"><span data-stu-id="625d7-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="625d7-1046">Символическое имя:</span><span class="sxs-lookup"><span data-stu-id="625d7-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="625d7-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1048">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="625d7-1049">
<b>Срок действия платформы антивирусного обеспечения истек. </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1050">Описание:</span><span class="sxs-lookup"><span data-stu-id="625d7-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="625d7-1051">Истек срок действия льготного периода для антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="625d7-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="625d7-1052">Отключена защита от вирусов, программ-шпионов и других потенциально нежелательных программ.</span><span class="sxs-lookup"><span data-stu-id="625d7-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="625d7-1053">
<dt>Причина истечения срока действия:</dt>срок
<dt>действия: </dt> 
<dt>код ошибки: код кода &lt; &gt; ошибки, связанный со статусом угрозы. Стандартные значения HRESULT.</dt> 
<dt>Описание ошибки: &lt; Описание &gt; ошибки Описание ошибки.</dt>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="625d7-1054">
</table>

<a id="error-codes"></a>
## Коды ошибок клиента антивирусной программы Microsoft Defender, если антивирус Microsoft Defender испытывает какие-либо проблемы, он обычно дает код ошибки, чтобы помочь устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="625d7-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="625d7-1055">Чаще всего ошибка означает, что возникла проблема с установкой обновления.</span><span class="sxs-lookup"><span data-stu-id="625d7-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="625d7-1056">В этом разделе приводится следующая информация об ошибках клиента антивирусной программы Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="625d7-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="625d7-1057">-   Код -   ошибки Возможная причина ошибки -   Советы о том, что делать сейчас</span><span class="sxs-lookup"><span data-stu-id="625d7-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="625d7-1058">Используйте сведения в этих таблицах для устранения неполадок кодов ошибок антивирусной программы Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="625d7-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="625d7-1059">Код ошибки: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="625d7-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="625d7-1060">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1060">Message</span></span></td>
<td><span data-ttu-id="625d7-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1062">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="625d7-1063">Эта ошибка указывает на то, что у вас может не быть памяти.</span><span class="sxs-lookup"><span data-stu-id="625d7-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="625d7-1064">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="625d7-1065">Проверьте доступную память на устройстве.</span><span class="sxs-lookup"><span data-stu-id="625d7-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="625d7-1066">Закройте все неиспользованые приложения, которые работают, чтобы освободить память на устройстве.</span><span class="sxs-lookup"><span data-stu-id="625d7-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="625d7-1067">Перезапустите устройство и снова запустите сканирование.</span><span class="sxs-lookup"><span data-stu-id="625d7-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1068">Код ошибки: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="625d7-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="625d7-1069">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1069">Message</span></span></td>
<td><span data-ttu-id="625d7-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1071">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1072">Эта ошибка указывает на то, что может возникнуть проблема с продуктом безопасности.</span><span class="sxs-lookup"><span data-stu-id="625d7-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="625d7-1073">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="625d7-1074">Обновление определений.</span><span class="sxs-lookup"><span data-stu-id="625d7-1074">Update the definitions.</span></span> <span data-ttu-id="625d7-1075">Либо:</span><span class="sxs-lookup"><span data-stu-id="625d7-1075">Either:</span></span><ol>
<li><span data-ttu-id="625d7-1076">Щелкните <b>кнопку Определения обновления</b> на вкладке <b>Обновление</b> в антивирусе Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="625d7-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="625d7-1077">Или:</span><span class="sxs-lookup"><span data-stu-id="625d7-1077">Or,</span></span>
</li>
<li><span data-ttu-id="625d7-1078">Скачайте последние определения с сайта <a href="https://aka.ms/wdsi">Microsoft Security Intelligence.</a></span><span class="sxs-lookup"><span data-stu-id="625d7-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="625d7-1079">Примечание. Размер файла определений, загруженного с сайта, может превышать 60 МБ и не должен использоваться в качестве долгосрочного решения для обновления определений.</span><span class="sxs-lookup"><span data-stu-id="625d7-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="625d7-1080">Запустите полное сканирование.</span><span class="sxs-lookup"><span data-stu-id="625d7-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="625d7-1081">Перезапустите устройство и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="625d7-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1082">Код ошибки: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="625d7-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="625d7-1083">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1083">Message</span></span></td>
<td><span data-ttu-id="625d7-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1085">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1086">Эта ошибка указывает на возможность ошибки конфигурации двигателя; Обычно это связано с входных данных, которые не позволяют нормально работать двигателю.</span><span class="sxs-lookup"><span data-stu-id="625d7-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1087">Код ошибки: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="625d7-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1088">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1088">Message</span></span></td>
<td><span data-ttu-id="625d7-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1090">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1091">Эта ошибка указывает на то, что антивирус Microsoft Defender не справился с карантином угрозы.</span><span class="sxs-lookup"><span data-stu-id="625d7-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1092">Код ошибки: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="625d7-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1093">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1093">Message</span></span></td>
<td><span data-ttu-id="625d7-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1095">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1096">Эта ошибка указывает на то, что для полного удаления угрозы требуется перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="625d7-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="625d7-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="625d7-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1098">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1098">Message</span></span></td>
<td><span data-ttu-id="625d7-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1100">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1101">Эта ошибка указывает на то, что угроза может больше не присутствовать в средствах массовой информации или вредоносные программы могут помешать вам сканировать устройство.</span><span class="sxs-lookup"><span data-stu-id="625d7-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="625d7-1102">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="625d7-1103">Запустите <a href="https://www.microsoft.com/security/scanner/default.aspx">сканер безопасности Майкрософт,</a> а затем обновите программное обеспечение безопасности и попробуйте еще раз.</span><span class="sxs-lookup"><span data-stu-id="625d7-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1104">Код ошибки: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="625d7-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="625d7-1105">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1105">Message</span></span></td>
<td><span data-ttu-id="625d7-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1107">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1108">Эта ошибка указывает на то, что может потребоваться полное сканирование системы.</span><span class="sxs-lookup"><span data-stu-id="625d7-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="625d7-1109">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1109">Resolution</span></span></td><td>
<span data-ttu-id="625d7-1110">Запустите полное сканирование системы.</span><span class="sxs-lookup"><span data-stu-id="625d7-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1111">Код ошибки: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="625d7-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1112">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1112">Message</span></span></td>
<td><span data-ttu-id="625d7-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1114">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1115">Эта ошибка указывает на то, что для завершения удаления угрозы требуются инструкции вручную.</span><span class="sxs-lookup"><span data-stu-id="625d7-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="625d7-1116">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1116">Resolution</span></span></td><td>
<span data-ttu-id="625d7-1117">Выполните инструкции по исправлению вручную, описанные в энциклопедии <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection.</a></span><span class="sxs-lookup"><span data-stu-id="625d7-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="625d7-1118">В истории событий можно найти ссылку, относяную к угрозам.</span><span class="sxs-lookup"><span data-stu-id="625d7-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1119">Код ошибки: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="625d7-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1120">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1120">Message</span></span></td>
<td><span data-ttu-id="625d7-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1122">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1123">Эта ошибка указывает на то, что удаление внутри типа контейнера может не поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="625d7-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="625d7-1124">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1124">Resolution</span></span></td><td>
<span data-ttu-id="625d7-1125">Антивирус Microsoft Defender не способен устранять угрозы, обнаруженные в архиве.</span><span class="sxs-lookup"><span data-stu-id="625d7-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="625d7-1126">Рассмотрите возможность вручную удалить обнаруженные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="625d7-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1127">Код ошибки: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="625d7-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1128">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1128">Message</span></span></td>
<td><span data-ttu-id="625d7-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1130">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1131">Эта ошибка указывает на то, что удаление низких и средних угроз может быть отключено.</span><span class="sxs-lookup"><span data-stu-id="625d7-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="625d7-1132">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1132">Resolution</span></span></td><td>
<span data-ttu-id="625d7-1133">Проверьте обнаруженные угрозы и устраняйте их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="625d7-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1134">Код ошибки: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="625d7-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1135">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1135">Message</span></span></td>
<td><span data-ttu-id="625d7-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1137">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1138">Эта ошибка указывает на то, что требуется повторное сообщение об угрозе.</span><span class="sxs-lookup"><span data-stu-id="625d7-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="625d7-1139">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1139">Resolution</span></span></td><td>
<span data-ttu-id="625d7-1140">Запустите полное сканирование системы.</span><span class="sxs-lookup"><span data-stu-id="625d7-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1141">Код ошибки: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="625d7-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1142">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1142">Message</span></span></td>
<td><span data-ttu-id="625d7-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="625d7-1144">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1145">Эта ошибка указывает на то, что требуется автономное сканирование.</span><span class="sxs-lookup"><span data-stu-id="625d7-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="625d7-1146">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1146">Resolution</span></span></td><td>
<span data-ttu-id="625d7-1147">Запуск автономного антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="625d7-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="625d7-1148">О том, как это сделать, можно прочитать в автономной статье <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Microsoft Defender Antivirus</a>.</span><span class="sxs-lookup"><span data-stu-id="625d7-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="625d7-1149">Код ошибки: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="625d7-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="625d7-1150">Сообщение</span><span class="sxs-lookup"><span data-stu-id="625d7-1150">Message</span></span></td>
<td><span data-ttu-id="625d7-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="625d7-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="625d7-1152">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="625d7-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="625d7-1153">Эта ошибка указывает на то, что антивирус Microsoft Defender не поддерживает текущую версию платформы и требует новой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="625d7-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="625d7-1154">Решение</span><span class="sxs-lookup"><span data-stu-id="625d7-1154">Resolution</span></span></td><td>
<span data-ttu-id="625d7-1155">Антивирус Microsoft Defender можно использовать только в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="625d7-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="625d7-1156">Для Windows 8 Windows 7 и Windows Vista можно использовать защиту конечных <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">точек System Center.</a></span><span class="sxs-lookup"><span data-stu-id="625d7-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="625d7-1157">

<a id="internal-error-codes"></a> Следующие коды ошибок используются во время внутреннего тестирования антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="625d7-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="625d7-1158">Если вы видите эти ошибки, вы можете попытаться [обновить](manage-updates-baselines-microsoft-defender-antivirus.md) определения и заставить rescan непосредственно на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="625d7-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="625d7-1159">Внутренние коды ошибок</span><span class="sxs-lookup"><span data-stu-id="625d7-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="625d7-1160"><b>Код ошибки</b></span><span class="sxs-lookup"><span data-stu-id="625d7-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="625d7-1161">Отображаемая</span><span class="sxs-lookup"><span data-stu-id="625d7-1161">Message displayed</span></span></th>
<th><span data-ttu-id="625d7-1162">Возможная причина ошибки и разрешения</span><span class="sxs-lookup"><span data-stu-id="625d7-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="625d7-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="625d7-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="625d7-1165">Проверьте подключение к Интернету и снова запустите сканирование.</span><span class="sxs-lookup"><span data-stu-id="625d7-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="625d7-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="625d7-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="625d7-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="625d7-1168">Это внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="625d7-1168">This is an internal error.</span></span> <span data-ttu-id="625d7-1169">Причина не определена.</span><span class="sxs-lookup"><span data-stu-id="625d7-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="625d7-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="625d7-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="625d7-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="625d7-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="625d7-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="625d7-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="625d7-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="625d7-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="625d7-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="625d7-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="625d7-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="625d7-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="625d7-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="625d7-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="625d7-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="625d7-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="625d7-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="625d7-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="625d7-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="625d7-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="625d7-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="625d7-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="625d7-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="625d7-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="625d7-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="625d7-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="625d7-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="625d7-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="625d7-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="625d7-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="625d7-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="625d7-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="625d7-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="625d7-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="625d7-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="625d7-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="625d7-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="625d7-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="625d7-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="625d7-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="625d7-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="625d7-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="625d7-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="625d7-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="625d7-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="625d7-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="625d7-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="625d7-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="625d7-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="625d7-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="625d7-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="625d7-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="625d7-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="625d7-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="625d7-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="625d7-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="625d7-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="625d7-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="625d7-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="625d7-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="625d7-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="625d7-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="625d7-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="625d7-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="625d7-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="625d7-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="625d7-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="625d7-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="625d7-1238">Это внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="625d7-1238">This is an internal error.</span></span> <span data-ttu-id="625d7-1239">Это может быть вызвано, когда удаление вредоносных программ не является успешным.</span><span class="sxs-lookup"><span data-stu-id="625d7-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="625d7-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="625d7-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="625d7-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="625d7-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="625d7-1242">Это внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="625d7-1242">This is an internal error.</span></span> <span data-ttu-id="625d7-1243">Возможно, она сработала, когда проверка не завершена.</span><span class="sxs-lookup"><span data-stu-id="625d7-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="625d7-1244">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="625d7-1244">Related topics</span></span>

- [<span data-ttu-id="625d7-1245">Отчет о защите антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="625d7-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="625d7-1246">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="625d7-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)