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
description: Администраторы могут узнать, как использовать новые пользователи пересылать электронную почту в центре безопасности & соответствия требованиям, чтобы выяснить, когда пользователи в Организации переносят сообщения в новые домены.
ms.openlocfilehash: af66a84efbd4c0b8f1ccdacf4b71d1caca1c3929
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877529"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="75d8c-103">Новые пользователи пересылает электронную почту в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="75d8c-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="75d8c-104">Она подозрительна, когда новые учетные записи пользователей в Организации неожиданно начинают пересылать сообщения электронной почты внешним доменам.</span><span class="sxs-lookup"><span data-stu-id="75d8c-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="75d8c-105">**Новые домены, перенаправляемые по электронной почте** , в [центре безопасности & соответствия требованиям](https://protection.office.com) уведомляют о пересылке сообщений во внешние домены в центре безопасности соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="75d8c-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="75d8c-106">Это условие может указывать на то, что для создания новых пользователей были использованы скомпрометированные учетные записи администратора.</span><span class="sxs-lookup"><span data-stu-id="75d8c-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="75d8c-107">Если вы подозреваете, что учетные записи были скомпрометированы, ознакомьтесь со [статьей ответ на скомпрометированную учетную запись электронной почты](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="75d8c-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="75d8c-108">Это представление отображается только в том случае, если проблема обнаружена, и она отображается на странице [отчет о переадресации](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="75d8c-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Анализ новых пользователей, которые пересылают сообщения электронной почты](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="75d8c-110">Если щелкнуть мини-приложение, появится раскрывающееся меню, в котором можно найти дополнительные сведения о переадресованных сообщениях, в том числе ссылку на [отчет о переадресации](#forwarding-modifications-report) , как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="75d8c-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![Всплывающее окно со сведениями, которое появляется после нажатия кнопки новые пользователи пересылает электронную почту.](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="75d8c-112">Кроме того, вы можете перейти к этой странице сведений при выборе команды **Просмотреть все** в верхней области сведений **& рекомендации** ( **Reports** \> **панель мониторинга** отчетов или <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="75d8c-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on ( **Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="75d8c-113">Вы можете щелкнуть ссылку **Просмотреть отчет, связанный с представлением** , чтобы перейти к **отчету об изменениях переадресации** , как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="75d8c-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="75d8c-114">Отчет о перенаправлении изменений</span><span class="sxs-lookup"><span data-stu-id="75d8c-114">Forwarding modifications report</span></span>

<span data-ttu-id="75d8c-115">В **отчете пересылка изменений** отображаются сведения о сообщениях, которые автоматически пересылаются от отправителей в Организации.</span><span class="sxs-lookup"><span data-stu-id="75d8c-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="75d8c-116">Новые учетные записи, пересылаемые сообщения на внешние домены.</span><span class="sxs-lookup"><span data-stu-id="75d8c-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="75d8c-117">Учетные записи, которые пересылают сообщения на внешние домены, которые не были переадресованы другими отправителями в Организации.</span><span class="sxs-lookup"><span data-stu-id="75d8c-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="75d8c-118">Эти типы переадресованных сообщений могут представлять угрозу безопасности или соответствия требованиям, а также могут указывать на скомпрометированные учетные записи.</span><span class="sxs-lookup"><span data-stu-id="75d8c-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="75d8c-119">Отчет содержит данные в течение до 90 дней.</span><span class="sxs-lookup"><span data-stu-id="75d8c-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="75d8c-120">По умолчанию в отчете отображаются данные за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="75d8c-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="75d8c-121">Этот отчет недоступен непосредственно в [панели мониторинга обработки почты](mail-flow-insights-v2.md) или на [панели мониторинга отчетов](view-mail-flow-reports.md).</span><span class="sxs-lookup"><span data-stu-id="75d8c-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="75d8c-122">В дополнение к щелчку ссылки **Просмотреть отчет, связанную с представлением** в статье **новые пользователи пересылает сообщение электронной почты** , вы получаете отчет по следующим адресам:</span><span class="sxs-lookup"><span data-stu-id="75d8c-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="75d8c-123">Щелкнув ссылку **отчет о переадресации** , в разделе сведения о [перенаправляемых почтовых доменах](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="75d8c-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="75d8c-124">Открытие <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="75d8c-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="75d8c-125">Представление отчета для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="75d8c-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="75d8c-126">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="75d8c-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="75d8c-127">**Показать данные для: новые пересылаемые пользователи** :</span><span class="sxs-lookup"><span data-stu-id="75d8c-127">**Show data for: New forwarding users** :</span></span>

  ![Новые пересылаемые пользователи Просмотр в отчете о перенаправлении](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="75d8c-129">**Показать данные для: новые домены пересылки** :</span><span class="sxs-lookup"><span data-stu-id="75d8c-129">**Show data for: New forwarding domains** :</span></span>

  ![Представление новых переадресованных доменов в отчете о пересылке](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="75d8c-131">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным** датами.</span><span class="sxs-lookup"><span data-stu-id="75d8c-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="75d8c-132">Представление таблицы сведений для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="75d8c-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="75d8c-133">Если щелкнуть **Таблица Просмотр сведений** , отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="75d8c-133">If you click **View details table** , the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="75d8c-134">**Показать данные для: новые пересылаемые пользователи** :</span><span class="sxs-lookup"><span data-stu-id="75d8c-134">**Show data for: New forwarding users** :</span></span>

  - <span data-ttu-id="75d8c-135">**Name** : адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="75d8c-135">**Name** : The email address of the sender.</span></span>
  - <span data-ttu-id="75d8c-136">**Тип переадресации**</span><span class="sxs-lookup"><span data-stu-id="75d8c-136">**Forwarding type**</span></span>
  - <span data-ttu-id="75d8c-137">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="75d8c-137">**Recipient address**</span></span>
  - <span data-ttu-id="75d8c-138">**Details**</span><span class="sxs-lookup"><span data-stu-id="75d8c-138">**Details**</span></span>
  - <span data-ttu-id="75d8c-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="75d8c-139">**Count**</span></span>
  - <span data-ttu-id="75d8c-140">**Дата первой пересылки**</span><span class="sxs-lookup"><span data-stu-id="75d8c-140">**First forward date**</span></span>

- <span data-ttu-id="75d8c-141">**Показать данные для: новые домены пересылки** :</span><span class="sxs-lookup"><span data-stu-id="75d8c-141">**Show data for: New forwarding domains** :</span></span>

  - <span data-ttu-id="75d8c-142">**Name** : домен электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="75d8c-142">**Name** : The email domain of the sender.</span></span>
  - <span data-ttu-id="75d8c-143">**Тип переадресации**</span><span class="sxs-lookup"><span data-stu-id="75d8c-143">**Forwarding type**</span></span>
  - <span data-ttu-id="75d8c-144">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="75d8c-144">**Recipient address**</span></span>
  - <span data-ttu-id="75d8c-145">**Details**</span><span class="sxs-lookup"><span data-stu-id="75d8c-145">**Details**</span></span>
  - <span data-ttu-id="75d8c-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="75d8c-146">**Count**</span></span>
  - <span data-ttu-id="75d8c-147">**Дата первой пересылки**</span><span class="sxs-lookup"><span data-stu-id="75d8c-147">**First forward date**</span></span>

<span data-ttu-id="75d8c-148">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="75d8c-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="75d8c-149">Если выбрать строку из таблицы, откроется всплывающее окно со **сведениями** со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="75d8c-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="75d8c-150">**Name** : адрес электронной почты отправителя ( **Показать данные для: новое перенаправление пользователей** ) или домен электронной почты отправителя ( **Показать данные для: новые домены пересылки** ).</span><span class="sxs-lookup"><span data-stu-id="75d8c-150">**Name** : This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="75d8c-151">**Тип переадресации**</span><span class="sxs-lookup"><span data-stu-id="75d8c-151">**Forwarding type**</span></span>
- <span data-ttu-id="75d8c-152">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="75d8c-152">**Recipient**</span></span>
- <span data-ttu-id="75d8c-153">**Details**</span><span class="sxs-lookup"><span data-stu-id="75d8c-153">**Details**</span></span>
- <span data-ttu-id="75d8c-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="75d8c-154">**Count**</span></span>
- <span data-ttu-id="75d8c-155">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="75d8c-155">**Start date**</span></span>
- <span data-ttu-id="75d8c-156">**Рекомендация** : отсюда вы можете щелкнуть ссылку для управления пользователем в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75d8c-156">**Recommendation** : From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Всплывающее окно со сведениями из таблицы "сведения" нового представления "перенаправление пользователей" в отчете "пересылка изменений".](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="75d8c-158">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="75d8c-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75d8c-159">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="75d8c-159">Related topics</span></span>

<span data-ttu-id="75d8c-160">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="75d8c-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
