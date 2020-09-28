---
title: Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Узнайте, как найти и использовать отчеты по обеспечению безопасности электронной почты для вашей организации. Отчеты о безопасности электронной почты доступны в центре безопасности & соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b26dd18754a96d1879a2f57ae9742ae1d1a36ce4
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295542"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="9535b-104">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9535b-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9535b-105">В [центре безопасности & соответствия](https://protection.office.com) доступны разнообразные отчеты, которые помогут вам понять, как функции безопасности электронной почты, такие как защита от нежелательной почты, защита от вредоносных программ и функции шифрования в Microsoft 365 защищают вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="9535b-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="9535b-106">Если у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-these-reports), вы можете просмотреть эти отчеты в центре безопасности & соответствия требованиям, перейдя **Reports** на \> **панель мониторинга**отчетов.</span><span class="sxs-lookup"><span data-stu-id="9535b-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="9535b-107">Чтобы перейти непосредственно к панели мониторинга отчетов, откройте ее <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="9535b-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="9535b-109">Отчет о скомпрометированных пользователях</span><span class="sxs-lookup"><span data-stu-id="9535b-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="9535b-110">Этот отчет доступен в организациях Microsoft 365 с почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9535b-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="9535b-111">Она недоступна в отдельных организациях Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="9535b-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="9535b-112">В отчете **скомпрометированные пользователи** отображается количество учетных записей пользователей, которые были помечены как **подозрительные** или **ограниченные** в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="9535b-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="9535b-113">Учетные записи в любом из этих состояний являются проблематичными или даже скомпрометированными.</span><span class="sxs-lookup"><span data-stu-id="9535b-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="9535b-114">При частом использовании отчет можно использовать для выявления пиков и даже тенденций в подозрительных или ограниченных учетных записях.</span><span class="sxs-lookup"><span data-stu-id="9535b-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="9535b-115">Дополнительные сведения о скомпрометированных пользователях можно узнать [в разделе ответ на скомпрометированную учетную запись электронной почты](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Мини-приложение "скомпрометированные пользователи" в панели мониторинга отчетов](../../media/compromised-users-report-widget.png)

<span data-ttu-id="9535b-117">В статистическом представлении отображаются данные за последние 90 дней, а в подробном представлении отображаются данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="9535b-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="9535b-118">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **скомпрометированных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="9535b-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="9535b-119">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="9535b-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="9535b-120">Вы можете отфильтровать как диаграмму, так и таблицу сведений, щелкнув **фильтры** и выбрав одно или несколько из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9535b-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="9535b-121">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="9535b-122">**Подозрительные**: учетная запись пользователя отправила подозрительные сообщения электронной почты и подвержена неограниченной отправке электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9535b-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="9535b-123">**Ограничено**: учетной записи пользователя запрещено отправлять электронную почту из-за очень подозрительных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9535b-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Представление отчета в отчете "скомпрометированные пользователи"](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="9535b-125">Если щелкнуть **Таблица Просмотр сведений**, можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9535b-126">**Время создания**</span><span class="sxs-lookup"><span data-stu-id="9535b-126">**Creation time**</span></span>
- <span data-ttu-id="9535b-127">**Идентификатор пользователя**</span><span class="sxs-lookup"><span data-stu-id="9535b-127">**User ID**</span></span>
- <span data-ttu-id="9535b-128">**Действие**</span><span class="sxs-lookup"><span data-stu-id="9535b-128">**Action**</span></span>

<span data-ttu-id="9535b-129">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="9535b-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="9535b-130">Отчет о шифровании</span><span class="sxs-lookup"><span data-stu-id="9535b-130">Encryption report</span></span>

<span data-ttu-id="9535b-131">**Отчет о шифровании** доступен в EOP (подписка на почтовые ящики в Exchange Online или отдельном EOP без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9535b-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="9535b-132">Группа безопасности Организации может использовать сведения из этого отчета для определения шаблонов и профилактического применения или настройки политик для конфиденциальных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9535b-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="9535b-133">Например:</span><span class="sxs-lookup"><span data-stu-id="9535b-133">For example:</span></span>

- <span data-ttu-id="9535b-134">Если вы видите большое количество сообщений электронной почты, зашифрованных пользователями, может потребоваться добавить политику шифрования для автоматизации шифрования для определенных вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="9535b-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="9535b-135">Для получения дополнительных сведений см. [Определение правил для почтового процесса для шифрования сообщений электронной почты в Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="9535b-136">Если у вас есть доступ к шаблонам шифрования, но никто их не использует, вы можете узнать, нужна ли для пользователей обучение функций.</span><span class="sxs-lookup"><span data-stu-id="9535b-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="9535b-137">Представление "Статистическая поддержка" позволяет фильтровать данные за последние 90 дней, в то время как в представлении Detailing допускается фильтрация в течение 10 дней.</span><span class="sxs-lookup"><span data-stu-id="9535b-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="9535b-138">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите пункт " **отчет о шифровании**".</span><span class="sxs-lookup"><span data-stu-id="9535b-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="9535b-139">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="9535b-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="9535b-140">Дополнительные сведения о шифровании приведены [в разделе Шифрование электронной почты в Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="9535b-141">Представление отчета для отчета о шифровании</span><span class="sxs-lookup"><span data-stu-id="9535b-141">Report view for the Encryption report</span></span>

<span data-ttu-id="9535b-142">На диаграмме можно использовать следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="9535b-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="9535b-143">**Просмотр данных по: отчет о шифровании сообщений** и **разбивка по: метод шифрования**: доступны следующие методы шифрования:</span><span class="sxs-lookup"><span data-stu-id="9535b-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="9535b-144">**Шифрование пользователем**</span><span class="sxs-lookup"><span data-stu-id="9535b-144">**Encryption by user**</span></span>
  - <span data-ttu-id="9535b-145">**Шифрование с помощью политики**</span><span class="sxs-lookup"><span data-stu-id="9535b-145">**Encryption by policy**</span></span>

  <span data-ttu-id="9535b-146">При нажатии кнопки **фильтры**можно изменить диаграмму с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="9535b-147">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9535b-148">Метод шифрования.</span><span class="sxs-lookup"><span data-stu-id="9535b-148">Encryption method.</span></span>
  - <span data-ttu-id="9535b-149">Шаблон шифрования.</span><span class="sxs-lookup"><span data-stu-id="9535b-149">Encryption template.</span></span>

- <span data-ttu-id="9535b-150">**Просмотр данных по: отчет о шифровании сообщений** и **разбивка по: шаблон шифрования**: доступны следующие методы шифрования:</span><span class="sxs-lookup"><span data-stu-id="9535b-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="9535b-151">**Не пересылать**</span><span class="sxs-lookup"><span data-stu-id="9535b-151">**Do not forward**</span></span>
  - <span data-ttu-id="9535b-152">**Только шифрование**</span><span class="sxs-lookup"><span data-stu-id="9535b-152">**Encrypt only**</span></span>
  - <span data-ttu-id="9535b-153">**OME Previous**</span><span class="sxs-lookup"><span data-stu-id="9535b-153">**OME previous**</span></span>
  - <span data-ttu-id="9535b-154">**Custom**</span><span class="sxs-lookup"><span data-stu-id="9535b-154">**Custom**</span></span>

  <span data-ttu-id="9535b-155">При нажатии кнопки **фильтры**можно изменить диаграмму с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="9535b-156">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9535b-157">Метод шифрования</span><span class="sxs-lookup"><span data-stu-id="9535b-157">Encryption method</span></span>
  - <span data-ttu-id="9535b-158">Шаблон шифрования</span><span class="sxs-lookup"><span data-stu-id="9535b-158">Encryption template</span></span>

- <span data-ttu-id="9535b-159">**Просмотр данных: пять доменов получателей**: в этом представлении отображается круговая диаграмма с числом отправленных сообщений для топ 5 доменов получателей.</span><span class="sxs-lookup"><span data-stu-id="9535b-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="9535b-160">При нажатии кнопки **фильтры**можно **выбрать начальную и** **конечную**даты.</span><span class="sxs-lookup"><span data-stu-id="9535b-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="9535b-161">Представление таблицы сведений для отчета о шифровании</span><span class="sxs-lookup"><span data-stu-id="9535b-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="9535b-162">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="9535b-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9535b-163">**Разбейте на: метод шифрования** или **разбивка по: шаблон шифрования**: отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="9535b-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="9535b-164">**Date**</span></span>
  - <span data-ttu-id="9535b-165">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="9535b-165">**Sender address**</span></span>
  - <span data-ttu-id="9535b-166">**Шаблон шифрования**</span><span class="sxs-lookup"><span data-stu-id="9535b-166">**Encryption template**</span></span>
  - <span data-ttu-id="9535b-167">**Метод шифрования**</span><span class="sxs-lookup"><span data-stu-id="9535b-167">**Encryption method**</span></span>
  - <span data-ttu-id="9535b-168">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="9535b-168">**Recipient address**</span></span>
  - <span data-ttu-id="9535b-169">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9535b-169">**Subject**</span></span>

- <span data-ttu-id="9535b-170">**Просмотр данных: 5 самых популярных доменов получателей**:</span><span class="sxs-lookup"><span data-stu-id="9535b-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="9535b-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="9535b-171">**Date**</span></span>
  - <span data-ttu-id="9535b-172">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="9535b-172">**Recipient domain**</span></span>
  - <span data-ttu-id="9535b-173">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="9535b-173">**Message count**</span></span>
  
<span data-ttu-id="9535b-174">Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9535b-175">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="9535b-176">Метод шифрования</span><span class="sxs-lookup"><span data-stu-id="9535b-176">Encryption method</span></span>
- <span data-ttu-id="9535b-177">Шаблон шифрования</span><span class="sxs-lookup"><span data-stu-id="9535b-177">Encryption template</span></span>

<span data-ttu-id="9535b-178">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="9535b-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="9535b-179">Отчет о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="9535b-179">Mailflow status report</span></span>

<span data-ttu-id="9535b-180">В **отчете о состоянии Mailflow** содержатся сведения о вредоносных и нежелательных сообщениях, фишинговых сообщениях и пограничных блокировках сообщений.</span><span class="sxs-lookup"><span data-stu-id="9535b-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="9535b-181">Для получения дополнительных сведений обратитесь к [отчету о состоянии Mailflow](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="9535b-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="9535b-182">Обнаружение вредоносных программ в отчете электронной почты</span><span class="sxs-lookup"><span data-stu-id="9535b-182">Malware detections in email report</span></span>

<span data-ttu-id="9535b-183">В отчете об **обнаружении вредоносных программ в сообщении электронной почты** отображаются сведения об обнаружении вредоносных программ в входящих и исходящих сообщениях электронной почты (вредоносная программа, обнаруженная Exchange Online Protection или EOP).</span><span class="sxs-lookup"><span data-stu-id="9535b-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="9535b-184">Дополнительные сведения о защите от вредоносных программ в EOP можно найти [в статье Защита от вредоносных программ в EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="9535b-185">Фильтр представления статистических данных допускает 90 дней, в то время как фильтр таблицы сведений разрешает только 10 дней.</span><span class="sxs-lookup"><span data-stu-id="9535b-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="9535b-186">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите на **Reports** \> **панель мониторинга** отчетов и выберите **Обнаружение вредоносных программ в электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="9535b-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="9535b-187">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="9535b-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Обнаружение вредоносных программ в мини-приложении "почта" на панели мониторинга отчетов](../../media/malware-detections-widget.png)

<span data-ttu-id="9535b-189">Вы можете отфильтровать как диаграмму, так и таблицу сведений, щелкнув **фильтры** и выбрав:</span><span class="sxs-lookup"><span data-stu-id="9535b-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="9535b-190">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="9535b-191">**Получение**</span><span class="sxs-lookup"><span data-stu-id="9535b-191">**Inbound**</span></span>
- <span data-ttu-id="9535b-192">**Прав**</span><span class="sxs-lookup"><span data-stu-id="9535b-192">**Outbound**</span></span>

![Представление отчета об обнаружении вредоносных программ в отчете электронной почты](../../media/malware-detections-report-view.png)

<span data-ttu-id="9535b-194">Если щелкнуть **Таблица Просмотр сведений**, можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9535b-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="9535b-195">**Date**</span></span>
- <span data-ttu-id="9535b-196">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="9535b-196">**Sender address**</span></span>
- <span data-ttu-id="9535b-197">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="9535b-197">**Recipient address**</span></span>
- <span data-ttu-id="9535b-198">**Идентификатор сообщения**: доступен в поле заголовка **Message — ID** в заголовке сообщения и должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="9535b-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="9535b-199">Пример значения: `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="9535b-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="9535b-200">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9535b-200">**Subject**</span></span>
- <span data-ttu-id="9535b-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="9535b-201">**Filename**</span></span>
- <span data-ttu-id="9535b-202">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="9535b-202">**Malware name**</span></span>

<span data-ttu-id="9535b-203">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="9535b-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="9535b-204">Отчет о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="9535b-204">Sent and received email report</span></span>

<span data-ttu-id="9535b-205">Отчет о **отправленных и полученных сообщениях** содержит сведения о вредоносных и нежелательных сообщениях, правилах обработки почты (также называемых правилами транспорта) и расширенные обнаружения вредоносных программ после того, как электронная почта поступает в службу.</span><span class="sxs-lookup"><span data-stu-id="9535b-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="9535b-206">Дополнительные сведения [см.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="9535b-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="9535b-207">Отчет об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="9535b-207">Spam detections report</span></span>

<span data-ttu-id="9535b-208">В отчете **обнаружения нежелательной почты** отображаются нежелательные сообщения электронной почты, заблокированные EOP.</span><span class="sxs-lookup"><span data-stu-id="9535b-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="9535b-209">Сообщения учитываются по отдельности, а не по получателям.</span><span class="sxs-lookup"><span data-stu-id="9535b-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="9535b-210">Например, если одно и то же нежелательное сообщение было отправлено в 100 получателей в Организации, оно считается одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="9535b-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="9535b-211">Представление "Статистическое представление" допускает фильтрацию 90 дней, а таблица сведений разрешает фильтрацию на 10 дней.</span><span class="sxs-lookup"><span data-stu-id="9535b-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="9535b-212">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите на **Reports** \> **панель мониторинга** отчетов и выберите **Обнаружение нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="9535b-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="9535b-213">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="9535b-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Мини-приложение обнаружения нежелательной почты на панели мониторинга отчетов](../../media/spam-detections-report-widget.png)

<span data-ttu-id="9535b-215">Дополнительные сведения о защите от нежелательной почты можно найти [в статье Защита от нежелательной почты в EOP](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="9535b-216">Режим отчета для отчета об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="9535b-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="9535b-217">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="9535b-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9535b-218">**Разбить на: действие**: отображаются следующие типы событий:</span><span class="sxs-lookup"><span data-stu-id="9535b-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="9535b-219">**Фильтр нежелательного содержимого**</span><span class="sxs-lookup"><span data-stu-id="9535b-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="9535b-220">**Блокировка IP-адресов спама**</span><span class="sxs-lookup"><span data-stu-id="9535b-220">**Spam IP block**</span></span>
  - <span data-ttu-id="9535b-221">**Блок конверта нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="9535b-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="9535b-222">**Фильтр DBEB нежелательной почты**: пограничная блокировка на основе каталогов (DBEB)</span><span class="sxs-lookup"><span data-stu-id="9535b-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="9535b-223">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете узнать, сколько элементов было заблокировано в этот день, а также как эти элементы классифицируются по категориям.</span><span class="sxs-lookup"><span data-stu-id="9535b-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Представление "действия" в отчете об обнаружении нежелательной почты](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="9535b-225">**Разбивается на: направление**: отображаются следующие направления:</span><span class="sxs-lookup"><span data-stu-id="9535b-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="9535b-226">**Получение**</span><span class="sxs-lookup"><span data-stu-id="9535b-226">**Inbound**</span></span>
  - <span data-ttu-id="9535b-227">**Прав**</span><span class="sxs-lookup"><span data-stu-id="9535b-227">**Outbound**</span></span>

  ![Представление "направление" в отчете об обнаружении нежелательной почты](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="9535b-229">Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9535b-230">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="9535b-231">Значения направления</span><span class="sxs-lookup"><span data-stu-id="9535b-231">Direction values</span></span>
- <span data-ttu-id="9535b-232">Значения типов событий</span><span class="sxs-lookup"><span data-stu-id="9535b-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="9535b-233">Представление таблицы сведений для отчета об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="9535b-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="9535b-234">Если в каком-либо представлении отчета выбрать **Таблица просмотреть сведения** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="9535b-235">**Date**</span><span class="sxs-lookup"><span data-stu-id="9535b-235">**Date**</span></span>
- <span data-ttu-id="9535b-236">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="9535b-236">**Sender address**</span></span>
- <span data-ttu-id="9535b-237">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="9535b-237">**Recipient address**</span></span>
- <span data-ttu-id="9535b-238">**Тип события**</span><span class="sxs-lookup"><span data-stu-id="9535b-238">**Event type**</span></span>
- <span data-ttu-id="9535b-239">**Действие**</span><span class="sxs-lookup"><span data-stu-id="9535b-239">**Action**</span></span>
- <span data-ttu-id="9535b-240">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9535b-240">**Subject**</span></span>

<span data-ttu-id="9535b-241">Если вы Нажимайте **фильтры** в таблице сведений, вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9535b-242">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="9535b-243">Значения направления</span><span class="sxs-lookup"><span data-stu-id="9535b-243">Direction values</span></span>
- <span data-ttu-id="9535b-244">Значения типов событий</span><span class="sxs-lookup"><span data-stu-id="9535b-244">Event type values</span></span>

<span data-ttu-id="9535b-245">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="9535b-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="9535b-246">Отчет об обнаружении поддельных поддельных</span><span class="sxs-lookup"><span data-stu-id="9535b-246">Spoof detections report</span></span>

<span data-ttu-id="9535b-247">Отчет об **обнаружении поддельных** поддельных сообщений показывает, сколько почтовых сообщений было обнаружено и какие из них были признаны "хорошими" (подделка почты выполнена по законным бизнес-причинам).</span><span class="sxs-lookup"><span data-stu-id="9535b-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="9535b-248">Дополнительные сведения о подмене данных можно найти [в статье Защита от спуфинга в EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="9535b-249">Сводное представление отчета поддерживает 90 дней фильтрации, в то время как в подробном представлении допускается не более десяти дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="9535b-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="9535b-250">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите на **Reports** \> **панель мониторинга** отчетов и выберите **Обнаружение поддельных поддельных**данных.</span><span class="sxs-lookup"><span data-stu-id="9535b-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="9535b-251">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="9535b-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Мини-приложение "Обнаружение поддельных поддельных" на панели мониторинга отчетов](../../media/spoof-detections-widget.png)

<span data-ttu-id="9535b-253">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете узнать, сколько поступило сообщений с подложным сообщением.</span><span class="sxs-lookup"><span data-stu-id="9535b-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="9535b-254">Вы можете отфильтровать как диаграмму, так и таблицу сведений, щелкнув **фильтры** и выбрав одно или несколько из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9535b-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="9535b-255">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="9535b-256">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="9535b-256">**Good mail**</span></span>

- <span data-ttu-id="9535b-257">**Перехвачено как нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="9535b-257">**Caught as spam**</span></span>

![Представление отчета в отчете об обнаружении поддельных поддельных](../../media/spoof-detections-report-view.png)

<span data-ttu-id="9535b-259">Если щелкнуть **Таблица Просмотр сведений**, можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9535b-260">**Date**</span><span class="sxs-lookup"><span data-stu-id="9535b-260">**Date**</span></span>
- <span data-ttu-id="9535b-261">**Поддельный отправитель**</span><span class="sxs-lookup"><span data-stu-id="9535b-261">**Spoofed sender**</span></span>
- <span data-ttu-id="9535b-262">**Отправитель**</span><span class="sxs-lookup"><span data-stu-id="9535b-262">**True sender**</span></span>
- <span data-ttu-id="9535b-263">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="9535b-263">**Sender IP**</span></span>
- <span data-ttu-id="9535b-264">**Действие**</span><span class="sxs-lookup"><span data-stu-id="9535b-264">**Action**</span></span>
- <span data-ttu-id="9535b-265">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="9535b-265">**Message count**</span></span>

<span data-ttu-id="9535b-266">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="9535b-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="9535b-267">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="9535b-267">Threat protection status report</span></span>

<span data-ttu-id="9535b-268">Отчет **о состоянии защиты от угроз** доступен как в EOP, так и в Office 365 ATP; Тем не менее, отчеты содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="9535b-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="9535b-269">Например, пользователи EOP могут просматривать сведения о вредоносных программах, обнаруженных в электронной почте, но не могут получить сведения о [вредоносных файлах, обнаруженных в SharePoint Online, OneDrive или Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="9535b-270">В отчете представлено количество сообщений электронной почты с вредоносным содержимым, такими как файлы или адреса веб-сайтов (URL-адреса), которые были заблокированы ядром защиты от вредоносных программ, функции [автоматического очистки (ZAP)](zero-hour-auto-purge.md)и ATP, такие как [безопасные ссылки](atp-safe-links.md)ATP, [безопасные вложения ATP](atp-safe-attachments.md)и [Защита от фишинга](set-up-anti-phishing-policies.md)ATP.</span><span class="sxs-lookup"><span data-stu-id="9535b-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="9535b-271">Эти сведения можно использовать для определения тенденций или определения необходимости коррекции политик организации.</span><span class="sxs-lookup"><span data-stu-id="9535b-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="9535b-272">Важно понимать, что если сообщение отправлено пяти получателям, оно подсчитано как пять разных сообщений, а не одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="9535b-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="9535b-273">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **состояние защиты от угроз**.</span><span class="sxs-lookup"><span data-stu-id="9535b-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="9535b-274">Чтобы перейти непосредственно к отчету, откройте один из следующих URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="9535b-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="9535b-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .</span><span class="sxs-lookup"><span data-stu-id="9535b-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="9535b-276">EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="9535b-276">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

![Мини-приложение "состояние защиты от угроз" на панели мониторинга отчетов](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="9535b-278">По умолчанию на диаграмме отображаются данные за предыдущие 7 дней.</span><span class="sxs-lookup"><span data-stu-id="9535b-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="9535b-279">При нажатии кнопки **фильтры**можно выбрать диапазон дат 90 дней (пробные подписки могут быть ограничены 30 днями).</span><span class="sxs-lookup"><span data-stu-id="9535b-279">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="9535b-280">В представлении Таблица сведений можно использовать фильтрацию в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="9535b-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="9535b-281">Представление отчета о состоянии защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="9535b-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="9535b-282">Доступны следующие представления:</span><span class="sxs-lookup"><span data-stu-id="9535b-282">The following views are available:</span></span>

- <span data-ttu-id="9535b-283">**Просмотр данных по: обзор**: отображаются следующие сведения об обнаружении:</span><span class="sxs-lookup"><span data-stu-id="9535b-283">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="9535b-284">**Вредоносные программы электронной почты**</span><span class="sxs-lookup"><span data-stu-id="9535b-284">**Email malware**</span></span>
  - <span data-ttu-id="9535b-285">**Фишинг электронной почты**</span><span class="sxs-lookup"><span data-stu-id="9535b-285">**Email phish**</span></span>
  - <span data-ttu-id="9535b-286">**Вредоносные программы для контента**</span><span class="sxs-lookup"><span data-stu-id="9535b-286">**Content malware**</span></span>

  ![Представление "Обзор" в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="9535b-288">**Просмотр данных по: контенту \> Malware**<sup>1</sup>: для организаций Office 365 ATP отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="9535b-289">**Модуль защиты от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="9535b-289">**Anti-malware engine**</span></span>
  - <span data-ttu-id="9535b-290">**Файл детонации**</span><span class="sxs-lookup"><span data-stu-id="9535b-290">**File detonation**</span></span>

  ![Просмотр вредоносных программ контента в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="9535b-292">**Разделите на: технология обнаружения** и **Просмотр данных по: \> Фишинг электронной почты**: отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-292">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="9535b-293">**Репутация создания URL-адреса, созданного ATP**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-293">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="9535b-294">**Расширенный фильтр фишинга**</span><span class="sxs-lookup"><span data-stu-id="9535b-294">**Advanced phish filter**</span></span>
  - <span data-ttu-id="9535b-295">**Защита от спуфинга: сбой DMARC**</span><span class="sxs-lookup"><span data-stu-id="9535b-295">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="9535b-296">**Защита от спуфинга: внутри Организации**</span><span class="sxs-lookup"><span data-stu-id="9535b-296">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="9535b-297">**Защита от спуфинга: внешний домен**</span><span class="sxs-lookup"><span data-stu-id="9535b-297">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="9535b-298">**Олицетворение торговой марки**</span><span class="sxs-lookup"><span data-stu-id="9535b-298">**Brand impersonation**</span></span>
  - <span data-ttu-id="9535b-299">**Олицетворение домена**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-299">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="9535b-300">**Репутация URL-адреса EOP**</span><span class="sxs-lookup"><span data-stu-id="9535b-300">**EOP URL reputation**</span></span>
  - <span data-ttu-id="9535b-301">**Общий фильтр фишинга**</span><span class="sxs-lookup"><span data-stu-id="9535b-301">**General phish filter**</span></span>
  - <span data-ttu-id="9535b-302">**Другие**</span><span class="sxs-lookup"><span data-stu-id="9535b-302">**Others**</span></span>
  - <span data-ttu-id="9535b-303">**ФИШИНГ ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-303">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="9535b-304">**URL-адрес детонации**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-304">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="9535b-305">**Олицетворение пользователя**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-305">**User impersonation**<sup>1</sup></span></span>

  ![Просмотр технологии обнаружения фишинговых сообщений в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="9535b-307">**Разделите на: технология обнаружения** и **Просмотр данных по: \> вредоносные программы электронной почты**: отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-307">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9535b-308">**Репутация файла, созданного ATP**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-308">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="9535b-309">**Модуль защиты от вредоносных программ**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-309">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="9535b-310">**Блок типа файла политики защиты от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="9535b-310">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="9535b-311">**Файл детонации**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-311">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="9535b-312">**Репутация вредоносных файлов**</span><span class="sxs-lookup"><span data-stu-id="9535b-312">**Malicious file reputation**</span></span>
  - <span data-ttu-id="9535b-313">**Вредоносный ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-313">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="9535b-314">**Другие**</span><span class="sxs-lookup"><span data-stu-id="9535b-314">**Others**</span></span>

  ![Представление технологии обнаружения вредоносных программ в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="9535b-316">**Разбейте на: тип политики** и **Просмотр данных по: " \> phishing-почта** " или **"Просмотр данных по": \> вредоносные программы электронной почты**: отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-316">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9535b-317">**Защита от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="9535b-317">**Anti-malware**</span></span>
  - <span data-ttu-id="9535b-318">**Безопасное вложение**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9535b-318">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="9535b-319">**Защита от фишинга**</span><span class="sxs-lookup"><span data-stu-id="9535b-319">**Anti-phish**</span></span>
  - <span data-ttu-id="9535b-320">**Защита от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="9535b-320">**Anti-spam**</span></span>
  - <span data-ttu-id="9535b-321">**Правило для процесса обработки почты** (также называемое правилом транспорта)</span><span class="sxs-lookup"><span data-stu-id="9535b-321">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="9535b-322">**Другие**</span><span class="sxs-lookup"><span data-stu-id="9535b-322">**Others**</span></span>

  ![Представление "тип политики" для фишинговых сообщений в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="9535b-324">**Разбивается на: состояние доставки** и **Просмотр данных по: " \> phishing-почта** " или **"Просмотр данных по": \> вредоносные программы электронной почты**: отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-324">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9535b-325">**Сбой доставки**</span><span class="sxs-lookup"><span data-stu-id="9535b-325">**Delivery failed**</span></span>
  - <span data-ttu-id="9535b-326">**Утерян**</span><span class="sxs-lookup"><span data-stu-id="9535b-326">**Dropped**</span></span>
  - <span data-ttu-id="9535b-327">**Пересылаются**</span><span class="sxs-lookup"><span data-stu-id="9535b-327">**Forwarded**</span></span>
  - <span data-ttu-id="9535b-328">**Размещенный почтовый ящик: настраиваемая папка**</span><span class="sxs-lookup"><span data-stu-id="9535b-328">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="9535b-329">**Размещенный почтовый ящик: удаленные элементы**</span><span class="sxs-lookup"><span data-stu-id="9535b-329">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="9535b-330">**Размещенный почтовый ящик: папка "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="9535b-330">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="9535b-331">**Размещенный почтовый ящик: Нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="9535b-331">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="9535b-332">**Локальный сервер: Доставка**</span><span class="sxs-lookup"><span data-stu-id="9535b-332">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="9535b-333">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="9535b-333">**Quarantine**</span></span>

  ![Представление состояния доставки для фишинговых сообщений в отчете о состоянии защиты от угроз](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="9535b-335"><sup>1</sup> только для Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="9535b-335"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="9535b-336"><sup>2</sup> -часовое автоматическое удаление (ZAP) недоступно в автономной EOP (работает только в почтовых ящиках Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9535b-336"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="9535b-337">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-337">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="9535b-338">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-338">**Start date** and **End date**</span></span>
- <span data-ttu-id="9535b-339">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="9535b-339">**Detection**</span></span>
- <span data-ttu-id="9535b-340">**Защита**: **ATP** или **EOP**</span><span class="sxs-lookup"><span data-stu-id="9535b-340">**Protected by**: **ATP** or **EOP**</span></span>
- <span data-ttu-id="9535b-341">**Тег**: фильтр по тегу, который возвращает пользователей или группы, к которым применен определенный тег.</span><span class="sxs-lookup"><span data-stu-id="9535b-341">**Tag**: filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="9535b-342">Дополнительные сведения о тегах пользователя приведены в статье [теги пользователей](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="9535b-342">For more information about user tags, see [User tags](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="9535b-343">**Домен**</span><span class="sxs-lookup"><span data-stu-id="9535b-343">**Domain**</span></span>

> [!NOTE]
> <span data-ttu-id="9535b-344">**Тег** и **домен** **защищены только для**Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="9535b-344">**Protected by**, **Tag** and **Domain** are Office 365 ATP only.</span></span> <span data-ttu-id="9535b-345">Эти фильтруемые свойства недоступны в **данных представления: контентная \> вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="9535b-345">These filterable properties are not available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="9535b-346">Представление таблицы сведений для отчета о состоянии защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="9535b-346">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="9535b-347">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="9535b-347">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9535b-348">**Просмотр данных по: контенту \> Вредоносные программы**:</span><span class="sxs-lookup"><span data-stu-id="9535b-348">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="9535b-349">**Date**</span><span class="sxs-lookup"><span data-stu-id="9535b-349">**Date**</span></span>
  - <span data-ttu-id="9535b-350">**Location**</span><span class="sxs-lookup"><span data-stu-id="9535b-350">**Location**</span></span>
  - <span data-ttu-id="9535b-351">**Направлено**</span><span class="sxs-lookup"><span data-stu-id="9535b-351">**Directed by**</span></span>
  - <span data-ttu-id="9535b-352">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="9535b-352">**Malware name**</span></span>

<span data-ttu-id="9535b-353">Если щелкнуть **фильтры** в этом представлении, вы можете изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-353">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="9535b-354">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-354">**Start date** and **End date**</span></span>
- <span data-ttu-id="9535b-355">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="9535b-355">**Detection**</span></span>

<span data-ttu-id="9535b-356">**Просмотр данных по: обзор**: кнопка **таблицы сведений о просмотре** недоступна.</span><span class="sxs-lookup"><span data-stu-id="9535b-356">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="9535b-357">Все остальные диаграммы:</span><span class="sxs-lookup"><span data-stu-id="9535b-357">All other charts:</span></span>

  - <span data-ttu-id="9535b-358">**Date**</span><span class="sxs-lookup"><span data-stu-id="9535b-358">**Date**</span></span>
  - <span data-ttu-id="9535b-359">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9535b-359">**Subject**</span></span>
  - <span data-ttu-id="9535b-360">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9535b-360">**Sender**</span></span>
  - <span data-ttu-id="9535b-361">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="9535b-361">**Recipients**</span></span>
  - <span data-ttu-id="9535b-362">**Определяется**</span><span class="sxs-lookup"><span data-stu-id="9535b-362">**Detected by**</span></span>
  - <span data-ttu-id="9535b-363">**Состояние доставки**.</span><span class="sxs-lookup"><span data-stu-id="9535b-363">**Delivery status**</span></span>
  - <span data-ttu-id="9535b-364">**Источник компромисса**</span><span class="sxs-lookup"><span data-stu-id="9535b-364">**Source of compromise**</span></span>
  - <span data-ttu-id="9535b-365">**Tags**</span><span class="sxs-lookup"><span data-stu-id="9535b-365">**Tags**</span></span>

<span data-ttu-id="9535b-366">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="9535b-366">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="9535b-367">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="9535b-367">**Start date** and **End date**</span></span>
- <span data-ttu-id="9535b-368">**Обнаружение**</span><span class="sxs-lookup"><span data-stu-id="9535b-368">**Detection**</span></span>
- <span data-ttu-id="9535b-369">**Защищено** (только для Office 365 ATP): **ATP** или **EOP**</span><span class="sxs-lookup"><span data-stu-id="9535b-369">**Protected by** (Office 365 ATP only): **ATP** or **EOP**</span></span>
- <span data-ttu-id="9535b-370">**Тег**: фильтр по тегу, который возвращает пользователей или группы, к которым применен определенный тег.</span><span class="sxs-lookup"><span data-stu-id="9535b-370">**Tag**: filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="9535b-371">Дополнительные сведения о тегах пользователя приведены в статье [теги пользователей](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="9535b-371">For more information about user tags, see [User tags](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="9535b-372">**Домен**</span><span class="sxs-lookup"><span data-stu-id="9535b-372">**Domain**</span></span>
- <span data-ttu-id="9535b-373">**Получатели** (Обратите внимание, что это фильтруемое свойство доступно только в представлении таблицы сведений).</span><span class="sxs-lookup"><span data-stu-id="9535b-373">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="9535b-374">Отчет о самых вредоносных программах</span><span class="sxs-lookup"><span data-stu-id="9535b-374">Top malware report</span></span>

<span data-ttu-id="9535b-375">В отчете о **самых вредоносных программах** отображаются различные виды вредоносных программ, обнаруженных функцией [защиты от вредоносных программ в EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-375">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="9535b-376">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите на **Reports** \> **панель мониторинга** отчетов и выберите **самые распространенные вредоносные программы**.</span><span class="sxs-lookup"><span data-stu-id="9535b-376">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="9535b-377">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="9535b-377">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Мини-приложение "первые вредоносные программы" на панели мониторинга отчетов](../../media/top-malware-report-widget.png)

<span data-ttu-id="9535b-379">При наведении указателя на сектор на круговой диаграмме отображается название типа вредоносных программ и количество сообщений, обнаруженных при наличии вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="9535b-379">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Представление отчета о самых вредоносных программах](../../media/top-malware-report-view.png)

<span data-ttu-id="9535b-381">Если щелкнуть **Таблица Просмотр сведений**, можно увидеть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9535b-381">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9535b-382">**Самые популярные вредоносные программы**</span><span class="sxs-lookup"><span data-stu-id="9535b-382">**Top malware**</span></span>
- <span data-ttu-id="9535b-383">**Count**</span><span class="sxs-lookup"><span data-stu-id="9535b-383">**Count**</span></span>

<span data-ttu-id="9535b-384">Если щелкнуть **фильтры** в представлении отчета или таблицы сведений, можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="9535b-384">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="9535b-385">URL-адрес отчета о защите от угроз</span><span class="sxs-lookup"><span data-stu-id="9535b-385">URL threat protection report</span></span>

<span data-ttu-id="9535b-386">**Отчет по защите от угроз для URL-адресов** доступен в Office 365 Advanced Threat protection (ATP).</span><span class="sxs-lookup"><span data-stu-id="9535b-386">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="9535b-387">Дополнительные сведения см. в разделе [URL-адрес защиты угроз](view-reports-for-atp.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="9535b-387">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="9535b-388">Отчет о сообщениях, отчет о пользователях</span><span class="sxs-lookup"><span data-stu-id="9535b-388">User-reported messages report</span></span>

<span data-ttu-id="9535b-389">Отчет о сообщениях в отчетах о **пользователях** содержит сведения о сообщениях электронной почты, которые пользователи сообщили как нежелательные, фишинговые попытки или хорошие сообщения с помощью [надстройки Report Message](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span><span class="sxs-lookup"><span data-stu-id="9535b-389">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="9535b-390">Для каждого сообщения доступны подробные сведения, в том числе причина доставки, такие как исключение политики нежелательной почты или правило обработки почты, настроенное для Организации.</span><span class="sxs-lookup"><span data-stu-id="9535b-390">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="9535b-391">Чтобы просмотреть сведения, выберите элемент в списке пользователь — отчеты, а затем просмотрите сведения на вкладках **Сводка** и **сведения** .</span><span class="sxs-lookup"><span data-stu-id="9535b-391">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Отчет о сообщениях с отчетами о пользователях показывает, что пользователи помечаются как нежелательная, Нежелательная почта или фишинговые попытки.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="9535b-393">Чтобы просмотреть этот отчет, в [центре безопасности & соответствия требованиям](https://protection.office.com)выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9535b-393">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="9535b-394">Перейдите к **Threat management** \> **Dashboard** \> **сообщению, сообщенному пользователями**панели управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="9535b-394">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="9535b-395">Перейдите к разделу **Управление угрозами** \> **Обзор** \> **сообщений, отправленных пользователями**.</span><span class="sxs-lookup"><span data-stu-id="9535b-395">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![В центре безопасности & соответствия требованиям выберите Обзор управления угрозами \> \> Пользователи, сообщающие о сообщениях](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="9535b-397">Чтобы отчет о сообщениях, отправленных пользователями, работал правильно, **необходимо включить ведение журнала аудита** для среды Office 365.</span><span class="sxs-lookup"><span data-stu-id="9535b-397">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="9535b-398">Это обычно делается для пользователей, которым назначена роль "журналы аудита" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9535b-398">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="9535b-399">Дополнительную информацию можно узнать [в статье Включение и отключение поиска в журнале аудита Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="9535b-399">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="9535b-400">Какие разрешения необходимы для просмотра отчетов?</span><span class="sxs-lookup"><span data-stu-id="9535b-400">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="9535b-401">Для просмотра и использования отчетов необходимо быть членом указанной группы ролей в центре безопасности & соответствия требованиям **и** в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9535b-401">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="9535b-402">В центре безопасности & соответствия требованиям необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="9535b-402">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="9535b-403">-Управление организацией — администратор безопасности (это можно также сделать в [центре администрирования Azure Active Directory](https://aad.portal.azure.com) — средство чтения безопасности</span><span class="sxs-lookup"><span data-stu-id="9535b-403">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="9535b-404">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="9535b-404">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="9535b-405">В Exchange Online необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="9535b-405">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="9535b-406">— Управление организацией — Управление организацией только для просмотра — "только просмотр получателей" — Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="9535b-406">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="9535b-407">Дополнительные сведения см в разделе [разрешения в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) и [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="9535b-407">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="9535b-408">Что делать, если в отчетах данные не отображаются?</span><span class="sxs-lookup"><span data-stu-id="9535b-408">What if the reports aren't showing data?</span></span>

<span data-ttu-id="9535b-409">Если вы не видите данные в отчетах, дважды проверьте правильность настройки политик.</span><span class="sxs-lookup"><span data-stu-id="9535b-409">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="9535b-410">Чтобы узнать больше, ознакомьтесь [со статьей защита от угроз](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-410">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9535b-411">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9535b-411">Related topics</span></span>

[<span data-ttu-id="9535b-412">Защита от нежелательной почты и вредоносных программ в EOP</span><span class="sxs-lookup"><span data-stu-id="9535b-412">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="9535b-413">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9535b-413">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="9535b-414">Просмотр отчетов о движении по почте в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9535b-414">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="9535b-415">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="9535b-415">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
