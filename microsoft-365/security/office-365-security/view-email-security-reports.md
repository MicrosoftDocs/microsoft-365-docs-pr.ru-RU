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
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930329"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="25fca-104">Просмотр отчетов о безопасности электронной почты на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25fca-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="25fca-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="25fca-105">**Applies to**</span></span>
- [<span data-ttu-id="25fca-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="25fca-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="25fca-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="25fca-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="25fca-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25fca-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="25fca-109">На портале [Microsoft 365 Defender](https://security.microsoft.com) доступны различные отчеты, которые помогут вам увидеть, как функции безопасности электронной почты, такие как средства защиты от нежелательной почты, защиты от вредоносных программ и шифрования в Microsoft 365 защищают вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="25fca-109">A variety of reports are available in the [Microsoft 365 Defender portal](https://security.microsoft.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="25fca-110">Если у вас [есть](#what-permissions-are-needed-to-view-these-reports)необходимые разрешения, вы можете просмотреть эти отчеты на портале Microsoft 365 Defender, переехав в отчеты электронной почты & совместной & отчеты о совместной  \>  \> **работе**.</span><span class="sxs-lookup"><span data-stu-id="25fca-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="25fca-111">Чтобы перейти непосредственно к панели мониторинга Отчетов, откройте <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="25fca-111">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Панель мониторинга отчетов на портале Microsoft 365 Defender](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a><span data-ttu-id="25fca-113">Отчет о скомпрометировании пользователей</span><span class="sxs-lookup"><span data-stu-id="25fca-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="25fca-114">Этот отчет доступен в Microsoft 365 организациях с Exchange Online почтовыми ящиками.</span><span class="sxs-lookup"><span data-stu-id="25fca-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="25fca-115">Он не доступен в автономных организациях Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="25fca-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="25fca-116">В **отчете о** скомпрометировании пользователей  показано  количество учетных записей пользователей, отмеченных как подозрительные или ограниченные в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="25fca-117">Учетные записи в любом из этих штатов являются проблемными или даже скомпрометированными.</span><span class="sxs-lookup"><span data-stu-id="25fca-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="25fca-118">При частом использовании вы можете использовать отчет для задания пиков и даже тенденций в подозрительных или ограниченных учетных записях.</span><span class="sxs-lookup"><span data-stu-id="25fca-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="25fca-119">Дополнительные сведения о скомпрометированных пользователях см. в [сообщении Responding to a compromised email account.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Скомпрометированная виджет пользователей в панели мониторинга отчетов](../../media/compromised-users-report-widget.png)

<span data-ttu-id="25fca-121">В сводном представлении показаны данные за последние 90 дней, а в представлении подробно показаны данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="25fca-122">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и щелкните Сведения о просмотре в скомпрометированных  \>  \>  **пользователях**. </span><span class="sxs-lookup"><span data-stu-id="25fca-122">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Compromised users**.</span></span> <span data-ttu-id="25fca-123">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="25fca-123">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="25fca-124">Вы можете фильтровать диаграмму и таблицу сведений, щелкнув **фильтры** и выбрав одно или несколько следующих значений:</span><span class="sxs-lookup"><span data-stu-id="25fca-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="25fca-125">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="25fca-126">**Подозрительный.** Учетная запись пользователя отправила подозрительные сообщения электронной почты и может быть ограничена отправкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="25fca-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="25fca-127">**Ограничение.** Учетная запись пользователя была ограничена отправкой электронной почты из-за весьма подозрительных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="25fca-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Представление отчета в отчете о скомпрометированных пользователях](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="25fca-129">Если **щелкнуть таблицу Просмотр** сведений, можно просмотреть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="25fca-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="25fca-130">**Время создания**</span><span class="sxs-lookup"><span data-stu-id="25fca-130">**Creation time**</span></span>
- <span data-ttu-id="25fca-131">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="25fca-131">**User ID**</span></span>
- <span data-ttu-id="25fca-132">**Действие**</span><span class="sxs-lookup"><span data-stu-id="25fca-132">**Action**</span></span>

<span data-ttu-id="25fca-133">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="25fca-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="25fca-134">Отчет о шифровании</span><span class="sxs-lookup"><span data-stu-id="25fca-134">Encryption report</span></span>

<span data-ttu-id="25fca-135">Отчет **шифрования** доступен в EOP (подписки с почтовыми ящиками в Exchange Online или автономный EOP без Exchange Online почтовых ящиков).</span><span class="sxs-lookup"><span data-stu-id="25fca-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="25fca-136">Группа безопасности организации может использовать сведения в этом отчете для определения шаблонов и активно применять или корректировать политики для конфиденциальных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="25fca-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="25fca-137">Пример.</span><span class="sxs-lookup"><span data-stu-id="25fca-137">For example:</span></span>

- <span data-ttu-id="25fca-138">Если вы видите большое количество зашифрованных пользователями сообщений электронной почты, может потребоваться добавить политику шифрования для автоматизации шифрования для определенных случаев использования.</span><span class="sxs-lookup"><span data-stu-id="25fca-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="25fca-139">Дополнительные сведения см. в тексте Определение правил потока почты для шифрования сообщений электронной почты [в Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="25fca-140">Если у вас есть несколько шаблонов шифрования, но их никто не использует, можно узнать, нужна ли пользователям подготовка функций.</span><span class="sxs-lookup"><span data-stu-id="25fca-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="25fca-141">Совокупное представление позволяет фильтровать в течение последних 90 дней, в то время как представление детализации позволяет фильтровать в течение 10 дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="25fca-142">Чтобы просмотреть отчет, откройте [портал Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и нажмите кнопку Просмотр сведений в отчете  \>  \>  **Шифрование**. </span><span class="sxs-lookup"><span data-stu-id="25fca-142">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Encryption report**.</span></span> <span data-ttu-id="25fca-143">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="25fca-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="25fca-144">Подробнее о шифровании [см.](../../compliance/email-encryption.md)в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25fca-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="25fca-145">Представление отчета для отчета шифрования</span><span class="sxs-lookup"><span data-stu-id="25fca-145">Report view for the Encryption report</span></span>

<span data-ttu-id="25fca-146">На диаграмме можно использовать следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="25fca-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="25fca-147">**Просмотр данных по: Отчет о шифровании сообщений** и **break down by: Метод** шифрования: Доступны следующие методы шифрования:</span><span class="sxs-lookup"><span data-stu-id="25fca-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="25fca-148">**Шифрование пользователем**</span><span class="sxs-lookup"><span data-stu-id="25fca-148">**Encryption by user**</span></span>
  - <span data-ttu-id="25fca-149">**Шифрование по политике**</span><span class="sxs-lookup"><span data-stu-id="25fca-149">**Encryption by policy**</span></span>

  <span data-ttu-id="25fca-150">При **нажатии фильтров** можно изменить диаграмму с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="25fca-151">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="25fca-152">Метод шифрования.</span><span class="sxs-lookup"><span data-stu-id="25fca-152">Encryption method.</span></span>
  - <span data-ttu-id="25fca-153">Шаблон шифрования.</span><span class="sxs-lookup"><span data-stu-id="25fca-153">Encryption template.</span></span>

- <span data-ttu-id="25fca-154">**Просмотр данных по: Отчет о шифровании сообщений** и **break down by: Шаблон шифрования:** Доступны следующие методы шифрования:</span><span class="sxs-lookup"><span data-stu-id="25fca-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="25fca-155">**Не переад.**</span><span class="sxs-lookup"><span data-stu-id="25fca-155">**Do not forward**</span></span>
  - <span data-ttu-id="25fca-156">**Только шифрование**</span><span class="sxs-lookup"><span data-stu-id="25fca-156">**Encrypt only**</span></span>
  - <span data-ttu-id="25fca-157">**Предыдущий OME**</span><span class="sxs-lookup"><span data-stu-id="25fca-157">**OME previous**</span></span>
  - <span data-ttu-id="25fca-158">**Custom**</span><span class="sxs-lookup"><span data-stu-id="25fca-158">**Custom**</span></span>

  <span data-ttu-id="25fca-159">При **нажатии фильтров** можно изменить диаграмму с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="25fca-160">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="25fca-161">Метод шифрования</span><span class="sxs-lookup"><span data-stu-id="25fca-161">Encryption method</span></span>
  - <span data-ttu-id="25fca-162">Шаблон шифрования</span><span class="sxs-lookup"><span data-stu-id="25fca-162">Encryption template</span></span>

- <span data-ttu-id="25fca-163">**Просмотр данных по: Топ-5** доменов получателей. В этом представлении показана диаграмма пирога с количеством отправленных сообщений для топ-5 доменов получателей.</span><span class="sxs-lookup"><span data-stu-id="25fca-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="25fca-164">Если **щелкнуть фильтры,** можно выбрать **дату** начала и **дату окончания.**</span><span class="sxs-lookup"><span data-stu-id="25fca-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="25fca-165">Представление таблицы сведений для отчета шифрования</span><span class="sxs-lookup"><span data-stu-id="25fca-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="25fca-166">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="25fca-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="25fca-167">**Break down by: Encryption method** or **Break down by: Encryption template:** Following information is shown:</span><span class="sxs-lookup"><span data-stu-id="25fca-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="25fca-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-168">**Date**</span></span>
  - <span data-ttu-id="25fca-169">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="25fca-169">**Sender address**</span></span>
  - <span data-ttu-id="25fca-170">**Шаблон шифрования**</span><span class="sxs-lookup"><span data-stu-id="25fca-170">**Encryption template**</span></span>
  - <span data-ttu-id="25fca-171">**Метод шифрования**</span><span class="sxs-lookup"><span data-stu-id="25fca-171">**Encryption method**</span></span>
  - <span data-ttu-id="25fca-172">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="25fca-172">**Recipient address**</span></span>
  - <span data-ttu-id="25fca-173">**Тема**</span><span class="sxs-lookup"><span data-stu-id="25fca-173">**Subject**</span></span>

- <span data-ttu-id="25fca-174">**Просмотр данных по: Топ-5 доменов получателей:**</span><span class="sxs-lookup"><span data-stu-id="25fca-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="25fca-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-175">**Date**</span></span>
  - <span data-ttu-id="25fca-176">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="25fca-176">**Recipient domain**</span></span>
  - <span data-ttu-id="25fca-177">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="25fca-177">**Message count**</span></span>

<span data-ttu-id="25fca-178">Если **щелкнуть Фильтры** в представлении таблицы сведений, результаты можно изменить следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="25fca-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="25fca-179">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="25fca-180">Метод шифрования</span><span class="sxs-lookup"><span data-stu-id="25fca-180">Encryption method</span></span>
- <span data-ttu-id="25fca-181">Шаблон шифрования</span><span class="sxs-lookup"><span data-stu-id="25fca-181">Encryption template</span></span>

<span data-ttu-id="25fca-182">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="25fca-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="25fca-183">Отчет о состоянии почтового потока</span><span class="sxs-lookup"><span data-stu-id="25fca-183">Mailflow status report</span></span>

<span data-ttu-id="25fca-184">Отчет **о состоянии mailflow содержит** сведения о вредоносных программах, спаме, фишинге и заблокированных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="25fca-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="25fca-185">Дополнительные сведения см. [в отчете о состоянии mailflow.](view-mail-flow-reports.md#mailflow-status-report)</span><span class="sxs-lookup"><span data-stu-id="25fca-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="25fca-186">Обнаружение вредоносных программ в отчете электронной почты</span><span class="sxs-lookup"><span data-stu-id="25fca-186">Malware detections in email report</span></span>

<span data-ttu-id="25fca-187">Обнаружение **вредоносных** программ в отчете электронной почты показывает сведения об обнаружении вредоносных программ в входящих и исходяющих сообщениях электронной почты (вредоносные программы, обнаруженные Exchange Online Protection или EOP).</span><span class="sxs-lookup"><span data-stu-id="25fca-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="25fca-188">Дополнительные сведения о защите от вредоносных программ в EOP см. в программе Защита от вредоносных [программ в EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="25fca-189">Совокупный фильтр представления позволяет в течение 90 дней, в то время как фильтр таблицы сведений разрешает только 10 дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="25fca-190">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и щелкните Сведения о просмотре в вредоносных программах, обнаруженных в электронной  \>  \>  **почте.** </span><span class="sxs-lookup"><span data-stu-id="25fca-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Malware detected in email**.</span></span> <span data-ttu-id="25fca-191">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="25fca-191">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Обнаружение вредоносных программ в виджете электронной почты на панели мониторинга Отчетов](../../media/malware-detections-widget.png)

<span data-ttu-id="25fca-193">Вы можете фильтровать диаграмму и таблицу сведений, щелкнув **фильтры** и выбрав:</span><span class="sxs-lookup"><span data-stu-id="25fca-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="25fca-194">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="25fca-195">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="25fca-195">**Inbound**</span></span>
- <span data-ttu-id="25fca-196">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="25fca-196">**Outbound**</span></span>

![Представление отчета в обнаружении вредоносных программ в отчете электронной почты](../../media/malware-detections-report-view.png)

<span data-ttu-id="25fca-198">Если **щелкнуть таблицу Просмотр** сведений, можно просмотреть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="25fca-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="25fca-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-199">**Date**</span></span>
- <span data-ttu-id="25fca-200">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="25fca-200">**Sender address**</span></span>
- <span data-ttu-id="25fca-201">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="25fca-201">**Recipient address**</span></span>
- <span data-ttu-id="25fca-202">**ID сообщения.** Доступно в **поле заглавной области Message-ID** в загонах сообщений и должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="25fca-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="25fca-203">Например, значение `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="25fca-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="25fca-204">**Тема**</span><span class="sxs-lookup"><span data-stu-id="25fca-204">**Subject**</span></span>
- <span data-ttu-id="25fca-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="25fca-205">**Filename**</span></span>
- <span data-ttu-id="25fca-206">**Имя вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="25fca-206">**Malware name**</span></span>

<span data-ttu-id="25fca-207">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="25fca-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="25fca-208">Отчет о задержке почты</span><span class="sxs-lookup"><span data-stu-id="25fca-208">Mail latency report</span></span>

<span data-ttu-id="25fca-209">Отчет **о задержке почты** содержит сведения о задержке доставки почты и детонации в организации.</span><span class="sxs-lookup"><span data-stu-id="25fca-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="25fca-210">Дополнительные сведения см. в [отчете о задержке почты.](view-reports-for-mdo.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="25fca-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="25fca-211">Отправленный и полученный отчет электронной почты</span><span class="sxs-lookup"><span data-stu-id="25fca-211">Sent and received email report</span></span>

<span data-ttu-id="25fca-212">Отчет **о отправленной** и полученной электронной почте содержит сведения о вредоносных программах, спаме, правилах потока почты (также известных как правила транспорта) и расширенных обнаружениях вредоносных программ после ввода электронной почты в службу.</span><span class="sxs-lookup"><span data-stu-id="25fca-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="25fca-213">Дополнительные сведения см. в [отчете по отправке и получению электронной почты.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="25fca-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="25fca-214">Отчет об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="25fca-214">Spam detections report</span></span>

<span data-ttu-id="25fca-215">В **отчете об обнаружении нежелательной** почты показаны сообщения электронной почты, заблокированные EOP.</span><span class="sxs-lookup"><span data-stu-id="25fca-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="25fca-216">Сообщения подсчитываются по отдельности, а не по каждому получателю.</span><span class="sxs-lookup"><span data-stu-id="25fca-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="25fca-217">Например, если одно и то же сообщение нежелательной почты было отправлено 100 получателям в организации, оно считается одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="25fca-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="25fca-218">Совокупное представление позволяет фильтровать в течение 90 дней, а в таблице сведений - 10 дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="25fca-219">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и нажмите кнопку Просмотр сведений в рамках обнаружения нежелательной почты  \>  \>   . </span><span class="sxs-lookup"><span data-stu-id="25fca-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click click **View details** under **Spam detections**.</span></span> <span data-ttu-id="25fca-220">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="25fca-220">To go directly to the report, open <https://security.microsoft.com/reports/SpamDetections>.</span></span>

![Виджет обнаружения нежелательной почты на панели мониторинга Отчетов](../../media/spam-detections-report-widget.png)

<span data-ttu-id="25fca-222">Дополнительные сведения о защите от нежелательной почты см. в сообщении [eOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="25fca-223">Представление отчета для отчета об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="25fca-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="25fca-224">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="25fca-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="25fca-225">**Break down by: Action:** Following event types are shown:</span><span class="sxs-lookup"><span data-stu-id="25fca-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="25fca-226">**Фильтрация контента нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="25fca-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="25fca-227">**Блокировка IP-адреса нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="25fca-227">**Spam IP block**</span></span>
  - <span data-ttu-id="25fca-228">**Блок конверта нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="25fca-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="25fca-229">**Фильтр DBEB нежелательной почты:** блокировка края на основе каталога (DBEB)</span><span class="sxs-lookup"><span data-stu-id="25fca-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="25fca-230">При наведении в течение дня (точки данных) на диаграмме можно увидеть, сколько элементов было заблокировано в этот день, а также то, как эти элементы классифицируются.</span><span class="sxs-lookup"><span data-stu-id="25fca-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Представление действий в отчете о обнаружениях нежелательной почты](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="25fca-232">**Break down by: Direction:** Following directions are shown:</span><span class="sxs-lookup"><span data-stu-id="25fca-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="25fca-233">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="25fca-233">**Inbound**</span></span>
  - <span data-ttu-id="25fca-234">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="25fca-234">**Outbound**</span></span>

  ![Представление направления в отчете о обнаружениях нежелательной почты](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="25fca-236">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="25fca-237">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="25fca-238">Значения направления</span><span class="sxs-lookup"><span data-stu-id="25fca-238">Direction values</span></span>
- <span data-ttu-id="25fca-239">Значения типа события</span><span class="sxs-lookup"><span data-stu-id="25fca-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="25fca-240">Представление таблицы сведений для отчета об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="25fca-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="25fca-241">Если вы **щелкните таблицу Просмотр** сведений в любом представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="25fca-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="25fca-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-242">**Date**</span></span>
- <span data-ttu-id="25fca-243">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="25fca-243">**Sender address**</span></span>
- <span data-ttu-id="25fca-244">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="25fca-244">**Recipient address**</span></span>
- <span data-ttu-id="25fca-245">**Тип события**</span><span class="sxs-lookup"><span data-stu-id="25fca-245">**Event type**</span></span>
- <span data-ttu-id="25fca-246">**Действие**</span><span class="sxs-lookup"><span data-stu-id="25fca-246">**Action**</span></span>
- <span data-ttu-id="25fca-247">**Тема**</span><span class="sxs-lookup"><span data-stu-id="25fca-247">**Subject**</span></span>

<span data-ttu-id="25fca-248">Если **щелкнуть фильтры** в таблице сведений, результаты можно изменить с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="25fca-249">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="25fca-250">Значения направления</span><span class="sxs-lookup"><span data-stu-id="25fca-250">Direction values</span></span>
- <span data-ttu-id="25fca-251">Значения типа события</span><span class="sxs-lookup"><span data-stu-id="25fca-251">Event type values</span></span>

<span data-ttu-id="25fca-252">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="25fca-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="25fca-253">Отчет об обнаружении подмены</span><span class="sxs-lookup"><span data-stu-id="25fca-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="25fca-254">Улучшенный отчет об обнаружении Spoof, описанный в этой статье, находится в предварительной версии, подлежит изменениям и доступен не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="25fca-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="25fca-255">Более старая версия отчета показывала только **хорошую** почту и **уловленную как spam.**</span><span class="sxs-lookup"><span data-stu-id="25fca-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="25fca-256">В **отчете о обнаружениях Spoof** показаны сведения о сообщениях, которые были заблокированы или разрешены из-за подмены.</span><span class="sxs-lookup"><span data-stu-id="25fca-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="25fca-257">Дополнительные сведения о подмене см. в этой информации в [EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="25fca-258">Совокупное представление отчета позволяет в течение 45 дней фильтрации, в то время как представление детализации позволяет фильтровать только десять <sup>\*</sup> дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="25fca-259"><sup>\*</sup> В конце концов, вы сможете использовать до 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="25fca-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="25fca-260">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и щелкните Сведения о просмотре в рамках обнаружения  \>  \>  **Spoof**. </span><span class="sxs-lookup"><span data-stu-id="25fca-260">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Spoof detections**.</span></span> <span data-ttu-id="25fca-261">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="25fca-261">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReport>.</span></span>

![Виджет обнаружения подмены в панели мониторинга Отчетов](../../media/spoof-detections-widget.png)

<span data-ttu-id="25fca-263">При наведении в течение дня (точки данных) на диаграмме можно увидеть, сколько поддельных сообщений было обнаружено и почему.</span><span class="sxs-lookup"><span data-stu-id="25fca-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="25fca-264">Вы можете фильтровать диаграмму и таблицу сведений, щелкнув **фильтры** и выбрав одно или несколько следующих значений:</span><span class="sxs-lookup"><span data-stu-id="25fca-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="25fca-265">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="25fca-266">**Результат**</span><span class="sxs-lookup"><span data-stu-id="25fca-266">**Result**</span></span>
  - <span data-ttu-id="25fca-267">**Pass**</span><span class="sxs-lookup"><span data-stu-id="25fca-267">**Pass**</span></span>
  - <span data-ttu-id="25fca-268">**Fail**</span><span class="sxs-lookup"><span data-stu-id="25fca-268">**Fail**</span></span>
  - <span data-ttu-id="25fca-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="25fca-269">**SoftPass**</span></span>
  - <span data-ttu-id="25fca-270">**Нет**</span><span class="sxs-lookup"><span data-stu-id="25fca-270">**None**</span></span>
  - <span data-ttu-id="25fca-271">**Other**</span><span class="sxs-lookup"><span data-stu-id="25fca-271">**Other**</span></span>

- <span data-ttu-id="25fca-272">**Тип Spoof:** **внутренний и** **внешний**</span><span class="sxs-lookup"><span data-stu-id="25fca-272">**Spoof type**: **Internal** and **External**</span></span>

![Представление отчета в отчете о обнаружениях Spoof](../../media/spoof-detections-report-view.png)

<span data-ttu-id="25fca-274">Если **щелкнуть таблицу Просмотр** сведений, можно просмотреть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="25fca-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="25fca-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-275">**Date**</span></span>
- <span data-ttu-id="25fca-276">**Подмена пользователя**</span><span class="sxs-lookup"><span data-stu-id="25fca-276">**Spoofed user**</span></span>
- <span data-ttu-id="25fca-277">**Отправка инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="25fca-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="25fca-278">**Тип Spoof**</span><span class="sxs-lookup"><span data-stu-id="25fca-278">**Spoof type**</span></span>
- <span data-ttu-id="25fca-279">**Результат**</span><span class="sxs-lookup"><span data-stu-id="25fca-279">**Result**</span></span>
- <span data-ttu-id="25fca-280">**Код результатов**</span><span class="sxs-lookup"><span data-stu-id="25fca-280">**Result code**</span></span>
- <span data-ttu-id="25fca-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="25fca-281">**SPF**</span></span>
- <span data-ttu-id="25fca-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="25fca-282">**DKIM**</span></span>
- <span data-ttu-id="25fca-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="25fca-283">**DMARC**</span></span>
- <span data-ttu-id="25fca-284">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="25fca-284">**Message count**</span></span>

<span data-ttu-id="25fca-285">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="25fca-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="25fca-286">Дополнительные сведения о сводных кодах результатов проверки подлинности см. в материале [Anti-spam message headers in Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="25fca-287">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="25fca-287">Threat protection status report</span></span>

<span data-ttu-id="25fca-288">Отчет **о состоянии защиты от** угроз доступен в EOP и Microsoft Defender для Office 365; однако отчеты содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="25fca-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="25fca-289">Например, клиенты EOP могут просматривать сведения о вредоносных программах, обнаруженных в электронной почте, но не сведения о вредоносных файлах, обнаруженных Сейф вложениями для [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)и Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="25fca-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="25fca-290">В отчете приводится количество сообщений электронной почты со вредоносным контентом, например файлов или веб-адресов (URL-адресов), заблокированных с помощью двигателя защиты от вредоносных программ, автоматической очистки нулевого часа [(ZAP)](zero-hour-auto-purge.md)и функций Defender для Office 365, таких как [Сейф Links,](safe-links.md) [Сейф Attachments](safe-attachments.md)и [Anti-phishing](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="25fca-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="25fca-291">Эти сведения можно использовать для определения тенденций или определения необходимости корректировки политик организации.</span><span class="sxs-lookup"><span data-stu-id="25fca-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="25fca-292">**Примечание.** Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="25fca-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="25fca-293">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и щелкните Сведения о просмотре в состоянии защиты от  \>  \>  **угроз.** </span><span class="sxs-lookup"><span data-stu-id="25fca-293">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Threat protection status**.</span></span> <span data-ttu-id="25fca-294">Чтобы перейти непосредственно к отчету, откройте один из следующих URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="25fca-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="25fca-295">Microsoft Defender для Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="25fca-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="25fca-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="25fca-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Виджет состояния защиты от угроз в панели мониторинга Отчетов](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="25fca-298">По умолчанию на диаграмме показаны данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="25fca-299">При **нажатии фильтров** можно выбрать диапазон дат в 90 дней (пробная подписка может быть ограничена 30 днями).</span><span class="sxs-lookup"><span data-stu-id="25fca-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="25fca-300">Представление таблицы сведений позволяет фильтровать в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="25fca-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="25fca-301">Представление отчета для отчета о состоянии защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="25fca-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="25fca-302">Доступны перечисленные ниже представления.</span><span class="sxs-lookup"><span data-stu-id="25fca-302">The following views are available:</span></span>

- <span data-ttu-id="25fca-303">**Просмотр данных по: Обзор:** Показаны следующие сведения об обнаружении:</span><span class="sxs-lookup"><span data-stu-id="25fca-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="25fca-304">**Вредоносные программы электронной почты**</span><span class="sxs-lookup"><span data-stu-id="25fca-304">**Email malware**</span></span>
  - <span data-ttu-id="25fca-305">**Фишинг электронной почты**</span><span class="sxs-lookup"><span data-stu-id="25fca-305">**Email phish**</span></span>
  - <span data-ttu-id="25fca-306">**Вредоносные программы контента**</span><span class="sxs-lookup"><span data-stu-id="25fca-306">**Content malware**</span></span>

  ![Обзор представления в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="25fca-308">**Просмотр данных по: Контент \> Вредоносные**<sup>программы 1.</sup>Следующие сведения показаны для Microsoft Defender для Office 365 организаций:</span><span class="sxs-lookup"><span data-stu-id="25fca-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="25fca-309">**Антивирусный** двигатель: вредоносные файлы, обнаруженные в Sharepoint, OneDrive и Microsoft Teams с помощью встроенного обнаружения вирусов в [Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="25fca-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="25fca-310">**Детонация** файлов: вредоносные файлы, обнаруженные Сейф вложениями для [SharePoint, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="25fca-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Просмотр вредоносных программ контента в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="25fca-312">**Просмотр данных по: Переопределения** сообщений: показана следующая информация о причинах переопределения:</span><span class="sxs-lookup"><span data-stu-id="25fca-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="25fca-313">**Локальное пропустить**</span><span class="sxs-lookup"><span data-stu-id="25fca-313">**On-premises skip**</span></span>
  - <span data-ttu-id="25fca-314">**РАЗРЕШЕНИЕ IP**</span><span class="sxs-lookup"><span data-stu-id="25fca-314">**IP Allow**</span></span>
  - <span data-ttu-id="25fca-315">**Правило потока почты**</span><span class="sxs-lookup"><span data-stu-id="25fca-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="25fca-316">**Разрешить отправитель**</span><span class="sxs-lookup"><span data-stu-id="25fca-316">**Sender allow**</span></span>
  - <span data-ttu-id="25fca-317">**Разрешить домен**</span><span class="sxs-lookup"><span data-stu-id="25fca-317">**Domain allow**</span></span>
  - <span data-ttu-id="25fca-318">**ZAP не включен**</span><span class="sxs-lookup"><span data-stu-id="25fca-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="25fca-319">**Папка нежелательной почты не включена**</span><span class="sxs-lookup"><span data-stu-id="25fca-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="25fca-320">**Отправитель Сейф пользователя**</span><span class="sxs-lookup"><span data-stu-id="25fca-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="25fca-321">**Домен пользователя Сейф**</span><span class="sxs-lookup"><span data-stu-id="25fca-321">**User Safe Domain**</span></span>

  ![Представление переопределения сообщений в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="25fca-323">**Break down by: Detection technology** and **View data by: Email \> Phish:** Following information is shown:</span><span class="sxs-lookup"><span data-stu-id="25fca-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="25fca-324">**Репутация URL-адреса,** созданная <sup>atP, 1:</sup>вредоносная репутация URL-адреса, созданная в Defender для Office 365 в других Microsoft 365 клиентах.</span><span class="sxs-lookup"><span data-stu-id="25fca-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="25fca-325">**Расширенный фильтр фишинга:** фишинговые сигналы на основе машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="25fca-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="25fca-326">**Отказ от подмены — Сбой DMARC:** сбой проверки подлинности DMARC в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="25fca-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="25fca-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span><span class="sxs-lookup"><span data-stu-id="25fca-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="25fca-328">**Anti-spoof — внешний домен.** Отправитель пытается подменить другой домен.</span><span class="sxs-lookup"><span data-stu-id="25fca-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="25fca-329">**Вымысление** бренда: обезличение известных брендов на основе отправителей.</span><span class="sxs-lookup"><span data-stu-id="25fca-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="25fca-330">**Вымысление** домена <sup>1.</sup>Вымысление доменов, которые клиент владеет или определяет.</span><span class="sxs-lookup"><span data-stu-id="25fca-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="25fca-331">**Репутация URL-адреса EOP.** Репутация вредоносного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="25fca-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="25fca-332">**Общий фильтр фишинга:** фишинговые сигналы, основанные на правилах аналитика.</span><span class="sxs-lookup"><span data-stu-id="25fca-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="25fca-333">**Другие**</span><span class="sxs-lookup"><span data-stu-id="25fca-333">**Others**</span></span>
  - <span data-ttu-id="25fca-334">**Phish ZAP**<sup>2.</sup>Автоматическая очистка фишинговых сообщений нулевого часа.</span><span class="sxs-lookup"><span data-stu-id="25fca-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="25fca-335">**Детонация URL-адреса**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25fca-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="25fca-336">**Выдаваемая пользователем**<sup>1.</sup>Вымысление пользователей, определенных администратором или выучатся с помощью разведки почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="25fca-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Представление технологии обнаружения фишинговой электронной почты в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="25fca-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: Following information is shown:</span><span class="sxs-lookup"><span data-stu-id="25fca-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="25fca-339">**Репутация файлов, созданных atP**<sup>1:</sup>вся репутация вредоносных файлов, созданная Defender для Office 365 детонации.</span><span class="sxs-lookup"><span data-stu-id="25fca-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="25fca-340">**Антивирусный двигатель**<sup>1:</sup>Обнаружение с антивирусных двигателей.</span><span class="sxs-lookup"><span data-stu-id="25fca-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="25fca-341">Блок типа файлов политики по борьбе с вредоносными программами. Это сообщения электронной почты, отфильтрованные **из-за** типа вредоносного файла, выявленного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="25fca-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="25fca-342">**Детонация файла**<sup>1.</sup>Обнаружение Сейф вложения.</span><span class="sxs-lookup"><span data-stu-id="25fca-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="25fca-343">**Репутация вредоносных файлов**</span><span class="sxs-lookup"><span data-stu-id="25fca-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="25fca-344">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="25fca-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="25fca-345">**Другие**</span><span class="sxs-lookup"><span data-stu-id="25fca-345">**Others**</span></span>

  ![Представление технологии обнаружения вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="25fca-347">**Break down by: Policy type** and View data by: Email Phish or **View data by: Email \> Malware:** Following information is shown: **\>**</span><span class="sxs-lookup"><span data-stu-id="25fca-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="25fca-348">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="25fca-348">**Anti-malware**</span></span>
  - <span data-ttu-id="25fca-349">**Сейф вложения**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25fca-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="25fca-350">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="25fca-350">**Anti-phish**</span></span>
  - <span data-ttu-id="25fca-351">**Противодействие нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="25fca-351">**Anti-spam**</span></span>
  - <span data-ttu-id="25fca-352">**Правило потока почты** (также известное как правило транспорта)</span><span class="sxs-lookup"><span data-stu-id="25fca-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="25fca-353">**Другие**</span><span class="sxs-lookup"><span data-stu-id="25fca-353">**Others**</span></span>

  ![Вид типа политики для фишинга электронной почты в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="25fca-355">**Break down by: Delivery status** and View data by: Email Phish or **View data by: Email \> Malware:** Following information is shown: **\>**</span><span class="sxs-lookup"><span data-stu-id="25fca-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="25fca-356">**Сбой доставки**</span><span class="sxs-lookup"><span data-stu-id="25fca-356">**Delivery failed**</span></span>
  - <span data-ttu-id="25fca-357">**Сброс**</span><span class="sxs-lookup"><span data-stu-id="25fca-357">**Dropped**</span></span>
  - <span data-ttu-id="25fca-358">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="25fca-358">**Forwarded**</span></span>
  - <span data-ttu-id="25fca-359">**Хост-почтовый ящик: настраиваемая папка**</span><span class="sxs-lookup"><span data-stu-id="25fca-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="25fca-360">**Хост-почтовый ящик: удаленные элементы**</span><span class="sxs-lookup"><span data-stu-id="25fca-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="25fca-361">**Хост-почтовый ящик: Почтовый ящик**</span><span class="sxs-lookup"><span data-stu-id="25fca-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="25fca-362">**Хост-почтовый ящик: нежелательной**</span><span class="sxs-lookup"><span data-stu-id="25fca-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="25fca-363">**Локального сервера: Доставлено**</span><span class="sxs-lookup"><span data-stu-id="25fca-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="25fca-364">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="25fca-364">**Quarantine**</span></span>

  ![Представление состояния доставки для фишинговой электронной почты в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="25fca-366"><sup>1</sup> Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="25fca-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="25fca-367"><sup>Авточистка 2</sup> zero-hour (ZAP) недоступна в автономных EOP (она работает только в Exchange Online почтовых ящиках).</span><span class="sxs-lookup"><span data-stu-id="25fca-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="25fca-368">Если щелкнуть **фильтры,** доступные фильтры зависят от диаграммы, на которая вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="25fca-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="25fca-369">Для **просмотра данных по: Вредоносные программы \>** контента , вы можете изменить отчет к **дате** начала и даты **окончания,** и **значение обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="25fca-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="25fca-370">Для **просмотра данных по: Переопределения сообщений** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="25fca-371">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="25fca-372">**Причина переопределения**</span><span class="sxs-lookup"><span data-stu-id="25fca-372">**Override Reason**</span></span>
  - <span data-ttu-id="25fca-373">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="25fca-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="25fca-374">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="25fca-375">**Домен**</span><span class="sxs-lookup"><span data-stu-id="25fca-375">**Domain**</span></span>

- <span data-ttu-id="25fca-376">Для всех остальных представлений можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="25fca-377">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="25fca-378">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="25fca-378">**Detection**</span></span>
  - <span data-ttu-id="25fca-379">**Защищено**: **ATP** или **EOP**</span><span class="sxs-lookup"><span data-stu-id="25fca-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="25fca-380">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="25fca-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="25fca-381">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="25fca-382">**Домен**</span><span class="sxs-lookup"><span data-stu-id="25fca-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="25fca-383">Представление таблицы сведений для отчета о состоянии защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="25fca-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="25fca-384">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="25fca-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="25fca-385">**Просмотр данных по: Обзор.** **Кнопка "Сведения о представлении"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="25fca-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="25fca-386">**Просмотр данных по: Контент \> Вредоносные** программы:</span><span class="sxs-lookup"><span data-stu-id="25fca-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="25fca-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-387">**Date**</span></span>
  - <span data-ttu-id="25fca-388">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="25fca-388">**Location**</span></span>
  - <span data-ttu-id="25fca-389">**Режиссер**</span><span class="sxs-lookup"><span data-stu-id="25fca-389">**Directed by**</span></span>
  - <span data-ttu-id="25fca-390">**Имя вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="25fca-390">**Malware name**</span></span>

  <span data-ttu-id="25fca-391">При  **нажатии фильтров** в этом представлении можно изменить отчет к дате начала и дате окончания **и** значению **Detection.**</span><span class="sxs-lookup"><span data-stu-id="25fca-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="25fca-392">**Просмотр данных по: Переопределения сообщений:**</span><span class="sxs-lookup"><span data-stu-id="25fca-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="25fca-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-393">**Date**</span></span>
  - <span data-ttu-id="25fca-394">**Тема**</span><span class="sxs-lookup"><span data-stu-id="25fca-394">**Subject**</span></span>
  - <span data-ttu-id="25fca-395">**Sender**</span><span class="sxs-lookup"><span data-stu-id="25fca-395">**Sender**</span></span>
  - <span data-ttu-id="25fca-396">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="25fca-396">**Recipients**</span></span>
  - <span data-ttu-id="25fca-397">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="25fca-397">**Detected by**</span></span>
  - <span data-ttu-id="25fca-398">**Причина переопределения**</span><span class="sxs-lookup"><span data-stu-id="25fca-398">**Override Reason**</span></span>
  - <span data-ttu-id="25fca-399">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="25fca-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="25fca-400">**Tags**</span><span class="sxs-lookup"><span data-stu-id="25fca-400">**Tags**</span></span>

  <span data-ttu-id="25fca-401">При **нажатии фильтров** в этом представлении можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="25fca-402">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="25fca-403">**Причина переопределения**</span><span class="sxs-lookup"><span data-stu-id="25fca-403">**Override Reason**</span></span>
  - <span data-ttu-id="25fca-404">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="25fca-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="25fca-405">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="25fca-406">**Домен**</span><span class="sxs-lookup"><span data-stu-id="25fca-406">**Domain**</span></span>
  - <span data-ttu-id="25fca-407">**Получатели** (Обратите внимание, что это фильтруемое свойство доступно только в представлении таблицы сведений)</span><span class="sxs-lookup"><span data-stu-id="25fca-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="25fca-408">Все остальные диаграммы:</span><span class="sxs-lookup"><span data-stu-id="25fca-408">All other charts:</span></span>

  - <span data-ttu-id="25fca-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="25fca-409">**Date**</span></span>
  - <span data-ttu-id="25fca-410">**Тема**</span><span class="sxs-lookup"><span data-stu-id="25fca-410">**Subject**</span></span>
  - <span data-ttu-id="25fca-411">**Sender**</span><span class="sxs-lookup"><span data-stu-id="25fca-411">**Sender**</span></span>
  - <span data-ttu-id="25fca-412">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="25fca-412">**Recipients**</span></span>
  - <span data-ttu-id="25fca-413">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="25fca-413">**Detected by**</span></span>
  - <span data-ttu-id="25fca-414">**Состояние доставки**</span><span class="sxs-lookup"><span data-stu-id="25fca-414">**Delivery Status**</span></span>
  - <span data-ttu-id="25fca-415">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="25fca-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="25fca-416">**Tags**</span><span class="sxs-lookup"><span data-stu-id="25fca-416">**Tags**</span></span>

  <span data-ttu-id="25fca-417">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="25fca-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="25fca-418">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="25fca-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="25fca-419">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="25fca-419">**Detection**</span></span>
  - <span data-ttu-id="25fca-420">**Защищено**: **Defender для Office 365** **или EOP**</span><span class="sxs-lookup"><span data-stu-id="25fca-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="25fca-421">**Тег.** Фильтр результатов пользователями или группами с указанным тегом пользователя (включая учетные записи приоритета).</span><span class="sxs-lookup"><span data-stu-id="25fca-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="25fca-422">Дополнительные сведения о тегах пользователей см. в [тегах пользователей.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="25fca-423">**Домен**</span><span class="sxs-lookup"><span data-stu-id="25fca-423">**Domain**</span></span>
  - <span data-ttu-id="25fca-424">**Получатели** (Обратите внимание, что это фильтруемое свойство доступно только в представлении таблицы сведений)</span><span class="sxs-lookup"><span data-stu-id="25fca-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="25fca-425">Топ отчета о вредоносных программах</span><span class="sxs-lookup"><span data-stu-id="25fca-425">Top malware report</span></span>

<span data-ttu-id="25fca-426">В **топовом отчете** о вредоносных программах показаны различные виды вредоносных программ, обнаруженных защитой от вредоносных программ [в EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="25fca-427">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и щелкните Сведения о просмотре в статье  \>  \>  **Top malware**. </span><span class="sxs-lookup"><span data-stu-id="25fca-427">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Top malware**.</span></span> <span data-ttu-id="25fca-428">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="25fca-428">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Топ-виджет вредоносных программ на панели мониторинга Отчетов](../../media/top-malware-report-widget.png)

<span data-ttu-id="25fca-430">При наведении на клин в диаграмме пирога можно увидеть имя типа вредоносных программ и количество сообщений, обнаруженных как наличие этого вредоносного ПО.</span><span class="sxs-lookup"><span data-stu-id="25fca-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Представление отчета о вредоносных программах](../../media/top-malware-report-view.png)

<span data-ttu-id="25fca-432">Если **щелкнуть таблицу Просмотр** сведений, можно просмотреть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="25fca-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="25fca-433">**Топ вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="25fca-433">**Top malware**</span></span>
- <span data-ttu-id="25fca-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="25fca-434">**Count**</span></span>

<span data-ttu-id="25fca-435">Если щелкнуть **фильтры** в представлении отчета или представлении  таблицы сведений, можно указать диапазон дат с датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="25fca-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="25fca-436">Отчет об угрозе URL-адреса</span><span class="sxs-lookup"><span data-stu-id="25fca-436">URL threat protection report</span></span>

<span data-ttu-id="25fca-437">Отчет **об угрозе** URL-адресов доступен в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="25fca-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="25fca-438">Дополнительные сведения см. в [отчете об угрозе URL-адреса.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="25fca-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="25fca-439">Отчет о сообщениях пользователя</span><span class="sxs-lookup"><span data-stu-id="25fca-439">User reported messages report</span></span>

<span data-ttu-id="25fca-440">Отчет **о** сообщениях пользователя показывает сведения о сообщениях электронной почты, которые пользователи сообщали как нежелательные, фишинговые попытки или хорошая почта с помощью надстройки Report [Message](enable-the-report-message-add-in.md) или надстройки [Report Phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="25fca-440">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="25fca-441">Сведения доступны для каждого сообщения, включая причину доставки, исключение политики нежелательной почты или правило потока почты, настроенное для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="25fca-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="25fca-442">Чтобы просмотреть сведения, выберите элемент в списке отчетов пользователей, а затем просмотреть сведения на вкладке **Сводка** **и** Сведения.</span><span class="sxs-lookup"><span data-stu-id="25fca-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![В отчете о сообщениях пользователя показаны сообщения, помеченные пользователями как нежелательные, а не нежелательные или фишинговые попытки.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="25fca-444">Чтобы просмотреть этот отчет, на [портале Microsoft 365 Defender](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & сообщения о совместной работе.  \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="25fca-444">To view this report, in the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span>

- <span data-ttu-id="25fca-445">Перейдите **в отчеты** электронной \> **почты & совместной** & \> **отчеты** о совместной работе \> **Сообщения пользователя сообщений**.</span><span class="sxs-lookup"><span data-stu-id="25fca-445">Go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span></span>

![На портале Microsoft 365 Defender выберите сообщения электронной почты & совместной & сообщений о \> \> \> совместной работе.](../../media/user-reported-messages.png)

> [!IMPORTANT]
> <span data-ttu-id="25fca-447">Чтобы отчет о сообщениях пользователя работал **правильно,** необходимо ввести журнал аудита для Office 365 среды.</span><span class="sxs-lookup"><span data-stu-id="25fca-447">In order for the User reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="25fca-448">Обычно это делается тем, кто имеет роль журналов аудита, назначенную в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="25fca-448">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="25fca-449">Дополнительные сведения см. в Microsoft 365 поиска журнала [аудита.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-449">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="25fca-450">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="25fca-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="25fca-451">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей на портале Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="25fca-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="25fca-452">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="25fca-452">**Organization Management**</span></span>
- <span data-ttu-id="25fca-453">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="25fca-453">**Security Administrator**</span></span>
- <span data-ttu-id="25fca-454">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="25fca-454">**Security Reader**</span></span>
- <span data-ttu-id="25fca-455">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="25fca-455">**Global Reader**</span></span>

<span data-ttu-id="25fca-456">Дополнительные сведения см. [в сайте Permissions in the Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-456">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="25fca-457">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в центре администрирования Microsoft 365 предоставляет пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25fca-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="25fca-458">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="25fca-458">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="25fca-459">Что делать, если отчеты не отображают данные?</span><span class="sxs-lookup"><span data-stu-id="25fca-459">What if the reports aren't showing data?</span></span>

<span data-ttu-id="25fca-460">Если в отчетах нет данных, убедитесь, что политики настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="25fca-460">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="25fca-461">Дополнительные новости см. в [см. в руберсе Защита от угроз.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="25fca-461">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="25fca-462">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="25fca-462">Related topics</span></span>

[<span data-ttu-id="25fca-463">Защита от нежелательной почты и вредоносных программ в EOP</span><span class="sxs-lookup"><span data-stu-id="25fca-463">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="25fca-464">Интеллектуальные отчеты и сведения на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25fca-464">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="25fca-465">Просмотр отчетов о потоке почты на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25fca-465">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="25fca-466">Просмотр отчетов для Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="25fca-466">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
