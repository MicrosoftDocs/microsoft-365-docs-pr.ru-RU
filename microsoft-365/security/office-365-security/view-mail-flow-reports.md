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
ms.openlocfilehash: 38beac44af191a027db722ade25ca7fd0e505d9b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245676"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="b15f1-103">Просмотр отчетов о потоке почты на панели мониторинга отчетов в центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="b15f1-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b15f1-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="b15f1-104">**Applies to**</span></span>
- [<span data-ttu-id="b15f1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b15f1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b15f1-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="b15f1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b15f1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b15f1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b15f1-108">Помимо отчетов о потоке почты, [](mail-flow-insights-v2.md) доступных на панели мониторинга потока почты в Центре обеспечения соответствия требованиям & безопасности, в панели отчетов доступны дополнительные отчеты о потоке почты, которые помогут отслеживать Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="b15f1-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="b15f1-109">Если у вас есть [необходимые](#what-permissions-are-needed-to-view-these-reports)разрешения, вы можете просмотреть эти отчеты в Центре & соответствия требованиям, переехав на панель мониторинга [](https://protection.office.com)  \> **отчетов**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="b15f1-110">Чтобы перейти непосредственно к панели мониторинга Отчетов, откройте <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="b15f1-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Информационная панель отчетов в Центре & безопасности](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="b15f1-112">Отчет connector</span><span class="sxs-lookup"><span data-stu-id="b15f1-112">Connector report</span></span>

<span data-ttu-id="b15f1-113">В **отчете Connector** показана активность потока почты на [входящие](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) и исходящие соединители, настроенные для организации.</span><span class="sxs-lookup"><span data-stu-id="b15f1-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="b15f1-114">Чтобы просмотреть отчет, откройте центр [&](https://protection.office.com)безопасности,  перейдите к панели мониторинга отчетов и \>  выберите **отчет Connector**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="b15f1-115">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="b15f1-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Виджет отчета connector в панели мониторинга Отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="b15f1-117">Представление отчета для отчета Connector</span><span class="sxs-lookup"><span data-stu-id="b15f1-117">Report view for the Connector report</span></span>

<span data-ttu-id="b15f1-118">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b15f1-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="b15f1-119">**Просмотр данных по: поток почты.** На этой диаграмме показано количество входящие и исходящие сообщения, организованные по:</span><span class="sxs-lookup"><span data-stu-id="b15f1-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="b15f1-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="b15f1-120">**Total**</span></span>
  - <span data-ttu-id="b15f1-121">**Из Интернета без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b15f1-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b15f1-122">**В Интернет без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b15f1-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b15f1-123">Определенный соединитатель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="b15f1-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="b15f1-124">Чтобы изолировать данные на диаграмме, используйте данные **Show** для управления, чтобы выбрать один из этих параметров или **весь поток почты.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных по потоку почты в отчете Connector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="b15f1-126">**Просмотр данных по: использование TLS.** На этой диаграмме показан процент использования версии TLS для потока почты.</span><span class="sxs-lookup"><span data-stu-id="b15f1-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="b15f1-127">Чтобы изолировать данные на диаграмме, используйте данные **Show** для управления, чтобы выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b15f1-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="b15f1-128">**Весь поток почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-128">**All mail flow**</span></span>
  - <span data-ttu-id="b15f1-129">**Из Интернета без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b15f1-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b15f1-130">**В Интернет без соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b15f1-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b15f1-131">Определенный соединитатель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="b15f1-131">A specific connector that you've configured.</span></span>

  ![Просмотр данных с помощью TLS в отчете Connector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="b15f1-133">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="b15f1-134">Представление таблицы сведений для отчета Connector</span><span class="sxs-lookup"><span data-stu-id="b15f1-134">Details table view for the Connector report</span></span>

<span data-ttu-id="b15f1-135">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="b15f1-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b15f1-136">**Date**</span><span class="sxs-lookup"><span data-stu-id="b15f1-136">**Date**</span></span>
- <span data-ttu-id="b15f1-137">**Направление и имя соединитетеля**</span><span class="sxs-lookup"><span data-stu-id="b15f1-137">**Connector direction and name**</span></span>
- <span data-ttu-id="b15f1-138">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="b15f1-138">**Connector type**</span></span>
- <span data-ttu-id="b15f1-139">**Forced TLS?**: Значение **True или** **False**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="b15f1-140">**Нет TLS** (процент)</span><span class="sxs-lookup"><span data-stu-id="b15f1-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="b15f1-141">**TLS 1.0** (процент)</span><span class="sxs-lookup"><span data-stu-id="b15f1-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="b15f1-142">**TLS 1.1** (процент)</span><span class="sxs-lookup"><span data-stu-id="b15f1-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="b15f1-143">**TLS 1.2** (процент)</span><span class="sxs-lookup"><span data-stu-id="b15f1-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="b15f1-144">**Том.** Количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="b15f1-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="b15f1-145">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b15f1-146">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="b15f1-147">Exchange отчет о правилах транспорта</span><span class="sxs-lookup"><span data-stu-id="b15f1-147">Exchange transport rule report</span></span>

<span data-ttu-id="b15f1-148">В **Exchange** правила транспорта показано влияние правил потока почты (также известных как правила транспорта) на входящие и исходяющие сообщения в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b15f1-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="b15f1-149">Чтобы просмотреть отчет, откройте Центр [&](https://protection.office.com)безопасности,  перейдите на панель мониторинга отчетов и \>  выберите правило **Exchange транспорта.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="b15f1-150">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="b15f1-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange виджет правила транспорта в панели мониторинга Отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b15f1-152">Представление отчета для отчета Exchange правил транспорта</span><span class="sxs-lookup"><span data-stu-id="b15f1-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="b15f1-153">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b15f1-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="b15f1-154">**Просмотр данных по: Exchange правил транспорта** \> **Break down by: Direction:** This chart shows the number of **Inbound** and **Outbound messages** that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="b15f1-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="b15f1-155">**Просмотр данных по: Exchange правил транспорта** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="b15f1-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="b15f1-156">Вы установите уровень серьезности в качестве действия в правиле **(Аудит** этого правила с уровнем серьезности или _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="b15f1-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="b15f1-157">Дополнительные сведения см. в сообщении о действиях правила [потока почты в Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="b15f1-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="b15f1-158">**Просмотр данных по: правила транспорта Exchange DLP** \> **Break down by: Direction:** This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span><span class="sxs-lookup"><span data-stu-id="b15f1-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="b15f1-159">Далее можно уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b15f1-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b15f1-160">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="b15f1-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b15f1-161">**Показать данные для: скомпрометированная пользователей**</span><span class="sxs-lookup"><span data-stu-id="b15f1-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b15f1-162">**Показать данные для: Низкий объем контента, обнаруженного Патриотический акт США**</span><span class="sxs-lookup"><span data-stu-id="b15f1-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="b15f1-163">**Просмотр данных по: правила транспорта Exchange DLP** \> **Break down by: Direction:** This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="b15f1-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="b15f1-164">Далее можно уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b15f1-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b15f1-165">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="b15f1-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b15f1-166">**Показать данные для: скомпрометированная пользователей**</span><span class="sxs-lookup"><span data-stu-id="b15f1-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b15f1-167">**Показать данные для: Низкий объем контента, обнаруженного Патриотический акт США**</span><span class="sxs-lookup"><span data-stu-id="b15f1-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="b15f1-168">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров::</span><span class="sxs-lookup"><span data-stu-id="b15f1-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="b15f1-169">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b15f1-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="b15f1-170">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b15f1-170">Direction values</span></span>
- <span data-ttu-id="b15f1-171">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="b15f1-171">Severity values</span></span>

![Представление отчета в отчете Exchange правила транспорта](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b15f1-173">Представление таблицы сведений для отчета Exchange транспорта</span><span class="sxs-lookup"><span data-stu-id="b15f1-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="b15f1-174">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="b15f1-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b15f1-175">**Просмотр данных по: Exchange правила транспорта:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="b15f1-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="b15f1-176">**Date**</span></span>
  - <span data-ttu-id="b15f1-177">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="b15f1-177">**Transport rule**</span></span>
  - <span data-ttu-id="b15f1-178">**Тема**</span><span class="sxs-lookup"><span data-stu-id="b15f1-178">**Subject**</span></span>
  - <span data-ttu-id="b15f1-179">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="b15f1-179">**Sender address**</span></span>
  - <span data-ttu-id="b15f1-180">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="b15f1-180">**Recipient address**</span></span>
  - <span data-ttu-id="b15f1-181">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="b15f1-181">**Severity**</span></span>
  - <span data-ttu-id="b15f1-182">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b15f1-182">**Direction**</span></span>

- <span data-ttu-id="b15f1-183">**Просмотр данных по: правила Exchange транспорта:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="b15f1-184">**Date**</span><span class="sxs-lookup"><span data-stu-id="b15f1-184">**Date**</span></span>
  - <span data-ttu-id="b15f1-185">**Политика DLP**</span><span class="sxs-lookup"><span data-stu-id="b15f1-185">**DLP policy**</span></span>
  - <span data-ttu-id="b15f1-186">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="b15f1-186">**Transport rule**</span></span>
  - <span data-ttu-id="b15f1-187">**Тема**</span><span class="sxs-lookup"><span data-stu-id="b15f1-187">**Subject**</span></span>
  - <span data-ttu-id="b15f1-188">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="b15f1-188">**Sender address**</span></span>
  - <span data-ttu-id="b15f1-189">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="b15f1-189">**Recipient address**</span></span>
  - <span data-ttu-id="b15f1-190">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="b15f1-190">**Severity**</span></span>
  - <span data-ttu-id="b15f1-191">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b15f1-191">**Direction**</span></span>

<span data-ttu-id="b15f1-192">Если **щелкнуть Фильтры** в представлении таблицы сведений, результаты можно изменить следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="b15f1-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b15f1-193">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b15f1-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="b15f1-194">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b15f1-194">Direction values</span></span>
- <span data-ttu-id="b15f1-195">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="b15f1-195">Severity values</span></span>

<span data-ttu-id="b15f1-196">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="b15f1-197">Отчет о переадпорте</span><span class="sxs-lookup"><span data-stu-id="b15f1-197">Forwarding report</span></span>

<span data-ttu-id="b15f1-198">В **отчете о** пересылке показаны автоматически пересылаемые сообщения организации во внешние домены из Exchange Online почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="b15f1-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="b15f1-199">Переадренные сообщения могут представлять угрозу безопасности или соответствия требованиям, а также указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="b15f1-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="b15f1-200">Чтобы просмотреть отчет, откройте Центр [&](https://protection.office.com)безопасности,  перейдите на панель мониторинга отчетов и \>  выберите отчет **о переадпорте.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="b15f1-201">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="b15f1-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Виджет отчета о переадпорте в панели мониторинга Отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="b15f1-203">Представление отчета для отчета о переадпорте</span><span class="sxs-lookup"><span data-stu-id="b15f1-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="b15f1-204">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b15f1-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b15f1-205">**Показать данные для: Методы переададки:** показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="b15f1-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="b15f1-206">**Правило транспорта:** Также известное как [правила потока почты.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="b15f1-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="b15f1-207">**Правило почтовых ящиков:** Также известное как [правила "Входящие".](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="b15f1-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Представление методов переададки в отчете о переадпорте](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="b15f1-209">**Показать данные для: Переадправление доменов.** В этом представлении показаны домены получателей, которые являются пунктами назначения для переадправления.</span><span class="sxs-lookup"><span data-stu-id="b15f1-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Представление переадпорта доменов в отчете о переадпорте](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="b15f1-211">**Показать данные для: Переадверы**: Показаны следующие переад.</span><span class="sxs-lookup"><span data-stu-id="b15f1-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="b15f1-212">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="b15f1-212">**Transport rule**</span></span>
  - <span data-ttu-id="b15f1-213">Почтовый ящик, содержащий правило "Входящие" пересылания.</span><span class="sxs-lookup"><span data-stu-id="b15f1-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Forwarders view in the Forwarding report](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="b15f1-215">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="b15f1-216">Представление таблицы сведений для отчета о переадпорте</span><span class="sxs-lookup"><span data-stu-id="b15f1-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="b15f1-217">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="b15f1-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b15f1-218">**Переадпортаторы.** **Правило** транспорта значения или почтовый ящик, содержащий правило почтовых ящиков пересылания.</span><span class="sxs-lookup"><span data-stu-id="b15f1-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="b15f1-219">**Тип пересылания:** правило **почтовых ящиков значения** или **правило транспорта.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="b15f1-220">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="b15f1-220">**Recipient name**</span></span>
- <span data-ttu-id="b15f1-221">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="b15f1-221">**Recipient domain**</span></span>
- <span data-ttu-id="b15f1-222">**Сведения.** Это значение GUID правила потока почты или значение RuleIdentity правила "Входящие".</span><span class="sxs-lookup"><span data-stu-id="b15f1-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="b15f1-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="b15f1-223">**Count**</span></span>
- <span data-ttu-id="b15f1-224">**Дата первой переададки**</span><span class="sxs-lookup"><span data-stu-id="b15f1-224">**First forward date**</span></span>

<span data-ttu-id="b15f1-225">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b15f1-226">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b15f1-227">Отчет о состоянии почтового потока</span><span class="sxs-lookup"><span data-stu-id="b15f1-227">Mailflow status report</span></span>

<span data-ttu-id="b15f1-228">Отчет **о состоянии почтового потока** похож на отчет отправленной и полученной электронной почты, а дополнительные сведения о электронной почте разрешены или заблокированы на краю. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="b15f1-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="b15f1-229">Это единственный отчет, содержащий сведения о защите края, и показывает, сколько сообщений электронной почты блокируется перед тем, как быть разрешено в службу для оценки Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="b15f1-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b15f1-230">Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его пятью разными сообщениями, а не одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="b15f1-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="b15f1-231">Чтобы просмотреть отчет, откройте Центр [&](https://protection.office.com)безопасности,  перейдите к панели мониторинга отчетов и выберите отчет о состоянии \>  **mailflow.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="b15f1-232">Чтобы перейти непосредственно к отчету о состоянии **потока почты,** откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="b15f1-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Виджет отчета о состоянии почтового потока в панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="b15f1-234">Введите представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b15f1-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="b15f1-235">При открывании отчета вкладка **Type** выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b15f1-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="b15f1-236">По умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b15f1-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b15f1-237">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="b15f1-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="b15f1-238">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-238">**Direction**:</span></span>

  - <span data-ttu-id="b15f1-239">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="b15f1-239">**Inbound**</span></span>
  - <span data-ttu-id="b15f1-240">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="b15f1-240">**Outbound**</span></span>
  - <span data-ttu-id="b15f1-241">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="b15f1-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b15f1-242">отправитель abc@domain.com получателям xyz@domain.com (засчитываются  отдельно от входящие и **исходящие)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="b15f1-243">**Тип:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-243">**Type**:</span></span>

  - <span data-ttu-id="b15f1-244">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="b15f1-244">**Good mail**</span></span>
  - <span data-ttu-id="b15f1-245">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="b15f1-245">**Malware**</span></span>
  - <span data-ttu-id="b15f1-246">**Спам**</span><span class="sxs-lookup"><span data-stu-id="b15f1-246">**Spam**</span></span>
  - <span data-ttu-id="b15f1-247">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="b15f1-247">**Edge protection**</span></span>
  - <span data-ttu-id="b15f1-248">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="b15f1-248">**Rule messages**</span></span>
  - <span data-ttu-id="b15f1-249">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="b15f1-249">**Phishing email**</span></span>

<span data-ttu-id="b15f1-250">Диаграмма организована **значениями Type.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="b15f1-251">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b15f1-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="b15f1-252">В таблице данных содержатся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b15f1-252">The data table contains the following information:</span></span>

- <span data-ttu-id="b15f1-253">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b15f1-253">**Direction**</span></span>
- <span data-ttu-id="b15f1-254">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b15f1-254">**Type**</span></span>
- <span data-ttu-id="b15f1-255">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="b15f1-255">**24 hours**</span></span>
- <span data-ttu-id="b15f1-256">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="b15f1-256">**3 days**</span></span>
- <span data-ttu-id="b15f1-257">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="b15f1-257">**7 days**</span></span>
- <span data-ttu-id="b15f1-258">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="b15f1-258">**15 days**</span></span>
- <span data-ttu-id="b15f1-259">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="b15f1-259">**30 days**</span></span>

<span data-ttu-id="b15f1-260">Если вы **нажмете Выберите категорию для получения** дополнительных сведений, вы можете выбрать из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b15f1-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="b15f1-261">**Фишинговое письмо.** Этот выбор принимает вас к отчету о [состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b15f1-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b15f1-262">**Вредоносные программы в электронной** почте: этот выбор принимает вас к отчету о [состоянии защиты от угрозы](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="b15f1-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b15f1-263">**Обнаружение нежелательной почты.** Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b15f1-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="b15f1-264">**Edge заблокирован нежелательной почты:** этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b15f1-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b15f1-265">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-265">**Export**:</span></span>

<span data-ttu-id="b15f1-266">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="b15f1-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b15f1-267">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="b15f1-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b15f1-268">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b15f1-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b15f1-269">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="b15f1-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Введите представление в отчете о состоянии mailflow](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="b15f1-271">Представление направления для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b15f1-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="b15f1-272">Если щелкнуть **вкладку Direction,** используются те же фильтры по умолчанию из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="b15f1-273">Диаграмма организована **значениями Direction.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="b15f1-274">Эти фильтры можно изменить, щелкнув **Фильтр** или щелкнув значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b15f1-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="b15f1-275">Используются те же фильтры из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b15f1-276">Таблица данных содержит те же сведения из представления **Type.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="b15f1-277">Выбор **категории для получения дополнительных** сведений о выборах и поведении такой же, как представление **Type.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="b15f1-278">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-278">**Export**:</span></span>

<span data-ttu-id="b15f1-279">Для представления подробной информации можно экспортировать данные только в течение одного дня.</span><span class="sxs-lookup"><span data-stu-id="b15f1-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b15f1-280">Поэтому, если вы хотите экспортировать данные в течение 7 дней, необходимо сделать 7 различных действий по экспорту.</span><span class="sxs-lookup"><span data-stu-id="b15f1-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b15f1-281">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b15f1-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b15f1-282">Если данные за этот день содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="b15f1-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Представление направления в отчете о состоянии mailflow](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="b15f1-284">Представление воронки для отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b15f1-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="b15f1-285">В **представлении Воронка** показано, как функции защиты от угроз электронной почты Майкрософт фильтруют входящие и исходяющие сообщения электронной почты в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b15f1-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="b15f1-286">В нем представлены сведения об общем числе сообщений электронной почты, а также о том, как настроенные функции защиты от угроз, включая защиту края, антивирусные программы, защиту от фишинга, защиту от нежелательной почты и защиту от спуфинга, влияют на этот счет.</span><span class="sxs-lookup"><span data-stu-id="b15f1-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="b15f1-287">Если щелкнуть вкладку **Воронка,** это представление по умолчанию содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b15f1-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b15f1-288">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="b15f1-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b15f1-289">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-289">**Direction**:</span></span>

  - <span data-ttu-id="b15f1-290">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="b15f1-290">**Inbound**</span></span>
  - <span data-ttu-id="b15f1-291">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="b15f1-291">**Outbound**</span></span>
  - <span data-ttu-id="b15f1-292">**Intra-org.** Это количество для сообщений, отправленных в клиенте; то есть отправитель отправляет abc@domain.com получателям xyz@domain.com (засчитываются отдельно от входящие и исходящие).</span><span class="sxs-lookup"><span data-stu-id="b15f1-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="b15f1-293">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b15f1-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b15f1-294">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="b15f1-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b15f1-295">На этой диаграмме показана графа электронной почты, организованного по:</span><span class="sxs-lookup"><span data-stu-id="b15f1-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="b15f1-296">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-296">**Total email**</span></span>
- <span data-ttu-id="b15f1-297">**Электронная почта после защиты края**</span><span class="sxs-lookup"><span data-stu-id="b15f1-297">**Email after edge protection**</span></span>
- <span data-ttu-id="b15f1-298">**Электронная почта после вредоносных программ, репутации файлов, блока типа файла**</span><span class="sxs-lookup"><span data-stu-id="b15f1-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="b15f1-299">**Электронная почта после защиты от фишинга, репутации URL-адресов, обезличения бренда и подмены**</span><span class="sxs-lookup"><span data-stu-id="b15f1-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="b15f1-300">**Электронная почта после фильтрации массовой почты после нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="b15f1-301">**Электронная почта после обезличения пользователя** и домена <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b15f1-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="b15f1-302">**Электронная почта после детонации файла и URL-адреса**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b15f1-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="b15f1-303">**Электронная почта, обнаруженная как доброкачественная после защиты после доставки (защита времени щелчка URL-адреса)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="b15f1-304"><sup>1</sup> Защитник только для Office 365</span><span class="sxs-lookup"><span data-stu-id="b15f1-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b15f1-305">Чтобы просмотреть сообщение электронной почты, фильтруемой EOP или Defender для Office 365, щелкните значение в легенде диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b15f1-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="b15f1-306">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="b15f1-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b15f1-307">**Date**</span><span class="sxs-lookup"><span data-stu-id="b15f1-307">**Date**</span></span>
- <span data-ttu-id="b15f1-308">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-308">**Total email**</span></span>
- <span data-ttu-id="b15f1-309">**Защита края**</span><span class="sxs-lookup"><span data-stu-id="b15f1-309">**Edge protection**</span></span>
- <span data-ttu-id="b15f1-310">**Anti-malware, file reputation, file type block:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="b15f1-311">**Репутация файла:** сообщения фильтруются из-за идентификации присоединенного файла другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b15f1-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="b15f1-312">**Блок типа файла.** Сообщения фильтруются из-за типа вредоносного файла, идентифицированного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="b15f1-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b15f1-313">**Защита от фишинга, репутация URL-адреса, вымысление бренда, защита от подмены:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="b15f1-314">**Репутация URL-адреса.** Сообщения фильтруются из-за идентификации URL-адреса другими клиентами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b15f1-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="b15f1-315">**Вымысление** бренда: сообщения фильтруются из-за сообщения, исходящем от известных отправителей бренда, вымыкающих себя.</span><span class="sxs-lookup"><span data-stu-id="b15f1-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="b15f1-316">**Anti-spoof**: Сообщения фильтруются из-за сообщения, пытающихся подменить домен, к который принадлежит получатель, или домена, который не принадлежит отправителю сообщения.</span><span class="sxs-lookup"><span data-stu-id="b15f1-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="b15f1-317">**Фильтрация массовой почты** для борьбы со спамом:</span><span class="sxs-lookup"><span data-stu-id="b15f1-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="b15f1-318">**Массовая фильтрация** почты: сообщения фильтруются из-за попытки доставки массовой почты ее получателям.</span><span class="sxs-lookup"><span data-stu-id="b15f1-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="b15f1-319">**Вымысление** пользователя и домена (Defender для Office 365) :</span><span class="sxs-lookup"><span data-stu-id="b15f1-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b15f1-320">Вымысление пользователя. Сообщения фильтруются из-за попытки выдать себя за пользователя (отправитель сообщений), определенного в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b15f1-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="b15f1-321">**Обезличение** домена. Сообщения фильтруются из-за попытки выдать себя за домен, определенный в параметрах защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="b15f1-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="b15f1-322">**Детонация файлов и URL-адресов (Defender для Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="b15f1-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b15f1-323">**Детонация файлов:** сообщения, фильтруемые политикой Сейф вложений.</span><span class="sxs-lookup"><span data-stu-id="b15f1-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="b15f1-324">**Детонация URL-адреса.** Сообщение фильтруется политикой Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="b15f1-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="b15f1-325">**Защита после доставки и ZAP (ATP) или ZAP (EOP)**: ZAP указывает на авточистку нулевого часа.</span><span class="sxs-lookup"><span data-stu-id="b15f1-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="b15f1-326">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b15f1-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b15f1-327">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-327">**Export**:</span></span>

<span data-ttu-id="b15f1-328">После нажатия **"Экспорт** в **параметрах"** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b15f1-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="b15f1-329">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b15f1-330">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b15f1-331">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b15f1-332">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="b15f1-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b15f1-333">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b15f1-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b15f1-334">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="b15f1-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Представление воронки в отчете о состоянии mailflow](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="b15f1-336">Техническое представление отчета о состоянии mailflow</span><span class="sxs-lookup"><span data-stu-id="b15f1-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="b15f1-337">Представление **Tech аналогично** представлению **Воронка,** предоставляя более подробные сведения о настроенных средствах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="b15f1-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="b15f1-338">На диаграмме можно увидеть, как классифицируются сообщения на различных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="b15f1-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="b15f1-339">Если вы щелкните вкладку **Tech View,** по умолчанию это представление содержит диаграмму и таблицу данных, настроенные с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b15f1-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b15f1-340">**Дата.** Последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="b15f1-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b15f1-341">**Направление:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-341">**Direction**:</span></span>

  - <span data-ttu-id="b15f1-342">**Входящий**</span><span class="sxs-lookup"><span data-stu-id="b15f1-342">**Inbound**</span></span>
  - <span data-ttu-id="b15f1-343">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="b15f1-343">**Outbound**</span></span>
  - <span data-ttu-id="b15f1-344">**Intra-org:** это количество для сообщений в клиенте, то есть</span><span class="sxs-lookup"><span data-stu-id="b15f1-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b15f1-345">отправитель abc@domain.com отправляет получателю xyz@domain.com (рассчитывается отдельно от входящие и исходящие)</span><span class="sxs-lookup"><span data-stu-id="b15f1-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="b15f1-346">Совокупное представление и представление таблицы данных позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b15f1-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b15f1-347">При **нажатии фильтра** можно отфильтровать диаграмму и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="b15f1-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b15f1-348">На этой диаграмме показаны сообщения, организованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="b15f1-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b15f1-349">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-349">**Total email**</span></span>
- <span data-ttu-id="b15f1-350">**Edge allow** and **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="b15f1-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="b15f1-351">**Не вредоносные** программы, **Сейф обнаружения** вложений, обнаружения вредоносных программ <sup>\*</sup> и **сообщений правил** </span><span class="sxs-lookup"><span data-stu-id="b15f1-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="b15f1-352">**Не фишинг,** **отказ DMARC,** **обнаружение** обезличения, **обнаружение Spoof** и **обнаружение фишинга**</span><span class="sxs-lookup"><span data-stu-id="b15f1-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="b15f1-353">**Отсутствие обнаружения с детонацией URL-адреса** и **обнаружением детонации URL-адреса**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b15f1-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b15f1-354">**Не нежелательной почты** и  **нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="b15f1-355">**Обнаружение ссылок,** **Сейф** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="b15f1-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="b15f1-356"><sup>\*</sup>Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b15f1-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b15f1-357">Когда вы наведите курсор над категорией на диаграмме, вы увидите количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="b15f1-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="b15f1-358">В таблице данных содержатся следующие сведения, показанные в порядке убывающих дат:</span><span class="sxs-lookup"><span data-stu-id="b15f1-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b15f1-359">**Date**</span><span class="sxs-lookup"><span data-stu-id="b15f1-359">**Date**</span></span>
- <span data-ttu-id="b15f1-360">**Всего сообщений электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-360">**Total email**</span></span>
- <span data-ttu-id="b15f1-361">**Отфильтрованный край**</span><span class="sxs-lookup"><span data-stu-id="b15f1-361">**Edge filtered**</span></span>
- <span data-ttu-id="b15f1-362">**Антивирусный двигатель, Сейф вложения, правило фильтруется:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="b15f1-363">**Фильтруется** правило: Сообщения фильтруются из-за правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="b15f1-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="b15f1-364">**DMARC, impersonation, spoof, phish filtered:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="b15f1-365">**DMARC:** Сообщения фильтруются из-за отказа сообщения проверки подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="b15f1-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="b15f1-366">**Обнаружение детонации URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="b15f1-366">**URL detonation detection**</span></span>
- <span data-ttu-id="b15f1-367">**Фильтрация от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="b15f1-368">**ZaP удален**</span><span class="sxs-lookup"><span data-stu-id="b15f1-368">**ZAP removed**</span></span>
- <span data-ttu-id="b15f1-369">**Обнаружение по Сейф ссылки**</span><span class="sxs-lookup"><span data-stu-id="b15f1-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="b15f1-370">Если вы выберите строку в таблице данных, в вылете будет показана дальнейшая разбивка учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b15f1-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b15f1-371">**Экспорт:**</span><span class="sxs-lookup"><span data-stu-id="b15f1-371">**Export**:</span></span>

<span data-ttu-id="b15f1-372">При **нажатии на экспорт** **можно** выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b15f1-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="b15f1-373">**Сводка (с данными за последние 90 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b15f1-374">**Сведения (с данными за последние 30 дней не более)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b15f1-375">В **соответствии с датой** выберите диапазон, а затем нажмите **кнопку Применить**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b15f1-376">Данные для текущих фильтров будут экспортироваться в .csv файл.</span><span class="sxs-lookup"><span data-stu-id="b15f1-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b15f1-377">Каждый экспорт .csv ограничивается 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b15f1-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b15f1-378">Если данные содержат более 150 000 строк, будет создано несколько .csv файлов.</span><span class="sxs-lookup"><span data-stu-id="b15f1-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Представление технологий в отчете о состоянии mailflow](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="b15f1-380">Отправленный и полученный отчет электронной почты</span><span class="sxs-lookup"><span data-stu-id="b15f1-380">Sent and received email report</span></span>

<span data-ttu-id="b15f1-381">Отправленный **и** полученный отчет электронной почты — это интеллектуальный отчет, в нем показаны сведения о входящих и исходяющих сообщениях электронной почты, включая обнаружение нежелательной почты, вредоносные программы и сообщения электронной почты, идентифицированные как "хорошие".</span><span class="sxs-lookup"><span data-stu-id="b15f1-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="b15f1-382">Разница между этим отчетом и отчетом о состоянии [mailflow](#mailflow-status-report) заключается в том, что в этом отчете не содержатся данные о сообщениях, заблокированных краевой защитой. Важно понимать, что если сообщение отправляется пяти получателям, мы считаем его одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="b15f1-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="b15f1-383">Совокупное представление и представление деталей отчета позволяют в течение 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b15f1-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="b15f1-384">Чтобы просмотреть отчет, откройте Центр & безопасности,  перейдите [на](https://protection.office.com)панель мониторинга отчетов и выберите \>  **отправленную и полученную электронную почту.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="b15f1-385">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="b15f1-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Виджет электронной почты, отправленный и полученный в панели мониторинга Отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b15f1-387">Представление отчета для отправленного и полученного отчета электронной почты</span><span class="sxs-lookup"><span data-stu-id="b15f1-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="b15f1-388">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b15f1-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b15f1-389">**Break down by: Type:** The chart shows all available categories:</span><span class="sxs-lookup"><span data-stu-id="b15f1-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="b15f1-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="b15f1-390">**Total**</span></span>
  - <span data-ttu-id="b15f1-391">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="b15f1-391">**Good mail**</span></span>
  - <span data-ttu-id="b15f1-392">**Вредоносные программы (антивирусные программы)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b15f1-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="b15f1-393">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-393">**Spam detections**</span></span>
  - <span data-ttu-id="b15f1-394">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="b15f1-394">**Rule messages**</span></span>
  - <span data-ttu-id="b15f1-395">**Расширенные вредоносные** программы (Microsoft Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="b15f1-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="b15f1-396">При наведении в течение дня (точки данных) на диаграмме можно увидеть сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="b15f1-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Введите представление в отчете отправленной и полученной электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="b15f1-398">**Break down by: Direction:** The chart shows **Total,** **Inbound**, and **Outbound** data.</span><span class="sxs-lookup"><span data-stu-id="b15f1-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="b15f1-399">При наведении в течение дня (точки данных) на диаграмме можно увидеть сведения за этот день.</span><span class="sxs-lookup"><span data-stu-id="b15f1-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление направления в отчете отправленной и полученной электронной почты](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="b15f1-401">**Сверлить** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="b15f1-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="b15f1-402">**Сверлить** \> **Обнаружения нежелательной почты)**: Этот выбор принимает вас к [отчету обнаружения нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b15f1-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b15f1-403">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="b15f1-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b15f1-404">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b15f1-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="b15f1-405">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b15f1-405">Direction values</span></span>
- <span data-ttu-id="b15f1-406">Значения типа</span><span class="sxs-lookup"><span data-stu-id="b15f1-406">Type values</span></span>

<span data-ttu-id="b15f1-407">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b15f1-408">Представление таблицы сведений для отправленного и полученного отчета электронной почты</span><span class="sxs-lookup"><span data-stu-id="b15f1-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="b15f1-409">Если **щелкнуть** таблицу Просмотр сведений в таблице **Break down by: Direction** or Break down **by: Direction** view, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="b15f1-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="b15f1-410">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-410">**Date (UTC)**</span></span>
- <span data-ttu-id="b15f1-411">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b15f1-411">**Type**</span></span>
- <span data-ttu-id="b15f1-412">**Направление**</span><span class="sxs-lookup"><span data-stu-id="b15f1-412">**Direction**</span></span>
- <span data-ttu-id="b15f1-413">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="b15f1-413">**Message count**</span></span>

<span data-ttu-id="b15f1-414">Если **щелкнуть Фильтры** в представлении таблицы сведений, результаты можно изменить следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="b15f1-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b15f1-415">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="b15f1-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="b15f1-416">Значения направления</span><span class="sxs-lookup"><span data-stu-id="b15f1-416">Direction values</span></span>
- <span data-ttu-id="b15f1-417">Значения типа</span><span class="sxs-lookup"><span data-stu-id="b15f1-417">Type values</span></span>

<span data-ttu-id="b15f1-418">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="b15f1-419">Отчет о главных отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="b15f1-419">Top senders and recipients report</span></span>

<span data-ttu-id="b15f1-420">Верхний **отчет отправителей** и получателей — это диаграмма пирога, показывающая главных отправителей и получателей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b15f1-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="b15f1-421">Чтобы просмотреть отчет, откройте центр & безопасности,  [перейдите к панели](https://protection.office.com)мониторинга отчетов и выберите главных отправителей \>  **и получателей.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="b15f1-422">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="b15f1-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Виджет главных отправителей и получателей в панели мониторинга Отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b15f1-424">Представление отчета для главных отправителей и получателей</span><span class="sxs-lookup"><span data-stu-id="b15f1-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="b15f1-425">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="b15f1-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b15f1-426">**Показать данные для \> отправителей верхней почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="b15f1-427">**Показать данные для \> получателей топ-почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="b15f1-428">**Демонстрация данных для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="b15f1-429">**Показать данные для \> Лучшие получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b15f1-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="b15f1-430">**Показать данные для \> получателей вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="b15f1-431">Состав диаграммы пирога изменяется на основе этих выборов.</span><span class="sxs-lookup"><span data-stu-id="b15f1-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="b15f1-432">При наведении на клин в диаграмме пирога можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="b15f1-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="b15f1-433">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Диаграмма пирога в представлении Report в отчете о главных отправителей и получателей](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b15f1-435">Представление таблицы сведений для отчета о главных отправителей и получателях</span><span class="sxs-lookup"><span data-stu-id="b15f1-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="b15f1-436">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="b15f1-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b15f1-437">**Показать данные для \> отправителей верхней почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="b15f1-438">**Главные отправители почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-438">**Top mail senders**</span></span>
  - <span data-ttu-id="b15f1-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="b15f1-439">**Count**</span></span>

- <span data-ttu-id="b15f1-440">**Показать данные для \> получателей топ-почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="b15f1-441">**Лучшие получатели почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="b15f1-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="b15f1-442">**Count**</span></span>

- <span data-ttu-id="b15f1-443">**Демонстрация данных для \> получателей нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="b15f1-444">**Лучшие получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="b15f1-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="b15f1-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="b15f1-445">**Count**</span></span>

- <span data-ttu-id="b15f1-446">**Показать данные для \> Лучшие получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b15f1-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="b15f1-447">**Лучшие получатели вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="b15f1-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="b15f1-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="b15f1-448">**Count**</span></span>

- <span data-ttu-id="b15f1-449">**Показать данные для \> получателей вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="b15f1-450">**Лучшие получатели вредоносных программ (Defender для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b15f1-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="b15f1-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="b15f1-451">**Count**</span></span>

<span data-ttu-id="b15f1-452">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="b15f1-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b15f1-453">Чтобы вернуться к представлению отчета, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="b15f1-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b15f1-454">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="b15f1-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b15f1-455">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="b15f1-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b15f1-456">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="b15f1-456">**Organization Management**</span></span>
- <span data-ttu-id="b15f1-457">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="b15f1-457">**Security Administrator**</span></span>
- <span data-ttu-id="b15f1-458">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="b15f1-458">**Security Reader**</span></span>
- <span data-ttu-id="b15f1-459">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="b15f1-459">**Global Reader**</span></span>

<span data-ttu-id="b15f1-460">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b15f1-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b15f1-461">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b15f1-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b15f1-462">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b15f1-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b15f1-463">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b15f1-463">Related topics</span></span>

[<span data-ttu-id="b15f1-464">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b15f1-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b15f1-465">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b15f1-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="b15f1-466">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b15f1-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="b15f1-467">Просмотр отчетов для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="b15f1-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
