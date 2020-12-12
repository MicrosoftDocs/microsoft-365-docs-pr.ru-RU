---
title: Анализ новых пользователей, которые пересылают сообщения электронной почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать, как использовать сведения о новых пользователях, которые перенаследуют данные электронной почты в Центре безопасности & соответствия требованиям, для изучения того, когда пользователи в своей организации перенаследуют сообщения в новые домены.
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660021"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="97b15-103">Новые пользователи, переадлиющие данные электронной почты в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="97b15-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="97b15-104">Это подозрительно, когда новые учетные записи пользователей в организации внезапно начинают переадружайте сообщения электронной почты на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="97b15-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="97b15-105">Новые **домены,** переадружающие данные электронной почты в Центре безопасности & [соответствия](https://protection.office.com) требованиям, будут извещение о том, когда только что созданные пользователи в организации переадружали сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="97b15-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="97b15-106">Это условие может указывать на то, что для создания новых пользователей использовались скомпрометированные учетные записи администраторов.</span><span class="sxs-lookup"><span data-stu-id="97b15-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="97b15-107">Если вы подозреваете, что учетные записи были скомпрометированы, см. ответ на компрометации учетной [записи электронной почты.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="97b15-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="97b15-108">Эта информация отображается только при обнаружении проблемы и отображается на странице отчета ["Переадпорт".](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="97b15-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых пользователей, которые пересылают сообщения электронной почты](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="97b15-110">При нажатии мини-приложения появится элемент, в котором можно найти дополнительные сведения о переададантных сообщениях, в том числе ссылку на отчет об изменениях в [forwarding,](#forwarding-modifications-report) как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="97b15-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Flyout Details that appears after clicking on the New users forwarding email insight](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="97b15-112">Вы также можете вернуться на эту страницу  сведений при выборе статистики после нажатия кнопки "Просмотреть все в области "Лучшие **сведения&** рекомендации"**(** панель мониторинга отчетов \>  или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="97b15-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="97b15-113">Вы можете щелкнуть ссылку  **"Просмотр отчета, связанного** с данными", чтобы перейти к отчету об изменениях в переадэинге, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="97b15-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="97b15-114">Отчет об изменениях при переададпорте</span><span class="sxs-lookup"><span data-stu-id="97b15-114">Forwarding modifications report</span></span>

<span data-ttu-id="97b15-115">В **отчете об изменениях** в forwarding показаны сведения о сообщениях, которые автоматически переадформируются от отправителей в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="97b15-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="97b15-116">Вновь созданные учетные записи, которые переадружют сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="97b15-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="97b15-117">Учетные записи, которые перенаправят сообщения на внешние домены, на которые никогда не переадружались другие отправителю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="97b15-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="97b15-118">Эти типы переададантных сообщений могут представлять угрозу безопасности или соответствия требованиям и указывать на компрометации учетных записей.</span><span class="sxs-lookup"><span data-stu-id="97b15-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="97b15-119">Отчет содержит данные за 90 дней.</span><span class="sxs-lookup"><span data-stu-id="97b15-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="97b15-120">По умолчанию в отчете показаны данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="97b15-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="97b15-121">Этот отчет не доступен напрямую на панели мониторинга потока [почты](mail-flow-insights-v2.md) или в панели [отчетов.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="97b15-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="97b15-122">Помимо нажатия отчета "Просмотр", связанного  со ссылкой **"Анализ"** в сообщении "Новые пользователи, перена которые перенабовыют данные электронной почты", к отчету можно получить:</span><span class="sxs-lookup"><span data-stu-id="97b15-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="97b15-123">Щелкните ссылку **отчета "Уведомления** о переададаторе" в сведениях о новых доменах, перена которые будут перена отправляться по [электронной почте.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="97b15-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="97b15-124">Открытие <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="97b15-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="97b15-125">Представление отчета об изменениях в переадпорте</span><span class="sxs-lookup"><span data-stu-id="97b15-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="97b15-126">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="97b15-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="97b15-127">**Показать данные для: новые пользователи, переадлицющие:**</span><span class="sxs-lookup"><span data-stu-id="97b15-127">**Show data for: New forwarding users**:</span></span>

  ![Представление новых пользователей переададантов в отчете об изменениях переададантов](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="97b15-129">**Показать данные для: новые домены переадантовки:**</span><span class="sxs-lookup"><span data-stu-id="97b15-129">**Show data for: New forwarding domains**:</span></span>

  ![Новое представление переададантных доменов в отчете об изменениях в переададаторе](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="97b15-131">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="97b15-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="97b15-132">Представление таблицы сведений для отчета об изменениях переададантов</span><span class="sxs-lookup"><span data-stu-id="97b15-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="97b15-133">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="97b15-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="97b15-134">**Показать данные для: новые пользователи, переадлицющие:**</span><span class="sxs-lookup"><span data-stu-id="97b15-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="97b15-135">**Name**: The email address of the sender.</span><span class="sxs-lookup"><span data-stu-id="97b15-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="97b15-136">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="97b15-136">**Forwarding type**</span></span>
  - <span data-ttu-id="97b15-137">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="97b15-137">**Recipient address**</span></span>
  - <span data-ttu-id="97b15-138">**Details**</span><span class="sxs-lookup"><span data-stu-id="97b15-138">**Details**</span></span>
  - <span data-ttu-id="97b15-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="97b15-139">**Count**</span></span>
  - <span data-ttu-id="97b15-140">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="97b15-140">**First forward date**</span></span>

- <span data-ttu-id="97b15-141">**Показать данные для: новые домены переадантовки:**</span><span class="sxs-lookup"><span data-stu-id="97b15-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="97b15-142">**Name**: The email domain of the sender.</span><span class="sxs-lookup"><span data-stu-id="97b15-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="97b15-143">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="97b15-143">**Forwarding type**</span></span>
  - <span data-ttu-id="97b15-144">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="97b15-144">**Recipient address**</span></span>
  - <span data-ttu-id="97b15-145">**Details**</span><span class="sxs-lookup"><span data-stu-id="97b15-145">**Details**</span></span>
  - <span data-ttu-id="97b15-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="97b15-146">**Count**</span></span>
  - <span data-ttu-id="97b15-147">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="97b15-147">**First forward date**</span></span>

<span data-ttu-id="97b15-148">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="97b15-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="97b15-149">Если вы выберете строку в таблице, появится flyout **Details** со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="97b15-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="97b15-150">**Name**: this is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from Show data **for: New forwarding domains** view).</span><span class="sxs-lookup"><span data-stu-id="97b15-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="97b15-151">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="97b15-151">**Forwarding type**</span></span>
- <span data-ttu-id="97b15-152">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="97b15-152">**Recipient**</span></span>
- <span data-ttu-id="97b15-153">**Details**</span><span class="sxs-lookup"><span data-stu-id="97b15-153">**Details**</span></span>
- <span data-ttu-id="97b15-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="97b15-154">**Count**</span></span>
- <span data-ttu-id="97b15-155">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="97b15-155">**Start date**</span></span>
- <span data-ttu-id="97b15-156">**Рекомендация.** Здесь можно щелкнуть ссылку для управления пользователем в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97b15-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Flyout details from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="97b15-158">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="97b15-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="97b15-159">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="97b15-159">Related topics</span></span>

<span data-ttu-id="97b15-160">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="97b15-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
