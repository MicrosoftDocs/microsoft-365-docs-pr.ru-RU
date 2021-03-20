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
ms.openlocfilehash: d1fea50ff0eaa5ed7d671485483ecb297b404db9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906556"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="b2a62-103">Просмотр отчетов о потоке почты на панели мониторинга отчетов в центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="b2a62-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b2a62-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="b2a62-104">**Applies to**</span></span>
- [<span data-ttu-id="b2a62-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b2a62-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b2a62-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="b2a62-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b2a62-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2a62-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b2a62-108">Помимо отчетов о потоках почты, [](mail-flow-insights-v2.md) доступных на панели мониторинга потока почты в Центре обеспечения безопасности & соответствия требованиям, в панели отчетов доступны дополнительные отчеты о потоках почты, которые помогут отслеживать организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2a62-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="b2a62-109">Если у вас есть [необходимые](#what-permissions-are-needed-to-view-these-reports)разрешения, вы можете просмотреть эти отчеты в Центре & соответствия требованиям, переехав на панель мониторинга [](https://protection.office.com)  \> **отчетов**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="b2a62-110">Чтобы перейти непосредственно к панели мониторинга Отчетов, откройте <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="b2a62-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Информационная панель отчетов в Центре & безопасности](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="b2a62-112">Отчет connector</span><span class="sxs-lookup"><span data-stu-id="b2a62-112">Connector report</span></span>

<span data-ttu-id="b2a62-113">В **отчете Connector** показана активность потока почты на [входящие](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) и исходящие соединители, настроенные для организации.</span><span class="sxs-lookup"><span data-stu-id="b2a62-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="b2a62-114">Чтобы просмотреть отчет, откройте центр [&](https://protection.office.com)безопасности,  перейдите к панели мониторинга отчетов и \>  выберите **отчет Connector**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="b2a62-115">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="b2a62-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Виджет отчета connector в панели мониторинга Отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="b2a62-117">Представление отчета для отчета Connector</span><span class="sxs-lookup"><span data-stu-id="b2a62-117">Report view for the Connector report</span></span>

<span data-ttu-id="b2a62-118">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b2a62-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="b2a62-119">**Просмотр данных по: поток почты.** На этой диаграмме показано количество входящие и исходящие сообщения, организованные по:</span><span class="sxs-lookup"><span data-stu-id="b2a62-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="b2a62-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="b2a62-120">**Total**</span></span>
  - <span data-ttu-id="b2a62-121">**Из Интернета без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b2a62-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b2a62-122">**В Интернет без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b2a62-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b2a62-123">Определенный соединитатель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="b2a62-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="b2a62-124">Чтобы изолировать данные на диаграмме, используйте данные **Show** для управления, чтобы выбрать один из этих параметров или **весь поток почты.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных по потоку почты в отчете Connector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="b2a62-126">**Просмотр данных по: использование TLS.** На этой диаграмме показан процент использования версии TLS для потока почты.</span><span class="sxs-lookup"><span data-stu-id="b2a62-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="b2a62-127">Чтобы изолировать данные на диаграмме, используйте данные **Show** для управления, чтобы выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b2a62-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="b2a62-128">**Весь поток почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-128">**All mail flow**</span></span>
  - <span data-ttu-id="b2a62-129">**Из Интернета без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b2a62-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b2a62-130">**В Интернет без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b2a62-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b2a62-131">Определенный соединитатель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="b2a62-131">A specific connector that you've configured.</span></span>

  ![Просмотр данных с помощью TLS в отчете Connector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="b2a62-133">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="b2a62-134">Представление таблицы сведений для отчета Connector</span><span class="sxs-lookup"><span data-stu-id="b2a62-134">Details table view for the Connector report</span></span>

<span data-ttu-id="b2a62-135">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="b2a62-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b2a62-136">**Дата**</span><span class="sxs-lookup"><span data-stu-id="b2a62-136">**Date**</span></span>
- <span data-ttu-id="b2a62-137">**Направление и имя соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b2a62-137">**Connector direction and name**</span></span>
- <span data-ttu-id="b2a62-138">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="b2a62-138">**Connector type**</span></span>
- <span data-ttu-id="b2a62-139">**Forced TLS?**: Значение **True или** **False**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="b2a62-140">**Нет TLS** (процент)</span><span class="sxs-lookup"><span data-stu-id="b2a62-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="b2a62-141">**TLS 1.0** (процент)</span><span class="sxs-lookup"><span data-stu-id="b2a62-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="b2a62-142">**TLS 1.1** (процент)</span><span class="sxs-lookup"><span data-stu-id="b2a62-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="b2a62-143">**TLS 1.2** (процент)</span><span class="sxs-lookup"><span data-stu-id="b2a62-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="b2a62-144">**Том.** Количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="b2a62-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="b2a62-145">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b2a62-146">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="b2a62-147">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="b2a62-147">Exchange transport rule report</span></span>

<span data-ttu-id="b2a62-148">В **отчете о** правилах транспорта Exchange показано влияние правил потока почты (также известных как правила транспорта) на входящие и исходяющие сообщения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b2a62-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="b2a62-149">Чтобы просмотреть отчет, откройте центр & безопасности,  перейдите [к](https://protection.office.com)панели мониторинга отчетов и выберите \>  правило **транспорта Exchange.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="b2a62-150">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="b2a62-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Виджет правила транспорта Exchange в панели мониторинга Отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b2a62-152">Представление отчета для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="b2a62-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="b2a62-153">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b2a62-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="b2a62-154">**Просмотр данных по: Правила транспорта** \> Exchange **Break down by: Direction:** This chart shows the number of **Inbound** and **Outbound messages** that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="b2a62-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="b2a62-155">**Просмотр данных по: Правила транспорта** \> Exchange **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="b2a62-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="b2a62-156">Вы установите уровень серьезности в качестве действия в правиле **(Аудит** этого правила с уровнем серьезности или _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="b2a62-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="b2a62-157">Дополнительные сведения см. в сообщении о действиях правила [потока почты в Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="b2a62-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="b2a62-158">**Просмотр данных по: правила транспорта DLP Exchange** \> **Break down by: Direction:** This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span><span class="sxs-lookup"><span data-stu-id="b2a62-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="b2a62-159">Далее можно уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b2a62-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b2a62-160">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="b2a62-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b2a62-161">**Показать данные для: скомпрометированная пользователей**</span><span class="sxs-lookup"><span data-stu-id="b2a62-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b2a62-162">**Показать данные для: Низкий объем контента, обнаруженного Патриотический акт США**</span><span class="sxs-lookup"><span data-stu-id="b2a62-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="b2a62-163">**Просмотр данных по: правила транспорта DLP Exchange** \> **Break down by: Direction:** This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="b2a62-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="b2a62-164">Далее можно уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b2a62-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b2a62-165">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="b2a62-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b2a62-166">**Показать данные для: скомпрометированная пользователей**</span><span class="sxs-lookup"><span data-stu-id="b2a62-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b2a62-167">**Показать данные для: Низкий объем контента, обнаруженного Патриотический акт США**</span><span class="sxs-lookup"><span data-stu-id="b2a62-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="b2a62-168">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров::</span><span class="sxs-lookup"><span data-stu-id="b2a62-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="b2a62-169">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b2a62-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="b2a62-170">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b2a62-170">Direction values</span></span>
- <span data-ttu-id="b2a62-171">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="b2a62-171">Severity values</span></span>

![Представление отчета в отчете о правилах транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b2a62-173">Представление таблицы сведений для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="b2a62-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="b2a62-174">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="b2a62-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b2a62-175">**Просмотр данных по: Правила транспорта Exchange:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="b2a62-176">**Дата**</span><span class="sxs-lookup"><span data-stu-id="b2a62-176">**Date**</span></span>
  - <span data-ttu-id="b2a62-177">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="b2a62-177">**Transport rule**</span></span>
  - <span data-ttu-id="b2a62-178">**Тема**</span><span class="sxs-lookup"><span data-stu-id="b2a62-178">**Subject**</span></span>
  - <span data-ttu-id="b2a62-179">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="b2a62-179">**Sender address**</span></span>
  - <span data-ttu-id="b2a62-180">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="b2a62-180">**Recipient address**</span></span>
  - <span data-ttu-id="b2a62-181">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="b2a62-181">**Severity**</span></span>
  - <span data-ttu-id="b2a62-182">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b2a62-182">**Direction**</span></span>

- <span data-ttu-id="b2a62-183">**Просмотр данных по: правила транспорта DLP Exchange:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="b2a62-184">**Дата**</span><span class="sxs-lookup"><span data-stu-id="b2a62-184">**Date**</span></span>
  - <span data-ttu-id="b2a62-185">**Политика защиты от потери данных**</span><span class="sxs-lookup"><span data-stu-id="b2a62-185">**DLP policy**</span></span>
  - <span data-ttu-id="b2a62-186">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="b2a62-186">**Transport rule**</span></span>
  - <span data-ttu-id="b2a62-187">**Тема**</span><span class="sxs-lookup"><span data-stu-id="b2a62-187">**Subject**</span></span>
  - <span data-ttu-id="b2a62-188">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="b2a62-188">**Sender address**</span></span>
  - <span data-ttu-id="b2a62-189">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="b2a62-189">**Recipient address**</span></span>
  - <span data-ttu-id="b2a62-190">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="b2a62-190">**Severity**</span></span>
  - <span data-ttu-id="b2a62-191">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b2a62-191">**Direction**</span></span>

<span data-ttu-id="b2a62-192">Если **щелкнуть Фильтры** в представлении таблицы сведений, результаты можно изменить следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="b2a62-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b2a62-193">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b2a62-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="b2a62-194">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b2a62-194">Direction values</span></span>
- <span data-ttu-id="b2a62-195">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="b2a62-195">Severity values</span></span>

<span data-ttu-id="b2a62-196">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="b2a62-197">Отчет о переадпорте</span><span class="sxs-lookup"><span data-stu-id="b2a62-197">Forwarding report</span></span>

<span data-ttu-id="b2a62-198">В **отчете о** пересылке показаны автоматически пересылаемые сообщения организации во внешние домены из почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b2a62-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="b2a62-199">Переадренные сообщения могут представлять угрозу безопасности или соответствия требованиям, а также указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="b2a62-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="b2a62-200">Чтобы просмотреть отчет, откройте Центр [&](https://protection.office.com)безопасности,  перейдите на панель мониторинга отчетов и \>  выберите отчет **о переадпорте.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="b2a62-201">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="b2a62-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Виджет отчета о переадпорте в панели мониторинга Отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="b2a62-203">Представление отчета для отчета о переадпорте</span><span class="sxs-lookup"><span data-stu-id="b2a62-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="b2a62-204">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b2a62-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b2a62-205">**Показать данные для: Методы переададки:** показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="b2a62-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="b2a62-206">**Правило транспорта:** Также известное как [правила потока почты.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="b2a62-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="b2a62-207">**Правило почтовых ящиков:** Также известное как [правила "Входящие".](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="b2a62-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Представление методов переададки в отчете о переадпорте](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="b2a62-209">**Показать данные для: Переадправление доменов.** В этом представлении показаны домены получателей, которые являются пунктами назначения для переадправления.</span><span class="sxs-lookup"><span data-stu-id="b2a62-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Представление переадпорта доменов в отчете о переадпорте](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="b2a62-211">**Показать данные для: Переадверы**: Показаны следующие переад.</span><span class="sxs-lookup"><span data-stu-id="b2a62-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="b2a62-212">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="b2a62-212">**Transport rule**</span></span>
  - <span data-ttu-id="b2a62-213">Почтовый ящик, содержащий правило "Входящие" пересылания.</span><span class="sxs-lookup"><span data-stu-id="b2a62-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarders view in the Forwarding report](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="b2a62-215">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="b2a62-216">Представление таблицы сведений для отчета о переадпорте</span><span class="sxs-lookup"><span data-stu-id="b2a62-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="b2a62-217">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="b2a62-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b2a62-218">**Переадпортаторы.** **Правило** транспорта значения или почтовый ящик, содержащий правило почтовых ящиков пересылания.</span><span class="sxs-lookup"><span data-stu-id="b2a62-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="b2a62-219">**Тип пересылания:** правило **почтовых ящиков значения** или **правило транспорта.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="b2a62-220">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="b2a62-220">**Recipient name**</span></span>
- <span data-ttu-id="b2a62-221">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="b2a62-221">**Recipient domain**</span></span>
- <span data-ttu-id="b2a62-222">**Сведения.** Это значение GUID правила потока почты или значение RuleIdentity правила "Входящие".</span><span class="sxs-lookup"><span data-stu-id="b2a62-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="b2a62-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="b2a62-223">**Count**</span></span>
- <span data-ttu-id="b2a62-224">**Дата первой переададки**</span><span class="sxs-lookup"><span data-stu-id="b2a62-224">**First forward date**</span></span>

<span data-ttu-id="b2a62-225">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b2a62-226">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b2a62-227">Отчет о состоянии почтового потока</span><span class="sxs-lookup"><span data-stu-id="b2a62-227">Mailflow status report</span></span>

<span data-ttu-id="b2a62-228">Отчет **о состоянии почтового потока** похож на отчет отправленной и полученной электронной почты, а дополнительные сведения о электронной почте разрешены или заблокированы на краю. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="b2a62-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="b2a62-229">Это единственный отчет, содержащий сведения о защите края, и показывает, сколько сообщений электронной почты блокируется до того, как они будут допущены в службу для оценки в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="b2a62-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b2a62-230">Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="b2a62-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="b2a62-231">Чтобы просмотреть отчет, откройте Центр [&](https://protection.office.com)безопасности,  перейдите к панели мониторинга отчетов и выберите отчет о состоянии \>  **mailflow.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="b2a62-232">Чтобы перейти непосредственно к отчету о состоянии **потока почты,** откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="b2a62-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Виджет отчета о состоянии почтового потока в панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2a62-234">Введите представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="b2a62-235">При открывании отчета вкладка **Type** выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2a62-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="b2a62-236">По умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b2a62-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b2a62-237">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="b2a62-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="b2a62-238">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-238">**Direction**:</span></span>

  - <span data-ttu-id="b2a62-239">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="b2a62-239">**Inbound**</span></span>
  - <span data-ttu-id="b2a62-240">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="b2a62-240">**Outbound**</span></span>
  - <span data-ttu-id="b2a62-241">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="b2a62-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b2a62-242">отправитель abc@domain.com получателям xyz@domain.com (засчитываются  отдельно от входящие и **исходящие)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="b2a62-243">**Тип:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-243">**Type**:</span></span>

  - <span data-ttu-id="b2a62-244">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="b2a62-244">**Good mail**</span></span>
  - <span data-ttu-id="b2a62-245">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="b2a62-245">**Malware**</span></span>
  - <span data-ttu-id="b2a62-246">**Спам**</span><span class="sxs-lookup"><span data-stu-id="b2a62-246">**Spam**</span></span>
  - <span data-ttu-id="b2a62-247">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="b2a62-247">**Edge protection**</span></span>
  - <span data-ttu-id="b2a62-248">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="b2a62-248">**Rule messages**</span></span>
  - <span data-ttu-id="b2a62-249">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="b2a62-249">**Phishing email**</span></span>

<span data-ttu-id="b2a62-250">Диаграмма организована **значениями Type.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="b2a62-251">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b2a62-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="b2a62-252">В таблице данных содержатся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b2a62-252">The data table contains the following information:</span></span>

- <span data-ttu-id="b2a62-253">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b2a62-253">**Direction**</span></span>
- <span data-ttu-id="b2a62-254">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b2a62-254">**Type**</span></span>
- <span data-ttu-id="b2a62-255">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="b2a62-255">**24 hours**</span></span>
- <span data-ttu-id="b2a62-256">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="b2a62-256">**3 days**</span></span>
- <span data-ttu-id="b2a62-257">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="b2a62-257">**7 days**</span></span>
- <span data-ttu-id="b2a62-258">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="b2a62-258">**15 days**</span></span>
- <span data-ttu-id="b2a62-259">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="b2a62-259">**30 days**</span></span>

<span data-ttu-id="b2a62-260">Если вы **нажмете Выберите категорию для получения** дополнительных сведений, вы можете выбрать из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b2a62-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="b2a62-261">**Фишинговое письмо.** Этот выбор принимает вас к отчету о [состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b2a62-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b2a62-262">**Вредоносные программы в электронной** почте: этот выбор принимает вас к отчету о [состоянии защиты от угрозы](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="b2a62-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b2a62-263">**Обнаружение нежелательной почты.** Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b2a62-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="b2a62-264">**Edge заблокирован нежелательной почты:** этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b2a62-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b2a62-265">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-265">**Export**:</span></span>

<span data-ttu-id="b2a62-266">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="b2a62-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b2a62-267">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="b2a62-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b2a62-268">Каждый экспортируемый файл csv ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b2a62-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2a62-269">Если данные за этот день содержат более 150 000 строк, будет создано несколько файлов CSV.</span><span class="sxs-lookup"><span data-stu-id="b2a62-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="b2a62-270">Введите представление в отчете о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2a62-271">Представление направления для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="b2a62-272">Если щелкнуть **вкладку Direction,** используются те же фильтры по умолчанию из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="b2a62-273">Диаграмма организована **значениями Direction.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="b2a62-274">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b2a62-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="b2a62-275">Используются те же фильтры из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b2a62-276">Таблица данных содержит те же сведения из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="b2a62-277">Выбор **категории для получения дополнительных** сведений о выборах и поведении такой же, как представление **Type.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="b2a62-278">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-278">**Export**:</span></span>

<span data-ttu-id="b2a62-279">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="b2a62-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b2a62-280">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="b2a62-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b2a62-281">Каждый экспортируемый файл csv ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b2a62-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2a62-282">Если данные за этот день содержат более 150 000 строк, будет создано несколько файлов CSV.</span><span class="sxs-lookup"><span data-stu-id="b2a62-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="b2a62-283">Представление направления в отчете о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2a62-284">Представление воронки для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="b2a62-285">В **представлении Воронка** показано, как функции защиты от угроз электронной почты Майкрософт фильтруют входящие и исходяющие сообщения электронной почты в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b2a62-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="b2a62-286">В нем представлены сведения об общем числе сообщений электронной почты, а также о том, как настроенные функции защиты от угроз, включая защиту края, антивирусные программы, защиту от фишинга, защиту от нежелательной почты и защиту от спуфинга, влияют на этот счет.</span><span class="sxs-lookup"><span data-stu-id="b2a62-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="b2a62-287">Если щелкнуть вкладку **Воронка,** это представление по умолчанию содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b2a62-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b2a62-288">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="b2a62-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b2a62-289">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-289">**Direction**:</span></span>

  - <span data-ttu-id="b2a62-290">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="b2a62-290">**Inbound**</span></span>
  - <span data-ttu-id="b2a62-291">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="b2a62-291">**Outbound**</span></span>
  - <span data-ttu-id="b2a62-292">**Intra-org.** Это количество для сообщений, отправленных в клиенте; то есть отправитель отправляет abc@domain.com получателям xyz@domain.com (засчитываются отдельно от входящие и исходящие).</span><span class="sxs-lookup"><span data-stu-id="b2a62-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="b2a62-293">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b2a62-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b2a62-294">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="b2a62-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b2a62-295">На этой диаграмме показана графа электронной почты, организованного по:</span><span class="sxs-lookup"><span data-stu-id="b2a62-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="b2a62-296">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-296">**Total email**</span></span>
- <span data-ttu-id="b2a62-297">**Электронная почта после защиты края**</span><span class="sxs-lookup"><span data-stu-id="b2a62-297">**Email after edge protection**</span></span>
- <span data-ttu-id="b2a62-298">**Электронная почта после вредоносных программ, репутации файлов, блока типа файла**</span><span class="sxs-lookup"><span data-stu-id="b2a62-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="b2a62-299">**Электронная почта после защиты от фишинга, репутации URL-адресов, обезличения бренда и подмены**</span><span class="sxs-lookup"><span data-stu-id="b2a62-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="b2a62-300">**Электронная почта после фильтрации массовой почты после нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="b2a62-301">**Электронная почта после обезличения пользователя** и домена <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2a62-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="b2a62-302">**Электронная почта после детонации файла и URL-адреса**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2a62-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="b2a62-303">**Электронная почта, обнаруженная как доброкачественная после защиты после доставки (защита времени щелчка URL-адреса)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="b2a62-304"><sup>1</sup> Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="b2a62-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b2a62-305">Чтобы просмотреть сообщение электронной почты, фильтруемой EOP или Defender для Office 365 отдельно, щелкните значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b2a62-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="b2a62-306">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="b2a62-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b2a62-307">**Дата**</span><span class="sxs-lookup"><span data-stu-id="b2a62-307">**Date**</span></span>
- <span data-ttu-id="b2a62-308">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-308">**Total email**</span></span>
- <span data-ttu-id="b2a62-309">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="b2a62-309">**Edge protection**</span></span>
- <span data-ttu-id="b2a62-310">**Anti-malware, file reputation, file type block:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="b2a62-311">**Репутация файла:** сообщения фильтруются из-за идентификации присоединенного файла другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b2a62-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="b2a62-312">**Блок типа файла.** Сообщения фильтруются из-за типа вредоносного файла, идентифицированного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="b2a62-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b2a62-313">**Защита от фишинга, репутация URL-адреса, вымысление бренда, защита от подмены:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="b2a62-314">**Репутация URL-адреса.** Сообщения фильтруются из-за идентификации URL-адреса другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b2a62-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="b2a62-315">**Вымысление** бренда: сообщения фильтруются из-за сообщения, исходящем от известных отправителей бренда, вымыкающих себя.</span><span class="sxs-lookup"><span data-stu-id="b2a62-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="b2a62-316">**Anti-spoof**: Сообщения фильтруются из-за сообщения, пытающихся подменить домен, к который принадлежит получатель, или домена, который не принадлежит отправителю сообщения.</span><span class="sxs-lookup"><span data-stu-id="b2a62-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="b2a62-317">**Фильтрация массовой почты** для борьбы со спамом:</span><span class="sxs-lookup"><span data-stu-id="b2a62-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="b2a62-318">**Массовая фильтрация** почты: сообщения фильтруются из-за попытки доставки массовой почты ее получателям.</span><span class="sxs-lookup"><span data-stu-id="b2a62-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="b2a62-319">**Вымысление пользователя и домена (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="b2a62-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b2a62-320">Вымысление пользователя. Сообщения фильтруются из-за попытки выдать себя за пользователя (отправитель сообщений), определенного в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b2a62-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="b2a62-321">**Обезличение** домена. Сообщения фильтруются из-за попытки выдать себя за домен, определенный в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b2a62-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="b2a62-322">**Детонация файлов и URL-адресов (Defender для Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="b2a62-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b2a62-323">**Детонация файлов:** сообщения, фильтруемые политикой безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="b2a62-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="b2a62-324">**Детонация URL-адреса.** Сообщение фильтруется политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="b2a62-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="b2a62-325">**Защита после доставки и ZAP (ATP) или ZAP (EOP)**: ZAP указывает на авточистку нулевого часа.</span><span class="sxs-lookup"><span data-stu-id="b2a62-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="b2a62-326">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b2a62-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b2a62-327">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-327">**Export**:</span></span>

<span data-ttu-id="b2a62-328">После нажатия **"Экспорт** в **параметрах"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b2a62-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="b2a62-329">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b2a62-330">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b2a62-331">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b2a62-332">Данные для текущих фильтров будут экспортироваться в файл csv.</span><span class="sxs-lookup"><span data-stu-id="b2a62-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b2a62-333">Каждый экспортируемый файл csv ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b2a62-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2a62-334">Если данные содержат более 150 000 строк, будет создано несколько файлов CSV.</span><span class="sxs-lookup"><span data-stu-id="b2a62-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="b2a62-335">Представление воронки в отчете о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2a62-336">Техническое представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="b2a62-337">Представление **Tech аналогично** представлению **Воронка,** предоставляя более подробные сведения о настроенных средствах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="b2a62-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="b2a62-338">На диаграмме можно увидеть, как классифицируются сообщения на различных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="b2a62-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="b2a62-339">Если вы щелкните вкладку **Tech View,** по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b2a62-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b2a62-340">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="b2a62-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b2a62-341">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-341">**Direction**:</span></span>

  - <span data-ttu-id="b2a62-342">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="b2a62-342">**Inbound**</span></span>
  - <span data-ttu-id="b2a62-343">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="b2a62-343">**Outbound**</span></span>
  - <span data-ttu-id="b2a62-344">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="b2a62-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b2a62-345">отправитель abc@domain.com отправляет получателю xyz@domain.com (рассчитывается отдельно от входящие и исходящие)</span><span class="sxs-lookup"><span data-stu-id="b2a62-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="b2a62-346">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b2a62-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b2a62-347">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="b2a62-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b2a62-348">На этой диаграмме показаны сообщения, организованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="b2a62-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b2a62-349">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-349">**Total email**</span></span>
- <span data-ttu-id="b2a62-350">**Edge allow** and **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="b2a62-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="b2a62-351">**Не вредоносные** программы, обнаружение безопасных **вложений,** обнаружение вредоносных <sup>\*</sup> **программ** и **сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="b2a62-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="b2a62-352">**Не фишинг,** **отказ DMARC,** **обнаружение** обезличения, **обнаружение Spoof** и **обнаружение фишинга**</span><span class="sxs-lookup"><span data-stu-id="b2a62-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="b2a62-353">**Отсутствие обнаружения с детонацией URL-адреса** и **обнаружением детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2a62-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b2a62-354">**Не нежелательной почты** и  **нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="b2a62-355">**Не вредоносная электронная почта,** **обнаружение безопасных ссылок** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="b2a62-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="b2a62-356"><sup>\*</sup> Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b2a62-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b2a62-357">Когда вы наведите курсор над категорией на диаграмме, вы увидите количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="b2a62-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="b2a62-358">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="b2a62-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b2a62-359">**Дата**</span><span class="sxs-lookup"><span data-stu-id="b2a62-359">**Date**</span></span>
- <span data-ttu-id="b2a62-360">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-360">**Total email**</span></span>
- <span data-ttu-id="b2a62-361">**Отфильтрованный край**</span><span class="sxs-lookup"><span data-stu-id="b2a62-361">**Edge filtered**</span></span>
- <span data-ttu-id="b2a62-362">**Антивирусный двигатель, безопасные вложения, правило фильтруется:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="b2a62-363">**Фильтруется** правило: Сообщения фильтруются из-за правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="b2a62-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="b2a62-364">**DMARC, impersonation, spoof, phish filtered:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="b2a62-365">**DMARC:** Сообщения фильтруются из-за отказа сообщения проверки подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="b2a62-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="b2a62-366">**Обнаружение детонации URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="b2a62-366">**URL detonation detection**</span></span>
- <span data-ttu-id="b2a62-367">**Фильтрация от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="b2a62-368">**ZaP удален**</span><span class="sxs-lookup"><span data-stu-id="b2a62-368">**ZAP removed**</span></span>
- <span data-ttu-id="b2a62-369">**Обнаружение по безопасным ссылкам**</span><span class="sxs-lookup"><span data-stu-id="b2a62-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="b2a62-370">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b2a62-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b2a62-371">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b2a62-371">**Export**:</span></span>

<span data-ttu-id="b2a62-372">При **нажатии на экспорт** **можно** выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b2a62-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="b2a62-373">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b2a62-374">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b2a62-375">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b2a62-376">Данные для текущих фильтров будут экспортироваться в файл csv.</span><span class="sxs-lookup"><span data-stu-id="b2a62-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b2a62-377">Каждый экспортируемый файл csv ограничен 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b2a62-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2a62-378">Если данные содержат более 150 000 строк, будет создано несколько файлов CSV.</span><span class="sxs-lookup"><span data-stu-id="b2a62-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="b2a62-379">Представление технологий в отчете о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b2a62-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="b2a62-380">Отправленный и полученный отчет электронной почты</span><span class="sxs-lookup"><span data-stu-id="b2a62-380">Sent and received email report</span></span>

<span data-ttu-id="b2a62-381">Отправленный **и** полученный отчет электронной почты — это интеллектуальный отчет, в нем показаны сведения о входящих и исходяющих сообщениях электронной почты, включая обнаружение нежелательной почты, вредоносные программы и сообщения электронной почты, идентифицированные как "хорошие".</span><span class="sxs-lookup"><span data-stu-id="b2a62-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="b2a62-382">Разница между этим отчетом и отчетом о состоянии [mailflow](#mailflow-status-report) заключается в том, что в этом отчете не содержатся данные о сообщениях, заблокированных краевой защитой. Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="b2a62-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="b2a62-383">Совокупное представление и представление деталей отчета позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b2a62-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="b2a62-384">Чтобы просмотреть отчет, откройте Центр & безопасности,  перейдите [на](https://protection.office.com)панель мониторинга отчетов и выберите \>  **отправленную и полученную электронную почту.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="b2a62-385">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="b2a62-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Виджет электронной почты, отправленный и полученный в панели мониторинга Отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b2a62-387">Представление отчета для отправленного и полученного отчета электронной почты</span><span class="sxs-lookup"><span data-stu-id="b2a62-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="b2a62-388">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b2a62-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b2a62-389">**Break down by: Type:** The chart shows all available categories:</span><span class="sxs-lookup"><span data-stu-id="b2a62-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="b2a62-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="b2a62-390">**Total**</span></span>
  - <span data-ttu-id="b2a62-391">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="b2a62-391">**Good mail**</span></span>
  - <span data-ttu-id="b2a62-392">**Вредоносные программы (антивирусные программы)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b2a62-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="b2a62-393">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-393">**Spam detections**</span></span>
  - <span data-ttu-id="b2a62-394">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="b2a62-394">**Rule messages**</span></span>
  - <span data-ttu-id="b2a62-395">**Расширенные вредоносные** программы (Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="b2a62-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="b2a62-396">При наведении в течение дня (точки данных) на диаграмме можно увидеть сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="b2a62-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Введите представление в отчете отправленной и полученной электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="b2a62-398">**Break down by: Direction:** The chart shows **Total,** **Inbound**, and **Outbound** data.</span><span class="sxs-lookup"><span data-stu-id="b2a62-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="b2a62-399">При наведении в течение дня (точки данных) на диаграмме можно увидеть сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="b2a62-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление направления в отчете отправленной и полученной электронной почты](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="b2a62-401">**Сверлить** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="b2a62-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="b2a62-402">**Сверлить** \> **Обнаружения нежелательной почты)**: Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b2a62-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b2a62-403">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b2a62-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b2a62-404">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b2a62-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="b2a62-405">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b2a62-405">Direction values</span></span>
- <span data-ttu-id="b2a62-406">Значения типа</span><span class="sxs-lookup"><span data-stu-id="b2a62-406">Type values</span></span>

<span data-ttu-id="b2a62-407">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b2a62-408">Представление таблицы сведений для отправленного и полученного отчета электронной почты</span><span class="sxs-lookup"><span data-stu-id="b2a62-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="b2a62-409">Если **щелкнуть** таблицу Просмотр сведений в таблице **Break down by: Direction** or Break down **by: Direction** view, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="b2a62-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="b2a62-410">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-410">**Date (UTC)**</span></span>
- <span data-ttu-id="b2a62-411">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b2a62-411">**Type**</span></span>
- <span data-ttu-id="b2a62-412">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b2a62-412">**Direction**</span></span>
- <span data-ttu-id="b2a62-413">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="b2a62-413">**Message count**</span></span>

<span data-ttu-id="b2a62-414">Если **щелкнуть Фильтры** в представлении таблицы сведений, результаты можно изменить следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="b2a62-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b2a62-415">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b2a62-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="b2a62-416">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b2a62-416">Direction values</span></span>
- <span data-ttu-id="b2a62-417">Значения типа</span><span class="sxs-lookup"><span data-stu-id="b2a62-417">Type values</span></span>

<span data-ttu-id="b2a62-418">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="b2a62-419">Отчет о главных отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="b2a62-419">Top senders and recipients report</span></span>

<span data-ttu-id="b2a62-420">Верхний **отчет отправителей** и получателей — это диаграмма пирога, показывающая главных отправителей и получателей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b2a62-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="b2a62-421">Чтобы просмотреть отчет, откройте центр & безопасности,  [перейдите к панели](https://protection.office.com)мониторинга отчетов и выберите главных отправителей \>  **и получателей.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="b2a62-422">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="b2a62-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Виджет главных отправителей и получателей в панели мониторинга Отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b2a62-424">Представление отчета для главных отправителей и получателей</span><span class="sxs-lookup"><span data-stu-id="b2a62-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="b2a62-425">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b2a62-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b2a62-426">**Показать данные для \> отправителей верхней почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="b2a62-427">**Показать данные для \> получателей топ-почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="b2a62-428">**Демонстрация данных для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="b2a62-429">**Показать данные для \> Лучшие получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b2a62-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="b2a62-430">**Показать данные для \> получателей топовых вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="b2a62-431">Состав диаграммы пирога изменяется на основе этих выборов.</span><span class="sxs-lookup"><span data-stu-id="b2a62-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="b2a62-432">При наведении на клин в диаграмме пирога можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="b2a62-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="b2a62-433">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Диаграмма пирога в представлении Report в отчете о главных отправителей и получателей](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b2a62-435">Представление таблицы сведений для отчета о главных отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="b2a62-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="b2a62-436">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="b2a62-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b2a62-437">**Показать данные для \> отправителей верхней почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="b2a62-438">**Главные отправители почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-438">**Top mail senders**</span></span>
  - <span data-ttu-id="b2a62-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="b2a62-439">**Count**</span></span>

- <span data-ttu-id="b2a62-440">**Показать данные для \> получателей топ-почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="b2a62-441">**Лучшие получатели почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="b2a62-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="b2a62-442">**Count**</span></span>

- <span data-ttu-id="b2a62-443">**Демонстрация данных для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="b2a62-444">**Лучшие получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b2a62-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="b2a62-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="b2a62-445">**Count**</span></span>

- <span data-ttu-id="b2a62-446">**Показать данные для \> Лучшие получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b2a62-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="b2a62-447">**Лучшие получатели вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="b2a62-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="b2a62-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="b2a62-448">**Count**</span></span>

- <span data-ttu-id="b2a62-449">**Показать данные для \> получателей топовых вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="b2a62-450">**Лучшие получатели вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b2a62-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="b2a62-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="b2a62-451">**Count**</span></span>

<span data-ttu-id="b2a62-452">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b2a62-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b2a62-453">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b2a62-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b2a62-454">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="b2a62-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b2a62-455">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="b2a62-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b2a62-456">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="b2a62-456">**Organization Management**</span></span>
- <span data-ttu-id="b2a62-457">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="b2a62-457">**Security Administrator**</span></span>
- <span data-ttu-id="b2a62-458">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="b2a62-458">**Security Reader**</span></span>
- <span data-ttu-id="b2a62-459">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="b2a62-459">**Global Reader**</span></span>

<span data-ttu-id="b2a62-460">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b2a62-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b2a62-461">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2a62-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b2a62-462">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b2a62-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2a62-463">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="b2a62-463">Related topics</span></span>

[<span data-ttu-id="b2a62-464">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b2a62-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b2a62-465">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b2a62-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="b2a62-466">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b2a62-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="b2a62-467">Просмотр отчетов для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b2a62-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)