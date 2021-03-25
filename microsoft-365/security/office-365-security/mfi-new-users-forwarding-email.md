---
title: Анализ новых пользователей, которые пересылают сообщения электронной почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать, как использовать новые сведения об отправке электронной почты новыми пользователями в Центре соответствия требованиям & безопасности, чтобы выяснить, когда пользователи в их организации переададкуют сообщения в новые домены.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206197"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="d0bc1-103">Новые пользователи, переадлив данные электронной почты в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="d0bc1-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d0bc1-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-104">**Applies to**</span></span>
- [<span data-ttu-id="d0bc1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d0bc1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d0bc1-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="d0bc1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d0bc1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0bc1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d0bc1-108">Подозрительно, когда новые учетные записи пользователей в организации внезапно начинают отправлять сообщения электронной почты во внешние домены.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="d0bc1-109">Новые **домены,** переадружающие [](https://protection.office.com) сведения об электронной почте в Центре & соответствия требованиям, извещение о том, когда вновь созданные пользователи в вашей организации переадружали сообщения во внешние домены.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="d0bc1-110">Это условие может указывать на то, что для создания новых пользователей использовались скомпрометированные учетные записи администратора.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="d0bc1-111">Если вы подозреваете, что учетные записи были скомпрометированы, см. в сообщении [Responding to a compromised email account.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="d0bc1-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="d0bc1-112">Это представление появляется только при обнаружении проблемы и отображается на странице [отчета о переадпорте.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="d0bc1-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых пользователей, которые пересылают сообщения электронной почты](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="d0bc1-114">При нажатии на виджет появляется флажок, в котором можно найти дополнительные [](#forwarding-modifications-report) сведения о переадпортных сообщениях, включая ссылку на отчет об изменениях в переадпорте, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Подробные сведения, которые появляются после нажатия на новые сведения об отправке электронной почты новыми пользователями](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="d0bc1-116">Вы также можете получить эту страницу сведений,  когда вы  выберите представление после нажатия Просмотреть все в области & рекомендации на (**Отчеты** \> **панель мониторинга** или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="d0bc1-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="d0bc1-117">Чтобы перейти  к отчету об изменениях  в переадпорте, как описано в следующем разделе, вы можете щелкнуть отчет См. в разделе См. ссылку на анализ.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="d0bc1-118">Отчет об изменениях в переадпорте</span><span class="sxs-lookup"><span data-stu-id="d0bc1-118">Forwarding modifications report</span></span>

<span data-ttu-id="d0bc1-119">В **отчете об изменениях** в переадпорте показаны сведения о сообщениях, которые автоматически отправляются от отправителей в организации:</span><span class="sxs-lookup"><span data-stu-id="d0bc1-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="d0bc1-120">Вновь созданные учетные записи, которые переадружая сообщения во внешние домены.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="d0bc1-121">Учетные записи, которые отправляют сообщения на внешние домены, которые никогда не переадружались другими отправителями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="d0bc1-122">Эти типы сообщений могут представлять угрозу безопасности или соответствия требованиям и могут указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="d0bc1-123">Отчет содержит данные на срок до 90 дней.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="d0bc1-124">По умолчанию в отчете показаны данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="d0bc1-125">Этот отчет не доступен непосредственно в панели мониторинга потока [почты](mail-flow-insights-v2.md) или в панели [отчетов.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="d0bc1-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="d0bc1-126">В дополнение к нажатию на отчет  **См.** ссылку на информацию о новых пользователях, переадпортующих сведения по электронной почте, вы получите в отчете по:</span><span class="sxs-lookup"><span data-stu-id="d0bc1-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="d0bc1-127">Щелкните **ссылку отчетов об** отправке уведомлений в сведениях о новых доменах, которые будут переадпортуться [по электронной почте.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="d0bc1-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="d0bc1-128">Открытие <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="d0bc1-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="d0bc1-129">Представление отчета для отчета об изменениях в переадпорте</span><span class="sxs-lookup"><span data-stu-id="d0bc1-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="d0bc1-130">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="d0bc1-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d0bc1-131">**Показать данные для: Новые пользователи переададки:**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-131">**Show data for: New forwarding users**:</span></span>

  ![Просмотр новых пользователей-переадпортов в отчете об изменениях переададки](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="d0bc1-133">**Показать данные для: Новые домены переададки:**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-133">**Show data for: New forwarding domains**:</span></span>

  ![Просмотр новых переадпортных доменов в отчете об изменениях переадпорта](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="d0bc1-135">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="d0bc1-136">Представление таблицы сведений для отчета об изменениях в переадпорте</span><span class="sxs-lookup"><span data-stu-id="d0bc1-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="d0bc1-137">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="d0bc1-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d0bc1-138">**Показать данные для: Новые пользователи переададки:**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="d0bc1-139">**Имя.** Адрес электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="d0bc1-140">**Тип переададки**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-140">**Forwarding type**</span></span>
  - <span data-ttu-id="d0bc1-141">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-141">**Recipient address**</span></span>
  - <span data-ttu-id="d0bc1-142">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-142">**Details**</span></span>
  - <span data-ttu-id="d0bc1-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-143">**Count**</span></span>
  - <span data-ttu-id="d0bc1-144">**Дата первой переададки**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-144">**First forward date**</span></span>

- <span data-ttu-id="d0bc1-145">**Показать данные для: Новые домены переададки:**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="d0bc1-146">**Имя.** Домен электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="d0bc1-147">**Тип переададки**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-147">**Forwarding type**</span></span>
  - <span data-ttu-id="d0bc1-148">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-148">**Recipient address**</span></span>
  - <span data-ttu-id="d0bc1-149">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-149">**Details**</span></span>
  - <span data-ttu-id="d0bc1-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-150">**Count**</span></span>
  - <span data-ttu-id="d0bc1-151">**Дата первой переададки**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-151">**First forward date**</span></span>

<span data-ttu-id="d0bc1-152">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d0bc1-153">Если выбрать строку из таблицы, появится флааут **Details** со следующей информацией:</span><span class="sxs-lookup"><span data-stu-id="d0bc1-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="d0bc1-154">**Имя.** Это либо адрес электронной почты отправитель (от Показать данные **для:** Просмотр новых пользователей переададки) или домен электронной почты отправитель (из Показать данные **для:** Новые домены переададки).</span><span class="sxs-lookup"><span data-stu-id="d0bc1-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="d0bc1-155">**Тип переададки**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-155">**Forwarding type**</span></span>
- <span data-ttu-id="d0bc1-156">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-156">**Recipient**</span></span>
- <span data-ttu-id="d0bc1-157">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-157">**Details**</span></span>
- <span data-ttu-id="d0bc1-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-158">**Count**</span></span>
- <span data-ttu-id="d0bc1-159">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="d0bc1-159">**Start date**</span></span>
- <span data-ttu-id="d0bc1-160">**Рекомендация.** Здесь вы можете щелкнуть ссылку для управления пользователем в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Подробные сведения из таблицы сведений о просмотре пользователей новой переадпорта в отчете об изменениях в переадпорте](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="d0bc1-162">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0bc1-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d0bc1-163">Related topics</span></span>

<span data-ttu-id="d0bc1-164">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="d0bc1-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
