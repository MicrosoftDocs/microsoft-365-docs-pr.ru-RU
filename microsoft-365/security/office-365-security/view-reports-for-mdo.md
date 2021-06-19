---
title: Просмотр отчетов Defender для Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут узнать, как найти и использовать Defender для Office 365 отчетов, доступных на Microsoft 365 Defender портале.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b9279614571c123ad92f1684f86175b410c6c5c
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022845"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="80bce-103">Просмотр отчетов Defender для Office 365 на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80bce-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80bce-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="80bce-104">**Applies to**</span></span>
- [<span data-ttu-id="80bce-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="80bce-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="80bce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80bce-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="80bce-107">Microsoft Defender для Office 365 организаций (например, Microsoft 365 E5 подписки или Microsoft Defender для Office 365 Plan 1 или Microsoft Defender для надстройки Office 365 Plan 2) содержат различные отчеты, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="80bce-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="80bce-108">Если у вас [есть](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)необходимые разрешения, вы можете просмотреть эти  отчеты на портале Microsoft 365 Defender, переехав в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе**.</span><span class="sxs-lookup"><span data-stu-id="80bce-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="80bce-109">Чтобы перейти непосредственно на **страницу отчетов & электронной почты,** откройте <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="80bce-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Страница & отчетов о совместной работе на Microsoft 365 Defender портале](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="80bce-111">Отчеты о безопасности электронной почты, которые не требуют Office 365 Defender, описаны в просмотре отчетов о безопасности электронной почты на [Microsoft 365 Defender портале](view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="80bce-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="80bce-112">Отчеты, связанные с потоком почты, теперь находятся Exchange центра администрирования (EAC).</span><span class="sxs-lookup"><span data-stu-id="80bce-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="80bce-113">Дополнительные сведения об этих отчетах см. в сообщении потока почты в [новом центре администрирования Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="80bce-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="80bce-114">Сейф Отчет о типах файлов вложения</span><span class="sxs-lookup"><span data-stu-id="80bce-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="80bce-115">Отчет **Сейф типов вложений** в конечном итоге будет отходить.</span><span class="sxs-lookup"><span data-stu-id="80bce-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="80bce-116">Такая же информация доступна в отчете о состоянии [защиты от угроз.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="80bce-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="80bce-117">Сейф Отчет о диспозиции сообщений вложения</span><span class="sxs-lookup"><span data-stu-id="80bce-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="80bce-118">Отчет **Сейф сообщений о диспозиции** вложений в конечном итоге будет отходить.</span><span class="sxs-lookup"><span data-stu-id="80bce-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="80bce-119">Такая же информация доступна в отчете о состоянии [защиты от угроз.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="80bce-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="80bce-120">Отчет о задержке почты</span><span class="sxs-lookup"><span data-stu-id="80bce-120">Mail latency report</span></span>

<span data-ttu-id="80bce-121">В **отчете о задержке** почты показано совокупное представление задержки доставки почты и детонации в организации.</span><span class="sxs-lookup"><span data-stu-id="80bce-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="80bce-122">Время доставки почты в службе зависит от ряда факторов, и абсолютное время доставки в секундах часто не является хорошим показателем успешности или проблемы.</span><span class="sxs-lookup"><span data-stu-id="80bce-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="80bce-123">Медленное время доставки в один день можно считать средним временем доставки в другой день или наоборот.</span><span class="sxs-lookup"><span data-stu-id="80bce-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="80bce-124">Это пытается квалифицировать доставку сообщений на основе статистических данных о наблюдаемом времени доставки других сообщений.</span><span class="sxs-lookup"><span data-stu-id="80bce-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="80bce-125">Клиентская сторона и задержка сети не включаются.</span><span class="sxs-lookup"><span data-stu-id="80bce-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="80bce-126">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="80bce-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="80bce-127">На странице **Отчеты &** электронной почты найдите отчет о задержке почты и нажмите  **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="80bce-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="80bce-128">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="80bce-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![Виджет отчета о задержке почты на странице отчетов & сообщения электронной почты](../../media/mail-latency-report-widget.png)

<span data-ttu-id="80bce-130">На странице **отчета о задержке** почты на странице отчета о задержке почты доступны следующие **вкладки:**</span><span class="sxs-lookup"><span data-stu-id="80bce-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="80bce-131">**50-й процентиль.** Это среднее время доставки сообщений.</span><span class="sxs-lookup"><span data-stu-id="80bce-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="80bce-132">Это значение можно рассматривать как среднее время доставки.</span><span class="sxs-lookup"><span data-stu-id="80bce-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="80bce-133">Эта вкладка выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="80bce-133">This tab is selected by default.</span></span>
- <span data-ttu-id="80bce-134">**90-й процентиль.** Это указывает на высокую задержку доставки сообщений.</span><span class="sxs-lookup"><span data-stu-id="80bce-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="80bce-135">Только 10% сообщений занимает больше времени, чем это значение для доставки.</span><span class="sxs-lookup"><span data-stu-id="80bce-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="80bce-136">**99-й процентиль.** Это указывает на наивысшую задержку доставки сообщений.</span><span class="sxs-lookup"><span data-stu-id="80bce-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="80bce-137">Независимо от выбранной вкладки на диаграмме показаны сообщения, организованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="80bce-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="80bce-138">**Задержка доставки почты**</span><span class="sxs-lookup"><span data-stu-id="80bce-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="80bce-139">**Детонации**</span><span class="sxs-lookup"><span data-stu-id="80bce-139">**Detonations**</span></span>

<span data-ttu-id="80bce-140">При наведении над категорией на диаграмме можно увидеть разбивку задержки в каждой категории.</span><span class="sxs-lookup"><span data-stu-id="80bce-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Представление 50 процентилов отчета о задержке почты](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="80bce-142">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу сведений следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="80bce-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="80bce-143">**Дата (UTC)**: **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="80bce-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="80bce-144">**Представление сообщения.** Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="80bce-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="80bce-145">**Все сообщения**;</span><span class="sxs-lookup"><span data-stu-id="80bce-145">**All messages**</span></span>
  - <span data-ttu-id="80bce-146">**Сообщения, содержащие вложения или URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="80bce-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="80bce-147">**Взорванные сообщения**</span><span class="sxs-lookup"><span data-stu-id="80bce-147">**Detonated messages**</span></span>

<span data-ttu-id="80bce-148">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="80bce-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="80bce-149">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="80bce-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="80bce-150">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="80bce-150">**Date (UTC)**</span></span>
- <span data-ttu-id="80bce-151">**Percentiles**: **50**, **90**, или **99**</span><span class="sxs-lookup"><span data-stu-id="80bce-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="80bce-152">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="80bce-152">**Message count**</span></span>
- <span data-ttu-id="80bce-153">**Общая задержка**</span><span class="sxs-lookup"><span data-stu-id="80bce-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="80bce-154">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="80bce-154">Threat protection status report</span></span>

<span data-ttu-id="80bce-155">Отчет **о состоянии** защиты от угроз представляет собой одно представление, которое объединяет сведения о вредоносном контенте и вредоносной электронной почте, обнаруженной и заблокированной Exchange Online Protection (EOP) и Microsoft Defender для Office 365. [](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="80bce-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="80bce-156">Дополнительные сведения см. в [отчете о состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="80bce-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="80bce-157">Отчет об угрозе URL-адреса</span><span class="sxs-lookup"><span data-stu-id="80bce-157">URL threat protection report</span></span>

<span data-ttu-id="80bce-158">В **отчете об угрозе** URL-адресов содержится сводка и представления тенденций для обнаруженных угроз и действия, принятые на щелчках [URL-адресов в Сейф ссылки.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="80bce-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="80bce-159">В этом отчете не будут щелкать данные пользователей,  Сейф применяемая политика ссылок имеет выбранный параметр Не отслеживать щелчки пользователя.</span><span class="sxs-lookup"><span data-stu-id="80bce-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="80bce-160">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="80bce-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="80bce-161">На странице **отчетов & электронной** почты найдите страницу **защиты URL-адресов** и нажмите **кнопку Просмотр сведений.**</span><span class="sxs-lookup"><span data-stu-id="80bce-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="80bce-162">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="80bce-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![Виджет отчета о защите URL-адресов на странице отчетов & электронной почты](../../media/url-protection-report-widget.png)

<span data-ttu-id="80bce-164">Доступные представления на странице **отчета об** угрозе url-адресов описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="80bce-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="80bce-165">Это отчет *тенденции защиты,* то есть данные представляют тенденции в большом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="80bce-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="80bce-166">В результате, данные на диаграммах недоступны в режиме реального времени, но данные в таблице сведений есть, поэтому между ними может возникнуть небольшое несоответствие.</span><span class="sxs-lookup"><span data-stu-id="80bce-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="80bce-167">Диаграммы обновляются один раз в четыре часа и содержат данные за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="80bce-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="80bce-168">Просмотр данных по URL-адресу щелкните действие защиты</span><span class="sxs-lookup"><span data-stu-id="80bce-168">View data by URL click protection action</span></span>

![URL-адрес щелкните представление действия защиты в отчете об угрозе URL-адреса](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="80bce-170">Представление **данных по URL-адресу** щелкните представление действия защиты, отображает количество нажатий URL-адресов пользователями в организации и результаты щелчка:</span><span class="sxs-lookup"><span data-stu-id="80bce-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="80bce-171">**Разрешено:** пользователю было разрешено перемещаться по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="80bce-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="80bce-172">**Заблокировано.** Пользователю было заблокировано перемещение по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="80bce-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="80bce-173">**Заблокировано и щелкнуло.** Пользователь решил продолжить навигацию по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="80bce-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="80bce-174">**Щелкнув во время сканирования:** пользователь щелкнул по ссылке до завершения сканирования.</span><span class="sxs-lookup"><span data-stu-id="80bce-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="80bce-175">Щелчком мыши указывается, что пользователь щелкнул по странице блокировки на вредоносный веб-сайт (администраторы могут отключить щелчок в Сейф ссылки).</span><span class="sxs-lookup"><span data-stu-id="80bce-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="80bce-176">При **нажатии фильтров** можно изменить отчет и таблицу сведений, выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="80bce-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="80bce-177">**Дата (UTC)**: **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="80bce-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="80bce-178">**Обнаружение:**</span><span class="sxs-lookup"><span data-stu-id="80bce-178">**Detection**:</span></span>
  - <span data-ttu-id="80bce-179">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="80bce-179">**Allowed**</span></span>
  - <span data-ttu-id="80bce-180">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="80bce-180">**Blocked**</span></span>
  - <span data-ttu-id="80bce-181">**Заблокировано и щелкнуть**</span><span class="sxs-lookup"><span data-stu-id="80bce-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="80bce-182">**Щелкнув во время сканирования**</span><span class="sxs-lookup"><span data-stu-id="80bce-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="80bce-183">**Домены:** URL-домены, указанные в результатах отчета.</span><span class="sxs-lookup"><span data-stu-id="80bce-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="80bce-184">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="80bce-184">**Recipients**</span></span>

<span data-ttu-id="80bce-185">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="80bce-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="80bce-186">В таблице сведений ниже диаграммы приведено следующее представление в режиме почти реального времени всех щелчков мыши, которые произошли в организации за последние 7 дней:</span><span class="sxs-lookup"><span data-stu-id="80bce-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="80bce-187">**Время щелчка**</span><span class="sxs-lookup"><span data-stu-id="80bce-187">**Click time**</span></span>
- <span data-ttu-id="80bce-188">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="80bce-188">**User**</span></span>
- <span data-ttu-id="80bce-189">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="80bce-189">**URL**</span></span>
- <span data-ttu-id="80bce-190">**Действие**</span><span class="sxs-lookup"><span data-stu-id="80bce-190">**Action**</span></span>
- <span data-ttu-id="80bce-191">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="80bce-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="80bce-192">Просмотр данных по URL-адресу по приложению</span><span class="sxs-lookup"><span data-stu-id="80bce-192">View data by URL click by application</span></span>

![URL-адрес щелкните по представлению приложения в отчете об угрозе URL-адреса](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="80bce-194">Просмотр **данных по URL-адресу** по представлению приложения показывает количество нажатий URL-адресов приложениями, Сейф ссылками:</span><span class="sxs-lookup"><span data-stu-id="80bce-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="80bce-195">**Клиент электронной почты**</span><span class="sxs-lookup"><span data-stu-id="80bce-195">**Email client**</span></span>
- <span data-ttu-id="80bce-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="80bce-196">**PowerPoint**</span></span>
- <span data-ttu-id="80bce-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="80bce-197">**Word**</span></span>
- <span data-ttu-id="80bce-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="80bce-198">**Excel**</span></span>
- <span data-ttu-id="80bce-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="80bce-199">**OneNote**</span></span>
- <span data-ttu-id="80bce-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="80bce-200">**Visio**</span></span>
- <span data-ttu-id="80bce-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="80bce-201">**Teams**</span></span>
- <span data-ttu-id="80bce-202">**Другие**</span><span class="sxs-lookup"><span data-stu-id="80bce-202">**Others**</span></span>

<span data-ttu-id="80bce-203">При **нажатии фильтров** можно изменить отчет и таблицу сведений, выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="80bce-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="80bce-204">**Дата (UTC)**: **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="80bce-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="80bce-205">**Обнаружение.** Доступные приложения из диаграммы.</span><span class="sxs-lookup"><span data-stu-id="80bce-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="80bce-206">**Домены:** URL-домены, указанные в результатах отчета.</span><span class="sxs-lookup"><span data-stu-id="80bce-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="80bce-207">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="80bce-207">**Recipients**</span></span>

<span data-ttu-id="80bce-208">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="80bce-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="80bce-209">В таблице сведений ниже диаграммы приведено следующее представление в режиме почти реального времени всех щелчков мыши, которые произошли в организации за последние 7 дней:</span><span class="sxs-lookup"><span data-stu-id="80bce-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="80bce-210">**Время щелчка**</span><span class="sxs-lookup"><span data-stu-id="80bce-210">**Click time**</span></span>
- <span data-ttu-id="80bce-211">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="80bce-211">**User**</span></span>
- <span data-ttu-id="80bce-212">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="80bce-212">**URL**</span></span>
- <span data-ttu-id="80bce-213">**Действие**</span><span class="sxs-lookup"><span data-stu-id="80bce-213">**Action**</span></span>
- <span data-ttu-id="80bce-214">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="80bce-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="80bce-215">Дополнительные отчеты для просмотра</span><span class="sxs-lookup"><span data-stu-id="80bce-215">Additional reports to view</span></span>

<span data-ttu-id="80bce-216">Помимо отчетов, описанных в этой статье, доступны еще несколько отчетов, описанных в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="80bce-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="80bce-217">Отчет</span><span class="sxs-lookup"><span data-stu-id="80bce-217">Report</span></span>|<span data-ttu-id="80bce-218">Тема</span><span class="sxs-lookup"><span data-stu-id="80bce-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="80bce-219">**Explorer** (Microsoft Defender для Office 365 Plan 2) или обнаружения в режиме реального времени **(Microsoft** Defender для Office 365 Plan 1)</span><span class="sxs-lookup"><span data-stu-id="80bce-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="80bce-220">Обозреватель угроз (и обнаружение в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="80bce-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="80bce-221">**Отчеты о безопасности** электронной почты, такие как отчеты о главных отправителей и получателях, почтовый отчет Spoof и отчет о обнаружениях нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="80bce-221">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="80bce-222">Просмотр отчетов о безопасности электронной почты на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="80bce-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="80bce-223">**Отчеты о потоке** почты, такие как отчет о перенаправе, отчет о состоянии почтового потока и отчет о главных отправителей и получателях.</span><span class="sxs-lookup"><span data-stu-id="80bce-223">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="80bce-224">Отчеты о потоке почты в новом центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="80bce-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|<span data-ttu-id="80bce-225">**Трассировка URL Сейф ссылки** (только PowerShell).</span><span class="sxs-lookup"><span data-stu-id="80bce-225">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="80bce-226">На выходе этого комлета показаны результаты действий Сейф ссылки за последние семь дней.</span><span class="sxs-lookup"><span data-stu-id="80bce-226">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="80bce-227">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="80bce-227">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="80bce-228">**Результаты трафика почты для EOP** и Microsoft Defender для Office 365 (только PowerShell).</span><span class="sxs-lookup"><span data-stu-id="80bce-228">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="80bce-229">Выход этого комлета содержит сведения о домене, дате, типе события, направлении, действии и графе сообщений.</span><span class="sxs-lookup"><span data-stu-id="80bce-229">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="80bce-230">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="80bce-230">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="80bce-231">**Отчеты о подробностях почты** для EOP и Defender для Office 365 обнаружения (только PowerShell).</span><span class="sxs-lookup"><span data-stu-id="80bce-231">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="80bce-232">Выход этого комлета содержит сведения о вредоносных файлах или URL-адресах, попытках фишинга, обезличив себя и других потенциальных угрозах в электронной почте или файлах.</span><span class="sxs-lookup"><span data-stu-id="80bce-232">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="80bce-233">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="80bce-233">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="80bce-234">Какие разрешения необходимы для просмотра отчетов Defender для Office 365?</span><span class="sxs-lookup"><span data-stu-id="80bce-234">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="80bce-235">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей на Microsoft 365 Defender портале:</span><span class="sxs-lookup"><span data-stu-id="80bce-235">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="80bce-236">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="80bce-236">**Organization Management**</span></span>
- <span data-ttu-id="80bce-237">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="80bce-237">**Security Administrator**</span></span>
- <span data-ttu-id="80bce-238">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="80bce-238">**Security Reader**</span></span>
- <span data-ttu-id="80bce-239">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="80bce-239">**Global Reader**</span></span>

<span data-ttu-id="80bce-240">Дополнительные сведения см. [на портале Permissions in the Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="80bce-240">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="80bce-241">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в Центр администрирования Microsoft 365 дает пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80bce-241">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="80bce-242">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="80bce-242">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="80bce-243">Что делать, если отчеты не отображают данные?</span><span class="sxs-lookup"><span data-stu-id="80bce-243">What if the reports aren't showing data?</span></span>

<span data-ttu-id="80bce-244">Если в отчете Defender не Office 365 данные, убедитесь, что политики настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="80bce-244">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="80bce-245">Ваша организация должна [иметь Сейф ссылки](set-up-safe-links-policies.md) и политики Сейф вложения, определенные для того, чтобы для defender Office 365 была установлена защита. [](set-up-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="80bce-245">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="80bce-246">Также [см. защиту от нежелательной почты и](anti-spam-and-anti-malware-protection.md)защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="80bce-246">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="80bce-247">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="80bce-247">Related topics</span></span>

[<span data-ttu-id="80bce-248">Интеллектуальные отчеты и сведения на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="80bce-248">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="80bce-249">Разрешения на роль (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="80bce-249">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
