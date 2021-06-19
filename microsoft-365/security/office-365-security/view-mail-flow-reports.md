---
title: Просмотр отчетов о потоке почты в панели мониторинга отчетов
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
description: Администраторы могут узнать о отчетах о потоке почты, доступных на панели мониторинга отчетов в центре & соответствия требованиям.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029480"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="04fde-103">Просмотр отчетов о потоке почты на панели мониторинга отчетов в центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="04fde-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04fde-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="04fde-104">**Applies to**</span></span>
- [<span data-ttu-id="04fde-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="04fde-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="04fde-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="04fde-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="04fde-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04fde-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="04fde-108">Большинство отчетов, описанных в этом разделе, доступны в центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="04fde-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="04fde-109">Дополнительные сведения см. в сообщении о потоке [почты в новом центре администрирования Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="04fde-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="04fde-110">Отчет [о правилах транспорта Exchange](view-email-security-reports.md#exchange-transport-rule-report) доступен на портале Защитник Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04fde-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="04fde-111">Помимо отчетов о потоках почты, [](mail-flow-insights-v2.md) доступных на панели мониторинга потока почты в Центре обеспечения безопасности & соответствия требованиям, в панели отчетов доступны дополнительные отчеты о потоках почты, которые помогут отслеживать организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04fde-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="04fde-112">Если у вас есть [необходимые](#what-permissions-are-needed-to-view-these-reports)разрешения, вы можете просмотреть эти отчеты в Центре & соответствия требованиям, переехав на панель мониторинга [](https://protection.office.com)  \> **отчетов**.</span><span class="sxs-lookup"><span data-stu-id="04fde-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="04fde-113">Чтобы перейти непосредственно к панели мониторинга Отчетов, откройте <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="04fde-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Информационная панель отчетов в Центре & безопасности](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="04fde-115">Отчет connector</span><span class="sxs-lookup"><span data-stu-id="04fde-115">Connector report</span></span>

<span data-ttu-id="04fde-116">В **отчете Connector** показана активность потока почты на [входящие](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) и исходящие соединители, настроенные для организации.</span><span class="sxs-lookup"><span data-stu-id="04fde-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="04fde-117">Чтобы просмотреть отчет, откройте центр [&](https://protection.office.com)безопасности,  перейдите к панели мониторинга отчетов и \>  выберите **отчет Connector**.</span><span class="sxs-lookup"><span data-stu-id="04fde-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="04fde-118">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="04fde-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Виджет отчета connector в панели мониторинга Отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="04fde-120">Представление отчета для отчета Connector</span><span class="sxs-lookup"><span data-stu-id="04fde-120">Report view for the Connector report</span></span>

<span data-ttu-id="04fde-121">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="04fde-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="04fde-122">**Просмотр данных по: поток почты.** На этой диаграмме показано количество входящие и исходящие сообщения, организованные по:</span><span class="sxs-lookup"><span data-stu-id="04fde-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="04fde-123">**Total**</span><span class="sxs-lookup"><span data-stu-id="04fde-123">**Total**</span></span>
  - <span data-ttu-id="04fde-124">**Из Интернета без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="04fde-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="04fde-125">**В Интернет без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="04fde-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="04fde-126">Определенный соединитатель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="04fde-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="04fde-127">Чтобы изолировать данные на диаграмме, используйте данные **Show** для управления, чтобы выбрать один из этих параметров или **весь поток почты.**</span><span class="sxs-lookup"><span data-stu-id="04fde-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных по потоку почты в отчете Connector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="04fde-129">**Просмотр данных по: использование TLS.** На этой диаграмме показан процент использования версии TLS для потока почты.</span><span class="sxs-lookup"><span data-stu-id="04fde-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="04fde-130">Чтобы изолировать данные на диаграмме, используйте данные **Show** для управления, чтобы выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="04fde-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="04fde-131">**Весь поток почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-131">**All mail flow**</span></span>
  - <span data-ttu-id="04fde-132">**Из Интернета без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="04fde-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="04fde-133">**В Интернет без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="04fde-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="04fde-134">Определенный соединитатель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="04fde-134">A specific connector that you've configured.</span></span>

  ![Просмотр данных с помощью TLS в отчете Connector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="04fde-136">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="04fde-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="04fde-137">Представление таблицы сведений для отчета Connector</span><span class="sxs-lookup"><span data-stu-id="04fde-137">Details table view for the Connector report</span></span>

<span data-ttu-id="04fde-138">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="04fde-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="04fde-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="04fde-139">**Date**</span></span>
- <span data-ttu-id="04fde-140">**Направление и имя соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="04fde-140">**Connector direction and name**</span></span>
- <span data-ttu-id="04fde-141">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="04fde-141">**Connector type**</span></span>
- <span data-ttu-id="04fde-142">**Forced TLS?**: Значение **True или** **False**.</span><span class="sxs-lookup"><span data-stu-id="04fde-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="04fde-143">**Нет TLS** (процент)</span><span class="sxs-lookup"><span data-stu-id="04fde-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="04fde-144">**TLS 1.0** (процент)</span><span class="sxs-lookup"><span data-stu-id="04fde-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="04fde-145">**TLS 1.1** (процент)</span><span class="sxs-lookup"><span data-stu-id="04fde-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="04fde-146">**TLS 1.2** (процент)</span><span class="sxs-lookup"><span data-stu-id="04fde-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="04fde-147">**Том.** Количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="04fde-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="04fde-148">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="04fde-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="04fde-149">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="04fde-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="04fde-150">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="04fde-150">Exchange transport rule report</span></span>

<span data-ttu-id="04fde-151">В **отчете о** правилах транспорта Exchange показано влияние правил потока почты (также известных как правила транспорта) на входящие и исходяющие сообщения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="04fde-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="04fde-152">Чтобы просмотреть отчет, откройте центр & безопасности,  перейдите [к](https://protection.office.com)панели мониторинга отчетов и выберите \>  правило **транспорта Exchange.**</span><span class="sxs-lookup"><span data-stu-id="04fde-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="04fde-153">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="04fde-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Виджет правила транспорта Exchange в панели мониторинга Отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="04fde-155">Представление отчета для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="04fde-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="04fde-156">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="04fde-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="04fde-157">**Просмотр данных по: Правила транспорта** \> Exchange **Break down by: Direction:** This chart shows the number of **Inbound** and **Outbound messages** that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="04fde-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="04fde-158">**Просмотр данных по: Правила транспорта** \> Exchange **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="04fde-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="04fde-159">Вы установите уровень серьезности в качестве действия в правиле **(Аудит** этого правила с уровнем серьезности или _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="04fde-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="04fde-160">Дополнительные сведения см. в сообщении о действиях правила [потока почты в Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="04fde-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="04fde-161">**Просмотр данных по: правила транспорта DLP Exchange** \> **Break down by: Direction:** This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span><span class="sxs-lookup"><span data-stu-id="04fde-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="04fde-162">Далее можно уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="04fde-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="04fde-163">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="04fde-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="04fde-164">**Показать данные для: скомпрометированная пользователей**</span><span class="sxs-lookup"><span data-stu-id="04fde-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="04fde-165">**Показать данные для: Низкий объем контента, обнаруженного Патриотический акт США**</span><span class="sxs-lookup"><span data-stu-id="04fde-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="04fde-166">**Просмотр данных по: правила транспорта DLP Exchange** \> **Break down by: Direction:** This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="04fde-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="04fde-167">Далее можно уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="04fde-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="04fde-168">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="04fde-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="04fde-169">**Показать данные для: скомпрометированная пользователей**</span><span class="sxs-lookup"><span data-stu-id="04fde-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="04fde-170">**Показать данные для: Низкий объем контента, обнаруженного Патриотический акт США**</span><span class="sxs-lookup"><span data-stu-id="04fde-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="04fde-171">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров::</span><span class="sxs-lookup"><span data-stu-id="04fde-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="04fde-172">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="04fde-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="04fde-173">Значения направления</span><span class="sxs-lookup"><span data-stu-id="04fde-173">Direction values</span></span>
- <span data-ttu-id="04fde-174">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="04fde-174">Severity values</span></span>

![Представление отчета в отчете о правилах транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="04fde-176">Представление таблицы сведений для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="04fde-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="04fde-177">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="04fde-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="04fde-178">**Просмотр данных по: Правила транспорта Exchange:**</span><span class="sxs-lookup"><span data-stu-id="04fde-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="04fde-179">**Date**</span><span class="sxs-lookup"><span data-stu-id="04fde-179">**Date**</span></span>
  - <span data-ttu-id="04fde-180">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="04fde-180">**Transport rule**</span></span>
  - <span data-ttu-id="04fde-181">**Тема**</span><span class="sxs-lookup"><span data-stu-id="04fde-181">**Subject**</span></span>
  - <span data-ttu-id="04fde-182">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="04fde-182">**Sender address**</span></span>
  - <span data-ttu-id="04fde-183">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="04fde-183">**Recipient address**</span></span>
  - <span data-ttu-id="04fde-184">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="04fde-184">**Severity**</span></span>
  - <span data-ttu-id="04fde-185">**Направление**</span><span class="sxs-lookup"><span data-stu-id="04fde-185">**Direction**</span></span>

- <span data-ttu-id="04fde-186">**Просмотр данных по: правила транспорта DLP Exchange:**</span><span class="sxs-lookup"><span data-stu-id="04fde-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="04fde-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="04fde-187">**Date**</span></span>
  - <span data-ttu-id="04fde-188">**Политика DLP**</span><span class="sxs-lookup"><span data-stu-id="04fde-188">**DLP policy**</span></span>
  - <span data-ttu-id="04fde-189">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="04fde-189">**Transport rule**</span></span>
  - <span data-ttu-id="04fde-190">**Тема**</span><span class="sxs-lookup"><span data-stu-id="04fde-190">**Subject**</span></span>
  - <span data-ttu-id="04fde-191">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="04fde-191">**Sender address**</span></span>
  - <span data-ttu-id="04fde-192">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="04fde-192">**Recipient address**</span></span>
  - <span data-ttu-id="04fde-193">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="04fde-193">**Severity**</span></span>
  - <span data-ttu-id="04fde-194">**Направление**</span><span class="sxs-lookup"><span data-stu-id="04fde-194">**Direction**</span></span>

<span data-ttu-id="04fde-195">Если **щелкнуть Фильтры** в представлении таблицы сведений, результаты можно изменить следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="04fde-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="04fde-196">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="04fde-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="04fde-197">Значения направления</span><span class="sxs-lookup"><span data-stu-id="04fde-197">Direction values</span></span>
- <span data-ttu-id="04fde-198">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="04fde-198">Severity values</span></span>

<span data-ttu-id="04fde-199">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="04fde-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="04fde-200">Отчет о переадпорте</span><span class="sxs-lookup"><span data-stu-id="04fde-200">Forwarding report</span></span>

<span data-ttu-id="04fde-201">В **отчете о** пересылке показаны автоматически пересылаемые сообщения организации во внешние домены из Exchange Online почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="04fde-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="04fde-202">Переадренные сообщения могут представлять угрозу безопасности или соответствия требованиям, а также указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="04fde-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="04fde-203">Чтобы просмотреть отчет, откройте Центр [&](https://protection.office.com)безопасности,  перейдите на панель мониторинга отчетов и \>  выберите отчет **о переадпорте.**</span><span class="sxs-lookup"><span data-stu-id="04fde-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="04fde-204">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="04fde-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Виджет отчета о переадпорте в панели мониторинга Отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="04fde-206">Представление отчета для отчета о переадпорте</span><span class="sxs-lookup"><span data-stu-id="04fde-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="04fde-207">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="04fde-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="04fde-208">**Показать данные для: Методы переададки:** показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="04fde-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="04fde-209">**Правило транспорта:** Также известное как [правила потока почты.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="04fde-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="04fde-210">**Правило почтовых ящиков:** Также известное как [правила "Входящие".](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="04fde-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Представление методов переададки в отчете о переадпорте](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="04fde-212">**Показать данные для: Переадправление доменов.** В этом представлении показаны домены получателей, которые являются пунктами назначения для переадправления.</span><span class="sxs-lookup"><span data-stu-id="04fde-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Представление переадпорта доменов в отчете о переадпорте](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="04fde-214">**Показать данные для: Переадверы**: Показаны следующие переад.</span><span class="sxs-lookup"><span data-stu-id="04fde-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="04fde-215">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="04fde-215">**Transport rule**</span></span>
  - <span data-ttu-id="04fde-216">Почтовый ящик, содержащий правило "Входящие" пересылания.</span><span class="sxs-lookup"><span data-stu-id="04fde-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarders view in the Forwarding report](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="04fde-218">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="04fde-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="04fde-219">Представление таблицы сведений для отчета о переадпорте</span><span class="sxs-lookup"><span data-stu-id="04fde-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="04fde-220">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="04fde-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="04fde-221">**Переадпортаторы.** **Правило** транспорта значения или почтовый ящик, содержащий правило почтовых ящиков пересылания.</span><span class="sxs-lookup"><span data-stu-id="04fde-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="04fde-222">**Тип пересылания:** правило **почтовых ящиков значения** или **правило транспорта.**</span><span class="sxs-lookup"><span data-stu-id="04fde-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="04fde-223">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="04fde-223">**Recipient name**</span></span>
- <span data-ttu-id="04fde-224">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="04fde-224">**Recipient domain**</span></span>
- <span data-ttu-id="04fde-225">**Сведения.** Это значение GUID правила потока почты или значение RuleIdentity правила "Входящие".</span><span class="sxs-lookup"><span data-stu-id="04fde-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="04fde-226">**Count**</span><span class="sxs-lookup"><span data-stu-id="04fde-226">**Count**</span></span>
- <span data-ttu-id="04fde-227">**Дата первой переададки**</span><span class="sxs-lookup"><span data-stu-id="04fde-227">**First forward date**</span></span>

<span data-ttu-id="04fde-228">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="04fde-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="04fde-229">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="04fde-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="04fde-230">Отчет о состоянии почтового потока</span><span class="sxs-lookup"><span data-stu-id="04fde-230">Mailflow status report</span></span>

<span data-ttu-id="04fde-231">Отчет **о состоянии почтового потока** похож на отчет отправленной и полученной электронной почты, а дополнительные сведения о электронной почте разрешены или заблокированы на краю. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="04fde-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="04fde-232">Это единственный отчет, содержащий сведения о защите края, и показывает, сколько сообщений электронной почты блокируется перед тем, как быть разрешено в службу для оценки Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="04fde-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="04fde-233">Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="04fde-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="04fde-234">Чтобы просмотреть отчет, откройте Центр [&](https://protection.office.com)безопасности,  перейдите к панели мониторинга отчетов и выберите отчет о состоянии \>  **mailflow.**</span><span class="sxs-lookup"><span data-stu-id="04fde-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="04fde-235">Чтобы перейти непосредственно к отчету о состоянии **потока почты,** откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="04fde-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Виджет отчета о состоянии почтового потока в панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="04fde-237">Введите представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="04fde-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="04fde-238">При открывании отчета вкладка **Type** выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="04fde-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="04fde-239">По умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="04fde-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="04fde-240">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="04fde-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="04fde-241">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="04fde-241">**Direction**:</span></span>

  - <span data-ttu-id="04fde-242">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="04fde-242">**Inbound**</span></span>
  - <span data-ttu-id="04fde-243">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="04fde-243">**Outbound**</span></span>
  - <span data-ttu-id="04fde-244">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="04fde-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="04fde-245">отправитель abc@domain.com получателям xyz@domain.com (засчитываются  отдельно от входящие и **исходящие)**</span><span class="sxs-lookup"><span data-stu-id="04fde-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="04fde-246">**Тип:**</span><span class="sxs-lookup"><span data-stu-id="04fde-246">**Type**:</span></span>

  - <span data-ttu-id="04fde-247">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="04fde-247">**Good mail**</span></span>
  - <span data-ttu-id="04fde-248">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="04fde-248">**Malware**</span></span>
  - <span data-ttu-id="04fde-249">**Спам**</span><span class="sxs-lookup"><span data-stu-id="04fde-249">**Spam**</span></span>
  - <span data-ttu-id="04fde-250">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="04fde-250">**Edge protection**</span></span>
  - <span data-ttu-id="04fde-251">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="04fde-251">**Rule messages**</span></span>
  - <span data-ttu-id="04fde-252">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="04fde-252">**Phishing email**</span></span>

<span data-ttu-id="04fde-253">Диаграмма организована **значениями Type.**</span><span class="sxs-lookup"><span data-stu-id="04fde-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="04fde-254">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="04fde-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="04fde-255">В таблице данных содержатся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="04fde-255">The data table contains the following information:</span></span>

- <span data-ttu-id="04fde-256">**Направление**</span><span class="sxs-lookup"><span data-stu-id="04fde-256">**Direction**</span></span>
- <span data-ttu-id="04fde-257">**Тип**</span><span class="sxs-lookup"><span data-stu-id="04fde-257">**Type**</span></span>
- <span data-ttu-id="04fde-258">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="04fde-258">**24 hours**</span></span>
- <span data-ttu-id="04fde-259">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="04fde-259">**3 days**</span></span>
- <span data-ttu-id="04fde-260">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="04fde-260">**7 days**</span></span>
- <span data-ttu-id="04fde-261">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="04fde-261">**15 days**</span></span>
- <span data-ttu-id="04fde-262">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="04fde-262">**30 days**</span></span>

<span data-ttu-id="04fde-263">Если вы **нажмете Выберите категорию для получения** дополнительных сведений, вы можете выбрать из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="04fde-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="04fde-264">**Фишинговое письмо.** Этот выбор принимает вас к отчету о [состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="04fde-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="04fde-265">**Вредоносные программы в электронной** почте: этот выбор принимает вас к отчету о [состоянии защиты от угрозы](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="04fde-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="04fde-266">**Обнаружение нежелательной почты.** Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="04fde-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="04fde-267">**Edge заблокирован нежелательной почты:** этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="04fde-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="04fde-268">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="04fde-268">**Export**:</span></span>

<span data-ttu-id="04fde-269">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="04fde-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="04fde-270">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="04fde-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="04fde-271">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="04fde-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="04fde-272">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="04fde-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Введите представление в отчете о состоянии mailflow](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="04fde-274">Представление направления для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="04fde-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="04fde-275">Если щелкнуть **вкладку Direction,** используются те же фильтры по умолчанию из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="04fde-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="04fde-276">Диаграмма организована **значениями Direction.**</span><span class="sxs-lookup"><span data-stu-id="04fde-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="04fde-277">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="04fde-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="04fde-278">Используются те же фильтры из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="04fde-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="04fde-279">Таблица данных содержит те же сведения из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="04fde-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="04fde-280">Выбор **категории для получения дополнительных** сведений о выборах и поведении такой же, как представление **Type.**</span><span class="sxs-lookup"><span data-stu-id="04fde-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="04fde-281">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="04fde-281">**Export**:</span></span>

<span data-ttu-id="04fde-282">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="04fde-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="04fde-283">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="04fde-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="04fde-284">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="04fde-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="04fde-285">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="04fde-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление направления в отчете о состоянии mailflow](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="04fde-287">Представление воронки для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="04fde-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="04fde-288">В **представлении Воронка** показано, как функции защиты от угроз электронной почты Майкрософт фильтруют входящие и исходяющие сообщения электронной почты в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="04fde-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="04fde-289">В нем представлены сведения об общем числе сообщений электронной почты, а также о том, как настроенные функции защиты от угроз, включая защиту края, антивирусные программы, защиту от фишинга, защиту от нежелательной почты и защиту от спуфинга, влияют на этот счет.</span><span class="sxs-lookup"><span data-stu-id="04fde-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="04fde-290">Если щелкнуть вкладку **Воронка,** это представление по умолчанию содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="04fde-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="04fde-291">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="04fde-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="04fde-292">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="04fde-292">**Direction**:</span></span>

  - <span data-ttu-id="04fde-293">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="04fde-293">**Inbound**</span></span>
  - <span data-ttu-id="04fde-294">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="04fde-294">**Outbound**</span></span>
  - <span data-ttu-id="04fde-295">**Intra-org.** Это количество для сообщений, отправленных в клиенте; то есть отправитель отправляет abc@domain.com получателям xyz@domain.com (засчитываются отдельно от входящие и исходящие).</span><span class="sxs-lookup"><span data-stu-id="04fde-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="04fde-296">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="04fde-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="04fde-297">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="04fde-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="04fde-298">На этой диаграмме показана графа электронной почты, организованного по:</span><span class="sxs-lookup"><span data-stu-id="04fde-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="04fde-299">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-299">**Total email**</span></span>
- <span data-ttu-id="04fde-300">**Электронная почта после защиты края**</span><span class="sxs-lookup"><span data-stu-id="04fde-300">**Email after edge protection**</span></span>
- <span data-ttu-id="04fde-301">**Электронная почта после вредоносных программ, репутации файлов, блока типа файла**</span><span class="sxs-lookup"><span data-stu-id="04fde-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="04fde-302">**Электронная почта после защиты от фишинга, репутации URL-адресов, обезличения бренда и подмены**</span><span class="sxs-lookup"><span data-stu-id="04fde-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="04fde-303">**Электронная почта после фильтрации массовой почты после нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="04fde-304">**Электронная почта после обезличения пользователя** и домена <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04fde-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="04fde-305">**Электронная почта после детонации файла и URL-адреса**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04fde-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="04fde-306">**Электронная почта, обнаруженная как доброкачественная после защиты после доставки (защита времени щелчка URL-адреса)**</span><span class="sxs-lookup"><span data-stu-id="04fde-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="04fde-307"><sup>1</sup> Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="04fde-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="04fde-308">Чтобы просмотреть сообщение электронной почты, фильтруемой EOP или Defender для Office 365, щелкните значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="04fde-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="04fde-309">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="04fde-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="04fde-310">**Date**</span><span class="sxs-lookup"><span data-stu-id="04fde-310">**Date**</span></span>
- <span data-ttu-id="04fde-311">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-311">**Total email**</span></span>
- <span data-ttu-id="04fde-312">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="04fde-312">**Edge protection**</span></span>
- <span data-ttu-id="04fde-313">**Anti-malware, file reputation, file type block:**</span><span class="sxs-lookup"><span data-stu-id="04fde-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="04fde-314">**Репутация файла:** сообщения фильтруются из-за идентификации присоединенного файла другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04fde-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="04fde-315">**Блок типа файла.** Сообщения фильтруются из-за типа вредоносного файла, идентифицированного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="04fde-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="04fde-316">**Защита от фишинга, репутация URL-адреса, вымысление бренда, защита от подмены:**</span><span class="sxs-lookup"><span data-stu-id="04fde-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="04fde-317">**Репутация URL-адреса.** Сообщения фильтруются из-за идентификации URL-адреса другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04fde-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="04fde-318">**Вымысление** бренда: сообщения фильтруются из-за сообщения, исходящем от известных отправителей бренда, вымыкающих себя.</span><span class="sxs-lookup"><span data-stu-id="04fde-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="04fde-319">**Anti-spoof**: Сообщения фильтруются из-за сообщения, пытающихся подменить домен, к который принадлежит получатель, или домена, который не принадлежит отправителю сообщения.</span><span class="sxs-lookup"><span data-stu-id="04fde-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="04fde-320">**Фильтрация массовой почты** для борьбы со спамом:</span><span class="sxs-lookup"><span data-stu-id="04fde-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="04fde-321">**Массовая фильтрация** почты: сообщения фильтруются из-за попытки доставки массовой почты ее получателям.</span><span class="sxs-lookup"><span data-stu-id="04fde-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="04fde-322">**Вымысление** пользователя и домена (Defender для Office 365) :</span><span class="sxs-lookup"><span data-stu-id="04fde-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="04fde-323">Вымысление пользователя. Сообщения фильтруются из-за попытки выдать себя за пользователя (отправитель сообщений), определенного в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="04fde-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="04fde-324">**Обезличение** домена. Сообщения фильтруются из-за попытки выдать себя за домен, определенный в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="04fde-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="04fde-325">**Детонация файлов и URL-адресов (Defender для Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="04fde-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="04fde-326">**Детонация файлов:** сообщения, фильтруемые политикой Сейф вложений.</span><span class="sxs-lookup"><span data-stu-id="04fde-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="04fde-327">**Детонация URL-адреса.** Сообщение фильтруется политикой Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="04fde-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="04fde-328">**Защита после доставки и ZAP (ATP) или ZAP (EOP)**: ZAP указывает на авточистку нулевого часа.</span><span class="sxs-lookup"><span data-stu-id="04fde-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="04fde-329">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fde-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="04fde-330">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="04fde-330">**Export**:</span></span>

<span data-ttu-id="04fde-331">После нажатия **"Экспорт** в **параметрах"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="04fde-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="04fde-332">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="04fde-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="04fde-333">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="04fde-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="04fde-334">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="04fde-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="04fde-335">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="04fde-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="04fde-336">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="04fde-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="04fde-337">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="04fde-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Представление воронки в отчете о состоянии mailflow](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="04fde-339">Техническое представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="04fde-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="04fde-340">Представление **Tech аналогично** представлению **Воронка,** предоставляя более подробные сведения о настроенных средствах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="04fde-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="04fde-341">На диаграмме можно увидеть, как классифицируются сообщения на различных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="04fde-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="04fde-342">Если вы щелкните вкладку **Tech View,** по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="04fde-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="04fde-343">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="04fde-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="04fde-344">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="04fde-344">**Direction**:</span></span>

  - <span data-ttu-id="04fde-345">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="04fde-345">**Inbound**</span></span>
  - <span data-ttu-id="04fde-346">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="04fde-346">**Outbound**</span></span>
  - <span data-ttu-id="04fde-347">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="04fde-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="04fde-348">отправитель abc@domain.com отправляет получателю xyz@domain.com (рассчитывается отдельно от входящие и исходящие)</span><span class="sxs-lookup"><span data-stu-id="04fde-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="04fde-349">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="04fde-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="04fde-350">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="04fde-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="04fde-351">На этой диаграмме показаны сообщения, организованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="04fde-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="04fde-352">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-352">**Total email**</span></span>
- <span data-ttu-id="04fde-353">**Edge allow** and **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="04fde-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="04fde-354">**Не вредоносные** программы, **Сейф обнаружения** вложений, обнаружения вредоносных программ <sup>\*</sup> и **сообщений правил** </span><span class="sxs-lookup"><span data-stu-id="04fde-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="04fde-355">**Не фишинг,** **отказ DMARC,** **обнаружение** обезличения, **обнаружение Spoof** и **обнаружение фишинга**</span><span class="sxs-lookup"><span data-stu-id="04fde-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="04fde-356">**Отсутствие обнаружения с детонацией URL-адреса** и **обнаружением детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04fde-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="04fde-357">**Не нежелательной почты** и  **нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="04fde-358">**Обнаружение ссылок,** **Сейф** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="04fde-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="04fde-359"><sup>\*</sup>Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="04fde-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="04fde-360">Когда вы наведите курсор над категорией на диаграмме, вы увидите количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="04fde-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="04fde-361">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="04fde-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="04fde-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="04fde-362">**Date**</span></span>
- <span data-ttu-id="04fde-363">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-363">**Total email**</span></span>
- <span data-ttu-id="04fde-364">**Отфильтрованный край**</span><span class="sxs-lookup"><span data-stu-id="04fde-364">**Edge filtered**</span></span>
- <span data-ttu-id="04fde-365">**Антивирусный двигатель, Сейф вложения, правило фильтруется:**</span><span class="sxs-lookup"><span data-stu-id="04fde-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="04fde-366">**Фильтруется** правило: Сообщения фильтруются из-за правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="04fde-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="04fde-367">**DMARC, impersonation, spoof, phish filtered:**</span><span class="sxs-lookup"><span data-stu-id="04fde-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="04fde-368">**DMARC:** Сообщения фильтруются из-за отказа сообщения проверки подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="04fde-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="04fde-369">**Обнаружение детонации URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="04fde-369">**URL detonation detection**</span></span>
- <span data-ttu-id="04fde-370">**Фильтрация от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="04fde-371">**ZaP удален**</span><span class="sxs-lookup"><span data-stu-id="04fde-371">**ZAP removed**</span></span>
- <span data-ttu-id="04fde-372">**Обнаружение по Сейф ссылки**</span><span class="sxs-lookup"><span data-stu-id="04fde-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="04fde-373">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fde-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="04fde-374">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="04fde-374">**Export**:</span></span>

<span data-ttu-id="04fde-375">При **нажатии на экспорт** **можно** выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="04fde-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="04fde-376">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="04fde-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="04fde-377">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="04fde-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="04fde-378">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="04fde-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="04fde-379">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="04fde-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="04fde-380">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="04fde-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="04fde-381">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="04fde-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Представление технологий в отчете о состоянии mailflow](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="04fde-383">Отправленный и полученный отчет электронной почты</span><span class="sxs-lookup"><span data-stu-id="04fde-383">Sent and received email report</span></span>

<span data-ttu-id="04fde-384">Отправленный **и** полученный отчет электронной почты — это интеллектуальный отчет, в нем показаны сведения о входящих и исходяющих сообщениях электронной почты, включая обнаружение нежелательной почты, вредоносные программы и сообщения электронной почты, идентифицированные как "хорошие".</span><span class="sxs-lookup"><span data-stu-id="04fde-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="04fde-385">Разница между этим отчетом и отчетом о состоянии [mailflow](#mailflow-status-report) заключается в том, что в этом отчете не содержатся данные о сообщениях, заблокированных краевой защитой.</span><span class="sxs-lookup"><span data-stu-id="04fde-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="04fde-386">**Примечание.** Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="04fde-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="04fde-387">Совокупное представление и представление деталей отчета позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="04fde-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="04fde-388">Чтобы просмотреть отчет, откройте Центр & безопасности,  перейдите [на](https://protection.office.com)панель мониторинга отчетов и выберите \>  **отправленную и полученную электронную почту.**</span><span class="sxs-lookup"><span data-stu-id="04fde-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="04fde-389">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="04fde-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Виджет электронной почты, отправленный и полученный в панели мониторинга Отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="04fde-391">Представление отчета для отправленного и полученного отчета электронной почты</span><span class="sxs-lookup"><span data-stu-id="04fde-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="04fde-392">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="04fde-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="04fde-393">**Break down by: Type:** The chart shows all available categories:</span><span class="sxs-lookup"><span data-stu-id="04fde-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="04fde-394">**Total**</span><span class="sxs-lookup"><span data-stu-id="04fde-394">**Total**</span></span>
  - <span data-ttu-id="04fde-395">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="04fde-395">**Good mail**</span></span>
  - <span data-ttu-id="04fde-396">**Вредоносные программы (антивирусные программы)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="04fde-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="04fde-397">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-397">**Spam detections**</span></span>
  - <span data-ttu-id="04fde-398">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="04fde-398">**Rule messages**</span></span>
  - <span data-ttu-id="04fde-399">**Расширенные вредоносные** программы (Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="04fde-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="04fde-400">При наведении в течение дня (точки данных) на диаграмме можно увидеть сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="04fde-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Введите представление в отчете отправленной и полученной электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="04fde-402">**Break down by: Direction:** The chart shows **Total,** **Inbound**, and **Outbound** data.</span><span class="sxs-lookup"><span data-stu-id="04fde-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="04fde-403">При наведении в течение дня (точки данных) на диаграмме можно увидеть сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="04fde-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление направления в отчете отправленной и полученной электронной почты](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="04fde-405">**Сверлить** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="04fde-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="04fde-406">**Сверлить** \> **Обнаружения нежелательной почты)**: Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="04fde-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="04fde-407">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="04fde-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="04fde-408">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="04fde-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="04fde-409">Значения направления</span><span class="sxs-lookup"><span data-stu-id="04fde-409">Direction values</span></span>
- <span data-ttu-id="04fde-410">Значения типа</span><span class="sxs-lookup"><span data-stu-id="04fde-410">Type values</span></span>

<span data-ttu-id="04fde-411">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="04fde-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="04fde-412">Представление таблицы сведений для отправленного и полученного отчета электронной почты</span><span class="sxs-lookup"><span data-stu-id="04fde-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="04fde-413">Если **щелкнуть** таблицу Просмотр сведений в таблице **Break down by: Direction** or Break down **by: Direction** view, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="04fde-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="04fde-414">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="04fde-414">**Date (UTC)**</span></span>
- <span data-ttu-id="04fde-415">**Тип**</span><span class="sxs-lookup"><span data-stu-id="04fde-415">**Type**</span></span>
- <span data-ttu-id="04fde-416">**Направление**</span><span class="sxs-lookup"><span data-stu-id="04fde-416">**Direction**</span></span>
- <span data-ttu-id="04fde-417">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="04fde-417">**Message count**</span></span>

<span data-ttu-id="04fde-418">Если **щелкнуть Фильтры** в представлении таблицы сведений, результаты можно изменить следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="04fde-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="04fde-419">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="04fde-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="04fde-420">Значения направления</span><span class="sxs-lookup"><span data-stu-id="04fde-420">Direction values</span></span>
- <span data-ttu-id="04fde-421">Значения типа</span><span class="sxs-lookup"><span data-stu-id="04fde-421">Type values</span></span>

<span data-ttu-id="04fde-422">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="04fde-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="04fde-423">Отчет о главных отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="04fde-423">Top senders and recipients report</span></span>

<span data-ttu-id="04fde-424">Верхний **отчет отправителей** и получателей — это диаграмма пирога, показывающая главных отправителей и получателей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="04fde-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="04fde-425">Чтобы просмотреть отчет, откройте центр & безопасности,  [перейдите к панели](https://protection.office.com)мониторинга отчетов и выберите главных отправителей \>  **и получателей.**</span><span class="sxs-lookup"><span data-stu-id="04fde-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="04fde-426">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="04fde-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Виджет главных отправителей и получателей в панели мониторинга Отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="04fde-428">Представление отчета для главных отправителей и получателей</span><span class="sxs-lookup"><span data-stu-id="04fde-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="04fde-429">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="04fde-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="04fde-430">**Показать данные для \> отправителей верхней почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="04fde-431">**Показать данные для \> получателей топ-почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="04fde-432">**Демонстрация данных для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="04fde-433">**Показать данные для \> Лучшие получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="04fde-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="04fde-434">**Показать данные для \> получателей вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="04fde-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="04fde-435">Состав диаграммы пирога изменяется на основе этих выборов.</span><span class="sxs-lookup"><span data-stu-id="04fde-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="04fde-436">При наведении на клин в диаграмме пирога можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="04fde-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="04fde-437">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="04fde-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Диаграмма пирога в представлении Report в отчете о главных отправителей и получателей](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="04fde-439">Представление таблицы сведений для отчета о главных отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="04fde-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="04fde-440">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="04fde-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="04fde-441">**Показать данные для \> отправителей верхней почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="04fde-442">**Главные отправители почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-442">**Top mail senders**</span></span>
  - <span data-ttu-id="04fde-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="04fde-443">**Count**</span></span>

- <span data-ttu-id="04fde-444">**Показать данные для \> получателей топ-почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="04fde-445">**Лучшие получатели почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="04fde-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="04fde-446">**Count**</span></span>

- <span data-ttu-id="04fde-447">**Демонстрация данных для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="04fde-448">**Лучшие получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="04fde-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="04fde-449">**Count**</span><span class="sxs-lookup"><span data-stu-id="04fde-449">**Count**</span></span>

- <span data-ttu-id="04fde-450">**Показать данные для \> Лучшие получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="04fde-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="04fde-451">**Лучшие получатели вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="04fde-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="04fde-452">**Count**</span><span class="sxs-lookup"><span data-stu-id="04fde-452">**Count**</span></span>

- <span data-ttu-id="04fde-453">**Показать данные для \> получателей вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="04fde-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="04fde-454">**Лучшие получатели вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="04fde-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="04fde-455">**Count**</span><span class="sxs-lookup"><span data-stu-id="04fde-455">**Count**</span></span>

<span data-ttu-id="04fde-456">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="04fde-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="04fde-457">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="04fde-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="04fde-458">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="04fde-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="04fde-459">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="04fde-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="04fde-460">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="04fde-460">**Organization Management**</span></span>
- <span data-ttu-id="04fde-461">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="04fde-461">**Security Administrator**</span></span>
- <span data-ttu-id="04fde-462">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="04fde-462">**Security Reader**</span></span>
- <span data-ttu-id="04fde-463">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="04fde-463">**Global Reader**</span></span>

<span data-ttu-id="04fde-464">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="04fde-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="04fde-465">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04fde-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="04fde-466">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="04fde-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="04fde-467">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="04fde-467">Related topics</span></span>

[<span data-ttu-id="04fde-468">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="04fde-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="04fde-469">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="04fde-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="04fde-470">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="04fde-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="04fde-471">Просмотр отчетов для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="04fde-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
