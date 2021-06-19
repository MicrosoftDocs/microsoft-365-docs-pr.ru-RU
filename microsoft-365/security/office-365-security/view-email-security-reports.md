---
title: Просмотр отчетов о безопасности электронной почты
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
description: Администраторы могут узнать, как находить и использовать отчеты о безопасности электронной почты, доступные на портале Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022932"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="93fae-103">Просмотр отчетов о безопасности электронной почты на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93fae-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="93fae-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="93fae-104">**Applies to**</span></span>
- [<span data-ttu-id="93fae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="93fae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="93fae-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="93fae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="93fae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93fae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="93fae-108">На портале Microsoft 365 Defender доступны различные отчеты, которые помогут вам увидеть, как функции безопасности электронной почты, такие как средства защиты от нежелательной почты, защиты от вредоносных программ и шифрования в <https://security.microsoft.com> Microsoft 365, защищают вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="93fae-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="93fae-109">Если у вас есть необходимые [разрешения,](#what-permissions-are-needed-to-view-these-reports)вы можете просмотреть эти отчеты  на портале Защитник Microsoft 365, переехав в отчеты электронной почты & совместной & отчеты о совместной работе \>  \> .</span><span class="sxs-lookup"><span data-stu-id="93fae-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-110">Чтобы перейти непосредственно на **страницу отчетов & электронной почты,** откройте <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="93fae-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Страница & отчетов о совместной работе на портале Microsoft 365 Defender](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="93fae-112">Некоторые отчеты на странице отчетов **о совместной &** требуют Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="93fae-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="93fae-113">Сведения об этих отчетах см. в отчетах [View Defender for Office 365 на портале Microsoft 365 Defender.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="93fae-114">Отчеты, связанные с потоком почты, теперь находятся в центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="93fae-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="93fae-115">Дополнительные сведения об этих отчетах см. в отчете о потоке [почты в новом центре администрирования Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="93fae-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="93fae-116">Отчет о скомпрометировании пользователей</span><span class="sxs-lookup"><span data-stu-id="93fae-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="93fae-117">Этот отчет доступен в организациях Microsoft 365 с почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93fae-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="93fae-118">Он не доступен в автономных организациях Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="93fae-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="93fae-119">В **отчете о** скомпрометировании пользователей  показано  количество учетных записей пользователей, отмеченных как подозрительные или ограниченные в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="93fae-120">Учетные записи в любом из этих штатов являются проблемными или даже скомпрометированными.</span><span class="sxs-lookup"><span data-stu-id="93fae-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="93fae-121">При частом использовании вы можете использовать отчет для задания пиков и даже тенденций в подозрительных или ограниченных учетных записях.</span><span class="sxs-lookup"><span data-stu-id="93fae-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="93fae-122">Дополнительные сведения о скомпрометированных пользователях см. в [сообщении Responding to a compromised email account.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Скомпрометированная виджет пользователей на странице отчетов & электронной почты](../../media/compromised-users-report-widget.png)

<span data-ttu-id="93fae-124">В сводном представлении показаны данные за последние 90 дней, а в представлении подробно показаны данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="93fae-125">Чтобы просмотреть отчет на портале Защитник Microsoft  365, перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-126">На странице **Отчеты & электронной** почты найдите скомпрометированную пользователей и нажмите  **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="93fae-127">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="93fae-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="93fae-128">На странице **"Скомпрометированная** страница пользователей" можно отфильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="93fae-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="93fae-129">**Дата (UTC)**: **Дата начала и** дата **окончания**.</span><span class="sxs-lookup"><span data-stu-id="93fae-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="93fae-130">**Действие:**</span><span class="sxs-lookup"><span data-stu-id="93fae-130">**Activity**:</span></span>
  - <span data-ttu-id="93fae-131">**Подозрительный.** Учетная запись пользователя отправила подозрительные сообщения электронной почты и может быть ограничена отправкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="93fae-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="93fae-132">**Ограничение.** Учетная запись пользователя была ограничена отправкой электронной почты из-за весьма подозрительных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="93fae-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="93fae-133">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Представление отчета в отчете о скомпрометированных пользователях](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="93fae-135">В таблице сведений под графиком можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="93fae-136">**Время создания**</span><span class="sxs-lookup"><span data-stu-id="93fae-136">**Creation time**</span></span>
- <span data-ttu-id="93fae-137">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="93fae-137">**User ID**</span></span>
- <span data-ttu-id="93fae-138">**Действие**</span><span class="sxs-lookup"><span data-stu-id="93fae-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="93fae-139">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="93fae-139">Exchange transport rule report</span></span>

<span data-ttu-id="93fae-140">В **отчете о** правилах транспорта Exchange показано влияние правил потока почты (также известных как правила транспорта) на входящие и исходяющие сообщения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="93fae-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="93fae-141">Чтобы просмотреть отчет на портале Защитник Microsoft  365, перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-142">На странице **Отчеты & сообщения** электронной почты найдите правило **транспорта Exchange** и нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="93fae-143">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="93fae-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Виджет правила транспорта Exchange на странице отчетов & электронной почты](../../media/transport-rule-report-widget.png)

<span data-ttu-id="93fae-145">На странице **отчета о правилах транспорта Exchange** доступные диаграммы и данные описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="93fae-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="93fae-146">Разбивка диаграмм по направлению</span><span class="sxs-lookup"><span data-stu-id="93fae-146">Chart breakdown by Direction</span></span>

![Представление направления для правил транспорта Exchange в отчете о правилах транспорта Exchange](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="93fae-148">Если выбрать **разбивку диаграммы по направлению,** доступны последующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="93fae-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="93fae-149">**Просмотр данных по правилам транспорта Exchange:**  количество входящие и исходящие сообщения, которые были затронуты правилами потока почты. </span><span class="sxs-lookup"><span data-stu-id="93fae-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="93fae-150">**Просмотр данных правил транспорта DLP Exchange:** количество  входящие и исходящие сообщения, которые были затронуты правилами предотвращения потери данных (DLP) потока почты. </span><span class="sxs-lookup"><span data-stu-id="93fae-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="93fae-151">Ниже приведены следующие сведения в таблице сведений под графиком:</span><span class="sxs-lookup"><span data-stu-id="93fae-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="93fae-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-152">**Date**</span></span>
- <span data-ttu-id="93fae-153">**Политика DLP** (Просмотр данных только по **правилам транспорта DLP Exchange)**</span><span class="sxs-lookup"><span data-stu-id="93fae-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="93fae-154">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="93fae-154">**Transport rule**</span></span>
- <span data-ttu-id="93fae-155">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-155">**Subject**</span></span>
- <span data-ttu-id="93fae-156">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="93fae-156">**Sender address**</span></span>
- <span data-ttu-id="93fae-157">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="93fae-157">**Recipient address**</span></span>
- <span data-ttu-id="93fae-158">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="93fae-158">**Severity**</span></span>
- <span data-ttu-id="93fae-159">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-159">**Direction**</span></span>

<span data-ttu-id="93fae-160">Вы можете фильтровать диаграмму и таблицу сведений, щелкнув **Фильтр** и выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="93fae-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="93fae-161">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-162">**Направление:** **исходящие и** **входящие**</span><span class="sxs-lookup"><span data-stu-id="93fae-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="93fae-163">**Серьезность:** **высокая серьезность,** **средняя серьезность** и **низкая серьезность**</span><span class="sxs-lookup"><span data-stu-id="93fae-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="93fae-164">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="93fae-165">Разбивка диаграммы по строгости</span><span class="sxs-lookup"><span data-stu-id="93fae-165">Chart breakdown by Severity</span></span>

![Представление строгости правил транспорта Exchange в отчете о правилах транспорта Exchange](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="93fae-167">Если выбрать **разбивку диаграммы по строгости,** доступны последующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="93fae-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="93fae-168">**Просмотр данных по правилам транспорта Exchange:** количество сообщений с высокой степенью серьезности, средней серьезности и **низкой** серьезности.</span><span class="sxs-lookup"><span data-stu-id="93fae-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="93fae-169">Вы установите уровень серьезности в качестве действия в правиле **(Аудит** этого правила с уровнем серьезности или _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="93fae-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="93fae-170">Дополнительные сведения см. в сообщении о действиях правила [потока почты в Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="93fae-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="93fae-171">Просмотр данных по правилам транспорта **DLP Exchange:** количество сообщений  высокой степени **тяжести,** средней серьезности и низкой степени тяжести, которые были затронуты правилами потока почты DLP.</span><span class="sxs-lookup"><span data-stu-id="93fae-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="93fae-172">Ниже приведены следующие сведения в таблице сведений под графиком:</span><span class="sxs-lookup"><span data-stu-id="93fae-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="93fae-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-173">**Date**</span></span>
- <span data-ttu-id="93fae-174">**Политика DLP** (Просмотр данных только по **правилам транспорта DLP Exchange)**</span><span class="sxs-lookup"><span data-stu-id="93fae-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="93fae-175">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="93fae-175">**Transport rule**</span></span>
- <span data-ttu-id="93fae-176">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-176">**Subject**</span></span>
- <span data-ttu-id="93fae-177">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="93fae-177">**Sender address**</span></span>
- <span data-ttu-id="93fae-178">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="93fae-178">**Recipient address**</span></span>
- <span data-ttu-id="93fae-179">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="93fae-179">**Severity**</span></span>
- <span data-ttu-id="93fae-180">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-180">**Direction**</span></span>

<span data-ttu-id="93fae-181">Вы можете фильтровать диаграмму и таблицу сведений, щелкнув **Фильтр** и выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="93fae-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="93fae-182">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-183">**Направление:** **исходящие и** **входящие**</span><span class="sxs-lookup"><span data-stu-id="93fae-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="93fae-184">**Серьезность:** **высокая серьезность,** **средняя серьезность** и **низкая серьезность**</span><span class="sxs-lookup"><span data-stu-id="93fae-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="93fae-185">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="93fae-186">Отчет о переадпорте</span><span class="sxs-lookup"><span data-stu-id="93fae-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="93fae-187">Отчет **о переадпорте** теперь доступен в EAC.</span><span class="sxs-lookup"><span data-stu-id="93fae-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="93fae-188">Дополнительные сведения см. в [отчете автопроизводить](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)сообщений в новом EAC.</span><span class="sxs-lookup"><span data-stu-id="93fae-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="93fae-189">Отчет о состоянии почтового потока</span><span class="sxs-lookup"><span data-stu-id="93fae-189">Mailflow status report</span></span>

<span data-ttu-id="93fae-190">Отчет **о** состоянии почтового потока — это интеллектуальный отчет, в нем показаны сведения о входящих и исходяющих сообщениях электронной почты, обнаружения нежелательной почты, вредоносных программ, электронной почты, идентифицированной как "хорошая", а также сведения о разрешенной или заблокированной электронной почте на краю.</span><span class="sxs-lookup"><span data-stu-id="93fae-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="93fae-191">Это единственный отчет, содержащий сведения о защите края, и показывает, сколько сообщений электронной почты блокируется до того, как они будут допущены в службу для оценки в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="93fae-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="93fae-192">Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="93fae-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="93fae-193">Чтобы просмотреть отчет на портале Защитник Microsoft  365, перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-194">На странице **отчеты &** электронной почты найдите сводку состояния **mailflow** и нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="93fae-195">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="93fae-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Виджет сводки состояния почтового потока на странице Отчеты & сообщения электронной почты](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="93fae-197">Введите представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="93fae-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="93fae-198">При открывании отчета вкладка **Type** выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93fae-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="93fae-199">По умолчанию это представление содержит диаграмму и таблицу сведений, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="93fae-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="93fae-200">**Дата (UTC)** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="93fae-201">**Направление почты:**</span><span class="sxs-lookup"><span data-stu-id="93fae-201">**Mail direction**:</span></span>
  - <span data-ttu-id="93fae-202">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="93fae-202">**Inbound**</span></span>
  - <span data-ttu-id="93fae-203">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="93fae-203">**Outbound**</span></span>
  - <span data-ttu-id="93fae-204">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="93fae-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="93fae-205">отправитель abc@domain.com получателям xyz@domain.com (засчитываются  отдельно от входящие и **исходящие)**</span><span class="sxs-lookup"><span data-stu-id="93fae-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="93fae-206">**Тип:**</span><span class="sxs-lookup"><span data-stu-id="93fae-206">**Type**:</span></span>
  - <span data-ttu-id="93fae-207">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="93fae-207">**Good mail**</span></span>
  - <span data-ttu-id="93fae-208">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="93fae-208">**Malware**</span></span>
  - <span data-ttu-id="93fae-209">**Спам**</span><span class="sxs-lookup"><span data-stu-id="93fae-209">**Spam**</span></span>
  - <span data-ttu-id="93fae-210">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="93fae-210">**Edge protection**</span></span>
  - <span data-ttu-id="93fae-211">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="93fae-211">**Rule messages**</span></span>
  - <span data-ttu-id="93fae-212">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="93fae-212">**Phishing email**</span></span>
- <span data-ttu-id="93fae-213">**Домен**: **Все**</span><span class="sxs-lookup"><span data-stu-id="93fae-213">**Domain**: **All**</span></span>

<span data-ttu-id="93fae-214">Диаграмма организована **значениями Type.**</span><span class="sxs-lookup"><span data-stu-id="93fae-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="93fae-215">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="93fae-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="93fae-216">Ниже приведены следующие сведения в таблице сведений под графиком:</span><span class="sxs-lookup"><span data-stu-id="93fae-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="93fae-217">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-217">**Direction**</span></span>
- <span data-ttu-id="93fae-218">**Тип**</span><span class="sxs-lookup"><span data-stu-id="93fae-218">**Type**</span></span>
- <span data-ttu-id="93fae-219">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="93fae-219">**24 hours**</span></span>
- <span data-ttu-id="93fae-220">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="93fae-220">**3 days**</span></span>
- <span data-ttu-id="93fae-221">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="93fae-221">**7 days**</span></span>
- <span data-ttu-id="93fae-222">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="93fae-222">**15 days**</span></span>
- <span data-ttu-id="93fae-223">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="93fae-223">**30 days**</span></span>

<span data-ttu-id="93fae-224">Если вы **нажмете Выберите категорию для получения** дополнительных сведений, вы можете выбрать из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="93fae-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="93fae-225">**Фишинговое письмо.** Этот выбор принимает вас к отчету о [состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="93fae-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="93fae-226">**Вредоносные программы в электронной** почте: этот выбор принимает вас к отчету о [состоянии защиты от угрозы](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="93fae-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="93fae-227">**Обнаружение нежелательной почты.** Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="93fae-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="93fae-228">**Edge заблокирован нежелательной почты:** этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="93fae-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="93fae-229">Экспорт из представления Type</span><span class="sxs-lookup"><span data-stu-id="93fae-229">Export from Type view</span></span>

<span data-ttu-id="93fae-230">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="93fae-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="93fae-231">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="93fae-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="93fae-232">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="93fae-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93fae-233">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="93fae-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Введите представление в отчете о состоянии mailflow](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="93fae-235">Представление направления для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="93fae-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="93fae-236">Если щелкнуть **вкладку Direction,** используются те же фильтры по умолчанию из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="93fae-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="93fae-237">Диаграмма организована **значениями Direction.**</span><span class="sxs-lookup"><span data-stu-id="93fae-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="93fae-238">Эти фильтры можно изменить, нажав **фильтр.**</span><span class="sxs-lookup"><span data-stu-id="93fae-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="93fae-239">Используются те же фильтры из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="93fae-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="93fae-240">В таблице сведений содержатся те же сведения из **представления Type.**</span><span class="sxs-lookup"><span data-stu-id="93fae-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="93fae-241">Выбор **категории для получения дополнительных** сведений о выборах и поведении такой же, как представление **Type.**</span><span class="sxs-lookup"><span data-stu-id="93fae-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="93fae-242">Экспорт из представления Direction</span><span class="sxs-lookup"><span data-stu-id="93fae-242">Export from Direction view</span></span>

<span data-ttu-id="93fae-243">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="93fae-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="93fae-244">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="93fae-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="93fae-245">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="93fae-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93fae-246">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="93fae-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление направления в отчете о состоянии mailflow](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="93fae-248">Представление воронки для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="93fae-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="93fae-249">В **представлении Воронка** показано, как функции защиты от угроз электронной почты Майкрософт фильтруют входящие и исходяющие сообщения электронной почты в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="93fae-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="93fae-250">В нем представлены сведения об общем числе сообщений электронной почты, а также о том, как настроенные функции защиты от угроз, включая защиту края, антивирусные программы, защиту от фишинга, защиту от нежелательной почты и защиту от спуфинга, влияют на этот счет.</span><span class="sxs-lookup"><span data-stu-id="93fae-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="93fae-251">Если щелкнуть вкладку **Воронка,** это представление по умолчанию содержит диаграмму и таблицу сведений, настроенных с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="93fae-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="93fae-252">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="93fae-253">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="93fae-253">**Direction**:</span></span>
  - <span data-ttu-id="93fae-254">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="93fae-254">**Inbound**</span></span>
  - <span data-ttu-id="93fae-255">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="93fae-255">**Outbound**</span></span>
  - <span data-ttu-id="93fae-256">**Intra-org.** Это количество для сообщений, отправленных в клиенте; то есть отправитель отправляет abc@domain.com получателям xyz@domain.com (засчитываются отдельно от входящие и исходящие).</span><span class="sxs-lookup"><span data-stu-id="93fae-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="93fae-257">Совокупное представление и представление таблицы сведений позволяет фильтровать в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="93fae-258">Эти фильтры можно изменить, нажав **фильтр.**</span><span class="sxs-lookup"><span data-stu-id="93fae-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="93fae-259">Используются те же фильтры из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="93fae-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="93fae-260">На этой диаграмме показана графа электронной почты, организованного по:</span><span class="sxs-lookup"><span data-stu-id="93fae-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="93fae-261">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-261">**Total email**</span></span>
- <span data-ttu-id="93fae-262">**Электронная почта после защиты края**</span><span class="sxs-lookup"><span data-stu-id="93fae-262">**Email after edge protection**</span></span>
- <span data-ttu-id="93fae-263">**Электронная почта после правила транспорта** (правило потока почты)</span><span class="sxs-lookup"><span data-stu-id="93fae-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="93fae-264">**Электронная почта после вредоносных программ, репутации файлов, блока типа файла**</span><span class="sxs-lookup"><span data-stu-id="93fae-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="93fae-265">**Электронная почта после защиты от фишинга, репутации URL-адресов, обезличения бренда и подмены**</span><span class="sxs-lookup"><span data-stu-id="93fae-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="93fae-266">**Электронная почта после фильтрации массовой почты после нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="93fae-267">**Электронная почта после обезличения пользователя и домена**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-268">**Электронная почта после детонации файла и URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-269">**Электронная почта, обнаруженная как доброкачественная после защиты после доставки (защита времени щелчка URL-адреса)**</span><span class="sxs-lookup"><span data-stu-id="93fae-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="93fae-270"><sup>\*</sup>Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="93fae-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="93fae-271">Чтобы просмотреть сообщение электронной почты, фильтруемой EOP или Defender для Office 365, щелкните значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="93fae-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="93fae-272">В таблице сведений содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="93fae-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="93fae-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-273">**Date**</span></span>
- <span data-ttu-id="93fae-274">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-274">**Total email**</span></span>
- <span data-ttu-id="93fae-275">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="93fae-275">**Edge protection**</span></span>
- <span data-ttu-id="93fae-276">**Anti-malware, file reputation, file type block:**</span><span class="sxs-lookup"><span data-stu-id="93fae-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="93fae-277">**Репутация файла:** сообщения фильтруются из-за идентификации присоединенного файла другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="93fae-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="93fae-278">**Блок типа файла.** Сообщения фильтруются из-за типа вредоносного файла, идентифицированного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="93fae-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="93fae-279">**Защита от фишинга, репутация URL-адреса, вымысление бренда, защита от подмены:**</span><span class="sxs-lookup"><span data-stu-id="93fae-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="93fae-280">**Репутация URL-адреса.** Сообщения фильтруются из-за идентификации URL-адреса другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="93fae-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="93fae-281">**Вымысление** бренда: сообщения фильтруются из-за сообщения, исходящем от известных отправителей бренда, вымыкающих себя.</span><span class="sxs-lookup"><span data-stu-id="93fae-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="93fae-282">**Anti-spoof**: Сообщения фильтруются из-за сообщения, пытающихся подменить домен, к который принадлежит получатель, или домена, который не принадлежит отправителю сообщения.</span><span class="sxs-lookup"><span data-stu-id="93fae-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="93fae-283">**Фильтрация массовой почты** для борьбы со спамом:</span><span class="sxs-lookup"><span data-stu-id="93fae-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="93fae-284">**Массовая фильтрация** почты: сообщения фильтруются на основе порогового значения уровня жалобы (BCL) в политике борьбы со спамом.</span><span class="sxs-lookup"><span data-stu-id="93fae-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="93fae-285">**Вымысление** пользователя и домена (Defender для Office 365) :</span><span class="sxs-lookup"><span data-stu-id="93fae-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="93fae-286">Вымысление пользователя. Сообщения фильтруются из-за попытки выдать себя за пользователя (отправитель сообщений), определенного в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="93fae-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="93fae-287">**Обезличение** домена. Сообщения фильтруются из-за попытки выдать себя за домен, определенный в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="93fae-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="93fae-288">**Детонация файлов и URL-адресов (Defender для Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="93fae-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="93fae-289">**Детонация файлов:** сообщения, фильтруемые политикой Сейф вложений.</span><span class="sxs-lookup"><span data-stu-id="93fae-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="93fae-290">**Детонация URL-адреса.** Сообщение фильтруется политикой Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="93fae-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="93fae-291">Защита после доставки и **ZAP (ATP) или ZAP (EOP)**: автоматическая очистка нулевого часа (ZAP) для вредоносных программ, нежелательной почты и фишинга.</span><span class="sxs-lookup"><span data-stu-id="93fae-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="93fae-292">Если вы выберите строку в таблице сведений, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="93fae-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="93fae-293">Экспорт из представления Воронка</span><span class="sxs-lookup"><span data-stu-id="93fae-293">Export from Funnel view</span></span>

<span data-ttu-id="93fae-294">После нажатия **"Экспорт** в **параметрах"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="93fae-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="93fae-295">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="93fae-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="93fae-296">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="93fae-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="93fae-297">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="93fae-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="93fae-298">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="93fae-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="93fae-299">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="93fae-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93fae-300">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="93fae-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление воронки в отчете о состоянии mailflow](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="93fae-302">Техническое представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="93fae-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="93fae-303">Представление **Tech аналогично** представлению **Воронка,** предоставляя более подробные сведения о настроенных средствах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="93fae-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="93fae-304">На диаграмме можно увидеть, как классифицируются сообщения на различных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="93fae-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="93fae-305">Если вы нажмете вкладку **"Просмотр** технологий", по умолчанию это представление содержит диаграмму и таблицу сведений, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="93fae-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="93fae-306">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="93fae-307">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="93fae-307">**Direction**:</span></span>
  - <span data-ttu-id="93fae-308">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="93fae-308">**Inbound**</span></span>
  - <span data-ttu-id="93fae-309">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="93fae-309">**Outbound**</span></span>
  - <span data-ttu-id="93fae-310">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="93fae-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="93fae-311">отправитель abc@domain.com отправляет получателю xyz@domain.com (рассчитывается отдельно от входящие и исходящие)</span><span class="sxs-lookup"><span data-stu-id="93fae-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="93fae-312">Совокупное представление и представление таблицы сведений позволяет фильтровать в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="93fae-313">Эти фильтры можно изменить, нажав **фильтр.**</span><span class="sxs-lookup"><span data-stu-id="93fae-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="93fae-314">Используются те же фильтры из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="93fae-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="93fae-315">На этой диаграмме показаны сообщения, организованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="93fae-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="93fae-316">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-316">**Total email**</span></span>
- <span data-ttu-id="93fae-317">**Edge allow** and **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="93fae-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="93fae-318">**Правила транспорта позволяют и** **правила транспорта фильтруются** (правила потока почты)</span><span class="sxs-lookup"><span data-stu-id="93fae-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="93fae-319">**Не вредоносные** программы, **Сейф обнаружения** вложений <sup>\*</sup> и обнаружения **вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="93fae-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="93fae-320">**Не фишинг,** **отказ DMARC,** **обнаружение** обезличения, <sup>\*</sup> обнаружение **Spoof** и **обнаружение фишинга**</span><span class="sxs-lookup"><span data-stu-id="93fae-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="93fae-321">**Отсутствие обнаружения с детонацией URL-адреса** и **обнаружением детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-322">**Не нежелательной почты** и  **нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="93fae-323">**Обнаружение ссылок,** **Сейф** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="93fae-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="93fae-324"><sup>\*</sup>Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="93fae-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="93fae-325">Когда вы наведите курсор над категорией на диаграмме, вы увидите количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="93fae-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="93fae-326">В таблице сведений содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="93fae-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="93fae-327">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="93fae-327">**Date (UTC)**</span></span>
- <span data-ttu-id="93fae-328">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-328">**Total email**</span></span>
- <span data-ttu-id="93fae-329">**Отфильтрованный край**</span><span class="sxs-lookup"><span data-stu-id="93fae-329">**Edge filtered**</span></span>
- <span data-ttu-id="93fae-330">**Сообщения правил:** сообщения фильтруются из-за правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="93fae-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="93fae-331">**Антивирусный двигатель**, **Сейф вложения** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="93fae-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="93fae-332">**DMARC, impersonation** <sup>\*</sup> , **spoof**, **phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="93fae-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="93fae-333">**DMARC:** Сообщения фильтруются из-за отказа сообщения проверки подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="93fae-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="93fae-334">**Обнаружение детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-335">**Фильтрация от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="93fae-336">**ZaP удален**</span><span class="sxs-lookup"><span data-stu-id="93fae-336">**ZAP removed**</span></span>
- <span data-ttu-id="93fae-337">**Обнаружение по Сейф ссылки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="93fae-338"><sup>\*</sup>Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="93fae-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="93fae-339">Если вы выберите строку в таблице сведений, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="93fae-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="93fae-340">Экспорт с точки зрения технологий</span><span class="sxs-lookup"><span data-stu-id="93fae-340">Export from Tech view</span></span>

<span data-ttu-id="93fae-341">При **нажатии на экспорт** **можно** выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="93fae-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="93fae-342">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="93fae-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="93fae-343">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="93fae-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="93fae-344">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="93fae-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="93fae-345">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="93fae-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="93fae-346">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="93fae-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93fae-347">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="93fae-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление технологий в отчете о состоянии mailflow](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="93fae-349">Отчет об обнаружении вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="93fae-349">Malware detections report</span></span>

<span data-ttu-id="93fae-350">В **отчете об** обнаружении вредоносных программ показаны сведения об обнаружении вредоносных программ в входящих и исходяющих сообщениях электронной почты (вредоносные программы, обнаруженные Exchange Online Protection или EOP).</span><span class="sxs-lookup"><span data-stu-id="93fae-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="93fae-351">Дополнительные сведения о защите от вредоносных программ в EOP см. в программе Защита от вредоносных [программ в EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="93fae-352">Совокупный фильтр представления позволяет в течение 90 дней, в то время как фильтр таблицы сведений разрешает только 10 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="93fae-353">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-354">На странице **Отчеты &** электронной почты найдите вредоносные программы, обнаруженные в электронной почте, а затем нажмите  **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="93fae-355">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="93fae-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Обнаружение вредоносных программ в виджете электронной почты на & отчетов о совместной работе](../../media/malware-detections-widget.png)

<span data-ttu-id="93fae-357">На странице **отчета об** обнаружении вредоносных программ можно фильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="93fae-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="93fae-358">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-359">**Направление:** **входящие и** **исходящие**</span><span class="sxs-lookup"><span data-stu-id="93fae-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Представление отчета в обнаружении вредоносных программ в отчете электронной почты](../../media/malware-detections-report-view.png)

<span data-ttu-id="93fae-361">В таблице сведений под графиком можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="93fae-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-362">**Date**</span></span>
- <span data-ttu-id="93fae-363">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="93fae-363">**Sender address**</span></span>
- <span data-ttu-id="93fae-364">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="93fae-364">**Recipient address**</span></span>
- <span data-ttu-id="93fae-365">**ID сообщения.** Доступно в **поле заглавной области Message-ID** в загонах сообщений и должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="93fae-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="93fae-366">Например, значение `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="93fae-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="93fae-367">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-367">**Subject**</span></span>
- <span data-ttu-id="93fae-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="93fae-368">**Filename**</span></span>
- <span data-ttu-id="93fae-369">**Имя вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="93fae-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="93fae-370">Отчет о задержке почты</span><span class="sxs-lookup"><span data-stu-id="93fae-370">Mail latency report</span></span>

<span data-ttu-id="93fae-371">Отчет **о задержке** почты в Defender for Office 365 содержит сведения о задержке доставки почты и детонации в организации.</span><span class="sxs-lookup"><span data-stu-id="93fae-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="93fae-372">Дополнительные сведения см. в [отчете о задержке почты.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="93fae-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="93fae-373">Отчет об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="93fae-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="93fae-374">Отчет **об обнаружении нежелательной почты** в конечном итоге пройдет.</span><span class="sxs-lookup"><span data-stu-id="93fae-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="93fae-375">Такая же информация доступна в отчете о состоянии [защиты от угроз.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="93fae-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="93fae-376">Отчет об обнаружении подмены</span><span class="sxs-lookup"><span data-stu-id="93fae-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="93fae-377">Улучшенный отчет об обнаружении Spoof, описанный в этой статье, находится в предварительной версии, подлежит изменениям и доступен не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="93fae-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="93fae-378">Более старая версия отчета показывает только хорошую почту **и** **уловлено как spam.**</span><span class="sxs-lookup"><span data-stu-id="93fae-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="93fae-379">В **отчете о обнаружениях Spoof** показаны сведения о сообщениях, которые были заблокированы или разрешены из-за подмены.</span><span class="sxs-lookup"><span data-stu-id="93fae-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="93fae-380">Дополнительные сведения о подмене см. в этой информации в [EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="93fae-381">Совокупное представление отчета позволяет в течение 45 дней фильтрации, в то время как представление детализации позволяет фильтровать только десять <sup>\*</sup> дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="93fae-382"><sup>\*</sup> В конце концов, вы сможете использовать до 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="93fae-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="93fae-383">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-384">На странице **отчеты &** сообщений о совместной работе найдите обнаружение **Spoof** и нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="93fae-385">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="93fae-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Виджет обнаружения подмены на странице отчетов & электронной почты](../../media/spoof-detections-widget.png)

<span data-ttu-id="93fae-387">На диаграмме показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-387">The chart shows the following information:</span></span>

- <span data-ttu-id="93fae-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="93fae-388">**Pass**</span></span>
- <span data-ttu-id="93fae-389">**Fail**</span><span class="sxs-lookup"><span data-stu-id="93fae-389">**Fail**</span></span>
- <span data-ttu-id="93fae-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="93fae-390">**SoftPass**</span></span>
- <span data-ttu-id="93fae-391">**Нет**</span><span class="sxs-lookup"><span data-stu-id="93fae-391">**None**</span></span>
- <span data-ttu-id="93fae-392">**Other**</span><span class="sxs-lookup"><span data-stu-id="93fae-392">**Other**</span></span>

<span data-ttu-id="93fae-393">При наведении в течение дня (точки данных) на диаграмме можно увидеть, сколько поддельных сообщений было обнаружено и почему.</span><span class="sxs-lookup"><span data-stu-id="93fae-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="93fae-394">На странице **Spoof mail report** можно отфильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав одно или несколько следующих значений:</span><span class="sxs-lookup"><span data-stu-id="93fae-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="93fae-395">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-396">**Результат:**</span><span class="sxs-lookup"><span data-stu-id="93fae-396">**Result**:</span></span>
  - <span data-ttu-id="93fae-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="93fae-397">**Pass**</span></span>
  - <span data-ttu-id="93fae-398">**Fail**</span><span class="sxs-lookup"><span data-stu-id="93fae-398">**Fail**</span></span>
  - <span data-ttu-id="93fae-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="93fae-399">**SoftPass**</span></span>
  - <span data-ttu-id="93fae-400">**Нет**</span><span class="sxs-lookup"><span data-stu-id="93fae-400">**None**</span></span>
  - <span data-ttu-id="93fae-401">**Other**</span><span class="sxs-lookup"><span data-stu-id="93fae-401">**Other**</span></span>
- <span data-ttu-id="93fae-402">**Тип Spoof:** **внутренний и** **внешний**</span><span class="sxs-lookup"><span data-stu-id="93fae-402">**Spoof type**: **Internal** and **External**</span></span>

![Страница отчета о подмене почты на Microsoft 365 Defender портале](../../media/spoof-detections-report-page.png)

<span data-ttu-id="93fae-404">В таблице сведений под графиком можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="93fae-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-405">**Date**</span></span>
- <span data-ttu-id="93fae-406">**Подмена пользователя**</span><span class="sxs-lookup"><span data-stu-id="93fae-406">**Spoofed user**</span></span>
- <span data-ttu-id="93fae-407">**Отправка инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="93fae-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="93fae-408">**Тип Spoof**</span><span class="sxs-lookup"><span data-stu-id="93fae-408">**Spoof type**</span></span>
- <span data-ttu-id="93fae-409">**Результат**</span><span class="sxs-lookup"><span data-stu-id="93fae-409">**Result**</span></span>
- <span data-ttu-id="93fae-410">**Код результатов**</span><span class="sxs-lookup"><span data-stu-id="93fae-410">**Result code**</span></span>
- <span data-ttu-id="93fae-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="93fae-411">**SPF**</span></span>
- <span data-ttu-id="93fae-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="93fae-412">**DKIM**</span></span>
- <span data-ttu-id="93fae-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="93fae-413">**DMARC**</span></span>
- <span data-ttu-id="93fae-414">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="93fae-414">**Message count**</span></span>

<span data-ttu-id="93fae-415">Дополнительные сведения о сводных кодах результатов проверки подлинности см. в материале [Anti-spam message headers in Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="93fae-416">Отчет о представлениях</span><span class="sxs-lookup"><span data-stu-id="93fae-416">Submissions report</span></span>

<span data-ttu-id="93fae-417">В **отчете Submissions** показаны сведения о том, что администраторы отчитались в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="93fae-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="93fae-418">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="93fae-419">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-420">На странице **Отчеты & электронной** почты найдите **материалы** и нажмите кнопку **Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="93fae-421">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="93fae-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="93fae-422">Чтобы перейти [к представлениям администратора на портале Microsoft 365 Defender,](admin-submission.md)нажмите **кнопку Перейти к отправкам.**</span><span class="sxs-lookup"><span data-stu-id="93fae-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Виджет отправки на странице отчетов & электронной почты](../../media/submissions-report-widget.png)

<span data-ttu-id="93fae-424">На диаграмме показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-424">The chart shows the following information:</span></span>

- <span data-ttu-id="93fae-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="93fae-425">**Pending**</span></span>
- <span data-ttu-id="93fae-426">**Выполнено**</span><span class="sxs-lookup"><span data-stu-id="93fae-426">**Completed**</span></span>

<span data-ttu-id="93fae-427">На странице **Представления** можно фильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав одно или несколько следующих значений:</span><span class="sxs-lookup"><span data-stu-id="93fae-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="93fae-428">**Дата, о чем сообщалось:** **время начала и** **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="93fae-429">**Тип отправки:** **электронная** **почта, URL-адрес** или **файл**</span><span class="sxs-lookup"><span data-stu-id="93fae-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="93fae-430">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="93fae-430">**Submission ID**</span></span>
- <span data-ttu-id="93fae-431">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="93fae-431">**Network Message ID**</span></span>
- <span data-ttu-id="93fae-432">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-432">**Sender**</span></span>
- <span data-ttu-id="93fae-433">**Название**</span><span class="sxs-lookup"><span data-stu-id="93fae-433">**Name**</span></span>
- <span data-ttu-id="93fae-434">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="93fae-434">**Submitted by**</span></span>
- <span data-ttu-id="93fae-435">**Причина отправки:** **не нежелательной,** **фишинг,** **вредоносные** программы или **нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="93fae-436">**Состояние Rescan:** **ожидание или** **заполнение**</span><span class="sxs-lookup"><span data-stu-id="93fae-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="93fae-437">В таблице сведений ниже графика показаны те же сведения, что и  в столбцах **Group** или **Customize,** что и на вкладке Отправка для анализа в email **&** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="93fae-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="93fae-438">Дополнительные сведения см. в [материале Просмотр представлений администратора в Корпорации Майкрософт.](admin-submission.md#view-admin-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="93fae-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Страница отчетов о представлениях на Microsoft 365 Defender портале](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="93fae-440">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="93fae-440">Threat protection status report</span></span>

<span data-ttu-id="93fae-441">Отчет **о состоянии защиты от** угроз доступен в EOP и Defender для Office 365; однако отчеты содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="93fae-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="93fae-442">Например, клиенты EOP могут просматривать сведения о вредоносных программах, обнаруженных в электронной почте, но не сведения о вредоносных файлах, обнаруженных Сейф вложениями для [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)и Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="93fae-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="93fae-443">В отчете приводится количество сообщений электронной почты со вредоносным контентом, например файлов или [веб-адресов](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)(URL-адресов), которые были заблокированы с помощью двигателя защиты от вредоносных программ, автоматической очистки нулевого часа [(ZAP)](zero-hour-auto-purge.md)и функций Defender для Office 365, таких как [Сейф Links,](safe-links.md) [Сейф Attachments](safe-attachments.md), и функции защиты от фишинга в политиках защиты от фишинга .</span><span class="sxs-lookup"><span data-stu-id="93fae-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="93fae-444">Эти сведения можно использовать для определения тенденций или определения необходимости корректировки политик организации.</span><span class="sxs-lookup"><span data-stu-id="93fae-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="93fae-445">**Примечание.** Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="93fae-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="93fae-446">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-447">На странице **отчеты & электронной** почты найдите состояние **защиты** от угроз и нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="93fae-448">Чтобы перейти непосредственно к отчету, откройте один из следующих URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="93fae-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="93fae-449">Defender для Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="93fae-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="93fae-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="93fae-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Виджет состояния защиты от угрозы на странице отчетов & электронной почты](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="93fae-452">По умолчанию на диаграмме показаны данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="93fae-453">При **нажатии фильтра** на странице отчета о состоянии защиты от угроз можно выбрать диапазон дат в 90 дней (пробная подписка может быть ограничена 30 днями). </span><span class="sxs-lookup"><span data-stu-id="93fae-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="93fae-454">Таблица сведений позволяет фильтровать в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="93fae-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="93fae-455">Доступные представления описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="93fae-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="93fae-456">Просмотр данных по обзору</span><span class="sxs-lookup"><span data-stu-id="93fae-456">View data by Overview</span></span>

![Обзор представления в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="93fae-458">В **представлении View data by Overview** на диаграмме показаны следующие сведения об обнаружении:</span><span class="sxs-lookup"><span data-stu-id="93fae-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="93fae-459">**Вредоносные программы электронной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-459">**Email malware**</span></span>
- <span data-ttu-id="93fae-460">**Фишинг электронной почты**</span><span class="sxs-lookup"><span data-stu-id="93fae-460">**Email phish**</span></span>
- <span data-ttu-id="93fae-461">**Вредоносные программы контента**</span><span class="sxs-lookup"><span data-stu-id="93fae-461">**Content malware**</span></span>

<span data-ttu-id="93fae-462">Таблица сведений недоступна ниже диаграммы.</span><span class="sxs-lookup"><span data-stu-id="93fae-462">No details table is available below the chart.</span></span>

<span data-ttu-id="93fae-463">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="93fae-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="93fae-464">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-465">**Обнаружение:** **вредоносные программы** по **электронной почте, фишинг электронной почты** или **вредоносные программы по контенту**</span><span class="sxs-lookup"><span data-stu-id="93fae-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="93fae-466">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="93fae-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="93fae-467">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="93fae-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="93fae-468">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="93fae-469">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-469">**Direction**</span></span>
- <span data-ttu-id="93fae-470">**Домен**</span><span class="sxs-lookup"><span data-stu-id="93fae-470">**Domain**</span></span>
- <span data-ttu-id="93fae-471">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="93fae-471">**Policy type**</span></span>

<span data-ttu-id="93fae-472">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="93fae-473">Просмотр данных с помощью \> фишинга электронной почты и разбивки диаграмм с помощью технологии обнаружения</span><span class="sxs-lookup"><span data-stu-id="93fae-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Представление технологии обнаружения фишинговой электронной почты в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="93fae-475">В **представлении данных по фишингу электронной \> почты** и разбивке диаграмм по представлению **технологии** обнаружения на диаграмме показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="93fae-476">**Вредоносная репутация** URL-адреса: вредоносная репутация URL-адреса, созданная в Defender для Office 365 в других Microsoft 365 <sup>\*</sup> клиентах.</span><span class="sxs-lookup"><span data-stu-id="93fae-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="93fae-477">**Расширенный фильтр:** фишинговые сигналы на основе машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="93fae-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="93fae-478">**Общий фильтр:** фишинговые сигналы, основанные на правилах аналитика.</span><span class="sxs-lookup"><span data-stu-id="93fae-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="93fae-479">**Spoof intra-org.** Отправитель пытается подменить домен получателя.</span><span class="sxs-lookup"><span data-stu-id="93fae-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="93fae-480">**Внешний домен Spoof.** Отправитель пытается подменить другой домен.</span><span class="sxs-lookup"><span data-stu-id="93fae-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="93fae-481">**Spoof DMARC:** Сбой проверки подлинности DMARC в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="93fae-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="93fae-482">**Бренд Impersonation**: Impersonation известных брендов на основе отправителей.</span><span class="sxs-lookup"><span data-stu-id="93fae-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="93fae-483">**Обнаружение с помощью смешанного анализа**</span><span class="sxs-lookup"><span data-stu-id="93fae-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="93fae-484">**Репутация файла**</span><span class="sxs-lookup"><span data-stu-id="93fae-484">**File reputation**</span></span>
- <span data-ttu-id="93fae-485">**Сопоставление отпечатков**</span><span class="sxs-lookup"><span data-stu-id="93fae-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="93fae-486">**Репутация детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-487">**Детонация URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-488">**Пользователь impersonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-489">**Домен impersonation** <sup>\*</sup> : Impersonation доменов, которые клиент владеет или определяет.</span><span class="sxs-lookup"><span data-stu-id="93fae-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="93fae-490">**Вымысление** сведении почтовых ящиков: обезличение пользователей, определенных администратором или <sup>\*</sup> выучатся с помощью разведки почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="93fae-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="93fae-491">**Детонация файлов**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-492">**Кампания**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="93fae-493">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="93fae-494">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-494">**Date**</span></span>
- <span data-ttu-id="93fae-495">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-495">**Subject**</span></span>
- <span data-ttu-id="93fae-496">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-496">**Sender**</span></span>
- <span data-ttu-id="93fae-497">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-497">**Recipients**</span></span>
- <span data-ttu-id="93fae-498">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="93fae-498">**Detected by**</span></span>
- <span data-ttu-id="93fae-499">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="93fae-499">**Delivery Status**</span></span>
- <span data-ttu-id="93fae-500">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="93fae-500">**Source of Compromise**</span></span>
- <span data-ttu-id="93fae-501">**Tags**</span><span class="sxs-lookup"><span data-stu-id="93fae-501">**Tags**</span></span>

<span data-ttu-id="93fae-502">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="93fae-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="93fae-503">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-504">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="93fae-504">**Detection**</span></span>
- <span data-ttu-id="93fae-505">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="93fae-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="93fae-506">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-506">**Direction**</span></span>
- <span data-ttu-id="93fae-507">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="93fae-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="93fae-508">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="93fae-509">**Домен**</span><span class="sxs-lookup"><span data-stu-id="93fae-509">**Domain**</span></span>
- <span data-ttu-id="93fae-510">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="93fae-510">**Policy type**</span></span>
- <span data-ttu-id="93fae-511">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="93fae-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="93fae-512">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-512">**Recipients**</span></span>

<span data-ttu-id="93fae-513">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="93fae-514">Просмотр данных по вредоносным программам электронной почты \> и разбивке диаграмм с помощью технологии обнаружения</span><span class="sxs-lookup"><span data-stu-id="93fae-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Представление технологии обнаружения вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="93fae-516">В **представлении данных \> по вредоносным программам электронной** почты и разбивке диаграмм по представлению **технологии** обнаружения на диаграмме показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="93fae-517">**Детонация файлов:** <sup>\*</sup> обнаружение Сейф вложения.</span><span class="sxs-lookup"><span data-stu-id="93fae-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="93fae-518">**Репутация детонации файлов:** <sup>\*</sup> вся репутация вредоносных файлов, созданных Defender для Office 365 детонации.</span><span class="sxs-lookup"><span data-stu-id="93fae-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="93fae-519">**Репутация файла**</span><span class="sxs-lookup"><span data-stu-id="93fae-519">**File reputation**</span></span>
- <span data-ttu-id="93fae-520">**Движок для борьбы с вредоносными** <sup>\*</sup> программами. Обнаружение с антивирусных двигателей.</span><span class="sxs-lookup"><span data-stu-id="93fae-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="93fae-521">Блок типа файлов политики по борьбе с вредоносными программами. Это сообщения электронной почты, отфильтрованные **из-за** типа вредоносного файла, выявленного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="93fae-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="93fae-522">**Репутация вредоносного URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="93fae-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="93fae-523">**Отключение URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="93fae-523">**URL detonation**</span></span>
- <span data-ttu-id="93fae-524">**Репутация отключения URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="93fae-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="93fae-525">**Кампания**</span><span class="sxs-lookup"><span data-stu-id="93fae-525">**Campaign**</span></span>

<span data-ttu-id="93fae-526">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="93fae-527">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-527">**Date**</span></span>
- <span data-ttu-id="93fae-528">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-528">**Subject**</span></span>
- <span data-ttu-id="93fae-529">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-529">**Sender**</span></span>
- <span data-ttu-id="93fae-530">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-530">**Recipients**</span></span>
- <span data-ttu-id="93fae-531">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="93fae-531">**Detected by**</span></span>
- <span data-ttu-id="93fae-532">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="93fae-532">**Delivery Status**</span></span>
- <span data-ttu-id="93fae-533">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="93fae-533">**Source of Compromise**</span></span>
- <span data-ttu-id="93fae-534">**Tags**</span><span class="sxs-lookup"><span data-stu-id="93fae-534">**Tags**</span></span>

<span data-ttu-id="93fae-535">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="93fae-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="93fae-536">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-537">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="93fae-537">**Detection**</span></span>
- <span data-ttu-id="93fae-538">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="93fae-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="93fae-539">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-539">**Direction**</span></span>
- <span data-ttu-id="93fae-540">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="93fae-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="93fae-541">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="93fae-542">**Домен**</span><span class="sxs-lookup"><span data-stu-id="93fae-542">**Domain**</span></span>
- <span data-ttu-id="93fae-543">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="93fae-543">**Policy type**</span></span>
- <span data-ttu-id="93fae-544">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="93fae-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="93fae-545">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-545">**Recipients**</span></span>

<span data-ttu-id="93fae-546">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="93fae-547">Разбивка диаграмм по типу политики и просмотру данных по фишингу электронной почты или \> просмотру данных по вредоносным программам электронной \> почты</span><span class="sxs-lookup"><span data-stu-id="93fae-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Вид типа политики для фишинга электронной почты или вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="93fae-549">В **разбивке диаграмм** по типу политики и просмотру данных по фишингу электронной почты или просмотру данных по представлениям вредоносных программ по электронной почте в диаграммах показаны следующие сведения: **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="93fae-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="93fae-550">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="93fae-550">**Anti-malware**</span></span>
- <span data-ttu-id="93fae-551">**Сейф Вложения**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93fae-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="93fae-552">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="93fae-552">**Anti-phish**</span></span>
- <span data-ttu-id="93fae-553">**Противодействие нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="93fae-553">**Anti-spam**</span></span>
- <span data-ttu-id="93fae-554">**Правило потока почты** (также известное как правило транспорта)</span><span class="sxs-lookup"><span data-stu-id="93fae-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="93fae-555">**Другие**</span><span class="sxs-lookup"><span data-stu-id="93fae-555">**Others**</span></span>

<span data-ttu-id="93fae-556">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="93fae-557">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-557">**Date**</span></span>
- <span data-ttu-id="93fae-558">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-558">**Subject**</span></span>
- <span data-ttu-id="93fae-559">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-559">**Sender**</span></span>
- <span data-ttu-id="93fae-560">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-560">**Recipients**</span></span>
- <span data-ttu-id="93fae-561">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="93fae-561">**Detected by**</span></span>
- <span data-ttu-id="93fae-562">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="93fae-562">**Delivery Status**</span></span>
- <span data-ttu-id="93fae-563">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="93fae-563">**Source of Compromise**</span></span>
- <span data-ttu-id="93fae-564">**Tags**</span><span class="sxs-lookup"><span data-stu-id="93fae-564">**Tags**</span></span>

<span data-ttu-id="93fae-565">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="93fae-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="93fae-566">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-567">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="93fae-567">**Detection**</span></span>
- <span data-ttu-id="93fae-568">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="93fae-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="93fae-569">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-569">**Direction**</span></span>
- <span data-ttu-id="93fae-570">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="93fae-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="93fae-571">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="93fae-572">**Домен**</span><span class="sxs-lookup"><span data-stu-id="93fae-572">**Domain**</span></span>
- <span data-ttu-id="93fae-573">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="93fae-573">**Policy type**</span></span>
- <span data-ttu-id="93fae-574">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="93fae-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="93fae-575">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-575">**Recipients**</span></span>

<span data-ttu-id="93fae-576">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="93fae-577">Разбивка диаграмм по статусу доставки и просмотру данных по фишингу электронной почты или \> просмотру данных вредоносными программами электронной \> почты</span><span class="sxs-lookup"><span data-stu-id="93fae-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Представление состояния доставки для фишинговой электронной почты и вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="93fae-579">В **разбивке диаграмм** по статусу доставки и просмотру данных по фишингу электронной почты или просмотру данных по представлениям вредоносных программ по электронной почте в диаграммах показаны следующие сведения: **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="93fae-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="93fae-580">**Хост-почтовый ящик: Почтовый ящик**</span><span class="sxs-lookup"><span data-stu-id="93fae-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="93fae-581">**Хост-почтовый ящик: нежелательной**</span><span class="sxs-lookup"><span data-stu-id="93fae-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="93fae-582">**Хост-почтовый ящик: настраиваемая папка**</span><span class="sxs-lookup"><span data-stu-id="93fae-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="93fae-583">**Хост-почтовый ящик: удаленные элементы**</span><span class="sxs-lookup"><span data-stu-id="93fae-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="93fae-584">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="93fae-584">**Forwarded**</span></span>
- <span data-ttu-id="93fae-585">**Локального сервера: Доставлено**</span><span class="sxs-lookup"><span data-stu-id="93fae-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="93fae-586">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="93fae-586">**Quarantine**</span></span>
- <span data-ttu-id="93fae-587">**Сбой доставки**</span><span class="sxs-lookup"><span data-stu-id="93fae-587">**Delivery failed**</span></span>
- <span data-ttu-id="93fae-588">**Сброс**</span><span class="sxs-lookup"><span data-stu-id="93fae-588">**Dropped**</span></span>

<span data-ttu-id="93fae-589">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="93fae-590">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-590">**Date**</span></span>
- <span data-ttu-id="93fae-591">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-591">**Subject**</span></span>
- <span data-ttu-id="93fae-592">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-592">**Sender**</span></span>
- <span data-ttu-id="93fae-593">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-593">**Recipients**</span></span>
- <span data-ttu-id="93fae-594">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="93fae-594">**Detected by**</span></span>
- <span data-ttu-id="93fae-595">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="93fae-595">**Delivery Status**</span></span>
- <span data-ttu-id="93fae-596">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="93fae-596">**Source of Compromise**</span></span>
- <span data-ttu-id="93fae-597">**Tags**</span><span class="sxs-lookup"><span data-stu-id="93fae-597">**Tags**</span></span>

<span data-ttu-id="93fae-598">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="93fae-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="93fae-599">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-600">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="93fae-600">**Detection**</span></span>
- <span data-ttu-id="93fae-601">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="93fae-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="93fae-602">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-602">**Direction**</span></span>
- <span data-ttu-id="93fae-603">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="93fae-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="93fae-604">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="93fae-605">**Домен**</span><span class="sxs-lookup"><span data-stu-id="93fae-605">**Domain**</span></span>
- <span data-ttu-id="93fae-606">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="93fae-606">**Policy type**</span></span>
- <span data-ttu-id="93fae-607">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="93fae-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="93fae-608">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-608">**Recipients**</span></span>

<span data-ttu-id="93fae-609">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="93fae-610">Просмотр данных по вредоносным \> программам контента</span><span class="sxs-lookup"><span data-stu-id="93fae-610">View data by Content \> Malware</span></span>

![Просмотр вредоносных программ контента в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="93fae-612">В **представлении View data by Content \> Malware** на диаграмме Для Microsoft Defender для Office 365 организаций показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="93fae-613">**Антивирусный** двигатель: вредоносные файлы, обнаруженные в Sharepoint, OneDrive и Microsoft Teams с помощью встроенного обнаружения вирусов в [Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="93fae-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="93fae-614">**Детонация** файлов: вредоносные файлы, обнаруженные Сейф вложениями для [SharePoint, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="93fae-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="93fae-615">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="93fae-616">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-617">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="93fae-617">**Location**</span></span>
- <span data-ttu-id="93fae-618">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="93fae-618">**Detected by**</span></span>
- <span data-ttu-id="93fae-619">**Имя вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="93fae-619">**Malware name**</span></span>

<span data-ttu-id="93fae-620">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="93fae-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="93fae-621">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-622">**Обнаружение:** **детонация антивирусных программ** **или детонация файлов**</span><span class="sxs-lookup"><span data-stu-id="93fae-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="93fae-623">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="93fae-624">Просмотр данных путем переопределения системы</span><span class="sxs-lookup"><span data-stu-id="93fae-624">View data by System override</span></span>

![Представление переопределения сообщений в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="93fae-626">В **представлении Просмотр данных по представлению Переопределения** системы в диаграмме показаны следующие сведения о причинах переопределения:</span><span class="sxs-lookup"><span data-stu-id="93fae-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="93fae-627">**Локальное пропустить**</span><span class="sxs-lookup"><span data-stu-id="93fae-627">**On-premises skip**</span></span>
- <span data-ttu-id="93fae-628">**РАЗРЕШЕНИЕ IP**</span><span class="sxs-lookup"><span data-stu-id="93fae-628">**IP allow**</span></span>
- <span data-ttu-id="93fae-629">**Exchange транспорта почты** (правило потока почты)</span><span class="sxs-lookup"><span data-stu-id="93fae-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="93fae-630">**Организация разрешила отправителям**</span><span class="sxs-lookup"><span data-stu-id="93fae-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="93fae-631">**Разрешенные домены организации**</span><span class="sxs-lookup"><span data-stu-id="93fae-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="93fae-632">**ZAP не включен**</span><span class="sxs-lookup"><span data-stu-id="93fae-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="93fae-633">**Папка нежелательной почты не включена**</span><span class="sxs-lookup"><span data-stu-id="93fae-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="93fae-634">**Отправитель Сейф пользователя**</span><span class="sxs-lookup"><span data-stu-id="93fae-634">**User Safe Sender**</span></span>
- <span data-ttu-id="93fae-635">**Домен пользователя Сейф**</span><span class="sxs-lookup"><span data-stu-id="93fae-635">**User Safe Domain**</span></span>

<span data-ttu-id="93fae-636">В таблице сведений ниже диаграммы доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="93fae-637">**Date**</span><span class="sxs-lookup"><span data-stu-id="93fae-637">**Date**</span></span>
- <span data-ttu-id="93fae-638">**Тема**</span><span class="sxs-lookup"><span data-stu-id="93fae-638">**Subject**</span></span>
- <span data-ttu-id="93fae-639">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-639">**Sender**</span></span>
- <span data-ttu-id="93fae-640">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-640">**Recipients**</span></span>
- <span data-ttu-id="93fae-641">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="93fae-641">**Detected by**</span></span>
- <span data-ttu-id="93fae-642">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="93fae-642">**Delivery Status**</span></span>
- <span data-ttu-id="93fae-643">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="93fae-643">**Source of Compromise**</span></span>
- <span data-ttu-id="93fae-644">**Tags**</span><span class="sxs-lookup"><span data-stu-id="93fae-644">**Tags**</span></span>

<span data-ttu-id="93fae-645">При **нажатии фильтра** доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="93fae-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="93fae-646">**Дата (UTC)** **Дата начала и** дата **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="93fae-647">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="93fae-647">**Detection**</span></span>
- <span data-ttu-id="93fae-648">**Защищено:** **MDO** (Defender for Office 365) или **EOP**</span><span class="sxs-lookup"><span data-stu-id="93fae-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="93fae-649">**Направление**</span><span class="sxs-lookup"><span data-stu-id="93fae-649">**Direction**</span></span>
- <span data-ttu-id="93fae-650">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="93fae-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="93fae-651">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="93fae-652">**Домен**</span><span class="sxs-lookup"><span data-stu-id="93fae-652">**Domain**</span></span>
- <span data-ttu-id="93fae-653">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="93fae-653">**Policy type**</span></span>
- <span data-ttu-id="93fae-654">**Имя политики** (только таблица сведений)</span><span class="sxs-lookup"><span data-stu-id="93fae-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="93fae-655">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="93fae-655">**Recipients**</span></span>

<span data-ttu-id="93fae-656">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="93fae-657"><sup>\*</sup>Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="93fae-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="93fae-658">Топ отчета о вредоносных программах</span><span class="sxs-lookup"><span data-stu-id="93fae-658">Top malware report</span></span>

<span data-ttu-id="93fae-659">В **топовом отчете** о вредоносных программах показаны различные виды вредоносных программ, обнаруженных защитой от вредоносных программ [в EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="93fae-660">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-661">На странице **Отчеты & электронной** почты **найдите** топ вредоносных программ и нажмите кнопку **Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="93fae-662">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="93fae-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Виджет топ вредоносных программ на странице отчетов & электронной почты](../../media/top-malware-report-widget.png)

<span data-ttu-id="93fae-664">При наведении на клин в диаграмме пирога можно увидеть имя типа вредоносных программ и количество сообщений, обнаруженных как наличие этого вредоносного ПО.</span><span class="sxs-lookup"><span data-stu-id="93fae-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="93fae-665">На странице **Отчет о вредоносных** программах на странице отчетов отображается более крупная версия диаграммы пирога. В таблице сведений ниже диаграммы показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="93fae-666">**Топ вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="93fae-666">**Top malware**</span></span>
- <span data-ttu-id="93fae-667">**Count**</span><span class="sxs-lookup"><span data-stu-id="93fae-667">**Count**</span></span>

<span data-ttu-id="93fae-668">При **нажатии фильтра** можно указать диапазон дат с **датой начала и** **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="93fae-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Представление отчета о вредоносных программах](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="93fae-670">Отчет об угрозе URL-адреса</span><span class="sxs-lookup"><span data-stu-id="93fae-670">URL threat protection report</span></span>

<span data-ttu-id="93fae-671">Отчет **об угрозе** URL-адресов доступен в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="93fae-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="93fae-672">Дополнительные сведения см. в [отчете об угрозе URL-адреса.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="93fae-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="93fae-673">Отчет о сообщениях пользователя</span><span class="sxs-lookup"><span data-stu-id="93fae-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93fae-674">Чтобы отчет **о сообщениях** пользователя работал **правильно,** необходимо ввести журнал аудита для Microsoft 365 среды.</span><span class="sxs-lookup"><span data-stu-id="93fae-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="93fae-675">Обычно это делается тем, кто имеет роль журналов аудита, назначенную в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93fae-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="93fae-676">Дополнительные сведения см. в Microsoft 365 поиска журнала [аудита.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="93fae-677">Отчет **о** сообщениях пользователя показывает сведения о сообщениях электронной почты, которые пользователи сообщали как нежелательные, фишинговые попытки или хорошая почта с помощью надстройки Report [Message](enable-the-report-message-add-in.md) или надстройки [Report Phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="93fae-678">Чтобы просмотреть отчет на портале Microsoft 365 Defender,  перейдите в отчеты электронной почты & совместной & отчеты о \>  \> **совместной работе.**</span><span class="sxs-lookup"><span data-stu-id="93fae-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="93fae-679">На странице **Отчеты & сообщения** о  совместной работе найдите сообщения пользователя, а затем нажмите **кнопку Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="93fae-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="93fae-680">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="93fae-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="93fae-681">Чтобы перейти [к представлениям администратора на портале Microsoft 365 Defender,](admin-submission.md)нажмите **кнопку Перейти к отправкам.**</span><span class="sxs-lookup"><span data-stu-id="93fae-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Виджет сообщений пользователей на странице отчетов о совместной & электронной почты](../../media/user-reported-messages-widget.png)

<span data-ttu-id="93fae-683">На странице **Сообщения** пользователя можно фильтровать диаграмму и таблицу сведений, щелкнув **фильтр** и выбрав одно или несколько следующих значений в вылете:</span><span class="sxs-lookup"><span data-stu-id="93fae-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="93fae-684">**Дата, о чем сообщалось:** **время начала и** **окончания**</span><span class="sxs-lookup"><span data-stu-id="93fae-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="93fae-685">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="93fae-685">**Reported by**</span></span>
- <span data-ttu-id="93fae-686">**Тема письма**</span><span class="sxs-lookup"><span data-stu-id="93fae-686">**Email subject**</span></span>
- <span data-ttu-id="93fae-687">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="93fae-687">**Message reported ID**</span></span>
- <span data-ttu-id="93fae-688">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="93fae-688">**Network Message ID**</span></span>
- <span data-ttu-id="93fae-689">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-689">**Sender**</span></span>
- <span data-ttu-id="93fae-690">**Сообщаемая причина**</span><span class="sxs-lookup"><span data-stu-id="93fae-690">**Reported reason**</span></span>
  - <span data-ttu-id="93fae-691">**Не нежелательно**</span><span class="sxs-lookup"><span data-stu-id="93fae-691">**Not junk**</span></span>
  - <span data-ttu-id="93fae-692">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="93fae-692">**Phish**</span></span>
  - <span data-ttu-id="93fae-693">**Спам**</span><span class="sxs-lookup"><span data-stu-id="93fae-693">**Spam**</span></span>
- <span data-ttu-id="93fae-694">**Фишинговое моделирование:** **да** или **нет**</span><span class="sxs-lookup"><span data-stu-id="93fae-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="93fae-695">Когда вы закончите настройку фильтров, нажмите **кнопку Применить,** **Отменить** или **очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="93fae-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="93fae-696">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="93fae-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="93fae-697">**Нет**</span><span class="sxs-lookup"><span data-stu-id="93fae-697">**None**</span></span>
- <span data-ttu-id="93fae-698">**Причина**</span><span class="sxs-lookup"><span data-stu-id="93fae-698">**Reason**</span></span>
- <span data-ttu-id="93fae-699">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-699">**Sender**</span></span>
- <span data-ttu-id="93fae-700">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="93fae-700">**Reported by**</span></span>
- <span data-ttu-id="93fae-701">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="93fae-701">**Rescan result**</span></span>
- <span data-ttu-id="93fae-702">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="93fae-702">**Phish simulation**</span></span>

![Отчет о сообщениях пользователя](../../media/user-reported-messages-report.png)

<span data-ttu-id="93fae-704">В таблице сведений под графиком можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="93fae-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="93fae-705">**Тема письма**</span><span class="sxs-lookup"><span data-stu-id="93fae-705">**Email subject**</span></span>
- <span data-ttu-id="93fae-706">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="93fae-706">**Reported by**</span></span>
- <span data-ttu-id="93fae-707">**Дата сообщается**</span><span class="sxs-lookup"><span data-stu-id="93fae-707">**Date reported**</span></span>
- <span data-ttu-id="93fae-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="93fae-708">**Sender**</span></span>
- <span data-ttu-id="93fae-709">**Сообщаемая причина**</span><span class="sxs-lookup"><span data-stu-id="93fae-709">**Reported reason**</span></span>
- <span data-ttu-id="93fae-710">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="93fae-710">**Rescan result**</span></span>
- <span data-ttu-id="93fae-711">**Tags**</span><span class="sxs-lookup"><span data-stu-id="93fae-711">**Tags**</span></span>

<span data-ttu-id="93fae-712">Чтобы отправить сообщение в Корпорацию Майкрософт для анализа, выберите запись сообщения из таблицы, щелкните Отправка в **Корпорацию Майкрософт** для анализа, а затем выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="93fae-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="93fae-713">**Отчет о чистоте**</span><span class="sxs-lookup"><span data-stu-id="93fae-713">**Report clean**</span></span>
- <span data-ttu-id="93fae-714">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="93fae-714">**Report phishing**</span></span>
- <span data-ttu-id="93fae-715">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="93fae-715">**Report malware**</span></span>
- <span data-ttu-id="93fae-716">**Сообщить о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="93fae-716">**Report spam**'</span></span>
- <span data-ttu-id="93fae-717">**Триггерное** расследование (Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="93fae-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="93fae-718">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="93fae-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="93fae-719">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей на Microsoft 365 Defender портале:</span><span class="sxs-lookup"><span data-stu-id="93fae-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="93fae-720">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="93fae-720">**Organization Management**</span></span>
- <span data-ttu-id="93fae-721">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="93fae-721">**Security Administrator**</span></span>
- <span data-ttu-id="93fae-722">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="93fae-722">**Security Reader**</span></span>
- <span data-ttu-id="93fae-723">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="93fae-723">**Global Reader**</span></span>

<span data-ttu-id="93fae-724">Дополнительные сведения см. [на портале Permissions in the Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="93fae-725">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в Центр администрирования Microsoft 365 дает пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93fae-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="93fae-726">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="93fae-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="93fae-727">Что делать, если отчеты не отображают данные?</span><span class="sxs-lookup"><span data-stu-id="93fae-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="93fae-728">Если в отчетах нет данных, убедитесь, что политики настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="93fae-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="93fae-729">Дополнительные новости см. в [см. в руберсе Защита от угроз.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="93fae-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="93fae-730">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="93fae-730">Related topics</span></span>

[<span data-ttu-id="93fae-731">Защита от нежелательной почты и вредоносных программ в EOP</span><span class="sxs-lookup"><span data-stu-id="93fae-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="93fae-732">Интеллектуальные отчеты и сведения на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="93fae-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="93fae-733">Просмотр отчетов о потоке почты на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="93fae-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="93fae-734">Просмотр отчетов для Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="93fae-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
