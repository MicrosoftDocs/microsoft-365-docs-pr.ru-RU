---
title: Анализ новых пользователей, которые пересылают сообщения электронной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут научиться использовать новые пользователи, пересылающие аналитические сведения электронной почты, в Центре безопасности & И требованиям для расследования, когда пользователи в их организации пересылают сообщения на новые домены.
ms.openlocfilehash: cb2e16d321e181916219e3425c26e59ebe31b866
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826987"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="d3df2-103">Новые пользователи пересылают аналитику электронной почты в Центре безопасности & требованиям</span><span class="sxs-lookup"><span data-stu-id="d3df2-103">New users forwarding email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="d3df2-104">Подозрительный процесс передачи сообщений на внешние домены подозрительным.</span><span class="sxs-lookup"><span data-stu-id="d3df2-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="d3df2-105">Новые **домены, которые пересылают электронную** почту, уведомляет вас о недавно создаваемых пользователями в организации, пересылающем сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="d3df2-105">The **New domains being forwarded email** insight notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="d3df2-106">Это условие может указывать на компрометацию учетных записей администраторов, созданных для создания новых пользователей.</span><span class="sxs-lookup"><span data-stu-id="d3df2-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="d3df2-107">Если вы подозревали, что учетные записи были скомпрометированы, см. раздел ["Реагирование на компрометацию учетной записи электронной почты".](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)</span><span class="sxs-lookup"><span data-stu-id="d3df2-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="d3df2-108">Эта аналитика появляется только при обнаружении проблемы и отображается на странице [отчета о пересылке.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="d3df2-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых пользователей, которые пересылают сообщения электронной почты](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="d3df2-110">Если щелкнуть мини-приложение, появляется всплывающий элемент, в котором можно получить дополнительные сведения об пересылаемых сообщениях, включая ссылку на [отчет изменений пересылки,](#forwarding-modifications-report) как описано ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d3df2-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![Всплывающий элемент "Подробности", который появляется после нажатия на аналитику "Новые пользователи"](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="d3df2-112">Вы также можете попадать на эту страницу сведений при выборе аналитики после нажатия кнопки **"Просмотреть** все" **в верхней & рекомендаций** в области рекомендования (**на панели** \> **мониторинга** <https://protection.office.com/insightdashboard> или).</span><span class="sxs-lookup"><span data-stu-id="d3df2-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="d3df2-113">Вы можете щелкнуть **ссылку "Просмотреть отчет, связанный со аналитическим** ссылкой", чтобы перейти **к отчету "Пересылка** изменений", как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="d3df2-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="d3df2-114">Отчет об изменениях переадресации</span><span class="sxs-lookup"><span data-stu-id="d3df2-114">Forwarding modifications report</span></span>

<span data-ttu-id="d3df2-115">В **отчете об изменениях пересылки** отображаются сведения о сообщениях, которые автоматически пересылаются отправителями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d3df2-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="d3df2-116">создание создаваемых учетных записей, которые пересылают сообщения на внешние домены;</span><span class="sxs-lookup"><span data-stu-id="d3df2-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="d3df2-117">Учетные записи, которые пересылают сообщения на внешние домены, которые никогда не пересылаются другими отправителями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d3df2-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="d3df2-118">Эти типы пересланных сообщений могут представлять угрозу безопасности или соответствия требованиям, а также могут указывать на компрометацию учетных записей.</span><span class="sxs-lookup"><span data-stu-id="d3df2-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="d3df2-119">В отчете содержатся данные за период до 90 дней.</span><span class="sxs-lookup"><span data-stu-id="d3df2-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="d3df2-120">По умолчанию в отчете отображаются данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d3df2-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="d3df2-121">Этот отчет недоступен напрямую на панели [мониторинга потока обработки почты](mail-flow-insights-v2.md) или на панели [мониторинга отчетов.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="d3df2-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="d3df2-122">Помимо щелчка **ссылки "Просмотреть отчет",** связанного со ссылкой "Сведения о новых пользователях" в аналитическом **сведениях** для новых пользователей, вы можете просмотреть отчет по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="d3df2-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="d3df2-123">Щелкните ссылку **"Отчет о пересылке"** в дополнительных сведениях о новых доменах, [которые пересылают ся.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="d3df2-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="d3df2-124"><https://protection.office.com/reportv2?id=MailFlowNewForwarding>Открытие.</span><span class="sxs-lookup"><span data-stu-id="d3df2-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="d3df2-125">Представление отчета для отчета "Пересылка изменений"</span><span class="sxs-lookup"><span data-stu-id="d3df2-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="d3df2-126">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="d3df2-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d3df2-127">**Показать данные для: Новые пользователи пересылки:**</span><span class="sxs-lookup"><span data-stu-id="d3df2-127">**Show data for: New forwarding users**:</span></span>

  ![Новые пользователи пересылки в отчете изменений пересылки](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="d3df2-129">**Отображение данных для: Новые домены пересылки:**</span><span class="sxs-lookup"><span data-stu-id="d3df2-129">**Show data for: New forwarding domains**:</span></span>

  ![Представление новых переадресованных доменов в отчете об изменениях пересылки](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="d3df2-131">При выборе **фильтров в представлении** отчета можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="d3df2-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="d3df2-132">Представление таблицы подробностей для отчета "Изменения пересылки"</span><span class="sxs-lookup"><span data-stu-id="d3df2-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="d3df2-133">При нажатии **кнопки "Просмотр таблицы**сведений" показанная информация зависит от диаграммы, на которую вы ищете:</span><span class="sxs-lookup"><span data-stu-id="d3df2-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d3df2-134">**Показать данные для: Новые пользователи пересылки:**</span><span class="sxs-lookup"><span data-stu-id="d3df2-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="d3df2-135">**Name**— адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="d3df2-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="d3df2-136">**Тип пересылки**</span><span class="sxs-lookup"><span data-stu-id="d3df2-136">**Forwarding type**</span></span>
  - <span data-ttu-id="d3df2-137">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="d3df2-137">**Recipient address**</span></span>
  - <span data-ttu-id="d3df2-138">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d3df2-138">**Details**</span></span>
  - <span data-ttu-id="d3df2-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="d3df2-139">**Count**</span></span>
  - <span data-ttu-id="d3df2-140">**Дата первого переадресации**</span><span class="sxs-lookup"><span data-stu-id="d3df2-140">**First forward date**</span></span>

- <span data-ttu-id="d3df2-141">**Отображение данных для: Новые домены пересылки:**</span><span class="sxs-lookup"><span data-stu-id="d3df2-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="d3df2-142">**Имя**— домен электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="d3df2-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="d3df2-143">**Тип пересылки**</span><span class="sxs-lookup"><span data-stu-id="d3df2-143">**Forwarding type**</span></span>
  - <span data-ttu-id="d3df2-144">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="d3df2-144">**Recipient address**</span></span>
  - <span data-ttu-id="d3df2-145">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d3df2-145">**Details**</span></span>
  - <span data-ttu-id="d3df2-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="d3df2-146">**Count**</span></span>
  - <span data-ttu-id="d3df2-147">**Дата первого переадресации**</span><span class="sxs-lookup"><span data-stu-id="d3df2-147">**First forward date**</span></span>

<span data-ttu-id="d3df2-148">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="d3df2-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d3df2-149">При выборе строки в таблице **появится** всплывающая область "Подробно" со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="d3df2-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="d3df2-150">**Имя**. Это адрес электронной почты отправителя (из поля "Показать данные для: представление **новых адресованных** пользователей") или домен электронной почты отправителя (из представления **доменов для новых доменов пересылки).**</span><span class="sxs-lookup"><span data-stu-id="d3df2-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="d3df2-151">**Тип пересылки**</span><span class="sxs-lookup"><span data-stu-id="d3df2-151">**Forwarding type**</span></span>
- <span data-ttu-id="d3df2-152">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="d3df2-152">**Recipient**</span></span>
- <span data-ttu-id="d3df2-153">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d3df2-153">**Details**</span></span>
- <span data-ttu-id="d3df2-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="d3df2-154">**Count**</span></span>
- <span data-ttu-id="d3df2-155">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="d3df2-155">**Start date**</span></span>
- <span data-ttu-id="d3df2-156">**Рекомендации:** здесь можно щелкнуть ссылку, чтобы управлять пользователем в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3df2-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Всплывающая подэлемент" таблицы сведений просмотра новых пользователей пересылки в отчете "Изменения пересылки"](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="d3df2-158">Чтобы вернуться в представление отчетов, нажмите **кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="d3df2-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3df2-159">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d3df2-159">Related topics</span></span>

<span data-ttu-id="d3df2-160">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d3df2-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
