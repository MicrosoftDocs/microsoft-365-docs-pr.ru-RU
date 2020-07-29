---
title: Просмотр отчетов потока обработки почты в Центре безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Узнайте, как найти и использовать отчеты безопасности почтовых систем для вашей организации. Отчеты о движении по почте доступны в центре безопасности & соответствия требованиям.
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434183"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="42b37-104">Просмотр отчетов потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="42b37-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="42b37-105">В дополнение к сведениям о [почтовых сообщениях](mail-flow-insights-v2.md) , которые доступны в центре безопасности & соответствия требованиям, доступны разнообразные отчеты о движении почты, которые помогут вам отслеживать свою организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42b37-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="42b37-106">Если у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-these-reports), вы можете просмотреть эти отчеты в центре безопасности & соответствия требованиям, <https://office.protection.com> перейдя на **Reports** \> **панель мониторинга**отчетов.</span><span class="sxs-lookup"><span data-stu-id="42b37-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="42b37-107">Чтобы перейти непосредственно к панели мониторинга отчетов, откройте ее <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="42b37-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="42b37-109">Отчет о соединителях</span><span class="sxs-lookup"><span data-stu-id="42b37-109">Connector report</span></span>

<span data-ttu-id="42b37-110">В **отчете о соединителе** отображаются действия потока обработки почты для [входящих и исходящих соединителей](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) , настроенных для Организации.</span><span class="sxs-lookup"><span data-stu-id="42b37-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="42b37-111">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите пункт " **отчет о соединителе**".</span><span class="sxs-lookup"><span data-stu-id="42b37-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="42b37-112">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="42b37-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Мини-приложение "отчет о соединителе" на панели мониторинга отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="42b37-114">Представление отчета для соединителя</span><span class="sxs-lookup"><span data-stu-id="42b37-114">Report view for the Connector report</span></span>

<span data-ttu-id="42b37-115">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="42b37-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="42b37-116">**Просмотр данных по: почтовые потоки**: на этой диаграмме показано количество входящих и исходящих сообщений, упорядоченных по следующим адресам:</span><span class="sxs-lookup"><span data-stu-id="42b37-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="42b37-117">**Total**</span><span class="sxs-lookup"><span data-stu-id="42b37-117">**Total**</span></span>
  - <span data-ttu-id="42b37-118">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="42b37-119">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="42b37-120">Указанный соединитель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="42b37-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="42b37-121">Чтобы изолировать данные на диаграмме, используйте параметр **Показать данные для** управления, чтобы выбрать один из этих параметров или **весь процесс обработки почты**.</span><span class="sxs-lookup"><span data-stu-id="42b37-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных с помощью почтовых ящиков в отчете о соединителях](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="42b37-123">**Просмотр данных по: использование TLS**: на этой диаграмме показан процент использования протокола TLS для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="42b37-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="42b37-124">Чтобы изолировать данные на диаграмме, используйте элемент управления **Показать данные для** выбора одного из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="42b37-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="42b37-125">**Весь процесс обработки почты**</span><span class="sxs-lookup"><span data-stu-id="42b37-125">**All mail flow**</span></span>
  - <span data-ttu-id="42b37-126">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="42b37-127">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="42b37-128">Указанный соединитель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="42b37-128">A specific connector that you've configured.</span></span>

  ![Просмотр данных по использованию TLS в отчете о соединителях](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="42b37-130">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="42b37-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="42b37-131">Представление таблицы сведений о соединителе</span><span class="sxs-lookup"><span data-stu-id="42b37-131">Details table view for the Connector report</span></span>

<span data-ttu-id="42b37-132">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="42b37-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="42b37-133">**Date**</span><span class="sxs-lookup"><span data-stu-id="42b37-133">**Date**</span></span>
- <span data-ttu-id="42b37-134">**Направление и имя соединителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-134">**Connector direction and name**</span></span>
- <span data-ttu-id="42b37-135">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-135">**Connector type**</span></span>
- <span data-ttu-id="42b37-136">**Принудительное TLS?**: значение **true** или **false**.</span><span class="sxs-lookup"><span data-stu-id="42b37-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="42b37-137">**Без TLS** (%)</span><span class="sxs-lookup"><span data-stu-id="42b37-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="42b37-138">**TLS 1,0** (%)</span><span class="sxs-lookup"><span data-stu-id="42b37-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="42b37-139">**TLS 1,1** (%)</span><span class="sxs-lookup"><span data-stu-id="42b37-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="42b37-140">**TLS 1,2** (%)</span><span class="sxs-lookup"><span data-stu-id="42b37-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="42b37-141">**Volume**: количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="42b37-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="42b37-142">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="42b37-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="42b37-143">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="42b37-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="42b37-144">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="42b37-144">Exchange transport rule report</span></span>

<span data-ttu-id="42b37-145">В **отчете о правиле транспорта Exchange** показано, как правила обработки почты (также называемые правилами транспорта) применяются к входящим и исходящим сообщениям в Организации.</span><span class="sxs-lookup"><span data-stu-id="42b37-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="42b37-146">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **правило транспорта Exchange**.</span><span class="sxs-lookup"><span data-stu-id="42b37-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="42b37-147">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="42b37-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Мини-приложение правил транспорта Exchange в панели мониторинга отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="42b37-149">Представление отчета для отчета о правиле транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="42b37-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="42b37-150">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="42b37-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="42b37-151">**Просмотр данных по: правила** \> транспорта Exchange **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта.</span><span class="sxs-lookup"><span data-stu-id="42b37-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="42b37-152">**Просмотр данных по: правила** \> транспорта Exchange **Разбить на: степень серьезности**: на этой диаграмме показано количество сообщений с **высокой степенью серьезности** и **средней**серьезности, а также сообщения о **низком уровне** серьезности.</span><span class="sxs-lookup"><span data-stu-id="42b37-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="42b37-153">Уровень серьезности задается как действие в правиле (**аудит этого правила со степенью серьезности** или _сетаудитсеверити_).</span><span class="sxs-lookup"><span data-stu-id="42b37-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="42b37-154">Дополнительные сведения см. [в разделе действие правил обработки почты в Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="42b37-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="42b37-155">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="42b37-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="42b37-156">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="42b37-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="42b37-157">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="42b37-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="42b37-158">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="42b37-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="42b37-159">**Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**</span><span class="sxs-lookup"><span data-stu-id="42b37-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="42b37-160">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: в этом представлении отображается количество **высоких** и **средних**уровней серьезности, а также сообщения о **низком** уровне, на которые влияют правила транспорта DLP.</span><span class="sxs-lookup"><span data-stu-id="42b37-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="42b37-161">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="42b37-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="42b37-162">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="42b37-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="42b37-163">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="42b37-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="42b37-164">**Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**</span><span class="sxs-lookup"><span data-stu-id="42b37-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="42b37-165">Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров::</span><span class="sxs-lookup"><span data-stu-id="42b37-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="42b37-166">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="42b37-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="42b37-167">Значения направления</span><span class="sxs-lookup"><span data-stu-id="42b37-167">Direction values</span></span>
- <span data-ttu-id="42b37-168">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="42b37-168">Severity values</span></span>

![Представление отчета в отчете о правиле транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="42b37-170">Представление таблицы сведений для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="42b37-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="42b37-171">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="42b37-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="42b37-172">**Просмотр данных по: правила транспорта Exchange**:</span><span class="sxs-lookup"><span data-stu-id="42b37-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="42b37-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="42b37-173">**Date**</span></span>
  - <span data-ttu-id="42b37-174">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="42b37-174">**Transport rule**</span></span>
  - <span data-ttu-id="42b37-175">**Тема**</span><span class="sxs-lookup"><span data-stu-id="42b37-175">**Subject**</span></span>
  - <span data-ttu-id="42b37-176">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-176">**Sender address**</span></span>
  - <span data-ttu-id="42b37-177">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="42b37-177">**Recipient address**</span></span>
  - <span data-ttu-id="42b37-178">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="42b37-178">**Severity**</span></span>
  - <span data-ttu-id="42b37-179">**Направление**</span><span class="sxs-lookup"><span data-stu-id="42b37-179">**Direction**</span></span>

- <span data-ttu-id="42b37-180">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных**:</span><span class="sxs-lookup"><span data-stu-id="42b37-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="42b37-181">**Date**</span><span class="sxs-lookup"><span data-stu-id="42b37-181">**Date**</span></span>
  - <span data-ttu-id="42b37-182">**Политика защиты от потери данных**</span><span class="sxs-lookup"><span data-stu-id="42b37-182">**DLP policy**</span></span>
  - <span data-ttu-id="42b37-183">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="42b37-183">**Transport rule**</span></span>
  - <span data-ttu-id="42b37-184">**Тема**</span><span class="sxs-lookup"><span data-stu-id="42b37-184">**Subject**</span></span>
  - <span data-ttu-id="42b37-185">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="42b37-185">**Sender address**</span></span>
  - <span data-ttu-id="42b37-186">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="42b37-186">**Recipient address**</span></span>
  - <span data-ttu-id="42b37-187">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="42b37-187">**Severity**</span></span>
  - <span data-ttu-id="42b37-188">**Направление**</span><span class="sxs-lookup"><span data-stu-id="42b37-188">**Direction**</span></span>

<span data-ttu-id="42b37-189">Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="42b37-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="42b37-190">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="42b37-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="42b37-191">Значения направления</span><span class="sxs-lookup"><span data-stu-id="42b37-191">Direction values</span></span>
- <span data-ttu-id="42b37-192">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="42b37-192">Severity values</span></span>

<span data-ttu-id="42b37-193">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="42b37-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="42b37-194">Отчет о переадресации</span><span class="sxs-lookup"><span data-stu-id="42b37-194">Forwarding report</span></span>

<span data-ttu-id="42b37-195">**Отчет о переадресации** показывает автоматически перенаправляемые сообщения вашей организации на внешние домены из почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="42b37-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="42b37-196">Пересылаемые сообщения могут представлять угрозу безопасности или соответствия требованиям и могут указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="42b37-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="42b37-197">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **Пересылка отчета**.</span><span class="sxs-lookup"><span data-stu-id="42b37-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="42b37-198">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="42b37-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Мини-приложение "пересылка отчетов" на панели мониторинга отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="42b37-200">Представление отчета для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="42b37-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="42b37-201">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="42b37-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="42b37-202">**Показать данные для: методы пересылки**: показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="42b37-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="42b37-203">**Правило транспорта**: также называется " [правила для поток обработки почты](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)".</span><span class="sxs-lookup"><span data-stu-id="42b37-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="42b37-204">**Правило почтовых ящиков**: также называются [правилами для папки "Входящие"](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="42b37-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Способы пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="42b37-206">**Показать данные для: пересылка доменов**: в этом представлении отображаются домены получателей, которые являются конечными объектами для переадресации.</span><span class="sxs-lookup"><span data-stu-id="42b37-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Просмотр пересылаемых доменов в отчете о перенаправлении](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="42b37-208">**Показать данные для: серверы пересылки**: отображаются следующие серверы пересылки:</span><span class="sxs-lookup"><span data-stu-id="42b37-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="42b37-209">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="42b37-209">**Transport rule**</span></span>
  - <span data-ttu-id="42b37-210">Почтовый ящик, который содержит правило пересылки папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="42b37-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Представление пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="42b37-212">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="42b37-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="42b37-213">Представление таблицы сведений для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="42b37-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="42b37-214">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="42b37-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="42b37-215">**Серверы пересылки**: **правило транспорта** или почтовый ящик, который содержит правило пересылки папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="42b37-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="42b37-216">**Тип перенаправления**: **правило почтового ящика** значения или **правило транспорта**.</span><span class="sxs-lookup"><span data-stu-id="42b37-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="42b37-217">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="42b37-217">**Recipient name**</span></span>
- <span data-ttu-id="42b37-218">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="42b37-218">**Recipient domain**</span></span>
- <span data-ttu-id="42b37-219">**Details**: это значение GUID почтового процесса или значение рулеидентити правила для папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="42b37-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="42b37-220">**Count**</span><span class="sxs-lookup"><span data-stu-id="42b37-220">**Count**</span></span>
- <span data-ttu-id="42b37-221">**Дата первой пересылки**</span><span class="sxs-lookup"><span data-stu-id="42b37-221">**First forward date**</span></span>

<span data-ttu-id="42b37-222">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="42b37-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="42b37-223">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="42b37-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="42b37-224">Отчет о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="42b37-224">Mailflow status report</span></span>

<span data-ttu-id="42b37-225">**Отчет о состоянии Mailflow** похож на отчет о [отправленных и полученных сообщениях электронной почты](#sent-and-received-email-report)с дополнительными сведениями об электронной почте, разрешенной или заблокированной для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="42b37-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="42b37-226">Это единственный отчет, содержащий сведения о защите от краев, а также показывает, сколько электронной почты блокируется до того, как она будет разрешена для оценки службой Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="42b37-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="42b37-227">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **отчет о состоянии Mailflow**.</span><span class="sxs-lookup"><span data-stu-id="42b37-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="42b37-228">Чтобы перейти непосредственно к **отчету о состоянии почтового процесса**, откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="42b37-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Мини-приложение "отчет о состоянии Mailflow" на панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="42b37-230">Тип представления для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="42b37-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="42b37-231">При открытии отчета по умолчанию выбирается вкладка **тип** .</span><span class="sxs-lookup"><span data-stu-id="42b37-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="42b37-232">По умолчанию это представление содержит диаграмму и таблицу данных, настроенную со следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="42b37-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="42b37-233">**Дата**: последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="42b37-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="42b37-234">**Направление**:</span><span class="sxs-lookup"><span data-stu-id="42b37-234">**Direction**:</span></span>

  - <span data-ttu-id="42b37-235">**Получение**</span><span class="sxs-lookup"><span data-stu-id="42b37-235">**Inbound**</span></span>
  - <span data-ttu-id="42b37-236">**Прав**</span><span class="sxs-lookup"><span data-stu-id="42b37-236">**Outbound**</span></span>
  - <span data-ttu-id="42b37-237">**Внутренняя** (подсчитывается отдельно от **входящих** и **исходящих**)</span><span class="sxs-lookup"><span data-stu-id="42b37-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="42b37-238">**Тип**:</span><span class="sxs-lookup"><span data-stu-id="42b37-238">**Type**:</span></span>

  - <span data-ttu-id="42b37-239">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="42b37-239">**Good mail**</span></span>
  - <span data-ttu-id="42b37-240">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="42b37-240">**Malware**</span></span>
  - <span data-ttu-id="42b37-241">**Спам**</span><span class="sxs-lookup"><span data-stu-id="42b37-241">**Spam**</span></span>
  - <span data-ttu-id="42b37-242">**Защита пограничной системы**</span><span class="sxs-lookup"><span data-stu-id="42b37-242">**Edge protection**</span></span>
  - <span data-ttu-id="42b37-243">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="42b37-243">**Rule messages**</span></span>
  - <span data-ttu-id="42b37-244">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="42b37-244">**Phishing email**</span></span>

<span data-ttu-id="42b37-245">Диаграмма организована по значениям **типов** .</span><span class="sxs-lookup"><span data-stu-id="42b37-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="42b37-246">Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="42b37-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="42b37-247">Таблица данных содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="42b37-247">The data table contains the following information:</span></span>

- <span data-ttu-id="42b37-248">**Направление**</span><span class="sxs-lookup"><span data-stu-id="42b37-248">**Direction**</span></span>
- <span data-ttu-id="42b37-249">**Тип**</span><span class="sxs-lookup"><span data-stu-id="42b37-249">**Type**</span></span>
- <span data-ttu-id="42b37-250">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="42b37-250">**24 hours**</span></span>
- <span data-ttu-id="42b37-251">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="42b37-251">**3 days**</span></span>
- <span data-ttu-id="42b37-252">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="42b37-252">**7 days**</span></span>
- <span data-ttu-id="42b37-253">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="42b37-253">**15 days**</span></span>
- <span data-ttu-id="42b37-254">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="42b37-254">**30 days**</span></span>

<span data-ttu-id="42b37-255">Если щелкнуть **выбрать категорию для получения дополнительных сведений**, можно выбрать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="42b37-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="42b37-256">**Фишинг-сообщение**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="42b37-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="42b37-257">**Вредоносные программы в электронной почте**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="42b37-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="42b37-258">**Обнаружения нежелательной почты**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="42b37-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="42b37-259">**Нежелательная почта с пограничным**сервером: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="42b37-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="42b37-260">**Export**:</span><span class="sxs-lookup"><span data-stu-id="42b37-260">**Export**:</span></span>

<span data-ttu-id="42b37-261">Для подробного представления можно экспортировать данные только один день.</span><span class="sxs-lookup"><span data-stu-id="42b37-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="42b37-262">Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="42b37-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="42b37-263">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="42b37-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="42b37-264">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="42b37-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="42b37-265">Введите View в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="42b37-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="42b37-266">Представление "направление" для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="42b37-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="42b37-267">При нажатии вкладки **направление** используются те же фильтры по умолчанию из представления **тип** .</span><span class="sxs-lookup"><span data-stu-id="42b37-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="42b37-268">Диаграмма организована по значениям **направления** .</span><span class="sxs-lookup"><span data-stu-id="42b37-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="42b37-269">Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="42b37-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="42b37-270">Используются те же фильтры из представления **типа** .</span><span class="sxs-lookup"><span data-stu-id="42b37-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="42b37-271">Таблица данных содержит одну и ту же информацию из представления **типа** .</span><span class="sxs-lookup"><span data-stu-id="42b37-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="42b37-272">**Для получения дополнительных сведений выберите категорию** , которая совпадает с представлением " **тип** ".</span><span class="sxs-lookup"><span data-stu-id="42b37-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="42b37-273">**Export**:</span><span class="sxs-lookup"><span data-stu-id="42b37-273">**Export**:</span></span>

<span data-ttu-id="42b37-274">Для подробного представления можно экспортировать данные только один день.</span><span class="sxs-lookup"><span data-stu-id="42b37-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="42b37-275">Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="42b37-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="42b37-276">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="42b37-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="42b37-277">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="42b37-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="42b37-278">Представление "направление" в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="42b37-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="42b37-279">Отчет о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="42b37-279">Sent and received email report</span></span>

<span data-ttu-id="42b37-280">Отчет о **отправленных и полученных сообщениях** — это интеллектуальный отчет, в котором отображаются сведения о входящих и исходящих сообщениях электронной почты, в том числе об обнаружении нежелательной почты, вредоносных программах и сообщениях электронной почты, определенных</span><span class="sxs-lookup"><span data-stu-id="42b37-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="42b37-281">Разница между этим отчетом и [отчетом о состоянии Mailflow](#mailflow-status-report) : этот отчет не содержит данные о сообщениях, заблокированных службой защиты от краев.</span><span class="sxs-lookup"><span data-stu-id="42b37-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="42b37-282">Сводное представление и подробное представление отчета допускают 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="42b37-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="42b37-283">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите **Отправленные и полученные сообщения электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="42b37-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="42b37-284">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="42b37-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Мини-приложение "Отправленные и полученные сообщения электронной почты" в панели мониторинга отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="42b37-286">Представление отчета для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="42b37-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="42b37-287">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="42b37-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="42b37-288">**Разбить на: тип**: на диаграмме отображаются все доступные категории:</span><span class="sxs-lookup"><span data-stu-id="42b37-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="42b37-289">**Total**</span><span class="sxs-lookup"><span data-stu-id="42b37-289">**Total**</span></span>
  - <span data-ttu-id="42b37-290">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="42b37-290">**Good mail**</span></span>
  - <span data-ttu-id="42b37-291">**Вредоносные программы (защита от вредоносных программ)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="42b37-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="42b37-292">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="42b37-292">**Spam detections**</span></span>
  - <span data-ttu-id="42b37-293">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="42b37-293">**Rule messages**</span></span>
  - <span data-ttu-id="42b37-294">**Расширенная вредоносная программа** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="42b37-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="42b37-295">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.</span><span class="sxs-lookup"><span data-stu-id="42b37-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Введите View в отчет о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="42b37-297">**Разбейте на: направление**: на диаграмме показаны **Общие**, **Входящие**и **Исходящие** данные.</span><span class="sxs-lookup"><span data-stu-id="42b37-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="42b37-298">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.</span><span class="sxs-lookup"><span data-stu-id="42b37-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление "направление" в отчете о отправленных и полученных сообщениях](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="42b37-300">**Детализация по** \> **Вредоносные программы (защита от вредоносных программ)**: при выборе этого параметра осуществляется [Поиск вредоносных программ в отчете по электронной почте](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="42b37-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="42b37-301">**Детализация по** \> **Обнаружения нежелательной почты)**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="42b37-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="42b37-302">Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="42b37-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="42b37-303">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="42b37-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="42b37-304">Значения направления</span><span class="sxs-lookup"><span data-stu-id="42b37-304">Direction values</span></span>
- <span data-ttu-id="42b37-305">Значения типов</span><span class="sxs-lookup"><span data-stu-id="42b37-305">Type values</span></span>

<span data-ttu-id="42b37-306">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="42b37-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="42b37-307">Представление таблицы сведений для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="42b37-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="42b37-308">Если вы нажимайте кнопку **Просмотреть таблицу сведений** в разделе " **разделить вниз: направление** или" **разбивка на:** представление "направление", отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="42b37-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="42b37-309">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="42b37-309">**Date (UTC)**</span></span>
- <span data-ttu-id="42b37-310">**Тип**</span><span class="sxs-lookup"><span data-stu-id="42b37-310">**Type**</span></span>
- <span data-ttu-id="42b37-311">**Направление**</span><span class="sxs-lookup"><span data-stu-id="42b37-311">**Direction**</span></span>
- <span data-ttu-id="42b37-312">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="42b37-312">**Message count**</span></span>

<span data-ttu-id="42b37-313">Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="42b37-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="42b37-314">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="42b37-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="42b37-315">Значения направления</span><span class="sxs-lookup"><span data-stu-id="42b37-315">Direction values</span></span>
- <span data-ttu-id="42b37-316">Значения типов</span><span class="sxs-lookup"><span data-stu-id="42b37-316">Type values</span></span>

<span data-ttu-id="42b37-317">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="42b37-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="42b37-318">Отчет по основным отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="42b37-318">Top senders and recipients report</span></span>

<span data-ttu-id="42b37-319">Отчет по **основным отправителям и получателям** — это круговая диаграмма, в которой показаны лучшие отправители и получатели сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="42b37-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="42b37-320">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **наиболее отправители и получатели**.</span><span class="sxs-lookup"><span data-stu-id="42b37-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="42b37-321">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="42b37-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Мини-приложение "лучшие отправители и получатели" в панели мониторинга отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="42b37-323">Представление отчета для отчета по верхним отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="42b37-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="42b37-324">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="42b37-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="42b37-325">**Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**</span><span class="sxs-lookup"><span data-stu-id="42b37-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="42b37-326">**Отображение данных для \> наиболее популярных получателей почты**</span><span class="sxs-lookup"><span data-stu-id="42b37-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="42b37-327">**Отображение данных для \> самых популярных нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="42b37-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="42b37-328">**Показать данные для \> Первые получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="42b37-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="42b37-329">**Показать данные для \> Первые получатели вредоносных программ (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="42b37-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="42b37-330">Структура круговой диаграммы изменяется в зависимости от выбранных вариантов.</span><span class="sxs-lookup"><span data-stu-id="42b37-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="42b37-331">При наведении указателя на сектор на круговой диаграмме можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="42b37-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="42b37-332">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="42b37-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Круговая диаграмма в представлении отчета в отчете по верхним отправителям и получателям](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="42b37-334">Представление таблицы "сведения" для отчета по верхним отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="42b37-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="42b37-335">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="42b37-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="42b37-336">**Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**</span><span class="sxs-lookup"><span data-stu-id="42b37-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="42b37-337">**Сообщения верхнего уровня**</span><span class="sxs-lookup"><span data-stu-id="42b37-337">**Top mail senders**</span></span>
  - <span data-ttu-id="42b37-338">**Count**</span><span class="sxs-lookup"><span data-stu-id="42b37-338">**Count**</span></span>

- <span data-ttu-id="42b37-339">**Отображение данных для \> наиболее популярных получателей почты**</span><span class="sxs-lookup"><span data-stu-id="42b37-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="42b37-340">**Самые популярные Получатели почты**</span><span class="sxs-lookup"><span data-stu-id="42b37-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="42b37-341">**Count**</span><span class="sxs-lookup"><span data-stu-id="42b37-341">**Count**</span></span>

- <span data-ttu-id="42b37-342">**Отображение данных для \> самых популярных нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="42b37-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="42b37-343">**Самые распространенные получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="42b37-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="42b37-344">**Count**</span><span class="sxs-lookup"><span data-stu-id="42b37-344">**Count**</span></span>

- <span data-ttu-id="42b37-345">**Показать данные для \> Первые получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="42b37-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="42b37-346">**Самые популярные получатели вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="42b37-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="42b37-347">**Count**</span><span class="sxs-lookup"><span data-stu-id="42b37-347">**Count**</span></span>

- <span data-ttu-id="42b37-348">**Показать данные для \> Первые получатели вредоносных программ (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="42b37-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="42b37-349">**Первые получатели вредоносных программ (ATP)**</span><span class="sxs-lookup"><span data-stu-id="42b37-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="42b37-350">**Count**</span><span class="sxs-lookup"><span data-stu-id="42b37-350">**Count**</span></span>

<span data-ttu-id="42b37-351">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="42b37-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="42b37-352">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="42b37-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="42b37-353">Какие разрешения необходимы для просмотра отчетов?</span><span class="sxs-lookup"><span data-stu-id="42b37-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="42b37-354">Для просмотра и использования отчетов необходимо быть членом указанной группы ролей в центре безопасности & соответствия требованиям **и** в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="42b37-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="42b37-355">В центре безопасности & соответствия требованиям необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="42b37-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="42b37-356">— Управление организацией</span><span class="sxs-lookup"><span data-stu-id="42b37-356">-Organization Management</span></span>

  <span data-ttu-id="42b37-357">-Администратор безопасности (это также можно сделать в [центре администрирования Azure Active Directory](https://aad.portal.azure.com) — средство чтения безопасности</span><span class="sxs-lookup"><span data-stu-id="42b37-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="42b37-358">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="42b37-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="42b37-359">В Exchange Online необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="42b37-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="42b37-360">— Управление организацией</span><span class="sxs-lookup"><span data-stu-id="42b37-360">-Organization Management</span></span>

  <span data-ttu-id="42b37-361">— Управление организацией только с просмотром</span><span class="sxs-lookup"><span data-stu-id="42b37-361">-View-only Organization Management</span></span>

  <span data-ttu-id="42b37-362">— Получатели только для просмотра</span><span class="sxs-lookup"><span data-stu-id="42b37-362">-View-Only Recipients</span></span>

  <span data-ttu-id="42b37-363">— Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="42b37-363">-Compliance Management</span></span>

<span data-ttu-id="42b37-364">Дополнительные сведения см в разделе [разрешения в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) и [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="42b37-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="42b37-365">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="42b37-365">Related topics</span></span>

[<span data-ttu-id="42b37-366">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="42b37-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="42b37-367">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="42b37-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
