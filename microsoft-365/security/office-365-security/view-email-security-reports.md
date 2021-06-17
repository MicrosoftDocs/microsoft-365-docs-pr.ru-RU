---
title: Просмотр отчетов о безопасности электронной почты на портале Microsoft 365 Defender
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Узнайте, как найти и использовать отчеты о безопасности электронной почты для организации. Отчеты о безопасности электронной почты доступны на портале Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985307"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="d8935-104">Просмотр отчетов о безопасности электронной почты на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8935-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d8935-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d8935-105">**Applies to**</span></span>
- [<span data-ttu-id="d8935-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d8935-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d8935-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="d8935-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d8935-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8935-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d8935-109">На портале Microsoft 365 Defender доступны различные отчеты, которые помогут вам увидеть, как функции безопасности электронной почты, такие как средства защиты от нежелательной почты, защиты от вредоносных программ и шифрования в <https://security.microsoft.com> Microsoft 365, защищают вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="d8935-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="d8935-110">Если у вас есть необходимые [разрешения,](#what-permissions-are-needed-to-view-these-reports)вы можете просмотреть эти отчеты  на портале Защитник Microsoft 365, переехав в отчеты электронной почты & совместной & отчеты о совместной работе \>  \> .</span><span class="sxs-lookup"><span data-stu-id="d8935-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-111">Чтобы перейти непосредственно на **страницу отчетов & электронной почты,** откройте <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="d8935-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Страница & отчетов о совместной работе на портале Microsoft 365 Defender](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="d8935-113">Некоторые отчеты на странице отчетов **о совместной &** требуют Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8935-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="d8935-114">Сведения об этих отчетах см. в отчетах [View Defender for Office 365 на портале Microsoft 365 Defender.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="d8935-115">Отчеты, связанные с потоком почты, теперь находятся в центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="d8935-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="d8935-116">Дополнительные сведения об этих отчетах см. в отчете о потоке [почты в новом центре администрирования Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="d8935-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="d8935-117">Отчет о скомпрометировании пользователей</span><span class="sxs-lookup"><span data-stu-id="d8935-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="d8935-118">Этот отчет доступен в организациях Microsoft 365 с почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d8935-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="d8935-119">Он не доступен в автономных организациях Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d8935-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="d8935-120">В **отчете о** скомпрометировании пользователей  показано  количество учетных записей пользователей, отмеченных как подозрительные или ограниченные в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="d8935-121">Учетные записи в любом из этих штатов являются проблемными или даже скомпрометированными.</span><span class="sxs-lookup"><span data-stu-id="d8935-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="d8935-122">При частом использовании вы можете использовать отчет для задания пиков и даже тенденций в подозрительных или ограниченных учетных записях.</span><span class="sxs-lookup"><span data-stu-id="d8935-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="d8935-123">Дополнительные сведения о скомпрометированных пользователях см. в [сообщении Responding to a compromised email account.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Скомпрометированная виджет пользователей на странице отчетов & электронной почты](../../media/compromised-users-report-widget.png)

<span data-ttu-id="d8935-125">В сводном представлении показаны данные за последние 90 дней, а в представлении подробно показаны данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="d8935-126">Чтобы просмотреть отчет на портале Защитник Microsoft  365, перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="d8935-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-127">На **скомпрометированную пользователей,** нажмите **просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="d8935-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="d8935-128">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="d8935-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="d8935-129">После нажатия кнопки **Просмотр** сведений можно отфильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="d8935-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="d8935-130">**Дата (UTC)**: **Дата начала и** дата **окончания**.</span><span class="sxs-lookup"><span data-stu-id="d8935-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="d8935-131">**Действие:**</span><span class="sxs-lookup"><span data-stu-id="d8935-131">**Activity**:</span></span>
  - <span data-ttu-id="d8935-132">**Подозрительный.** Учетная запись пользователя отправила подозрительные сообщения электронной почты и может быть ограничена отправкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d8935-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="d8935-133">**Ограничение.** Учетная запись пользователя была ограничена отправкой электронной почты из-за весьма подозрительных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d8935-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="d8935-134">Когда вы закончите фильтрацию, нажмите кнопку **Применить** или **Отменить**.</span><span class="sxs-lookup"><span data-stu-id="d8935-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![Представление отчета в отчете о скомпрометированных пользователях](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="d8935-136">В таблице ниже графика приведены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="d8935-137">**Время создания**</span><span class="sxs-lookup"><span data-stu-id="d8935-137">**Creation time**</span></span>
- <span data-ttu-id="d8935-138">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="d8935-138">**User ID**</span></span>
- <span data-ttu-id="d8935-139">**Действие**</span><span class="sxs-lookup"><span data-stu-id="d8935-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="d8935-140">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="d8935-140">Exchange transport rule report</span></span>

<span data-ttu-id="d8935-141">В **отчете о** правилах транспорта Exchange показано влияние правил потока почты (также известных как правила транспорта) на входящие и исходяющие сообщения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d8935-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="d8935-142">Чтобы просмотреть отчет на портале Защитник Microsoft  365, перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="d8935-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-143">В **правиле транспорта Exchange** нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="d8935-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="d8935-144">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="d8935-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Виджет правила транспорта Exchange на странице отчетов & электронной почты](../../media/transport-rule-report-widget.png)

<span data-ttu-id="d8935-146">После щелчка **"Просмотр сведений"** доступны следующие диаграммы и данные:</span><span class="sxs-lookup"><span data-stu-id="d8935-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="d8935-147">**Просмотр данных по правилам транспорта Exchange** \> **Разбивка диаграмм по направлению.**  На этой  диаграмме показано количество входящие и исходящие сообщения, на которые повлияли правила потока почты.</span><span class="sxs-lookup"><span data-stu-id="d8935-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="d8935-148">**Просмотр данных по правилам транспорта Exchange** \> **Разбивка диаграммы** по строгости. На этой диаграмме показано количество сообщений с высокой степенью тяжести, средней серьезности и **низкой** серьезности.</span><span class="sxs-lookup"><span data-stu-id="d8935-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="d8935-149">Вы установите уровень серьезности в качестве действия в правиле **(Аудит** этого правила с уровнем серьезности или _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="d8935-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="d8935-150">Дополнительные сведения см. в сообщении о действиях правила [потока почты в Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="d8935-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="d8935-151">**Просмотр данных по правилам транспорта DLP Exchange** \> **Разбивка диаграммы** по направлению  . На  этой диаграмме показано количество входящие и исходящие сообщения, которые были затронуты правилами предотвращения потери данных (DLP) потока почты.</span><span class="sxs-lookup"><span data-stu-id="d8935-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="d8935-152">**Просмотр данных по правилам транспорта DLP Exchange** \> **Разбивка диаграммы** по строгости. В этом представлении показано  количество сообщений высокой степени **тяжести,** средней степени тяжести и низкой степени тяжести, которые были затронуты правилами потока почты DLP.</span><span class="sxs-lookup"><span data-stu-id="d8935-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="d8935-153">Для **просмотра данных по выборам правил** транспорта Exchange в таблице сведений ниже показано следующее:</span><span class="sxs-lookup"><span data-stu-id="d8935-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="d8935-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-154">**Date**</span></span>
- <span data-ttu-id="d8935-155">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="d8935-155">**Transport rule**</span></span>
- <span data-ttu-id="d8935-156">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-156">**Subject**</span></span>
- <span data-ttu-id="d8935-157">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="d8935-157">**Sender address**</span></span>
- <span data-ttu-id="d8935-158">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="d8935-158">**Recipient address**</span></span>
- <span data-ttu-id="d8935-159">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="d8935-159">**Severity**</span></span>
- <span data-ttu-id="d8935-160">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-160">**Direction**</span></span>

<span data-ttu-id="d8935-161">Для **просмотра данных по выборам** правил транспорта DLP Exchange в таблице сведений ниже показано следующее:</span><span class="sxs-lookup"><span data-stu-id="d8935-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="d8935-162">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-162">**Date**</span></span>
- <span data-ttu-id="d8935-163">**Политика DLP**</span><span class="sxs-lookup"><span data-stu-id="d8935-163">**DLP policy**</span></span>
- <span data-ttu-id="d8935-164">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="d8935-164">**Transport rule**</span></span>
- <span data-ttu-id="d8935-165">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-165">**Subject**</span></span>
- <span data-ttu-id="d8935-166">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="d8935-166">**Sender address**</span></span>
- <span data-ttu-id="d8935-167">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="d8935-167">**Recipient address**</span></span>
- <span data-ttu-id="d8935-168">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="d8935-168">**Severity**</span></span>
- <span data-ttu-id="d8935-169">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-169">**Direction**</span></span>

<span data-ttu-id="d8935-170">Вы можете фильтровать диаграмму и таблицу сведений, щелкнув **Фильтр** и выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="d8935-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="d8935-171">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-172">**Направление:** **исходящие и** **входящие**</span><span class="sxs-lookup"><span data-stu-id="d8935-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="d8935-173">**Серьезность:** **высокая серьезность,** **средняя серьезность** и **низкая серьезность**</span><span class="sxs-lookup"><span data-stu-id="d8935-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Представление отчета в отчете о правилах транспорта Exchange](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="d8935-175">Отчет о состоянии почтового потока</span><span class="sxs-lookup"><span data-stu-id="d8935-175">Mailflow status report</span></span>

<span data-ttu-id="d8935-176">Отчет **о** состоянии почтового потока — это интеллектуальный отчет, в нем показаны сведения о входящих и исходяющих сообщениях электронной почты, обнаружения нежелательной почты, вредоносных программ, электронной почты, идентифицированной как "хорошая", а также сведения о разрешенной или заблокированной электронной почте на краю.</span><span class="sxs-lookup"><span data-stu-id="d8935-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="d8935-177">Это единственный отчет, содержащий сведения о защите края, и показывает, сколько сообщений электронной почты блокируется до того, как они будут допущены в службу для оценки в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d8935-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d8935-178">Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="d8935-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="d8935-179">Чтобы просмотреть отчет на портале Защитник Microsoft  365, перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="d8935-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-180">В **сводке состояния mailflow** щелкните **Сведения о просмотре.**</span><span class="sxs-lookup"><span data-stu-id="d8935-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="d8935-181">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="d8935-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Виджет сводки состояния почтового потока на странице Отчеты & сообщения электронной почты](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="d8935-183">Введите представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="d8935-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="d8935-184">При открывании отчета вкладка **Type** выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8935-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="d8935-185">По умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="d8935-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d8935-186">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="d8935-187">**Направление почты:**</span><span class="sxs-lookup"><span data-stu-id="d8935-187">**Mail direction**:</span></span>
  - <span data-ttu-id="d8935-188">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="d8935-188">**Inbound**</span></span>
  - <span data-ttu-id="d8935-189">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="d8935-189">**Outbound**</span></span>
  - <span data-ttu-id="d8935-190">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="d8935-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="d8935-191">отправитель abc@domain.com получателям xyz@domain.com (засчитываются  отдельно от входящие и **исходящие)**</span><span class="sxs-lookup"><span data-stu-id="d8935-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="d8935-192">**Тип:**</span><span class="sxs-lookup"><span data-stu-id="d8935-192">**Type**:</span></span>
  - <span data-ttu-id="d8935-193">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="d8935-193">**Good mail**</span></span>
  - <span data-ttu-id="d8935-194">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="d8935-194">**Malware**</span></span>
  - <span data-ttu-id="d8935-195">**Спам**</span><span class="sxs-lookup"><span data-stu-id="d8935-195">**Spam**</span></span>
  - <span data-ttu-id="d8935-196">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="d8935-196">**Edge protection**</span></span>
  - <span data-ttu-id="d8935-197">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="d8935-197">**Rule messages**</span></span>
  - <span data-ttu-id="d8935-198">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="d8935-198">**Phishing email**</span></span>
- <span data-ttu-id="d8935-199">**Домен**: **Все**</span><span class="sxs-lookup"><span data-stu-id="d8935-199">**Domain**: **All**</span></span>

<span data-ttu-id="d8935-200">Диаграмма организована **значениями Type.**</span><span class="sxs-lookup"><span data-stu-id="d8935-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="d8935-201">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d8935-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="d8935-202">В таблице данных содержатся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-202">The data table contains the following information:</span></span>

- <span data-ttu-id="d8935-203">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-203">**Direction**</span></span>
- <span data-ttu-id="d8935-204">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d8935-204">**Type**</span></span>
- <span data-ttu-id="d8935-205">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="d8935-205">**24 hours**</span></span>
- <span data-ttu-id="d8935-206">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="d8935-206">**3 days**</span></span>
- <span data-ttu-id="d8935-207">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="d8935-207">**7 days**</span></span>
- <span data-ttu-id="d8935-208">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="d8935-208">**15 days**</span></span>
- <span data-ttu-id="d8935-209">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="d8935-209">**30 days**</span></span>

<span data-ttu-id="d8935-210">Если вы **нажмете Выберите категорию для получения** дополнительных сведений, вы можете выбрать из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d8935-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="d8935-211">**Фишинговое письмо.** Этот выбор принимает вас к отчету о [состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="d8935-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="d8935-212">**Вредоносные программы в электронной** почте: этот выбор принимает вас к отчету о [состоянии защиты от угрозы](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="d8935-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="d8935-213">**Обнаружение нежелательной почты.** Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="d8935-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="d8935-214">**Edge заблокирован нежелательной почты:** этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="d8935-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="d8935-215">Экспорт из представления Type</span><span class="sxs-lookup"><span data-stu-id="d8935-215">Export from Type view</span></span>

<span data-ttu-id="d8935-216">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="d8935-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="d8935-217">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="d8935-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="d8935-218">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="d8935-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d8935-219">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="d8935-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Введите представление в отчете о состоянии mailflow](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="d8935-221">Представление направления для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="d8935-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="d8935-222">Если щелкнуть **вкладку Direction,** используются те же фильтры по умолчанию из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="d8935-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="d8935-223">Диаграмма организована **значениями Direction.**</span><span class="sxs-lookup"><span data-stu-id="d8935-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="d8935-224">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d8935-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="d8935-225">Используются те же фильтры из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="d8935-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="d8935-226">Таблица данных содержит те же сведения из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="d8935-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="d8935-227">Выбор **категории для получения дополнительных** сведений о выборах и поведении такой же, как представление **Type.**</span><span class="sxs-lookup"><span data-stu-id="d8935-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="d8935-228">Экспорт из представления Direction</span><span class="sxs-lookup"><span data-stu-id="d8935-228">Export from Direction view</span></span>

<span data-ttu-id="d8935-229">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="d8935-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="d8935-230">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="d8935-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="d8935-231">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="d8935-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d8935-232">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="d8935-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление направления в отчете о состоянии mailflow](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="d8935-234">Представление воронки для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="d8935-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="d8935-235">В **представлении Воронка** показано, как функции защиты от угроз электронной почты Майкрософт фильтруют входящие и исходяющие сообщения электронной почты в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d8935-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="d8935-236">В нем представлены сведения об общем числе сообщений электронной почты, а также о том, как настроенные функции защиты от угроз, включая защиту края, антивирусные программы, защиту от фишинга, защиту от нежелательной почты и защиту от спуфинга, влияют на этот счет.</span><span class="sxs-lookup"><span data-stu-id="d8935-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="d8935-237">Если щелкнуть вкладку **Воронка,** это представление по умолчанию содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="d8935-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d8935-238">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="d8935-239">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="d8935-239">**Direction**:</span></span>

  - <span data-ttu-id="d8935-240">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="d8935-240">**Inbound**</span></span>
  - <span data-ttu-id="d8935-241">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="d8935-241">**Outbound**</span></span>
  - <span data-ttu-id="d8935-242">**Intra-org.** Это количество для сообщений, отправленных в клиенте; то есть отправитель отправляет abc@domain.com получателям xyz@domain.com (засчитываются отдельно от входящие и исходящие).</span><span class="sxs-lookup"><span data-stu-id="d8935-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="d8935-243">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="d8935-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="d8935-244">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="d8935-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="d8935-245">На этой диаграмме показана графа электронной почты, организованного по:</span><span class="sxs-lookup"><span data-stu-id="d8935-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="d8935-246">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-246">**Total email**</span></span>
- <span data-ttu-id="d8935-247">**Электронная почта после защиты края**</span><span class="sxs-lookup"><span data-stu-id="d8935-247">**Email after edge protection**</span></span>
- <span data-ttu-id="d8935-248">**Электронная почта после правила транспорта** (правило потока почты)</span><span class="sxs-lookup"><span data-stu-id="d8935-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="d8935-249">**Электронная почта после вредоносных программ, репутации файлов, блока типа файла**</span><span class="sxs-lookup"><span data-stu-id="d8935-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="d8935-250">**Электронная почта после защиты от фишинга, репутации URL-адресов, обезличения бренда и подмены**</span><span class="sxs-lookup"><span data-stu-id="d8935-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="d8935-251">**Электронная почта после фильтрации массовой почты после нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="d8935-252">**Электронная почта после обезличения пользователя и домена**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-253">**Электронная почта после детонации файла и URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-254">**Электронная почта, обнаруженная как доброкачественная после защиты после доставки (защита времени щелчка URL-адреса)**</span><span class="sxs-lookup"><span data-stu-id="d8935-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="d8935-255"><sup>\*</sup>Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="d8935-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="d8935-256">Чтобы просмотреть сообщение электронной почты, фильтруемой EOP или Defender для Office 365, щелкните значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d8935-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="d8935-257">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="d8935-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="d8935-258">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-258">**Date**</span></span>
- <span data-ttu-id="d8935-259">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-259">**Total email**</span></span>
- <span data-ttu-id="d8935-260">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="d8935-260">**Edge protection**</span></span>
- <span data-ttu-id="d8935-261">**Anti-malware, file reputation, file type block:**</span><span class="sxs-lookup"><span data-stu-id="d8935-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="d8935-262">**Репутация файла:** сообщения фильтруются из-за идентификации присоединенного файла другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d8935-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="d8935-263">**Блок типа файла.** Сообщения фильтруются из-за типа вредоносного файла, идентифицированного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="d8935-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="d8935-264">**Защита от фишинга, репутация URL-адреса, вымысление бренда, защита от подмены:**</span><span class="sxs-lookup"><span data-stu-id="d8935-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="d8935-265">**Репутация URL-адреса.** Сообщения фильтруются из-за идентификации URL-адреса другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d8935-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="d8935-266">**Вымысление** бренда: сообщения фильтруются из-за сообщения, исходящем от известных отправителей бренда, вымыкающих себя.</span><span class="sxs-lookup"><span data-stu-id="d8935-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="d8935-267">**Anti-spoof**: Сообщения фильтруются из-за сообщения, пытающихся подменить домен, к который принадлежит получатель, или домена, который не принадлежит отправителю сообщения.</span><span class="sxs-lookup"><span data-stu-id="d8935-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="d8935-268">**Фильтрация массовой почты** для борьбы со спамом:</span><span class="sxs-lookup"><span data-stu-id="d8935-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="d8935-269">**Массовая фильтрация** почты: сообщения фильтруются на основе порогового значения уровня жалобы (BCL) в политике борьбы со спамом.</span><span class="sxs-lookup"><span data-stu-id="d8935-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="d8935-270">**Вымысление** пользователя и домена (Defender для Office 365) :</span><span class="sxs-lookup"><span data-stu-id="d8935-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="d8935-271">Вымысление пользователя. Сообщения фильтруются из-за попытки выдать себя за пользователя (отправитель сообщений), определенного в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="d8935-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="d8935-272">**Обезличение** домена. Сообщения фильтруются из-за попытки выдать себя за домен, определенный в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="d8935-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="d8935-273">**Детонация файлов и URL-адресов (Defender для Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="d8935-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="d8935-274">**Детонация файлов:** сообщения, фильтруемые политикой Сейф вложений.</span><span class="sxs-lookup"><span data-stu-id="d8935-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="d8935-275">**Детонация URL-адреса.** Сообщение фильтруется политикой Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="d8935-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="d8935-276">Защита после доставки и **ZAP (ATP) или ZAP (EOP)**: автоматическая очистка нулевого часа (ZAP) для вредоносных программ, нежелательной почты и фишинга.</span><span class="sxs-lookup"><span data-stu-id="d8935-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="d8935-277">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d8935-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="d8935-278">Экспорт из представления Воронка</span><span class="sxs-lookup"><span data-stu-id="d8935-278">Export from Funnel view</span></span>

<span data-ttu-id="d8935-279">После нажатия **"Экспорт** в **параметрах"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d8935-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="d8935-280">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="d8935-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="d8935-281">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="d8935-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="d8935-282">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="d8935-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="d8935-283">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="d8935-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="d8935-284">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="d8935-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d8935-285">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="d8935-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление воронки в отчете о состоянии mailflow](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="d8935-287">Техническое представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="d8935-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="d8935-288">Представление **Tech аналогично** представлению **Воронка,** предоставляя более подробные сведения о настроенных средствах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="d8935-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="d8935-289">На диаграмме можно увидеть, как классифицируются сообщения на различных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="d8935-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="d8935-290">Если вы щелкните вкладку **Tech View,** по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="d8935-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d8935-291">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="d8935-292">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="d8935-292">**Direction**:</span></span>

  - <span data-ttu-id="d8935-293">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="d8935-293">**Inbound**</span></span>
  - <span data-ttu-id="d8935-294">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="d8935-294">**Outbound**</span></span>
  - <span data-ttu-id="d8935-295">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="d8935-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="d8935-296">отправитель abc@domain.com отправляет получателю xyz@domain.com (рассчитывается отдельно от входящие и исходящие)</span><span class="sxs-lookup"><span data-stu-id="d8935-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="d8935-297">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="d8935-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="d8935-298">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="d8935-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="d8935-299">На этой диаграмме показаны сообщения, организованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="d8935-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="d8935-300">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-300">**Total email**</span></span>
- <span data-ttu-id="d8935-301">**Edge allow** and **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="d8935-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="d8935-302">**Правила транспорта позволяют и** **правила транспорта фильтруются** (правила потока почты)</span><span class="sxs-lookup"><span data-stu-id="d8935-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="d8935-303">**Не вредоносные** программы, **Сейф обнаружения** вложений <sup>\*</sup> и обнаружения **вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="d8935-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="d8935-304">**Не фишинг,** **отказ DMARC,** **обнаружение** обезличения, <sup>\*</sup> обнаружение **Spoof** и **обнаружение фишинга**</span><span class="sxs-lookup"><span data-stu-id="d8935-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="d8935-305">**Отсутствие обнаружения с детонацией URL-адреса** и **обнаружением детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-306">**Не нежелательной почты** и  **нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="d8935-307">**Обнаружение ссылок,** **Сейф** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="d8935-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="d8935-308"><sup>\*</sup>Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="d8935-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="d8935-309">Когда вы наведите курсор над категорией на диаграмме, вы увидите количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="d8935-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="d8935-310">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="d8935-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="d8935-311">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-311">**Date**</span></span>
- <span data-ttu-id="d8935-312">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-312">**Total email**</span></span>
- <span data-ttu-id="d8935-313">**Отфильтрованный край**</span><span class="sxs-lookup"><span data-stu-id="d8935-313">**Edge filtered**</span></span>
- <span data-ttu-id="d8935-314">**Сообщения правил:** сообщения фильтруются из-за правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="d8935-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="d8935-315">**Антивирусный двигатель**, **Сейф вложения** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="d8935-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="d8935-316">**DMARC, impersonation** <sup>\*</sup> , **spoof**, **phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="d8935-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="d8935-317">**DMARC:** Сообщения фильтруются из-за отказа сообщения проверки подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="d8935-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="d8935-318">**Обнаружение детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-319">**Фильтрация от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="d8935-320">**ZaP удален**</span><span class="sxs-lookup"><span data-stu-id="d8935-320">**ZAP removed**</span></span>
- <span data-ttu-id="d8935-321">**Обнаружение по Сейф ссылки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="d8935-322"><sup>\*</sup>Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="d8935-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="d8935-323">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d8935-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="d8935-324">Экспорт с точки зрения технологий</span><span class="sxs-lookup"><span data-stu-id="d8935-324">Export from Tech view</span></span>

<span data-ttu-id="d8935-325">При **нажатии на экспорт** **можно** выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d8935-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="d8935-326">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="d8935-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="d8935-327">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="d8935-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="d8935-328">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="d8935-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="d8935-329">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="d8935-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="d8935-330">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="d8935-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d8935-331">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="d8935-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление технологий в отчете о состоянии mailflow](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="d8935-333">Отчет об обнаружении вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="d8935-333">Malware detections report</span></span>

<span data-ttu-id="d8935-334">В **отчете об** обнаружении вредоносных программ показаны сведения об обнаружении вредоносных программ в входящих и исходяющих сообщениях электронной почты (вредоносные программы, обнаруженные Exchange Online Protection или EOP).</span><span class="sxs-lookup"><span data-stu-id="d8935-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="d8935-335">Дополнительные сведения о защите от вредоносных программ в EOP см. в программе Защита от вредоносных [программ в EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="d8935-336">Совокупный фильтр представления позволяет в течение 90 дней, в то время как фильтр таблицы сведений разрешает только 10 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="d8935-337">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="d8935-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-338">О **вредоносных программах, обнаруженных в электронной почте,** **щелкните Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="d8935-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="d8935-339">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="d8935-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Обнаружение вредоносных программ в виджете электронной почты на & отчетов о совместной работе](../../media/malware-detections-widget.png)

<span data-ttu-id="d8935-341">После нажатия **кнопки Просмотр** сведений можно отфильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав:</span><span class="sxs-lookup"><span data-stu-id="d8935-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="d8935-342">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-343">**Направление:** **входящие и** **исходящие**</span><span class="sxs-lookup"><span data-stu-id="d8935-343">**Direction**: **Inbound** and **Outbound**</span></span>

![Представление отчета в обнаружении вредоносных программ в отчете электронной почты](../../media/malware-detections-report-view.png)

<span data-ttu-id="d8935-345">В таблице сведений под графиком можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="d8935-346">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-346">**Date**</span></span>
- <span data-ttu-id="d8935-347">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="d8935-347">**Sender address**</span></span>
- <span data-ttu-id="d8935-348">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="d8935-348">**Recipient address**</span></span>
- <span data-ttu-id="d8935-349">**ID сообщения.** Доступно в **поле заглавной области Message-ID** в загонах сообщений и должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="d8935-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="d8935-350">Например, значение `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="d8935-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="d8935-351">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-351">**Subject**</span></span>
- <span data-ttu-id="d8935-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="d8935-352">**Filename**</span></span>
- <span data-ttu-id="d8935-353">**Имя вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="d8935-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="d8935-354">Отчет о задержке почты</span><span class="sxs-lookup"><span data-stu-id="d8935-354">Mail latency report</span></span>

<span data-ttu-id="d8935-355">Отчет **о задержке** почты в Defender for Office 365 содержит сведения о задержке доставки почты и детонации в организации.</span><span class="sxs-lookup"><span data-stu-id="d8935-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="d8935-356">Дополнительные сведения см. в [отчете о задержке почты.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="d8935-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="d8935-357">Отчет об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="d8935-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="d8935-358">Отчет **об обнаружении нежелательной** почты пройдет 30 июня 2021 г.</span><span class="sxs-lookup"><span data-stu-id="d8935-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="d8935-359">Такая же информация доступна в отчете о состоянии [защиты от угроз.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="d8935-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="d8935-360">Отчет об обнаружении подмены</span><span class="sxs-lookup"><span data-stu-id="d8935-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="d8935-361">Улучшенный отчет об обнаружении Spoof, описанный в этой статье, находится в предварительной версии, подлежит изменениям и доступен не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="d8935-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="d8935-362">Более старая версия отчета показывает только хорошую почту **и** **уловлено как spam.**</span><span class="sxs-lookup"><span data-stu-id="d8935-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="d8935-363">В **отчете о обнаружениях Spoof** показаны сведения о сообщениях, которые были заблокированы или разрешены из-за подмены.</span><span class="sxs-lookup"><span data-stu-id="d8935-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="d8935-364">Дополнительные сведения о подмене см. в этой информации в [EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="d8935-365">Совокупное представление отчета позволяет в течение 45 дней фильтрации, в то время как представление детализации позволяет фильтровать только десять <sup>\*</sup> дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="d8935-366"><sup>\*</sup> В конце концов, вы сможете использовать до 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="d8935-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="d8935-367">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="d8935-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-368">При **обнаружении Spoof** нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="d8935-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="d8935-369">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="d8935-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Виджет обнаружения подмены на странице отчетов & электронной почты](../../media/spoof-detections-widget.png)

<span data-ttu-id="d8935-371">При наведении в течение дня (точки данных) на диаграмме можно увидеть, сколько поддельных сообщений было обнаружено и почему.</span><span class="sxs-lookup"><span data-stu-id="d8935-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="d8935-372">После нажатия **кнопки Просмотр** сведений можно отфильтровать диаграмму и таблицу сведений, щелкнув **Фильтр** и выбрав одно или несколько следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d8935-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="d8935-373">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-374">**Результат:**</span><span class="sxs-lookup"><span data-stu-id="d8935-374">**Result**:</span></span>
  - <span data-ttu-id="d8935-375">**Pass**</span><span class="sxs-lookup"><span data-stu-id="d8935-375">**Pass**</span></span>
  - <span data-ttu-id="d8935-376">**Fail**</span><span class="sxs-lookup"><span data-stu-id="d8935-376">**Fail**</span></span>
  - <span data-ttu-id="d8935-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="d8935-377">**SoftPass**</span></span>
  - <span data-ttu-id="d8935-378">**Нет**</span><span class="sxs-lookup"><span data-stu-id="d8935-378">**None**</span></span>
  - <span data-ttu-id="d8935-379">**Other**</span><span class="sxs-lookup"><span data-stu-id="d8935-379">**Other**</span></span>
- <span data-ttu-id="d8935-380">**Тип Spoof:** **внутренний и** **внешний**</span><span class="sxs-lookup"><span data-stu-id="d8935-380">**Spoof type**: **Internal** and **External**</span></span>

![Страница отчета о подмене почты на Microsoft 365 Defender портале](../../media/spoof-detections-report-page.png)

<span data-ttu-id="d8935-382">В таблице ниже графика приведены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="d8935-383">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-383">**Date**</span></span>
- <span data-ttu-id="d8935-384">**Подмена пользователя**</span><span class="sxs-lookup"><span data-stu-id="d8935-384">**Spoofed user**</span></span>
- <span data-ttu-id="d8935-385">**Отправка инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="d8935-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="d8935-386">**Тип Spoof**</span><span class="sxs-lookup"><span data-stu-id="d8935-386">**Spoof type**</span></span>
- <span data-ttu-id="d8935-387">**Результат**</span><span class="sxs-lookup"><span data-stu-id="d8935-387">**Result**</span></span>
- <span data-ttu-id="d8935-388">**Код результатов**</span><span class="sxs-lookup"><span data-stu-id="d8935-388">**Result code**</span></span>
- <span data-ttu-id="d8935-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="d8935-389">**SPF**</span></span>
- <span data-ttu-id="d8935-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="d8935-390">**DKIM**</span></span>
- <span data-ttu-id="d8935-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="d8935-391">**DMARC**</span></span>
- <span data-ttu-id="d8935-392">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="d8935-392">**Message count**</span></span>

<span data-ttu-id="d8935-393">Дополнительные сведения о сводных кодах результатов проверки подлинности см. в материале [Anti-spam message headers in Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="d8935-394">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="d8935-394">Threat protection status report</span></span>

<span data-ttu-id="d8935-395">Отчет **о состоянии защиты от** угроз доступен в EOP и Defender для Office 365; однако отчеты содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="d8935-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="d8935-396">Например, клиенты EOP могут просматривать сведения о вредоносных программах, обнаруженных в электронной почте, но не сведения о вредоносных файлах, обнаруженных Сейф вложениями для [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)и Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="d8935-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d8935-397">В отчете приводится количество сообщений электронной почты со вредоносным контентом, например файлов или [веб-адресов](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)(URL-адресов), которые были заблокированы с помощью двигателя защиты от вредоносных программ, автоматической очистки нулевого часа [(ZAP)](zero-hour-auto-purge.md)и функций Defender для Office 365, таких как [Сейф Links,](safe-links.md) [Сейф Attachments](safe-attachments.md), и функции защиты от фишинга в политиках защиты от фишинга .</span><span class="sxs-lookup"><span data-stu-id="d8935-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="d8935-398">Эти сведения можно использовать для определения тенденций или определения необходимости корректировки политик организации.</span><span class="sxs-lookup"><span data-stu-id="d8935-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="d8935-399">**Примечание.** Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="d8935-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="d8935-400">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="d8935-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-401">В **статусе защиты от угроз** нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="d8935-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="d8935-402">Чтобы перейти непосредственно к отчету, откройте один из следующих URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="d8935-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="d8935-403">Defender для Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="d8935-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="d8935-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="d8935-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Виджет состояния защиты от угрозы на странице отчетов & электронной почты](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="d8935-406">По умолчанию после нажатия сведений **Просмотреть** на диаграмме показаны данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="d8935-407">При **нажатии фильтра** можно выбрать диапазон дат в 90 дней (пробная подписка может быть ограничена 30 днями).</span><span class="sxs-lookup"><span data-stu-id="d8935-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="d8935-408">Таблица сведений позволяет фильтровать в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d8935-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="d8935-409">Доступные представления описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d8935-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="d8935-410">Просмотр данных по обзору</span><span class="sxs-lookup"><span data-stu-id="d8935-410">View data by Overview</span></span>

![Обзор представления в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="d8935-412">В **представлении View data by Overview** на диаграмме показаны следующие сведения об обнаружении:</span><span class="sxs-lookup"><span data-stu-id="d8935-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="d8935-413">**Вредоносные программы электронной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-413">**Email malware**</span></span>
- <span data-ttu-id="d8935-414">**Фишинг электронной почты**</span><span class="sxs-lookup"><span data-stu-id="d8935-414">**Email phish**</span></span>
- <span data-ttu-id="d8935-415">**Вредоносные программы контента**</span><span class="sxs-lookup"><span data-stu-id="d8935-415">**Content malware**</span></span>

<span data-ttu-id="d8935-416">Таблица сведений недоступна ниже диаграммы.</span><span class="sxs-lookup"><span data-stu-id="d8935-416">No details table is available below the chart.</span></span>

<span data-ttu-id="d8935-417">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d8935-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="d8935-418">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-419">**Обнаружение:** **вредоносные программы** по **электронной почте, фишинг электронной почты** или **вредоносные программы по контенту**</span><span class="sxs-lookup"><span data-stu-id="d8935-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="d8935-420">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="d8935-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="d8935-421">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="d8935-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d8935-422">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="d8935-423">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-423">**Direction**</span></span>
- <span data-ttu-id="d8935-424">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8935-424">**Domain**</span></span>
- <span data-ttu-id="d8935-425">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="d8935-425">**Policy type**</span></span>

<span data-ttu-id="d8935-426">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="d8935-427">Просмотр данных с помощью \> фишинга электронной почты и разбивки диаграмм с помощью технологии обнаружения</span><span class="sxs-lookup"><span data-stu-id="d8935-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Представление технологии обнаружения фишинговой электронной почты в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="d8935-429">В **представлении данных по фишингу электронной \> почты** и разбивке диаграмм по представлению **технологии** обнаружения на диаграмме показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="d8935-430">**Вредоносная репутация** URL-адреса: вредоносная репутация URL-адреса, созданная в Defender для Office 365 в других Microsoft 365 <sup>\*</sup> клиентах.</span><span class="sxs-lookup"><span data-stu-id="d8935-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="d8935-431">**Расширенный фильтр:** фишинговые сигналы на основе машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="d8935-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="d8935-432">**Общий фильтр:** фишинговые сигналы, основанные на правилах аналитика.</span><span class="sxs-lookup"><span data-stu-id="d8935-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="d8935-433">**Spoof intra-org.** Отправитель пытается подменить домен получателя.</span><span class="sxs-lookup"><span data-stu-id="d8935-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="d8935-434">**Внешний домен Spoof.** Отправитель пытается подменить другой домен.</span><span class="sxs-lookup"><span data-stu-id="d8935-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="d8935-435">**Spoof DMARC:** Сбой проверки подлинности DMARC в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="d8935-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="d8935-436">**Бренд Impersonation**: Impersonation известных брендов на основе отправителей.</span><span class="sxs-lookup"><span data-stu-id="d8935-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="d8935-437">**Обнаружение с помощью смешанного анализа**</span><span class="sxs-lookup"><span data-stu-id="d8935-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="d8935-438">**Репутация файла**</span><span class="sxs-lookup"><span data-stu-id="d8935-438">**File reputation**</span></span>
- <span data-ttu-id="d8935-439">**Сопоставление отпечатков**</span><span class="sxs-lookup"><span data-stu-id="d8935-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="d8935-440">**Репутация детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-441">**Детонация URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-442">**Пользователь impersonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-443">**Домен impersonation** <sup>\*</sup> : Impersonation доменов, которые клиент владеет или определяет.</span><span class="sxs-lookup"><span data-stu-id="d8935-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="d8935-444">**Вымысление** сведении почтовых ящиков: обезличение пользователей, определенных администратором или <sup>\*</sup> выучатся с помощью разведки почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="d8935-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="d8935-445">**Детонация файлов**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-446">**Кампания**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="d8935-447">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="d8935-448">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-448">**Date**</span></span>
- <span data-ttu-id="d8935-449">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-449">**Subject**</span></span>
- <span data-ttu-id="d8935-450">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-450">**Sender**</span></span>
- <span data-ttu-id="d8935-451">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-451">**Recipients**</span></span>
- <span data-ttu-id="d8935-452">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="d8935-452">**Detected by**</span></span>
- <span data-ttu-id="d8935-453">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="d8935-453">**Delivery Status**</span></span>
- <span data-ttu-id="d8935-454">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="d8935-454">**Source of Compromise**</span></span>
- <span data-ttu-id="d8935-455">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d8935-455">**Tags**</span></span>

<span data-ttu-id="d8935-456">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d8935-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="d8935-457">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-458">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="d8935-458">**Detection**</span></span>
- <span data-ttu-id="d8935-459">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="d8935-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="d8935-460">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-460">**Direction**</span></span>
- <span data-ttu-id="d8935-461">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="d8935-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d8935-462">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="d8935-463">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8935-463">**Domain**</span></span>
- <span data-ttu-id="d8935-464">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="d8935-464">**Policy type**</span></span>
- <span data-ttu-id="d8935-465">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="d8935-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="d8935-466">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-466">**Recipients**</span></span>

<span data-ttu-id="d8935-467">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="d8935-468">Просмотр данных по вредоносным программам электронной почты \> и разбивке диаграмм с помощью технологии обнаружения</span><span class="sxs-lookup"><span data-stu-id="d8935-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Представление технологии обнаружения вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="d8935-470">В **представлении данных \> по вредоносным программам электронной** почты и разбивке диаграмм по представлению **технологии** обнаружения на диаграмме показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="d8935-471">**Детонация файлов:** <sup>\*</sup> обнаружение Сейф вложения.</span><span class="sxs-lookup"><span data-stu-id="d8935-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="d8935-472">**Репутация детонации файлов:** <sup>\*</sup> вся репутация вредоносных файлов, созданных Defender для Office 365 детонации.</span><span class="sxs-lookup"><span data-stu-id="d8935-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="d8935-473">**Репутация файла**</span><span class="sxs-lookup"><span data-stu-id="d8935-473">**File reputation**</span></span>
- <span data-ttu-id="d8935-474">**Движок для борьбы с вредоносными** <sup>\*</sup> программами. Обнаружение с антивирусных двигателей.</span><span class="sxs-lookup"><span data-stu-id="d8935-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="d8935-475">Блок типа файлов политики по борьбе с вредоносными программами. Это сообщения электронной почты, отфильтрованные **из-за** типа вредоносного файла, выявленного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="d8935-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="d8935-476">**Репутация вредоносного URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="d8935-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="d8935-477">**Отключение URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="d8935-477">**URL detonation**</span></span>
- <span data-ttu-id="d8935-478">**Репутация отключения URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="d8935-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="d8935-479">**Кампания**</span><span class="sxs-lookup"><span data-stu-id="d8935-479">**Campaign**</span></span>

<span data-ttu-id="d8935-480">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="d8935-481">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-481">**Date**</span></span>
- <span data-ttu-id="d8935-482">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-482">**Subject**</span></span>
- <span data-ttu-id="d8935-483">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-483">**Sender**</span></span>
- <span data-ttu-id="d8935-484">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-484">**Recipients**</span></span>
- <span data-ttu-id="d8935-485">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="d8935-485">**Detected by**</span></span>
- <span data-ttu-id="d8935-486">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="d8935-486">**Delivery Status**</span></span>
- <span data-ttu-id="d8935-487">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="d8935-487">**Source of Compromise**</span></span>
- <span data-ttu-id="d8935-488">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d8935-488">**Tags**</span></span>

<span data-ttu-id="d8935-489">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d8935-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="d8935-490">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-491">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="d8935-491">**Detection**</span></span>
- <span data-ttu-id="d8935-492">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="d8935-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="d8935-493">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-493">**Direction**</span></span>
- <span data-ttu-id="d8935-494">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="d8935-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d8935-495">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="d8935-496">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8935-496">**Domain**</span></span>
- <span data-ttu-id="d8935-497">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="d8935-497">**Policy type**</span></span>
- <span data-ttu-id="d8935-498">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="d8935-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="d8935-499">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-499">**Recipients**</span></span>

<span data-ttu-id="d8935-500">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="d8935-501">Разбивка диаграмм по типу политики и просмотру данных по фишингу электронной почты или \> просмотру данных по вредоносным программам электронной \> почты</span><span class="sxs-lookup"><span data-stu-id="d8935-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Вид типа политики для фишинга электронной почты или вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="d8935-503">В **разбивке диаграмм** по типу политики и просмотру данных по фишингу электронной почты или просмотру данных по представлениям вредоносных программ по электронной почте в диаграммах показаны следующие сведения: **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="d8935-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="d8935-504">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="d8935-504">**Anti-malware**</span></span>
- <span data-ttu-id="d8935-505">**Сейф Вложения**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d8935-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="d8935-506">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="d8935-506">**Anti-phish**</span></span>
- <span data-ttu-id="d8935-507">**Противодействие нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="d8935-507">**Anti-spam**</span></span>
- <span data-ttu-id="d8935-508">**Правило потока почты** (также известное как правило транспорта)</span><span class="sxs-lookup"><span data-stu-id="d8935-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="d8935-509">**Другие**</span><span class="sxs-lookup"><span data-stu-id="d8935-509">**Others**</span></span>

<span data-ttu-id="d8935-510">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="d8935-511">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-511">**Date**</span></span>
- <span data-ttu-id="d8935-512">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-512">**Subject**</span></span>
- <span data-ttu-id="d8935-513">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-513">**Sender**</span></span>
- <span data-ttu-id="d8935-514">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-514">**Recipients**</span></span>
- <span data-ttu-id="d8935-515">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="d8935-515">**Detected by**</span></span>
- <span data-ttu-id="d8935-516">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="d8935-516">**Delivery Status**</span></span>
- <span data-ttu-id="d8935-517">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="d8935-517">**Source of Compromise**</span></span>
- <span data-ttu-id="d8935-518">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d8935-518">**Tags**</span></span>

<span data-ttu-id="d8935-519">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d8935-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="d8935-520">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-521">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="d8935-521">**Detection**</span></span>
- <span data-ttu-id="d8935-522">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="d8935-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="d8935-523">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-523">**Direction**</span></span>
- <span data-ttu-id="d8935-524">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="d8935-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d8935-525">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="d8935-526">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8935-526">**Domain**</span></span>
- <span data-ttu-id="d8935-527">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="d8935-527">**Policy type**</span></span>
- <span data-ttu-id="d8935-528">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="d8935-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="d8935-529">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-529">**Recipients**</span></span>

<span data-ttu-id="d8935-530">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="d8935-531">Разбивка диаграмм по статусу доставки и просмотру данных по фишингу электронной почты или \> просмотру данных вредоносными программами электронной \> почты</span><span class="sxs-lookup"><span data-stu-id="d8935-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Представление состояния доставки для фишинговой электронной почты и вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="d8935-533">В **разбивке диаграмм** по статусу доставки и просмотру данных по фишингу электронной почты или просмотру данных по представлениям вредоносных программ по электронной почте в диаграммах показаны следующие сведения: **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="d8935-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="d8935-534">**Хост-почтовый ящик: Почтовый ящик**</span><span class="sxs-lookup"><span data-stu-id="d8935-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="d8935-535">**Хост-почтовый ящик: нежелательной**</span><span class="sxs-lookup"><span data-stu-id="d8935-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="d8935-536">**Хост-почтовый ящик: настраиваемая папка**</span><span class="sxs-lookup"><span data-stu-id="d8935-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="d8935-537">**Хост-почтовый ящик: удаленные элементы**</span><span class="sxs-lookup"><span data-stu-id="d8935-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="d8935-538">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="d8935-538">**Forwarded**</span></span>
- <span data-ttu-id="d8935-539">**Локального сервера: Доставлено**</span><span class="sxs-lookup"><span data-stu-id="d8935-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="d8935-540">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="d8935-540">**Quarantine**</span></span>
- <span data-ttu-id="d8935-541">**Сбой доставки**</span><span class="sxs-lookup"><span data-stu-id="d8935-541">**Delivery failed**</span></span>
- <span data-ttu-id="d8935-542">**Сброс**</span><span class="sxs-lookup"><span data-stu-id="d8935-542">**Dropped**</span></span>

<span data-ttu-id="d8935-543">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="d8935-544">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-544">**Date**</span></span>
- <span data-ttu-id="d8935-545">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-545">**Subject**</span></span>
- <span data-ttu-id="d8935-546">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-546">**Sender**</span></span>
- <span data-ttu-id="d8935-547">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-547">**Recipients**</span></span>
- <span data-ttu-id="d8935-548">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="d8935-548">**Detected by**</span></span>
- <span data-ttu-id="d8935-549">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="d8935-549">**Delivery Status**</span></span>
- <span data-ttu-id="d8935-550">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="d8935-550">**Source of Compromise**</span></span>
- <span data-ttu-id="d8935-551">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d8935-551">**Tags**</span></span>

<span data-ttu-id="d8935-552">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d8935-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="d8935-553">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-554">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="d8935-554">**Detection**</span></span>
- <span data-ttu-id="d8935-555">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="d8935-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="d8935-556">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-556">**Direction**</span></span>
- <span data-ttu-id="d8935-557">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="d8935-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d8935-558">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="d8935-559">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8935-559">**Domain**</span></span>
- <span data-ttu-id="d8935-560">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="d8935-560">**Policy type**</span></span>
- <span data-ttu-id="d8935-561">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="d8935-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="d8935-562">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-562">**Recipients**</span></span>

<span data-ttu-id="d8935-563">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="d8935-564">Просмотр данных по вредоносным \> программам контента</span><span class="sxs-lookup"><span data-stu-id="d8935-564">View data by Content \> Malware</span></span>

![Просмотр вредоносных программ контента в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="d8935-566">В **представлении View data by Content \> Malware** на диаграмме Для Microsoft Defender для Office 365 организаций показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="d8935-567">**Антивирусный** двигатель: вредоносные файлы, обнаруженные в Sharepoint, OneDrive и Microsoft Teams с помощью встроенного обнаружения вирусов в [Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="d8935-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="d8935-568">**Детонация** файлов: вредоносные файлы, обнаруженные Сейф вложениями для [SharePoint, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d8935-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d8935-569">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="d8935-570">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-571">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="d8935-571">**Location**</span></span>
- <span data-ttu-id="d8935-572">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="d8935-572">**Detected by**</span></span>
- <span data-ttu-id="d8935-573">**Имя вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="d8935-573">**Malware name**</span></span>

<span data-ttu-id="d8935-574">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d8935-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="d8935-575">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-576">**Обнаружение:** **детонация антивирусных программ** **или детонация файлов**</span><span class="sxs-lookup"><span data-stu-id="d8935-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="d8935-577">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="d8935-578">Просмотр данных путем переопределения системы</span><span class="sxs-lookup"><span data-stu-id="d8935-578">View data by System override</span></span>

![Представление переопределения сообщений в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="d8935-580">В **представлении Просмотр данных по представлению Переопределения** системы в диаграмме показаны следующие сведения о причинах переопределения:</span><span class="sxs-lookup"><span data-stu-id="d8935-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="d8935-581">**Локальное пропустить**</span><span class="sxs-lookup"><span data-stu-id="d8935-581">**On-premises skip**</span></span>
- <span data-ttu-id="d8935-582">**РАЗРЕШЕНИЕ IP**</span><span class="sxs-lookup"><span data-stu-id="d8935-582">**IP allow**</span></span>
- <span data-ttu-id="d8935-583">**Exchange транспорта почты** (правило потока почты)</span><span class="sxs-lookup"><span data-stu-id="d8935-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="d8935-584">**Организация разрешила отправителям**</span><span class="sxs-lookup"><span data-stu-id="d8935-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="d8935-585">**Разрешенные домены организации**</span><span class="sxs-lookup"><span data-stu-id="d8935-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="d8935-586">**ZAP не включен**</span><span class="sxs-lookup"><span data-stu-id="d8935-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="d8935-587">**Папка нежелательной почты не включена**</span><span class="sxs-lookup"><span data-stu-id="d8935-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="d8935-588">**Отправитель Сейф пользователя**</span><span class="sxs-lookup"><span data-stu-id="d8935-588">**User Safe Sender**</span></span>
- <span data-ttu-id="d8935-589">**Домен пользователя Сейф**</span><span class="sxs-lookup"><span data-stu-id="d8935-589">**User Safe Domain**</span></span>

<span data-ttu-id="d8935-590">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="d8935-591">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8935-591">**Date**</span></span>
- <span data-ttu-id="d8935-592">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d8935-592">**Subject**</span></span>
- <span data-ttu-id="d8935-593">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-593">**Sender**</span></span>
- <span data-ttu-id="d8935-594">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-594">**Recipients**</span></span>
- <span data-ttu-id="d8935-595">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="d8935-595">**Detected by**</span></span>
- <span data-ttu-id="d8935-596">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="d8935-596">**Delivery Status**</span></span>
- <span data-ttu-id="d8935-597">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="d8935-597">**Source of Compromise**</span></span>
- <span data-ttu-id="d8935-598">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d8935-598">**Tags**</span></span>

<span data-ttu-id="d8935-599">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="d8935-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="d8935-600">**Дата:** **дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="d8935-601">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="d8935-601">**Detection**</span></span>
- <span data-ttu-id="d8935-602">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="d8935-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="d8935-603">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d8935-603">**Direction**</span></span>
- <span data-ttu-id="d8935-604">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="d8935-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d8935-605">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="d8935-606">**Домен**</span><span class="sxs-lookup"><span data-stu-id="d8935-606">**Domain**</span></span>
- <span data-ttu-id="d8935-607">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="d8935-607">**Policy type**</span></span>
- <span data-ttu-id="d8935-608">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="d8935-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="d8935-609">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="d8935-609">**Recipients**</span></span>

<span data-ttu-id="d8935-610">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="d8935-611"><sup>\*</sup>Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="d8935-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="d8935-612">Топ отчета о вредоносных программах</span><span class="sxs-lookup"><span data-stu-id="d8935-612">Top malware report</span></span>

<span data-ttu-id="d8935-613">В **топовом отчете** о вредоносных программах показаны различные виды вредоносных программ, обнаруженных защитой от вредоносных программ [в EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="d8935-614">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="d8935-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d8935-615">В **верхней части вредоносных** программ **щелкните Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="d8935-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="d8935-616">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="d8935-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Виджет топ вредоносных программ на странице отчетов & электронной почты](../../media/top-malware-report-widget.png)

<span data-ttu-id="d8935-618">При наведении на клин в диаграмме пирога можно увидеть имя типа вредоносных программ и количество сообщений, обнаруженных как наличие этого вредоносного ПО.</span><span class="sxs-lookup"><span data-stu-id="d8935-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="d8935-619">После нажатия **сведений Просмотра** на странице отчетов отображается более крупная версия диаграммы пирога. В таблице сведений ниже диаграммы показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="d8935-620">**Топ вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="d8935-620">**Top malware**</span></span>
- <span data-ttu-id="d8935-621">**Count**</span><span class="sxs-lookup"><span data-stu-id="d8935-621">**Count**</span></span>

<span data-ttu-id="d8935-622">При **нажатии фильтра** можно указать диапазон дат с **датой начала и** **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="d8935-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Представление отчета о вредоносных программах](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="d8935-624">Отчет об угрозе URL-адреса</span><span class="sxs-lookup"><span data-stu-id="d8935-624">URL threat protection report</span></span>

<span data-ttu-id="d8935-625">Отчет **об угрозе** URL-адресов доступен в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8935-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="d8935-626">Дополнительные сведения см. в [отчете об угрозе URL-адреса.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="d8935-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="d8935-627">Отчет о сообщениях пользователя</span><span class="sxs-lookup"><span data-stu-id="d8935-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8935-628">Чтобы отчет **о сообщениях** пользователя работал **правильно,** необходимо ввести журнал аудита для Microsoft 365 среды.</span><span class="sxs-lookup"><span data-stu-id="d8935-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="d8935-629">Обычно это делается тем, кто имеет роль журналов аудита, назначенную в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d8935-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="d8935-630">Дополнительные сведения см. в Microsoft 365 поиска журнала [аудита.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="d8935-631">Отчет **о** сообщениях пользователя показывает сведения о сообщениях электронной почты, которые пользователи сообщали как нежелательные, фишинговые попытки или хорошая почта с помощью надстройки Report [Message](enable-the-report-message-add-in.md) или надстройки [Report Phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="d8935-632">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & сообщений о совместной работе. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="d8935-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="d8935-633">В **сообщениях пользователя нажмите** кнопку Просмотр **сведений**.</span><span class="sxs-lookup"><span data-stu-id="d8935-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="d8935-634">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="d8935-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="d8935-635">Чтобы перейти [к представлениям администратора на портале Microsoft 365 Defender,](admin-submission.md)нажмите **кнопку Перейти к отправкам.**</span><span class="sxs-lookup"><span data-stu-id="d8935-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Виджет сообщений пользователей на странице отчетов о совместной & электронной почты](../../media/user-reported-messages-widget.png)

<span data-ttu-id="d8935-637">После нажатия кнопки **Просмотр** сведений можно отфильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="d8935-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="d8935-638">**Дата, о чем сообщалось:** **время начала и** **окончания**</span><span class="sxs-lookup"><span data-stu-id="d8935-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="d8935-639">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="d8935-639">**Reported by**</span></span>
- <span data-ttu-id="d8935-640">**Тема письма**</span><span class="sxs-lookup"><span data-stu-id="d8935-640">**Email subject**</span></span>
- <span data-ttu-id="d8935-641">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="d8935-641">**Message reported ID**</span></span>
- <span data-ttu-id="d8935-642">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="d8935-642">**Network Message ID**</span></span>
- <span data-ttu-id="d8935-643">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-643">**Sender**</span></span>
- <span data-ttu-id="d8935-644">**Сообщаемая причина**</span><span class="sxs-lookup"><span data-stu-id="d8935-644">**Reported reason**</span></span>
  - <span data-ttu-id="d8935-645">**Не нежелательно**</span><span class="sxs-lookup"><span data-stu-id="d8935-645">**Not junk**</span></span>
  - <span data-ttu-id="d8935-646">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="d8935-646">**Phish**</span></span>
  - <span data-ttu-id="d8935-647">**Спам**</span><span class="sxs-lookup"><span data-stu-id="d8935-647">**Spam**</span></span>
- <span data-ttu-id="d8935-648">**Фишинговое моделирование:** **да** или **нет**</span><span class="sxs-lookup"><span data-stu-id="d8935-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="d8935-649">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="d8935-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="d8935-650">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="d8935-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="d8935-651">**Нет**</span><span class="sxs-lookup"><span data-stu-id="d8935-651">**None**</span></span>
- <span data-ttu-id="d8935-652">**Причина**</span><span class="sxs-lookup"><span data-stu-id="d8935-652">**Reason**</span></span>
- <span data-ttu-id="d8935-653">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-653">**Sender**</span></span>
- <span data-ttu-id="d8935-654">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="d8935-654">**Reported by**</span></span>
- <span data-ttu-id="d8935-655">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="d8935-655">**Rescan result**</span></span>
- <span data-ttu-id="d8935-656">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="d8935-656">**Phish simulation**</span></span>

![Отчет о сообщениях пользователя](../../media/user-reported-messages-report.png)

<span data-ttu-id="d8935-658">В таблице ниже графика приведены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d8935-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="d8935-659">**Тема письма**</span><span class="sxs-lookup"><span data-stu-id="d8935-659">**Email subject**</span></span>
- <span data-ttu-id="d8935-660">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="d8935-660">**Reported by**</span></span>
- <span data-ttu-id="d8935-661">**Дата сообщается**</span><span class="sxs-lookup"><span data-stu-id="d8935-661">**Date reported**</span></span>
- <span data-ttu-id="d8935-662">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d8935-662">**Sender**</span></span>
- <span data-ttu-id="d8935-663">**Сообщаемая причина**</span><span class="sxs-lookup"><span data-stu-id="d8935-663">**Reported reason**</span></span>
- <span data-ttu-id="d8935-664">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="d8935-664">**Rescan result**</span></span>
- <span data-ttu-id="d8935-665">**Tags**</span><span class="sxs-lookup"><span data-stu-id="d8935-665">**Tags**</span></span>

<span data-ttu-id="d8935-666">Чтобы отправить сообщение в Корпорацию Майкрософт для анализа, выберите запись сообщения из таблицы, щелкните Отправка в **Корпорацию Майкрософт** для анализа, а затем выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="d8935-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="d8935-667">**Отчет о чистоте**</span><span class="sxs-lookup"><span data-stu-id="d8935-667">**Report clean**</span></span>
- <span data-ttu-id="d8935-668">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="d8935-668">**Report phishing**</span></span>
- <span data-ttu-id="d8935-669">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="d8935-669">**Report malware**</span></span>
- <span data-ttu-id="d8935-670">**Сообщить о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="d8935-670">**Report spam**'</span></span>
- <span data-ttu-id="d8935-671">**Триггерное** расследование (Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="d8935-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="d8935-672">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="d8935-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="d8935-673">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей на Microsoft 365 Defender портале:</span><span class="sxs-lookup"><span data-stu-id="d8935-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="d8935-674">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="d8935-674">**Organization Management**</span></span>
- <span data-ttu-id="d8935-675">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="d8935-675">**Security Administrator**</span></span>
- <span data-ttu-id="d8935-676">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="d8935-676">**Security Reader**</span></span>
- <span data-ttu-id="d8935-677">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="d8935-677">**Global Reader**</span></span>

<span data-ttu-id="d8935-678">Дополнительные сведения см. [на портале Permissions in the Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="d8935-679">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в Центр администрирования Microsoft 365 дает пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8935-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d8935-680">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d8935-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="d8935-681">Что делать, если отчеты не отображают данные?</span><span class="sxs-lookup"><span data-stu-id="d8935-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="d8935-682">Если в отчетах нет данных, убедитесь, что политики настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="d8935-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="d8935-683">Дополнительные новости см. в [см. в руберсе Защита от угроз.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="d8935-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8935-684">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d8935-684">Related topics</span></span>

[<span data-ttu-id="d8935-685">Защита от нежелательной почты и вредоносных программ в EOP</span><span class="sxs-lookup"><span data-stu-id="d8935-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="d8935-686">Интеллектуальные отчеты и сведения на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="d8935-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="d8935-687">Просмотр отчетов о потоке почты на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="d8935-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="d8935-688">Просмотр отчетов для Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="d8935-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
