---
title: Просмотр отчетов о потоке почты на панели мониторинга отчетов
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать об отчетах о потоке обработки почты, доступных на панели мониторинга отчетов в Центре безопасности & соответствия требованиям.
ms.custom: ''
ms.openlocfilehash: 1ededf2d0d693c537c159c52d00deb03f278b4b2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659469"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="a393f-103">Просмотр отчетов о потоке обработки почты на панели мониторинга отчетов в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a393f-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a393f-104">Помимо отчетов о потоке обработки [](mail-flow-insights-v2.md) почты, доступных на панели мониторинга потока обработки почты в Центре безопасности и & соответствия требованиям, на панели мониторинга отчетов доступны различные дополнительные отчеты о потоке обработки почты, которые помогут отслеживать организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a393f-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="a393f-105">Если у вас есть [необходимые](#what-permissions-are-needed-to-view-these-reports)разрешения, вы можете просмотреть эти отчеты в Центре безопасности [&](https://office.protection.com) соответствия требованиям, переходить на панель мониторинга  \> **отчетов.**</span><span class="sxs-lookup"><span data-stu-id="a393f-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="a393f-106">Чтобы перейти непосредственно на панель мониторинга отчетов, откройте <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="a393f-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в Центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="a393f-108">Отчет о соединители</span><span class="sxs-lookup"><span data-stu-id="a393f-108">Connector report</span></span>

<span data-ttu-id="a393f-109">В **отчете о соединители** [](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) показаны действия потока почты на входящие и исходящие соединители, настроенные для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a393f-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="a393f-110">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)  соответствия требованиям, перейдите на панель мониторинга отчетов и выберите отчет \>  **"Соединители".**</span><span class="sxs-lookup"><span data-stu-id="a393f-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="a393f-111">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="a393f-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Мини-приложения отчетов соединитела на панели мониторинга отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="a393f-113">Представление отчета о соединители</span><span class="sxs-lookup"><span data-stu-id="a393f-113">Report view for the Connector report</span></span>

<span data-ttu-id="a393f-114">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="a393f-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="a393f-115">**Просмотр данных по: поток обработки** почты : на этой диаграмме показано количество входящие и исходящие сообщения, организованные по:</span><span class="sxs-lookup"><span data-stu-id="a393f-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="a393f-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="a393f-116">**Total**</span></span>
  - <span data-ttu-id="a393f-117">**Из Интернета без соединители**</span><span class="sxs-lookup"><span data-stu-id="a393f-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a393f-118">**В Интернет без соединители**</span><span class="sxs-lookup"><span data-stu-id="a393f-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a393f-119">Определенный настроенный соединител.</span><span class="sxs-lookup"><span data-stu-id="a393f-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="a393f-120">Чтобы изолировать данные на диаграмме, используйте данные **"Показать"** для управления, чтобы выбрать один из этих параметров или **весь поток обработки почты.**</span><span class="sxs-lookup"><span data-stu-id="a393f-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных по потоку обработки почты в отчете о соединители](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="a393f-122">**Просмотр данных по: использование TLS**: на этой диаграмме показан процент использования версий TLS для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="a393f-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="a393f-123">Чтобы изолировать данные на диаграмме, используйте данные **"Показать"** для управления, чтобы выбрать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a393f-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="a393f-124">**Весь поток почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-124">**All mail flow**</span></span>
  - <span data-ttu-id="a393f-125">**Из Интернета без соединители**</span><span class="sxs-lookup"><span data-stu-id="a393f-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a393f-126">**В Интернет без соединители**</span><span class="sxs-lookup"><span data-stu-id="a393f-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a393f-127">Определенный настроенный соединител.</span><span class="sxs-lookup"><span data-stu-id="a393f-127">A specific connector that you've configured.</span></span>

  ![Просмотр данных по использованию TLS в отчете соединителов](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="a393f-129">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="a393f-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="a393f-130">Представление таблицы сведений для отчета о соединители</span><span class="sxs-lookup"><span data-stu-id="a393f-130">Details table view for the Connector report</span></span>

<span data-ttu-id="a393f-131">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a393f-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a393f-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="a393f-132">**Date**</span></span>
- <span data-ttu-id="a393f-133">**Направление и имя соединители**</span><span class="sxs-lookup"><span data-stu-id="a393f-133">**Connector direction and name**</span></span>
- <span data-ttu-id="a393f-134">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="a393f-134">**Connector type**</span></span>
- <span data-ttu-id="a393f-135">**Принудительный TLS?**— значение **True или** **False.**</span><span class="sxs-lookup"><span data-stu-id="a393f-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="a393f-136">**Нет TLS** (в процентах)</span><span class="sxs-lookup"><span data-stu-id="a393f-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="a393f-137">**TLS 1.0** (процент)</span><span class="sxs-lookup"><span data-stu-id="a393f-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="a393f-138">**TLS 1.1** (процент)</span><span class="sxs-lookup"><span data-stu-id="a393f-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="a393f-139">**TLS 1.2** (процент)</span><span class="sxs-lookup"><span data-stu-id="a393f-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="a393f-140">**Volume**: Количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="a393f-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="a393f-141">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="a393f-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a393f-142">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a393f-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="a393f-143">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="a393f-143">Exchange transport rule report</span></span>

<span data-ttu-id="a393f-144">В **отчете о правилах** транспорта Exchange показано влияние правил потока почты (также известных как правила транспорта) на входящие и исходяющие сообщения в организации.</span><span class="sxs-lookup"><span data-stu-id="a393f-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="a393f-145">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)  соответствия требованиям, перейдите на панель мониторинга отчетов и выберите \>  правило **транспорта Exchange.**</span><span class="sxs-lookup"><span data-stu-id="a393f-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="a393f-146">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="a393f-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Мини-приложения правил транспорта Exchange на панели мониторинга отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a393f-148">Представление отчета для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="a393f-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="a393f-149">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="a393f-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="a393f-150">**Просмотр данных с помощью: правила транспорта** \> Exchange **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="a393f-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="a393f-151">**Просмотр данных с помощью: правила транспорта** \> Exchange **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="a393f-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="a393f-152">Уровень серьезности задавается в качестве действия в правиле **(** аудит этого правила со степенью серьезности или _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="a393f-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="a393f-153">Дополнительные сведения см. в [действиях правил потока почты в Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="a393f-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="a393f-154">**Просмотр данных с помощью правил транспорта DLP Exchange** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span><span class="sxs-lookup"><span data-stu-id="a393f-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="a393f-155">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a393f-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a393f-156">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="a393f-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a393f-157">**Показать данные для: скомпрометированная пользователи**</span><span class="sxs-lookup"><span data-stu-id="a393f-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a393f-158">**Показать данные для: низкий объем обнаруженного содержимого в США**</span><span class="sxs-lookup"><span data-stu-id="a393f-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="a393f-159">**Просмотр данных с помощью правил транспорта DLP Exchange** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="a393f-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="a393f-160">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a393f-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a393f-161">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="a393f-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a393f-162">**Показать данные для: скомпрометированная пользователи**</span><span class="sxs-lookup"><span data-stu-id="a393f-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a393f-163">**Показать данные для: низкий объем обнаруженного содержимого в США**</span><span class="sxs-lookup"><span data-stu-id="a393f-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="a393f-164">Если **щелкнуть "Фильтры"** в представлении отчета, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="a393f-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="a393f-165">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="a393f-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="a393f-166">Значения направления</span><span class="sxs-lookup"><span data-stu-id="a393f-166">Direction values</span></span>
- <span data-ttu-id="a393f-167">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="a393f-167">Severity values</span></span>

![Представление отчета в отчете о правилах транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a393f-169">Представление таблицы сведений для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="a393f-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="a393f-170">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="a393f-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a393f-171">**Просмотр данных с помощью: правила транспорта Exchange:**</span><span class="sxs-lookup"><span data-stu-id="a393f-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="a393f-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="a393f-172">**Date**</span></span>
  - <span data-ttu-id="a393f-173">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="a393f-173">**Transport rule**</span></span>
  - <span data-ttu-id="a393f-174">**Тема**</span><span class="sxs-lookup"><span data-stu-id="a393f-174">**Subject**</span></span>
  - <span data-ttu-id="a393f-175">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="a393f-175">**Sender address**</span></span>
  - <span data-ttu-id="a393f-176">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="a393f-176">**Recipient address**</span></span>
  - <span data-ttu-id="a393f-177">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="a393f-177">**Severity**</span></span>
  - <span data-ttu-id="a393f-178">**Направление**</span><span class="sxs-lookup"><span data-stu-id="a393f-178">**Direction**</span></span>

- <span data-ttu-id="a393f-179">**Просмотр данных с помощью: правила транспорта DLP Exchange:**</span><span class="sxs-lookup"><span data-stu-id="a393f-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="a393f-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="a393f-180">**Date**</span></span>
  - <span data-ttu-id="a393f-181">**Политика защиты от потери данных**</span><span class="sxs-lookup"><span data-stu-id="a393f-181">**DLP policy**</span></span>
  - <span data-ttu-id="a393f-182">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="a393f-182">**Transport rule**</span></span>
  - <span data-ttu-id="a393f-183">**Тема**</span><span class="sxs-lookup"><span data-stu-id="a393f-183">**Subject**</span></span>
  - <span data-ttu-id="a393f-184">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="a393f-184">**Sender address**</span></span>
  - <span data-ttu-id="a393f-185">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="a393f-185">**Recipient address**</span></span>
  - <span data-ttu-id="a393f-186">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="a393f-186">**Severity**</span></span>
  - <span data-ttu-id="a393f-187">**Направление**</span><span class="sxs-lookup"><span data-stu-id="a393f-187">**Direction**</span></span>

<span data-ttu-id="a393f-188">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="a393f-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a393f-189">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="a393f-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="a393f-190">Значения направления</span><span class="sxs-lookup"><span data-stu-id="a393f-190">Direction values</span></span>
- <span data-ttu-id="a393f-191">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="a393f-191">Severity values</span></span>

<span data-ttu-id="a393f-192">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a393f-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="a393f-193">Отчет о переададпорте</span><span class="sxs-lookup"><span data-stu-id="a393f-193">Forwarding report</span></span>

<span data-ttu-id="a393f-194">В **отчете о** пересылке показано, как автоматически пересылаются сообщения организации на внешние домены из почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a393f-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="a393f-195">Переадренные сообщения могут представлять угрозу безопасности или соответствия требованиям и указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="a393f-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="a393f-196">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите \>  **"Отчет о переадрании".**</span><span class="sxs-lookup"><span data-stu-id="a393f-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="a393f-197">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="a393f-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Мини-приложения "Отчеты о переададаторе" на панели мониторинга отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="a393f-199">Представление отчета о переададпорте</span><span class="sxs-lookup"><span data-stu-id="a393f-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="a393f-200">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="a393f-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a393f-201">**Показать данные для: методы переад вперед**: показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="a393f-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="a393f-202">**Правило транспорта:** также известное как [правила потока почты.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="a393f-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="a393f-203">**Правило почтового ящика**: также известное как [правила для входящих сообщений.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="a393f-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Представление методов переададпорта в отчете о переададпорте](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="a393f-205">**Показать данные для: переадправление доменов**: в этом представлении показаны домены получателей, которые являются пунктами назначения для переадправления.</span><span class="sxs-lookup"><span data-stu-id="a393f-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Представление "Переададант домены" в отчете "Переададант".](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="a393f-207">**Показать данные для: forwarders**: показаны следующие переадверки:</span><span class="sxs-lookup"><span data-stu-id="a393f-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="a393f-208">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="a393f-208">**Transport rule**</span></span>
  - <span data-ttu-id="a393f-209">Почтовый ящик, содержащий правило пересылаемой почты.</span><span class="sxs-lookup"><span data-stu-id="a393f-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Представление "Переадверщики" в отчете о переададаторах](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="a393f-211">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="a393f-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="a393f-212">Представление таблицы сведений для отчета "Переад сообщений"</span><span class="sxs-lookup"><span data-stu-id="a393f-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="a393f-213">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a393f-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a393f-214">**Пересылатели:** значение **правила транспорта** или почтовый ящик, содержащий правило пересылки входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="a393f-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="a393f-215">**Тип пересылки:** правило **почтового ящика или** **правило транспорта.**</span><span class="sxs-lookup"><span data-stu-id="a393f-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="a393f-216">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="a393f-216">**Recipient name**</span></span>
- <span data-ttu-id="a393f-217">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="a393f-217">**Recipient domain**</span></span>
- <span data-ttu-id="a393f-218">**Сведения:** это значение GUID правила потока почты или значение RuleIdentity правила для почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="a393f-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="a393f-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="a393f-219">**Count**</span></span>
- <span data-ttu-id="a393f-220">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="a393f-220">**First forward date**</span></span>

<span data-ttu-id="a393f-221">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="a393f-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a393f-222">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a393f-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="a393f-223">Отчет о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-223">Mailflow status report</span></span>

<span data-ttu-id="a393f-224">Отчет **о состоянии потока** почты похож на отчет о отправленных и полученных сообщениях электронной почты с дополнительными сведениями о сообщениях электронной почты, разрешенных или заблокированных на границе. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="a393f-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="a393f-225">Это единственный отчет, содержащий сведения о защите по краям, и показывает, сколько сообщений электронной почты блокируется, прежде чем они будут разрешены в службу для оценки службой Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a393f-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a393f-226">Важно понимать, что если сообщение отправляется пяти получателям, мы подсчитывем его как пять разных сообщений, а не одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="a393f-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="a393f-227">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите отчет о состоянии \>  **потока обработки почты.**</span><span class="sxs-lookup"><span data-stu-id="a393f-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="a393f-228">Чтобы перейти непосредственно к **отчету о состоянии потока почты,** откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="a393f-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Мини-виджет отчета о состоянии потока почты на панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="a393f-230">Представление типа для отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="a393f-231">При открываемом отчете вкладка **"Тип"** выбрана по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a393f-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="a393f-232">По умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="a393f-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a393f-233">**Дата:** последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="a393f-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="a393f-234">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="a393f-234">**Direction**:</span></span>

  - <span data-ttu-id="a393f-235">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="a393f-235">**Inbound**</span></span>
  - <span data-ttu-id="a393f-236">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="a393f-236">**Outbound**</span></span>
  - <span data-ttu-id="a393f-237">**Внутри организации:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="a393f-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="a393f-238">отправитель abc@domain.com получателям xyz@domain.com (учитывается отдельно от  входящие и **исходящие)**</span><span class="sxs-lookup"><span data-stu-id="a393f-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="a393f-239">**Тип:**</span><span class="sxs-lookup"><span data-stu-id="a393f-239">**Type**:</span></span>

  - <span data-ttu-id="a393f-240">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="a393f-240">**Good mail**</span></span>
  - <span data-ttu-id="a393f-241">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="a393f-241">**Malware**</span></span>
  - <span data-ttu-id="a393f-242">**Спам**</span><span class="sxs-lookup"><span data-stu-id="a393f-242">**Spam**</span></span>
  - <span data-ttu-id="a393f-243">**Защита на границе**</span><span class="sxs-lookup"><span data-stu-id="a393f-243">**Edge protection**</span></span>
  - <span data-ttu-id="a393f-244">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="a393f-244">**Rule messages**</span></span>
  - <span data-ttu-id="a393f-245">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="a393f-245">**Phishing email**</span></span>

<span data-ttu-id="a393f-246">Диаграмма организована по **значениям Type.**</span><span class="sxs-lookup"><span data-stu-id="a393f-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="a393f-247">Вы можете изменить эти фильтры, **щелкнув** фильтр или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="a393f-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="a393f-248">Таблица данных содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a393f-248">The data table contains the following information:</span></span>

- <span data-ttu-id="a393f-249">**Направление**</span><span class="sxs-lookup"><span data-stu-id="a393f-249">**Direction**</span></span>
- <span data-ttu-id="a393f-250">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a393f-250">**Type**</span></span>
- <span data-ttu-id="a393f-251">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="a393f-251">**24 hours**</span></span>
- <span data-ttu-id="a393f-252">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="a393f-252">**3 days**</span></span>
- <span data-ttu-id="a393f-253">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="a393f-253">**7 days**</span></span>
- <span data-ttu-id="a393f-254">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="a393f-254">**15 days**</span></span>
- <span data-ttu-id="a393f-255">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="a393f-255">**30 days**</span></span>

<span data-ttu-id="a393f-256">Если выбрать **категорию для получения дополнительных** сведений, можно выбрать один из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="a393f-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="a393f-257">**Фишинговое сообщение** электронной почты: этот выбор перенабирает отчет [о состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="a393f-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a393f-258">**Вредоносная программа в** электронной почте: этот выбор перенабирает отчет о [состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="a393f-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a393f-259">**Обнаружение нежелательной почты:** этот выбор перенабирает отчет [об обнаружении нежелательной почты.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="a393f-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="a393f-260">**Edge blocked spam**: this selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a393f-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a393f-261">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="a393f-261">**Export**:</span></span>

<span data-ttu-id="a393f-262">Для подробного представления можно экспортировать данные только за один день.</span><span class="sxs-lookup"><span data-stu-id="a393f-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a393f-263">Поэтому, если вы хотите экспортировать данные за 7 дней, необходимо сделать 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="a393f-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a393f-264">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="a393f-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a393f-265">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="a393f-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="a393f-266">Представление типа в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="a393f-267">Представление направления для отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="a393f-268">Если щелкнуть вкладку **"Направление",** будут использоваться те же фильтры по умолчанию из представления **"Тип".**</span><span class="sxs-lookup"><span data-stu-id="a393f-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="a393f-269">Диаграмма организована по **значениям Направления.**</span><span class="sxs-lookup"><span data-stu-id="a393f-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="a393f-270">Вы можете изменить эти фильтры, **щелкнув** фильтр или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="a393f-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="a393f-271">Используются те же фильтры **из** представления "Тип".</span><span class="sxs-lookup"><span data-stu-id="a393f-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="a393f-272">Таблица данных содержит те же сведения из представления **"Тип".**</span><span class="sxs-lookup"><span data-stu-id="a393f-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="a393f-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="a393f-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="a393f-274">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="a393f-274">**Export**:</span></span>

<span data-ttu-id="a393f-275">Для подробного представления можно экспортировать данные только за один день.</span><span class="sxs-lookup"><span data-stu-id="a393f-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a393f-276">Поэтому, если вы хотите экспортировать данные за 7 дней, необходимо сделать 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="a393f-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a393f-277">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="a393f-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a393f-278">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="a393f-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="a393f-279">Представление направления в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="a393f-280">Представление воронки для отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="a393f-281">В **представлении воронки** показано, как функции защиты от угроз электронной почты Майкрософт фильтруют входящие и исходящую электронную почту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a393f-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="a393f-282">В нем представлены сведения об общем числе сообщений электронной почты и о том, как настроенные функции защиты от угроз, в том числе по краям защиты, защиты от вредоносных программ, защиты от фишинга, защиты от нежелательной почты и спуфинга, влияют на это количество.</span><span class="sxs-lookup"><span data-stu-id="a393f-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="a393f-283">Если щелкнуть вкладку **"Воронка",** по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="a393f-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a393f-284">**Дата:** последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="a393f-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="a393f-285">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="a393f-285">**Direction**:</span></span>

  - <span data-ttu-id="a393f-286">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="a393f-286">**Inbound**</span></span>
  - <span data-ttu-id="a393f-287">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="a393f-287">**Outbound**</span></span>
  - <span data-ttu-id="a393f-288">**Внутри организации:** это количество для сообщений, отправленных в клиенте; То есть отправитель abc@domain.com получателям xyz@domain.com (учитывается отдельно от входящие и исходящие).</span><span class="sxs-lookup"><span data-stu-id="a393f-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="a393f-289">Агрегированное представление и представление таблицы данных допускает фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="a393f-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="a393f-290">Если **щелкнуть "Фильтр",** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="a393f-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="a393f-291">На этой диаграмме показано количество сообщений электронной почты, организованных по:</span><span class="sxs-lookup"><span data-stu-id="a393f-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="a393f-292">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-292">**Total email**</span></span>
- <span data-ttu-id="a393f-293">**Электронная почта после защиты по краям**</span><span class="sxs-lookup"><span data-stu-id="a393f-293">**Email after edge protection**</span></span>
- <span data-ttu-id="a393f-294">**Электронная почта после вредоносных программ, репутация файла, блок типов файлов**</span><span class="sxs-lookup"><span data-stu-id="a393f-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="a393f-295">**Электронная почта после фишинга, репутации URL-адреса, фирменный подмена, защита от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="a393f-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="a393f-296">**Электронная почта после нежелательной почты, массовая фильтрация почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="a393f-297">**Электронная почта после подступа пользователя и домена**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a393f-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="a393f-298">**Электронная почта после детонации файла и URL-адреса**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a393f-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="a393f-299">**Электронная почта, обнаруженная как безвластие после защиты после доставки (защита при щелчке URL-адреса)**</span><span class="sxs-lookup"><span data-stu-id="a393f-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="a393f-300"><sup>1</sup> Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="a393f-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="a393f-301">Чтобы просмотреть электронную почту, отфильтрованную по EOP или Защитнику для Office 365 отдельно, щелкните значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="a393f-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="a393f-302">Таблица данных содержит следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="a393f-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="a393f-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="a393f-303">**Date**</span></span>
- <span data-ttu-id="a393f-304">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-304">**Total email**</span></span>
- <span data-ttu-id="a393f-305">**Защита на границе**</span><span class="sxs-lookup"><span data-stu-id="a393f-305">**Edge protection**</span></span>
- <span data-ttu-id="a393f-306">**Антивредоносная программа, репутация файла, блок типов файлов:**</span><span class="sxs-lookup"><span data-stu-id="a393f-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="a393f-307">**Репутация файла:** сообщения, отфильтрованные из-за идентификации вложенного файла другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a393f-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="a393f-308">**Блок типов файлов:** сообщения фильтруются из-за типа вредоносного файла, обнаруженного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="a393f-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="a393f-309">**Защита от фишинга, репутация URL-адреса, фирменный подмена, защита от спуфинга:**</span><span class="sxs-lookup"><span data-stu-id="a393f-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="a393f-310">**Репутация URL-адреса:** сообщения отфильтровываются из-за идентификации URL-адреса другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a393f-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="a393f-311">**Фирменный под названием:** сообщения, отфильтрованные из-за сообщений от известных отправителей, которые подавят себя за фирменую марку.</span><span class="sxs-lookup"><span data-stu-id="a393f-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="a393f-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span><span class="sxs-lookup"><span data-stu-id="a393f-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="a393f-313">**Anti-spam, bulk mail filtering**:</span><span class="sxs-lookup"><span data-stu-id="a393f-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="a393f-314">**Массовая фильтрация** почты: сообщения отфильтровыются из-за попытки доставить массовые сообщения получателям.</span><span class="sxs-lookup"><span data-stu-id="a393f-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="a393f-315">**Поднаступ пользователя и домена (Защитник для Office 365):**</span><span class="sxs-lookup"><span data-stu-id="a393f-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="a393f-316">**Подрисовка** пользователя: сообщения, отфильтрованные из-за попытки выдать себя за пользователя (отправитель сообщений), определенного в параметрах защиты от фишинга в политике защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="a393f-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="a393f-317">**Подрисовка** домена: сообщения, отфильтрованные из-за попытки подлиться на домен, определенный в параметрах защиты от фишинга в политике защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="a393f-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="a393f-318">**Детонация файлов и URL-адресов (Защитник для Office 365):**</span><span class="sxs-lookup"><span data-stu-id="a393f-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="a393f-319">**Детонация файлов:** сообщения, отфильтрованные политикой безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="a393f-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="a393f-320">**Детонация URL-адресов:** сообщение, отфильтрованное политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="a393f-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="a393f-321">Защита после доставки и автоматическая очистка (ATP) или АВТОМАТИЧЕСКАЯ ОЧИСТКА **(EOP):** АВТОМАТИЧЕСКАЯ ОЧИСТКА означает автоматическую очистку в течение нулевого часа.</span><span class="sxs-lookup"><span data-stu-id="a393f-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="a393f-322">Если выбрать строку в таблице данных, во flyout будет показана дополнительная разбивка по количеством сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a393f-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="a393f-323">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="a393f-323">**Export**:</span></span>

<span data-ttu-id="a393f-324">После нажатия кнопки **"Экспорт** в **параметрах"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="a393f-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="a393f-325">**Сводка (с данными не более чем за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="a393f-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="a393f-326">**Сведения (с данными не более чем за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="a393f-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="a393f-327">В **области "Дата"** выберите диапазон и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="a393f-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="a393f-328">Данные для текущих фильтров будут экспортироваться в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="a393f-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="a393f-329">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="a393f-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a393f-330">Если данные содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="a393f-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="a393f-331">Представление воронки в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="a393f-332">Техническое представление отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="a393f-333">Представление **Tech похоже** на представление **воронки,** предоставляя более подробные сведения о настроенных средствах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="a393f-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="a393f-334">На диаграмме можно увидеть, как сообщения классифицируются на различных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="a393f-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="a393f-335">Если щелкнуть вкладку **"Техническое** представление", по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="a393f-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a393f-336">**Дата:** последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="a393f-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="a393f-337">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="a393f-337">**Direction**:</span></span>

  - <span data-ttu-id="a393f-338">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="a393f-338">**Inbound**</span></span>
  - <span data-ttu-id="a393f-339">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="a393f-339">**Outbound**</span></span>
  - <span data-ttu-id="a393f-340">**Внутри организации:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="a393f-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="a393f-341">отправитель abc@domain.com получателям xyz@domain.com (учитывается отдельно от входящие и исходящие)</span><span class="sxs-lookup"><span data-stu-id="a393f-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="a393f-342">Агрегированное представление и представление таблицы данных допускает фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="a393f-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="a393f-343">Если **щелкнуть "Фильтр",** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="a393f-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="a393f-344">На этой диаграмме показаны сообщения, уорганизованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="a393f-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="a393f-345">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-345">**Total email**</span></span>
- <span data-ttu-id="a393f-346">**Edge allow** and **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="a393f-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="a393f-347">**Не вредоносное** ПО, **обнаружение безопасных вложений,** обнаружение <sup>\*</sup> **антивредоносной программы и** сообщения **правил**</span><span class="sxs-lookup"><span data-stu-id="a393f-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="a393f-348">**Не фишинг,** **сбой DMARC,** **обнаружение** подмены, обнаружение спуфингов и обнаружение **фишинга**</span><span class="sxs-lookup"><span data-stu-id="a393f-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="a393f-349">**Отсутствие обнаружения с детонацией URL-адресов** **и обнаружением детонации URL-адресов**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a393f-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="a393f-350">**Не спам** и нежелаемая  **почта**</span><span class="sxs-lookup"><span data-stu-id="a393f-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="a393f-351">**Невредоносная электронная почта,** **обнаружение безопасных ссылок** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="a393f-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="a393f-352"><sup>\*</sup> Защитник для Office 365</span><span class="sxs-lookup"><span data-stu-id="a393f-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="a393f-353">При наведении курсор на категорию на диаграмме можно увидеть количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="a393f-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="a393f-354">Таблица данных содержит следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="a393f-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="a393f-355">**Date**</span><span class="sxs-lookup"><span data-stu-id="a393f-355">**Date**</span></span>
- <span data-ttu-id="a393f-356">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-356">**Total email**</span></span>
- <span data-ttu-id="a393f-357">**Отфильтрованный по краям**</span><span class="sxs-lookup"><span data-stu-id="a393f-357">**Edge filtered**</span></span>
- <span data-ttu-id="a393f-358">**Антивредоносный механизм, безопасные вложения, отфильтрованное правило:**</span><span class="sxs-lookup"><span data-stu-id="a393f-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="a393f-359">**Отфильтрованное правило:** сообщения отфильтровыются из-за правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="a393f-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="a393f-360">**DMARC, подмена, подмена, фильтрация фишинга:**</span><span class="sxs-lookup"><span data-stu-id="a393f-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="a393f-361">**DMARC**: сообщения, отфильтрованные из-за сбоя проверки подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="a393f-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="a393f-362">**Обнаружение детонации URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="a393f-362">**URL detonation detection**</span></span>
- <span data-ttu-id="a393f-363">**Фильтрация нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="a393f-364">**Удалена ZAP**</span><span class="sxs-lookup"><span data-stu-id="a393f-364">**ZAP removed**</span></span>
- <span data-ttu-id="a393f-365">**Обнаружение с помощью безопасных ссылок**</span><span class="sxs-lookup"><span data-stu-id="a393f-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="a393f-366">Если выбрать строку в таблице данных, во flyout будет показана дополнительная разбивка по количеством сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a393f-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="a393f-367">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="a393f-367">**Export**:</span></span>

<span data-ttu-id="a393f-368">При нажатии кнопки **"Экспорт"** в меню **"Параметры"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="a393f-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="a393f-369">**Сводка (с данными не более чем за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="a393f-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="a393f-370">**Сведения (с данными не более чем за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="a393f-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="a393f-371">В **области "Дата"** выберите диапазон и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="a393f-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="a393f-372">Данные для текущих фильтров будут экспортироваться в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="a393f-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="a393f-373">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="a393f-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a393f-374">Если данные содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="a393f-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="a393f-375">Техническое представление в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="a393f-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="a393f-376">Отправленный и полученный отчет по электронной почте</span><span class="sxs-lookup"><span data-stu-id="a393f-376">Sent and received email report</span></span>

<span data-ttu-id="a393f-377">Отчет **об отправленных** и полученных сообщениях электронной почты — это интеллектуальный отчет, включающий сведения о входящих и исходяющих сообщениях электронной почты, в том числе об обнаружении нежелательной почты, вредоносных программах и сообщениях электронной почты, которые определены как "хорошие".</span><span class="sxs-lookup"><span data-stu-id="a393f-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="a393f-378">Разница между этим отчетом и отчетом [о](#mailflow-status-report) состоянии потока обработки почты состоит в том, что этот отчет не включает данные о сообщениях, заблокированных по краям защиты. Важно понимать, что если сообщение отправляется пяти получателям, оно считается одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="a393f-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="a393f-379">Агрегированное представление и подробное представление отчета позволяют использовать фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="a393f-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="a393f-380">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите "Отправлено" \>  **и "Получено сообщение электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="a393f-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="a393f-381">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="a393f-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Отправленные и полученные мини-приложения электронной почты на панели мониторинга отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a393f-383">Представление отчета об отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="a393f-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="a393f-384">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="a393f-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a393f-385">**Break down by: Type**: The chart shows all available categories:</span><span class="sxs-lookup"><span data-stu-id="a393f-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="a393f-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="a393f-386">**Total**</span></span>
  - <span data-ttu-id="a393f-387">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="a393f-387">**Good mail**</span></span>
  - <span data-ttu-id="a393f-388">**Вредоносная программа (EOP)**</span><span class="sxs-lookup"><span data-stu-id="a393f-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="a393f-389">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-389">**Spam detections**</span></span>
  - <span data-ttu-id="a393f-390">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="a393f-390">**Rule messages**</span></span>
  - <span data-ttu-id="a393f-391">**Advanced malware** (Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="a393f-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="a393f-392">При наведении указателя мыши на день (точку данных) на диаграмме можно увидеть подробные сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="a393f-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление типа в отчете о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="a393f-394">**Break down by: Direction**: The chart shows **Total,** **Inbound**, and **Outbound** data.</span><span class="sxs-lookup"><span data-stu-id="a393f-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="a393f-395">При наведении указателя мыши на день (точку данных) на диаграмме можно увидеть подробные сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="a393f-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление направления в отчете о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="a393f-397">**Drill down by** \> **Вредоносные программы (антивредоносные программы):** этот выбор перенабирает обнаружение [вредоносных программ в отчете по электронной почте.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="a393f-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="a393f-398">**Drill down by** \> **Обнаружения нежелательной почты)**— этот выбор перенабирает отчет [об обнаружении нежелательной почты.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="a393f-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a393f-399">Если **щелкнуть "Фильтры"** в представлении отчета, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="a393f-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a393f-400">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="a393f-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="a393f-401">Значения направления</span><span class="sxs-lookup"><span data-stu-id="a393f-401">Direction values</span></span>
- <span data-ttu-id="a393f-402">Значения типов</span><span class="sxs-lookup"><span data-stu-id="a393f-402">Type values</span></span>

<span data-ttu-id="a393f-403">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a393f-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a393f-404">Представление таблицы сведений для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="a393f-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="a393f-405">Если **щелкнуть "Просмотреть таблицу сведений"** в области "Разбить **по:** направление" или "Разбить **по:** представление направления", будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a393f-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="a393f-406">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="a393f-406">**Date (UTC)**</span></span>
- <span data-ttu-id="a393f-407">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a393f-407">**Type**</span></span>
- <span data-ttu-id="a393f-408">**Направление**</span><span class="sxs-lookup"><span data-stu-id="a393f-408">**Direction**</span></span>
- <span data-ttu-id="a393f-409">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="a393f-409">**Message count**</span></span>

<span data-ttu-id="a393f-410">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="a393f-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a393f-411">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="a393f-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="a393f-412">Значения направления</span><span class="sxs-lookup"><span data-stu-id="a393f-412">Direction values</span></span>
- <span data-ttu-id="a393f-413">Значения типов</span><span class="sxs-lookup"><span data-stu-id="a393f-413">Type values</span></span>

<span data-ttu-id="a393f-414">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a393f-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="a393f-415">Отчет об отправителям и получателях</span><span class="sxs-lookup"><span data-stu-id="a393f-415">Top senders and recipients report</span></span>

<span data-ttu-id="a393f-416">Отчет **о наиболее отправителям** и получателях — это круговая диаграмма, на которой отображаются ваши лучшие отправитые и получатели электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a393f-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="a393f-417">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите самых отправителей \>  **и получателей.**</span><span class="sxs-lookup"><span data-stu-id="a393f-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="a393f-418">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="a393f-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Виджет "Отправителю и получателям" на панели мониторинга отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a393f-420">Представление отчета для самых отправителей и получателей</span><span class="sxs-lookup"><span data-stu-id="a393f-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="a393f-421">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="a393f-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a393f-422">**Показать данные для самых \> больших отправителей почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="a393f-423">**Показать данные для самых \> больших получателей почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="a393f-424">**Показать данные для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="a393f-425">**Показать данные для \> Получатели самых вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="a393f-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="a393f-426">**Показать данные для самых \> вредоносных получателей (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a393f-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="a393f-427">Композиция круговой диаграммы изменяется в зависимости от этих выборов.</span><span class="sxs-lookup"><span data-stu-id="a393f-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="a393f-428">При наведении курсор на замещение круговой диаграммы можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a393f-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="a393f-429">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="a393f-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Круговая диаграмма в представлении "Отчет" в отчете "Лучшие отправитые и получатели"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a393f-431">Представление таблицы сведений для отчета о самых отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="a393f-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="a393f-432">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="a393f-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a393f-433">**Показать данные для самых \> больших отправителей почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="a393f-434">**Лучшие отправитые сообщения**</span><span class="sxs-lookup"><span data-stu-id="a393f-434">**Top mail senders**</span></span>
  - <span data-ttu-id="a393f-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="a393f-435">**Count**</span></span>

- <span data-ttu-id="a393f-436">**Показать данные для самых \> больших получателей почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="a393f-437">**Получатели почты, которые больше всего**</span><span class="sxs-lookup"><span data-stu-id="a393f-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="a393f-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="a393f-438">**Count**</span></span>

- <span data-ttu-id="a393f-439">**Показать данные для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="a393f-440">**Получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="a393f-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="a393f-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="a393f-441">**Count**</span></span>

- <span data-ttu-id="a393f-442">**Показать данные для \> Получатели самых вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="a393f-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="a393f-443">**Получатели самых вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="a393f-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="a393f-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="a393f-444">**Count**</span></span>

- <span data-ttu-id="a393f-445">**Показать данные для самых \> вредоносных получателей (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a393f-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="a393f-446">**Получатели самых вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a393f-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="a393f-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="a393f-447">**Count**</span></span>

<span data-ttu-id="a393f-448">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="a393f-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a393f-449">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a393f-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="a393f-450">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="a393f-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="a393f-451">Чтобы просматривать и использовать отчеты &, описанные в этой статье, необходимо быть участником одной из следующих групп ролей в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="a393f-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a393f-452">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="a393f-452">**Organization Management**</span></span>
- <span data-ttu-id="a393f-453">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="a393f-453">**Security Administrator**</span></span>
- <span data-ttu-id="a393f-454">**Читатель безопасности**</span><span class="sxs-lookup"><span data-stu-id="a393f-454">**Security Reader**</span></span>
- <span data-ttu-id="a393f-455">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="a393f-455">**Global Reader**</span></span>

<span data-ttu-id="a393f-456">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a393f-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="a393f-457">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в Центре администрирования Microsoft 365 предоставляет  пользователям необходимые разрешения в Центре безопасности и & соответствия требованиям и разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a393f-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a393f-458">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a393f-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a393f-459">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a393f-459">Related topics</span></span>

[<span data-ttu-id="a393f-460">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a393f-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="a393f-461">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a393f-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="a393f-462">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a393f-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="a393f-463">Просмотр отчетов для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="a393f-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
