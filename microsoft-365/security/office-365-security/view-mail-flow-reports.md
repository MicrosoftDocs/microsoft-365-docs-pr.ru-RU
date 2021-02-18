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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать об отчетах о потоке обработки почты, доступных на панели мониторинга отчетов в Центре безопасности & соответствия требованиям.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286721"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="dd5e0-103">Просмотр отчетов о потоке обработки почты на панели мониторинга отчетов в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dd5e0-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dd5e0-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-104">**Applies to**</span></span>
- [<span data-ttu-id="dd5e0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dd5e0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dd5e0-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="dd5e0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd5e0-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="dd5e0-108">Помимо отчетов о потоке обработки [](mail-flow-insights-v2.md) почты, доступных на панели мониторинга потока обработки почты в Центре безопасности и & соответствия требованиям, на панели мониторинга отчетов доступны различные дополнительные отчеты о потоке обработки почты, которые помогут отслеживать организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="dd5e0-109">Если у вас есть [необходимые](#what-permissions-are-needed-to-view-these-reports)разрешения, вы можете просмотреть эти отчеты в Центре безопасности [&](https://protection.office.com) соответствия требованиям, переходить на панель мониторинга  \> **отчетов.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="dd5e0-110">Чтобы перейти непосредственно на панель мониторинга отчетов, откройте <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="dd5e0-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в Центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="dd5e0-112">Отчет о соединители</span><span class="sxs-lookup"><span data-stu-id="dd5e0-112">Connector report</span></span>

<span data-ttu-id="dd5e0-113">В **отчете о соединители** показаны действия потока почты на входящие и исходящие соединители, [](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) настроенные для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="dd5e0-114">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)  соответствия требованиям, перейдите на панель мониторинга отчетов и выберите отчет \>  **"Соединители".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="dd5e0-115">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="dd5e0-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Мини-приложения отчетов соединитела на панели мониторинга отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="dd5e0-117">Представление отчета о соединители</span><span class="sxs-lookup"><span data-stu-id="dd5e0-117">Report view for the Connector report</span></span>

<span data-ttu-id="dd5e0-118">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="dd5e0-119">**Просмотр данных по: поток обработки** почты : на этой диаграмме показано количество входящие и исходящие сообщения, организованные по:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="dd5e0-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-120">**Total**</span></span>
  - <span data-ttu-id="dd5e0-121">**Из Интернета без соединители**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="dd5e0-122">**В Интернет без соединители**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="dd5e0-123">Определенный настроенный соединител.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="dd5e0-124">Чтобы изолировать данные на диаграмме, используйте данные **"Показать"** для управления, чтобы выбрать один из этих параметров или **весь поток обработки почты.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных по потоку обработки почты в отчете о соединители](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="dd5e0-126">**Просмотр данных по: использование TLS**: на этой диаграмме показан процент использования версий TLS для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="dd5e0-127">Чтобы изолировать данные на диаграмме, используйте данные **"Показать"** для управления, чтобы выбрать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="dd5e0-128">**Весь поток почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-128">**All mail flow**</span></span>
  - <span data-ttu-id="dd5e0-129">**Из Интернета без соединители**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="dd5e0-130">**В Интернет без соединители**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="dd5e0-131">Определенный настроенный соединител.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-131">A specific connector that you've configured.</span></span>

  ![Просмотр данных по использованию TLS в отчете соединителов](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="dd5e0-133">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="dd5e0-134">Представление таблицы сведений для отчета о соединители</span><span class="sxs-lookup"><span data-stu-id="dd5e0-134">Details table view for the Connector report</span></span>

<span data-ttu-id="dd5e0-135">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dd5e0-136">**Дата**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-136">**Date**</span></span>
- <span data-ttu-id="dd5e0-137">**Направление и имя соединители**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-137">**Connector direction and name**</span></span>
- <span data-ttu-id="dd5e0-138">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-138">**Connector type**</span></span>
- <span data-ttu-id="dd5e0-139">**Принудительный TLS?**— значение **True или** **False.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="dd5e0-140">**Нет TLS** (в процентах)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="dd5e0-141">**TLS 1.0** (процент)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="dd5e0-142">**TLS 1.1** (процент)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="dd5e0-143">**TLS 1.2** (процент)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="dd5e0-144">**Volume**: Количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="dd5e0-145">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dd5e0-146">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="dd5e0-147">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="dd5e0-147">Exchange transport rule report</span></span>

<span data-ttu-id="dd5e0-148">В **отчете о правилах** транспорта Exchange показано влияние правил потока почты (также известных как правила транспорта) на входящие и исходяющие сообщения в организации.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="dd5e0-149">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)  соответствия требованиям, перейдите на панель мониторинга отчетов и выберите \>  правило **транспорта Exchange.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="dd5e0-150">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="dd5e0-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Мини-приложения правил транспорта Exchange на панели мониторинга отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="dd5e0-152">Представление отчета для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="dd5e0-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="dd5e0-153">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="dd5e0-154">**Просмотр данных с помощью: правила транспорта** \> Exchange **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="dd5e0-155">**Просмотр данных с помощью: правила транспорта** \> Exchange **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="dd5e0-156">Уровень серьезности задавается в качестве действия в правиле **(** аудит этого правила со степенью серьезности или _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="dd5e0-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="dd5e0-157">Дополнительные сведения см. в [действиях правил потока почты в Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-157">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="dd5e0-158">**Просмотр данных с помощью правил транспорта DLP Exchange** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="dd5e0-159">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="dd5e0-160">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="dd5e0-161">**Показать данные для: скомпрометированная пользователи**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="dd5e0-162">**Показать данные для: низкий объем обнаруженного содержимого в США**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="dd5e0-163">**Просмотр данных с помощью правил транспорта DLP Exchange** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="dd5e0-164">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="dd5e0-165">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="dd5e0-166">**Показать данные для: скомпрометированная пользователи**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="dd5e0-167">**Показать данные для: низкий объем обнаруженного содержимого в США**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="dd5e0-168">Если **щелкнуть "Фильтры"** в представлении отчета, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="dd5e0-169">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="dd5e0-170">Значения направления</span><span class="sxs-lookup"><span data-stu-id="dd5e0-170">Direction values</span></span>
- <span data-ttu-id="dd5e0-171">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="dd5e0-171">Severity values</span></span>

![Представление отчета в отчете о правилах транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="dd5e0-173">Представление таблицы сведений для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="dd5e0-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="dd5e0-174">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="dd5e0-175">**Просмотр данных с помощью: правила транспорта Exchange:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="dd5e0-176">**Дата**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-176">**Date**</span></span>
  - <span data-ttu-id="dd5e0-177">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-177">**Transport rule**</span></span>
  - <span data-ttu-id="dd5e0-178">**Тема**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-178">**Subject**</span></span>
  - <span data-ttu-id="dd5e0-179">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-179">**Sender address**</span></span>
  - <span data-ttu-id="dd5e0-180">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-180">**Recipient address**</span></span>
  - <span data-ttu-id="dd5e0-181">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-181">**Severity**</span></span>
  - <span data-ttu-id="dd5e0-182">**Направление**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-182">**Direction**</span></span>

- <span data-ttu-id="dd5e0-183">**Просмотр данных с помощью: правила транспорта DLP Exchange:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="dd5e0-184">**Дата**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-184">**Date**</span></span>
  - <span data-ttu-id="dd5e0-185">**Политика защиты от потери данных**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-185">**DLP policy**</span></span>
  - <span data-ttu-id="dd5e0-186">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-186">**Transport rule**</span></span>
  - <span data-ttu-id="dd5e0-187">**Тема**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-187">**Subject**</span></span>
  - <span data-ttu-id="dd5e0-188">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-188">**Sender address**</span></span>
  - <span data-ttu-id="dd5e0-189">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-189">**Recipient address**</span></span>
  - <span data-ttu-id="dd5e0-190">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-190">**Severity**</span></span>
  - <span data-ttu-id="dd5e0-191">**Направление**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-191">**Direction**</span></span>

<span data-ttu-id="dd5e0-192">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="dd5e0-193">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="dd5e0-194">Значения направления</span><span class="sxs-lookup"><span data-stu-id="dd5e0-194">Direction values</span></span>
- <span data-ttu-id="dd5e0-195">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="dd5e0-195">Severity values</span></span>

<span data-ttu-id="dd5e0-196">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="dd5e0-197">Отчет о переададпорте</span><span class="sxs-lookup"><span data-stu-id="dd5e0-197">Forwarding report</span></span>

<span data-ttu-id="dd5e0-198">В **отчете о** пересылке показано, как автоматически пересылаются сообщения организации на внешние домены из почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="dd5e0-199">Переадренные сообщения могут представлять угрозу безопасности или соответствия требованиям и указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="dd5e0-200">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите \>  **"Отчет о переадрании".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="dd5e0-201">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="dd5e0-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Виджет "Отчеты о переададпорте" на панели мониторинга отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="dd5e0-203">Представление отчета о переададпорте</span><span class="sxs-lookup"><span data-stu-id="dd5e0-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="dd5e0-204">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="dd5e0-205">**Показать данные для: методы переад вперед**: показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="dd5e0-206">**Правило транспорта:** также известное как [правила потока почты.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-206">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="dd5e0-207">**Правило почтового ящика**: также известное как [правила для входящих сообщений.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Представление методов переададпорта в отчете о переададпорте](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="dd5e0-209">**Показать данные для: домены переадправления**: в этом представлении показаны домены получателей, которые являются пунктами назначения для переадправления.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Представление "Переададант домены" в отчете "Переададант".](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="dd5e0-211">**Показать данные для: forwarders**: показаны следующие переадверы:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="dd5e0-212">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-212">**Transport rule**</span></span>
  - <span data-ttu-id="dd5e0-213">Почтовый ящик, содержащий правило для пересылаемой почты.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Представление "Переадверщики" в отчете о переададаторах](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="dd5e0-215">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="dd5e0-216">Представление таблицы сведений для отчета "Переад вперед"</span><span class="sxs-lookup"><span data-stu-id="dd5e0-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="dd5e0-217">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dd5e0-218">**Пересылатели:** значение **правила транспорта** или почтовый ящик, содержащий правило пересылки входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="dd5e0-219">**Тип пересылки:** правило почтового **ящика или** **правило транспорта.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="dd5e0-220">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-220">**Recipient name**</span></span>
- <span data-ttu-id="dd5e0-221">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-221">**Recipient domain**</span></span>
- <span data-ttu-id="dd5e0-222">**Сведения:** это значение GUID правила потока почты или значение RuleIdentity правила для почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="dd5e0-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-223">**Count**</span></span>
- <span data-ttu-id="dd5e0-224">**Дата первой переададности**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-224">**First forward date**</span></span>

<span data-ttu-id="dd5e0-225">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dd5e0-226">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="dd5e0-227">Отчет о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-227">Mailflow status report</span></span>

<span data-ttu-id="dd5e0-228">Отчет **о состоянии потока** почты похож на отчет о отправленных и полученных сообщениях электронной почты с дополнительными сведениями о сообщениях электронной почты, разрешенных или заблокированных на границе. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="dd5e0-229">Это единственный отчет, который содержит сведения о защите по краям и показывает, сколько сообщений электронной почты блокируется перед тем, как получить доступ к службе для оценки в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="dd5e0-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="dd5e0-230">Важно понимать, что если сообщение отправляется пяти получателям, мы подсчитывем его как пять разных сообщений, а не одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="dd5e0-231">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите отчет о состоянии \>  **потока обработки почты.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="dd5e0-232">Чтобы перейти непосредственно к **отчету о состоянии потока почты,** откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="dd5e0-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Мини-виджет отчета о состоянии потока почты на панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="dd5e0-234">Представление типа для отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="dd5e0-235">При открываемом отчете вкладка **"Тип"** выбрана по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="dd5e0-236">По умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="dd5e0-237">**Дата:** последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="dd5e0-238">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-238">**Direction**:</span></span>

  - <span data-ttu-id="dd5e0-239">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-239">**Inbound**</span></span>
  - <span data-ttu-id="dd5e0-240">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-240">**Outbound**</span></span>
  - <span data-ttu-id="dd5e0-241">**Внутри организации:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="dd5e0-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="dd5e0-242">отправитель abc@domain.com получателям xyz@domain.com (учитывается отдельно от  входящие и **исходящие)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="dd5e0-243">**Тип:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-243">**Type**:</span></span>

  - <span data-ttu-id="dd5e0-244">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-244">**Good mail**</span></span>
  - <span data-ttu-id="dd5e0-245">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-245">**Malware**</span></span>
  - <span data-ttu-id="dd5e0-246">**Спам**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-246">**Spam**</span></span>
  - <span data-ttu-id="dd5e0-247">**Защита на границе**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-247">**Edge protection**</span></span>
  - <span data-ttu-id="dd5e0-248">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-248">**Rule messages**</span></span>
  - <span data-ttu-id="dd5e0-249">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-249">**Phishing email**</span></span>

<span data-ttu-id="dd5e0-250">Диаграмма организована по **значениям Type.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="dd5e0-251">Вы можете изменить эти фильтры, **щелкнув** фильтр или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="dd5e0-252">Таблица данных содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-252">The data table contains the following information:</span></span>

- <span data-ttu-id="dd5e0-253">**Направление**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-253">**Direction**</span></span>
- <span data-ttu-id="dd5e0-254">**Тип**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-254">**Type**</span></span>
- <span data-ttu-id="dd5e0-255">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-255">**24 hours**</span></span>
- <span data-ttu-id="dd5e0-256">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-256">**3 days**</span></span>
- <span data-ttu-id="dd5e0-257">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-257">**7 days**</span></span>
- <span data-ttu-id="dd5e0-258">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-258">**15 days**</span></span>
- <span data-ttu-id="dd5e0-259">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-259">**30 days**</span></span>

<span data-ttu-id="dd5e0-260">Если выбрать **категорию для получения дополнительных сведений,** можно выбрать один из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="dd5e0-261">**Фишинговое сообщение** электронной почты: этот выбор перенабирает отчет [о состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="dd5e0-262">**Вредоносная программа в** электронной почте: этот выбор перенабирает отчет о [состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="dd5e0-263">**Обнаружение нежелательной почты:** этот выбор перенабирает отчет [об обнаружении нежелательной почты.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="dd5e0-264">**Edge blocked spam**: this selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="dd5e0-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="dd5e0-265">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-265">**Export**:</span></span>

<span data-ttu-id="dd5e0-266">Для подробного представления можно экспортировать данные только за один день.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="dd5e0-267">Поэтому, если вы хотите экспортировать данные за 7 дней, необходимо сделать 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="dd5e0-268">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dd5e0-269">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="dd5e0-270">Представление типа в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="dd5e0-271">Представление направления для отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="dd5e0-272">Если щелкнуть вкладку **"Направление",** будут использоваться те же фильтры по умолчанию из представления **"Тип".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="dd5e0-273">Диаграмма организована по **значениям Направления.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="dd5e0-274">Вы можете изменить эти фильтры, **щелкнув** фильтр или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="dd5e0-275">Используются те же фильтры **из** представления "Тип".</span><span class="sxs-lookup"><span data-stu-id="dd5e0-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="dd5e0-276">Таблица данных содержит те же сведения из представления **"Тип".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="dd5e0-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="dd5e0-278">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-278">**Export**:</span></span>

<span data-ttu-id="dd5e0-279">Для подробного представления можно экспортировать данные только за один день.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="dd5e0-280">Поэтому, если вы хотите экспортировать данные за 7 дней, необходимо сделать 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="dd5e0-281">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dd5e0-282">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="dd5e0-283">Представление направления в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="dd5e0-284">Представление воронки для отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="dd5e0-285">В **представлении воронки** показано, как функции защиты от угроз электронной почты Майкрософт фильтруют входящие и исходящую электронную почту в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="dd5e0-286">В нем представлены сведения об общем числе сообщений электронной почты и о том, как настроенные функции защиты от угроз, включая защиту от по краям, защиту от вредоносных программ, защиту от фишинга, нежелательной почты и спуфинга, влияют на это количество.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="dd5e0-287">Если щелкнуть вкладку **"Воронка",** по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="dd5e0-288">**Дата:** последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="dd5e0-289">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-289">**Direction**:</span></span>

  - <span data-ttu-id="dd5e0-290">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-290">**Inbound**</span></span>
  - <span data-ttu-id="dd5e0-291">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-291">**Outbound**</span></span>
  - <span data-ttu-id="dd5e0-292">**Внутри организации:** это количество для сообщений, отправленных в клиенте; То есть отправитель может abc@domain.com получателям xyz@domain.com (учитывается отдельно от входящие и исходящие).</span><span class="sxs-lookup"><span data-stu-id="dd5e0-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="dd5e0-293">Агрегированное представление и представление таблицы данных допускает фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="dd5e0-294">Если **щелкнуть "Фильтр",** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="dd5e0-295">На этой диаграмме показано количество сообщений электронной почты, организованных по:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="dd5e0-296">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-296">**Total email**</span></span>
- <span data-ttu-id="dd5e0-297">**Электронная почта после защиты по краям**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-297">**Email after edge protection**</span></span>
- <span data-ttu-id="dd5e0-298">**Электронная почта после вредоносных программ, репутация файла, блок типов файлов**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="dd5e0-299">**Электронная почта после фишинга, репутации URL-адреса, фирменный подмена, защита от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="dd5e0-300">**Электронная почта после нежелательной почты, массовая фильтрация почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="dd5e0-301">**Электронная почта после подступа пользователя и домена**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dd5e0-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="dd5e0-302">**Электронная почта после детонации файла и URL-адреса**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dd5e0-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="dd5e0-303">**Электронная почта, обнаруженная как безвластие после защиты после доставки (защита при щелчке URL-адреса)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="dd5e0-304"><sup>1</sup> Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="dd5e0-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="dd5e0-305">Чтобы просмотреть электронную почту, отфильтрованную по EOP или Защитнику для Office 365 отдельно, щелкните значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="dd5e0-306">Таблица данных содержит следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="dd5e0-307">**Дата**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-307">**Date**</span></span>
- <span data-ttu-id="dd5e0-308">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-308">**Total email**</span></span>
- <span data-ttu-id="dd5e0-309">**Защита на границе**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-309">**Edge protection**</span></span>
- <span data-ttu-id="dd5e0-310">**Антивредоносная программа, репутация файла, блок типов файлов:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="dd5e0-311">**Репутация файла:** сообщения, отфильтрованные из-за идентификации вложенного файла другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="dd5e0-312">**Блок типов файлов:** сообщения фильтруются из-за типа вредоносного файла, обнаруженного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="dd5e0-313">**Защита от фишинга, репутация URL-адреса, фирменный подмена, защита от спуфинга:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="dd5e0-314">**Репутация URL-адреса:** сообщения отфильтровываются из-за идентификации URL-адреса другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="dd5e0-315">**Фирменный под названием:** сообщения, отфильтрованные из-за сообщений от известных отправителей, которые подавят себя за фирменую марку.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="dd5e0-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="dd5e0-317">**Фильтрация нежелательной почты, массовая фильтрация почты:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="dd5e0-318">**Массовая фильтрация** почты: сообщения отфильтровыются из-за попытки доставить массовые сообщения получателям.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="dd5e0-319">**Поднаступ пользователя и домена (Защитник для Office 365):**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="dd5e0-320">**Подрисовка** пользователя: сообщения, отфильтрованные из-за попытки выдать себя за пользователя (отправитель сообщений), определенного в параметрах защиты от фишинга в политике защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="dd5e0-321">**Подрисовка** домена: сообщения, отфильтрованные из-за попытки подлиться на домен, определенный в параметрах защиты от фишинга в политике защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="dd5e0-322">**Детонация файлов и URL-адресов (Защитник для Office 365):**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="dd5e0-323">**Детонация файлов:** сообщения, отфильтрованные политикой безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="dd5e0-324">**Детонация URL-адресов:** сообщение, отфильтрованное политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="dd5e0-325">Защита после доставки и автоматическая очистка (ATP) или АВТОМАТИЧЕСКАЯ ОЧИСТКА **(EOP):** АВТОМАТИЧЕСКАЯ ОЧИСТКА означает автоматическую очистку в течение нулевого часа.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="dd5e0-326">Если выбрать строку в таблице данных, во flyout будет показана дополнительная разбивка по количеством сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="dd5e0-327">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-327">**Export**:</span></span>

<span data-ttu-id="dd5e0-328">После нажатия кнопки **"Экспорт"** в меню **"Параметры"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="dd5e0-329">**Сводка (с данными не более чем за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="dd5e0-330">**Сведения (с данными не более чем за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="dd5e0-331">В **области "Дата"** выберите диапазон и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="dd5e0-332">Данные для текущих фильтров будут экспортироваться в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="dd5e0-333">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dd5e0-334">Если данные содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="dd5e0-335">Представление воронки в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="dd5e0-336">Техническое представление отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="dd5e0-337">Представление **Tech похоже** на представление **воронки,** предоставляя более подробные сведения о настроенных средствах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="dd5e0-338">На диаграмме можно увидеть, как сообщения классифицируются на различных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="dd5e0-339">Если щелкнуть вкладку **"Техническое** представление", по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="dd5e0-340">**Дата:** последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="dd5e0-341">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-341">**Direction**:</span></span>

  - <span data-ttu-id="dd5e0-342">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-342">**Inbound**</span></span>
  - <span data-ttu-id="dd5e0-343">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-343">**Outbound**</span></span>
  - <span data-ttu-id="dd5e0-344">**Внутри организации:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="dd5e0-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="dd5e0-345">отправитель abc@domain.com получателям xyz@domain.com (учитывается отдельно от входящие и исходящие)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="dd5e0-346">Агрегированное представление и представление таблицы данных допускает фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="dd5e0-347">Если **щелкнуть "Фильтр",** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="dd5e0-348">На этой диаграмме показаны сообщения, уорганизованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="dd5e0-349">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-349">**Total email**</span></span>
- <span data-ttu-id="dd5e0-350">**Edge allow** and **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="dd5e0-351">**Не вредоносное** ПО, **обнаружение безопасных вложений,** обнаружение <sup>\*</sup> **антивредоносной программы и** сообщения **правил**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="dd5e0-352">**Не фишинг,** **сбой DMARC,** **обнаружение** подмены, обнаружение спуфингов и обнаружение **фишинга**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="dd5e0-353">**Отсутствие обнаружения с детонацией URL-адресов** **и обнаружением детонации URL-адресов**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd5e0-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="dd5e0-354">**Не спам** и нежелаемая  **почта**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="dd5e0-355">**Невредоносная электронная почта,** **обнаружение безопасных ссылок** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="dd5e0-356"><sup>\*</sup> Защитник для Office 365</span><span class="sxs-lookup"><span data-stu-id="dd5e0-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="dd5e0-357">При наведении курсор на категорию на диаграмме можно увидеть количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="dd5e0-358">Таблица данных содержит следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="dd5e0-359">**Дата**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-359">**Date**</span></span>
- <span data-ttu-id="dd5e0-360">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-360">**Total email**</span></span>
- <span data-ttu-id="dd5e0-361">**Отфильтрованный по краям**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-361">**Edge filtered**</span></span>
- <span data-ttu-id="dd5e0-362">**Антивредоносный механизм, безопасные вложения, отфильтрованное правило:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="dd5e0-363">**Отфильтрованное правило:** сообщения отфильтровыются из-за правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="dd5e0-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="dd5e0-364">**DMARC, подмена, подмена, фильтрация фишинга:**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="dd5e0-365">**DMARC**: сообщения, отфильтрованные из-за сбоя проверки подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="dd5e0-366">**Обнаружение детонации URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-366">**URL detonation detection**</span></span>
- <span data-ttu-id="dd5e0-367">**Фильтрация нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="dd5e0-368">**Удалена ZAP**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-368">**ZAP removed**</span></span>
- <span data-ttu-id="dd5e0-369">**Обнаружение с помощью безопасных ссылок**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="dd5e0-370">Если выбрать строку в таблице данных, во flyout будет показана дополнительная разбивка по количеством сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="dd5e0-371">**Экспорт**:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-371">**Export**:</span></span>

<span data-ttu-id="dd5e0-372">При нажатии кнопки **"Экспорт"** в меню **"Параметры"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="dd5e0-373">**Сводка (с данными не более чем за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="dd5e0-374">**Сведения (с данными не более чем за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="dd5e0-375">В **области "Дата"** выберите диапазон и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="dd5e0-376">Данные для текущих фильтров будут экспортироваться в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="dd5e0-377">Каждый экспортированный CSV-файл может быть ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="dd5e0-378">Если данные содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="dd5e0-379">Техническое представление в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="dd5e0-380">Отправленный и полученный отчет по электронной почте</span><span class="sxs-lookup"><span data-stu-id="dd5e0-380">Sent and received email report</span></span>

<span data-ttu-id="dd5e0-381">Отчет **об отправленных** и полученных сообщениях электронной почты — это интеллектуальный отчет, включающий сведения о входящих и исходяющих сообщениях электронной почты, в том числе об обнаружении нежелательной почты, вредоносных программах и сообщениях электронной почты, которые определены как "хорошие".</span><span class="sxs-lookup"><span data-stu-id="dd5e0-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="dd5e0-382">Разница между этим отчетом и отчетом [о](#mailflow-status-report) состоянии потока обработки почты состоит в том, что этот отчет не включает данные о сообщениях, заблокированных по краям защиты. Важно понимать, что если сообщение отправляется пяти получателям, оно считается одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="dd5e0-383">Агрегированное представление и подробное представление отчета позволяют использовать фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="dd5e0-384">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите "Отправлено" \>  **и "Получено сообщение электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="dd5e0-385">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="dd5e0-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Отправленные и полученные мини-приложения электронной почты на панели мониторинга отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="dd5e0-387">Представление отчета об отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="dd5e0-388">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="dd5e0-389">**Break down by: Type**: The chart shows all available categories:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="dd5e0-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-390">**Total**</span></span>
  - <span data-ttu-id="dd5e0-391">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-391">**Good mail**</span></span>
  - <span data-ttu-id="dd5e0-392">**Вредоносная программа (EOP)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="dd5e0-393">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-393">**Spam detections**</span></span>
  - <span data-ttu-id="dd5e0-394">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-394">**Rule messages**</span></span>
  - <span data-ttu-id="dd5e0-395">**Advanced malware** (Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="dd5e0-396">При наведении указателя мыши на день (точку данных) на диаграмме можно увидеть подробные сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление типа в отчете о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="dd5e0-398">**Break down by: Direction**: The chart shows **Total,** **Inbound**, and **Outbound** data.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="dd5e0-399">При наведении указателя мыши на день (точку данных) на диаграмме можно увидеть подробные сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление направления в отчете о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="dd5e0-401">**Drill down by** \> **Вредоносные программы (антивредоносные программы):** этот выбор перенабирает обнаружение [вредоносных программ в отчете по электронной почте.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="dd5e0-402">**Drill down by** \> **Обнаружения нежелательной почты)**— этот выбор перенабирает отчет [об обнаружении нежелательной почты.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="dd5e0-403">Если **щелкнуть "Фильтры"** в представлении отчета, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="dd5e0-404">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="dd5e0-405">Значения направления</span><span class="sxs-lookup"><span data-stu-id="dd5e0-405">Direction values</span></span>
- <span data-ttu-id="dd5e0-406">Значения типов</span><span class="sxs-lookup"><span data-stu-id="dd5e0-406">Type values</span></span>

<span data-ttu-id="dd5e0-407">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="dd5e0-408">Представление таблицы сведений для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="dd5e0-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="dd5e0-409">Если **щелкнуть "Просмотреть таблицу сведений"** в области "Разбить **по:** направление" или "Разбить **по:** представление направления", будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="dd5e0-410">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-410">**Date (UTC)**</span></span>
- <span data-ttu-id="dd5e0-411">**Тип**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-411">**Type**</span></span>
- <span data-ttu-id="dd5e0-412">**Направление**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-412">**Direction**</span></span>
- <span data-ttu-id="dd5e0-413">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-413">**Message count**</span></span>

<span data-ttu-id="dd5e0-414">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="dd5e0-415">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="dd5e0-416">Значения направления</span><span class="sxs-lookup"><span data-stu-id="dd5e0-416">Direction values</span></span>
- <span data-ttu-id="dd5e0-417">Значения типов</span><span class="sxs-lookup"><span data-stu-id="dd5e0-417">Type values</span></span>

<span data-ttu-id="dd5e0-418">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="dd5e0-419">Отчет об отправителям и получателях</span><span class="sxs-lookup"><span data-stu-id="dd5e0-419">Top senders and recipients report</span></span>

<span data-ttu-id="dd5e0-420">Отчет **о наиболее отправителям** и получателях — это круговая диаграмма, на которой отображаются ваши лучшие отправитые и получатели электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="dd5e0-421">Чтобы просмотреть отчет, откройте Центр безопасности [&](https://protection.office.com)соответствия  требованиям, перейдите на панель мониторинга отчетов и выберите самых отправителей \>  **и получателей.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="dd5e0-422">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="dd5e0-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Мини-приложения "Отправителю и получателям" на панели мониторинга отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="dd5e0-424">Представление отчета для самых отправителей и получателей</span><span class="sxs-lookup"><span data-stu-id="dd5e0-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="dd5e0-425">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="dd5e0-426">**Показать данные для самых \> больших отправителей почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="dd5e0-427">**Показать данные для самых \> больших получателей почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="dd5e0-428">**Показать данные для самых \> нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="dd5e0-429">**Показать данные для \> Получатели самых вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="dd5e0-430">**Показать данные для \> самых вредоносных получателей (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="dd5e0-431">Композиция круговой диаграммы изменяется в зависимости от этих выборов.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="dd5e0-432">При наведении курсор на замещение круговой диаграммы можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="dd5e0-433">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Круговая диаграмма в представлении "Отчет" в отчете "Лучшие отправитые и получатели"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="dd5e0-435">Представление таблицы сведений для отчета о самых отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="dd5e0-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="dd5e0-436">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="dd5e0-437">**Показать данные для самых \> больших отправителей почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="dd5e0-438">**Лучшие отправитые сообщения**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-438">**Top mail senders**</span></span>
  - <span data-ttu-id="dd5e0-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-439">**Count**</span></span>

- <span data-ttu-id="dd5e0-440">**Показать данные для самых \> больших получателей почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="dd5e0-441">**Получатели почты, которые больше всего**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="dd5e0-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-442">**Count**</span></span>

- <span data-ttu-id="dd5e0-443">**Показать данные для самых \> нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="dd5e0-444">**Получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="dd5e0-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-445">**Count**</span></span>

- <span data-ttu-id="dd5e0-446">**Показать данные для \> Получатели самых вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="dd5e0-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="dd5e0-447">**Получатели самых вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="dd5e0-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-448">**Count**</span></span>

- <span data-ttu-id="dd5e0-449">**Показать данные для \> самых вредоносных получателей (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="dd5e0-450">**Получатели самых вредоносных программ (Защитник Office 365)**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="dd5e0-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-451">**Count**</span></span>

<span data-ttu-id="dd5e0-452">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dd5e0-453">Чтобы вернуться в представление отчета, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="dd5e0-454">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="dd5e0-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="dd5e0-455">Чтобы просматривать и использовать отчеты &, описанные в этой статье, необходимо быть участником одной из следующих групп ролей в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="dd5e0-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="dd5e0-456">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-456">**Organization Management**</span></span>
- <span data-ttu-id="dd5e0-457">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-457">**Security Administrator**</span></span>
- <span data-ttu-id="dd5e0-458">**Читатель безопасности**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-458">**Security Reader**</span></span>
- <span data-ttu-id="dd5e0-459">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-459">**Global Reader**</span></span>

<span data-ttu-id="dd5e0-460">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dd5e0-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dd5e0-461">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd5e0-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="dd5e0-462">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="dd5e0-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dd5e0-463">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dd5e0-463">Related topics</span></span>

[<span data-ttu-id="dd5e0-464">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dd5e0-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="dd5e0-465">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dd5e0-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="dd5e0-466">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dd5e0-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="dd5e0-467">Просмотр отчетов для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="dd5e0-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
