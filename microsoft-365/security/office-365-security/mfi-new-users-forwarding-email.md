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
ms.openlocfilehash: 7b86d726979991a55e7d4e43bf3581a4a664ee4f
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150259"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="69d48-103">Новые пользователи, переадлиющие данные электронной почты в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="69d48-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="69d48-104">**Относится к**</span><span class="sxs-lookup"><span data-stu-id="69d48-104">**Applies to**</span></span>
- [<span data-ttu-id="69d48-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="69d48-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="69d48-106">Microsoft Defender для Office 365 (план 1) и план 2</span><span class="sxs-lookup"><span data-stu-id="69d48-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="69d48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69d48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="69d48-108">Это подозрительно, когда новые учетные записи пользователей в организации внезапно начинают переадружайте сообщения электронной почты на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="69d48-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="69d48-109">Новые **домены,** переадружающие данные электронной почты в Центре безопасности & [соответствия](https://protection.office.com) требованиям, будут извещение о том, когда только что созданные пользователи в организации переадружали сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="69d48-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="69d48-110">Это условие может указывать на то, что для создания новых пользователей использовались скомпрометированные учетные записи администраторов.</span><span class="sxs-lookup"><span data-stu-id="69d48-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="69d48-111">Если вы подозреваете, что учетные записи были скомпрометированы, см. ответ на компрометации учетной [записи электронной почты.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="69d48-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="69d48-112">Эта информация отображается только при обнаружении проблемы и отображается на странице отчета ["Переадпорт".](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="69d48-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых пользователей, которые пересылают сообщения электронной почты](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="69d48-114">При нажатии мини-приложения появится элемент, в котором можно найти дополнительные сведения о переададантных сообщениях, в том числе ссылку на отчет об изменениях в [forwarding,](#forwarding-modifications-report) как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="69d48-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Flyout Details that appears after clicking on the New users forwarding email insight](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="69d48-116">Вы также можете вернуться на эту страницу  сведений при выборе статистики после нажатия кнопки "Просмотреть все в области "Лучшие **сведения&** рекомендации"**(** панель мониторинга отчетов \>  или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="69d48-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="69d48-117">Вы можете щелкнуть ссылку  **"Просмотр отчета, связанного** с данными", чтобы перейти к отчету об изменениях в переадэинге, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="69d48-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="69d48-118">Отчет об изменениях при переададпорте</span><span class="sxs-lookup"><span data-stu-id="69d48-118">Forwarding modifications report</span></span>

<span data-ttu-id="69d48-119">В **отчете об изменениях** в forwarding показаны сведения о сообщениях, которые автоматически переадформируются от отправителей в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="69d48-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="69d48-120">Вновь созданные учетные записи, которые переадружют сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="69d48-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="69d48-121">Учетные записи, которые перенаправят сообщения на внешние домены, на которые никогда не переадружались другие отправителю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="69d48-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="69d48-122">Эти типы переададантных сообщений могут представлять угрозу безопасности или соответствия требованиям и указывать на компрометации учетных записей.</span><span class="sxs-lookup"><span data-stu-id="69d48-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="69d48-123">Отчет содержит данные за 90 дней.</span><span class="sxs-lookup"><span data-stu-id="69d48-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="69d48-124">По умолчанию в отчете показаны данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="69d48-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="69d48-125">Этот отчет не доступен напрямую на панели мониторинга потока [почты](mail-flow-insights-v2.md) или в панели [отчетов.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="69d48-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="69d48-126">Помимо нажатия отчета  "Просмотр", связанного  со ссылкой "Анализ" в сообщении "Новые пользователи, переадлижимые по электронной почте", вы можете получить к отчету:</span><span class="sxs-lookup"><span data-stu-id="69d48-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="69d48-127">Щелкните **ссылку отчета "Уведомления** о переададаторе" в сведениях о новых доменах, которые перена электронная почта [перенанола.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="69d48-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="69d48-128">Открытие <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="69d48-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="69d48-129">Представление отчета об изменениях в переададантовке</span><span class="sxs-lookup"><span data-stu-id="69d48-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="69d48-130">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="69d48-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="69d48-131">**Показать данные для: новые пользователи, переадлицющие:**</span><span class="sxs-lookup"><span data-stu-id="69d48-131">**Show data for: New forwarding users**:</span></span>

  ![Представление "Новые пользователи переададантов" в отчете об изменениях переададантов](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="69d48-133">**Показать данные для: новые домены переадантовки:**</span><span class="sxs-lookup"><span data-stu-id="69d48-133">**Show data for: New forwarding domains**:</span></span>

  ![Новое представление переададантных доменов в отчете об изменениях в переададаторе](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="69d48-135">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="69d48-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="69d48-136">Представление таблицы сведений для отчета об изменениях переададантов</span><span class="sxs-lookup"><span data-stu-id="69d48-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="69d48-137">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="69d48-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="69d48-138">**Показать данные для: новые пользователи, переадлицющие:**</span><span class="sxs-lookup"><span data-stu-id="69d48-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="69d48-139">**Name**: The email address of the sender.</span><span class="sxs-lookup"><span data-stu-id="69d48-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="69d48-140">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="69d48-140">**Forwarding type**</span></span>
  - <span data-ttu-id="69d48-141">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="69d48-141">**Recipient address**</span></span>
  - <span data-ttu-id="69d48-142">**Details**</span><span class="sxs-lookup"><span data-stu-id="69d48-142">**Details**</span></span>
  - <span data-ttu-id="69d48-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="69d48-143">**Count**</span></span>
  - <span data-ttu-id="69d48-144">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="69d48-144">**First forward date**</span></span>

- <span data-ttu-id="69d48-145">**Показать данные для: новые домены переадантовки:**</span><span class="sxs-lookup"><span data-stu-id="69d48-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="69d48-146">**Name**: The email domain of the sender.</span><span class="sxs-lookup"><span data-stu-id="69d48-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="69d48-147">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="69d48-147">**Forwarding type**</span></span>
  - <span data-ttu-id="69d48-148">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="69d48-148">**Recipient address**</span></span>
  - <span data-ttu-id="69d48-149">**Details**</span><span class="sxs-lookup"><span data-stu-id="69d48-149">**Details**</span></span>
  - <span data-ttu-id="69d48-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="69d48-150">**Count**</span></span>
  - <span data-ttu-id="69d48-151">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="69d48-151">**First forward date**</span></span>

<span data-ttu-id="69d48-152">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="69d48-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="69d48-153">Если вы выберете строку в таблице, появится flyout **Details** со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="69d48-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="69d48-154">**Name**: this is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from Show data **for: New forwarding domains** view).</span><span class="sxs-lookup"><span data-stu-id="69d48-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="69d48-155">**Тип переад вперед**</span><span class="sxs-lookup"><span data-stu-id="69d48-155">**Forwarding type**</span></span>
- <span data-ttu-id="69d48-156">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="69d48-156">**Recipient**</span></span>
- <span data-ttu-id="69d48-157">**Details**</span><span class="sxs-lookup"><span data-stu-id="69d48-157">**Details**</span></span>
- <span data-ttu-id="69d48-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="69d48-158">**Count**</span></span>
- <span data-ttu-id="69d48-159">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="69d48-159">**Start date**</span></span>
- <span data-ttu-id="69d48-160">**Рекомендация.** Здесь можно щелкнуть ссылку для управления пользователем в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69d48-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Flyout details from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="69d48-162">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="69d48-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69d48-163">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="69d48-163">Related topics</span></span>

<span data-ttu-id="69d48-164">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="69d48-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
