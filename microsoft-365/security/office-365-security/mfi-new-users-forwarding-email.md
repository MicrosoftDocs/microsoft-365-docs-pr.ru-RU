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
description: Администраторы могут узнать, как использовать сведения о новых пользователях, которые перенаследуют данные электронной почты в Центре безопасности & соответствия требованиям, для изучения того, когда пользователи в своей организации перенаследуют сообщения в новые домены.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af991cb0af20a0f48bc5283d4e4fb26ea75d6ba6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029874"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="3fa2c-103">Новые пользователи, переадлиющие данные электронной почты в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="3fa2c-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3fa2c-104">Это подозрительно, когда новые учетные записи пользователей в организации внезапно начинают переадружайте сообщения электронной почты на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="3fa2c-105">Новые **домены,** переадружающие данные электронной почты в Центре безопасности & [соответствия](https://protection.office.com) требованиям, будут извещение о том, когда только что созданные пользователи в организации переадружали сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="3fa2c-106">Это условие может указывать на то, что для создания новых пользователей использовались скомпрометированные учетные записи администраторов.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="3fa2c-107">Если вы подозреваете, что учетные записи были скомпрометированы, см. ответ на компрометации учетной [записи электронной почты.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="3fa2c-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="3fa2c-108">Эта информация отображается только при обнаружении проблемы и отображается на странице отчета ["Переад](view-mail-flow-reports.md#forwarding-report) сообщений".</span><span class="sxs-lookup"><span data-stu-id="3fa2c-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых пользователей, которые пересылают сообщения электронной почты](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="3fa2c-110">При нажатии мини-приложения появится элемент, в котором можно найти дополнительные сведения о переададантных сообщениях, в том числе ссылку на отчет об изменениях в [forwarding,](#forwarding-modifications-report) как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Flyout Details that appears after clicking on the New users forwarding email insight](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="3fa2c-112">Вы также можете вернуться на эту страницу  сведений при выборе статистики после нажатия кнопки "Просмотреть все" в области "Лучшие **сведения&** **рекомендации"** (панель мониторинга отчетов или \>  <https://protection.office.com/insightdashboard> панель мониторинга).</span><span class="sxs-lookup"><span data-stu-id="3fa2c-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="3fa2c-113">Вы можете щелкнуть ссылку  **"Просмотр отчета, связанного** с данными", чтобы перейти к отчету об изменениях в переадэинге, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="3fa2c-114">Отчет об изменениях при переададпорте</span><span class="sxs-lookup"><span data-stu-id="3fa2c-114">Forwarding modifications report</span></span>

<span data-ttu-id="3fa2c-115">В **отчете об изменениях** в forwarding показаны сведения о сообщениях, которые автоматически переадформируются от отправителей в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="3fa2c-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="3fa2c-116">Вновь созданные учетные записи, которые переадружют сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="3fa2c-117">Учетные записи, которые перенаправят сообщения на внешние домены, на которые никогда не переадружались другие отправителю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="3fa2c-118">Эти типы переададантных сообщений могут представлять угрозу безопасности или соответствия требованиям и указывать на компрометации учетных записей.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="3fa2c-119">Отчет содержит данные за 90 дней.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="3fa2c-120">По умолчанию в отчете показаны данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="3fa2c-121">Этот отчет не доступен напрямую на панели мониторинга потока [почты](mail-flow-insights-v2.md) или в панели [отчетов.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="3fa2c-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="3fa2c-122">Помимо нажатия отчета  "Просмотр", связанного  со ссылкой "Анализ" в сообщении "Новые пользователи, переадлижимые по электронной почте", вы можете получить к отчету:</span><span class="sxs-lookup"><span data-stu-id="3fa2c-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="3fa2c-123">Щелкните ссылку **отчета "Уведомления** о переададаторе" в сведениях о новых доменах, перена которые будут перена отправляться по [электронной почте.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="3fa2c-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="3fa2c-124">Открытие <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="3fa2c-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="3fa2c-125">Представление отчета об изменениях в переадпорте</span><span class="sxs-lookup"><span data-stu-id="3fa2c-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="3fa2c-126">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="3fa2c-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="3fa2c-127">**Показать данные для: новые пользователи, переадлицющие:**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-127">**Show data for: New forwarding users**:</span></span>

  ![Представление новых пользователей переададантов в отчете об изменениях переададантов](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="3fa2c-129">**Показать данные для: новые домены переадантовки:**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-129">**Show data for: New forwarding domains**:</span></span>

  ![Новое представление переададантных доменов в отчете об изменениях в переададаторе](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="3fa2c-131">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="3fa2c-132">Представление таблицы сведений для отчета об изменениях переададантов</span><span class="sxs-lookup"><span data-stu-id="3fa2c-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="3fa2c-133">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="3fa2c-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3fa2c-134">**Показать данные для: новые пользователи, переадлицющие:**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="3fa2c-135">**Name**: The email address of the sender.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="3fa2c-136">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-136">**Forwarding type**</span></span>
  - <span data-ttu-id="3fa2c-137">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-137">**Recipient address**</span></span>
  - <span data-ttu-id="3fa2c-138">**Details**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-138">**Details**</span></span>
  - <span data-ttu-id="3fa2c-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-139">**Count**</span></span>
  - <span data-ttu-id="3fa2c-140">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-140">**First forward date**</span></span>

- <span data-ttu-id="3fa2c-141">**Показать данные для: новые домены переадантовки:**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="3fa2c-142">**Name**: The email domain of the sender.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="3fa2c-143">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-143">**Forwarding type**</span></span>
  - <span data-ttu-id="3fa2c-144">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-144">**Recipient address**</span></span>
  - <span data-ttu-id="3fa2c-145">**Details**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-145">**Details**</span></span>
  - <span data-ttu-id="3fa2c-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-146">**Count**</span></span>
  - <span data-ttu-id="3fa2c-147">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-147">**First forward date**</span></span>

<span data-ttu-id="3fa2c-148">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3fa2c-149">Если вы выберете строку в таблице, появится flyout **Details** со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="3fa2c-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="3fa2c-150">**Name**: this is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from Show data **for: New forwarding domains** view).</span><span class="sxs-lookup"><span data-stu-id="3fa2c-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="3fa2c-151">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-151">**Forwarding type**</span></span>
- <span data-ttu-id="3fa2c-152">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-152">**Recipient**</span></span>
- <span data-ttu-id="3fa2c-153">**Details**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-153">**Details**</span></span>
- <span data-ttu-id="3fa2c-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-154">**Count**</span></span>
- <span data-ttu-id="3fa2c-155">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-155">**Start date**</span></span>
- <span data-ttu-id="3fa2c-156">**Рекомендация.** Здесь можно щелкнуть ссылку для управления пользователем в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fa2c-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Flyout details from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="3fa2c-158">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="3fa2c-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3fa2c-159">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3fa2c-159">Related topics</span></span>

<span data-ttu-id="3fa2c-160">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="3fa2c-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
