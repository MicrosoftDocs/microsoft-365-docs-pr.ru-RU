---
title: Просмотр отчетов о движении почты на панели мониторинга отчетов
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
description: Администраторы могут узнать о отчетах о движении по почте, доступных в панели мониторинга отчетов в центре безопасности & соответствия требованиям.
ms.custom: ''
ms.openlocfilehash: acf74136fc61d38ea9aac47f36d96aa51a7b9905
ms.sourcegitcommit: 6319e73b3690b4cf1b7932f2b9f51c2c99e70eaa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "46635038"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="cbf10-103">Просмотр отчетов о движении почты в панели мониторинга отчетов в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cbf10-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="cbf10-104">В дополнение к отчетам о почтовых процессах, доступным в [панели мониторинга "почтовый ящик](mail-flow-insights-v2.md) " в центре безопасности & соответствия требованиям, в панели мониторинга отчетов доступны различные дополнительные отчеты о почтовых сообщениях, которые помогут вам отслеживать свою организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cbf10-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="cbf10-105">Если у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-these-reports), вы можете просмотреть эти отчеты в [центре безопасности & соответствия требованиям](https://office.protection.com) , перейдя на **Reports** \> **панель мониторинга**отчетов.</span><span class="sxs-lookup"><span data-stu-id="cbf10-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="cbf10-106">Чтобы перейти непосредственно к панели мониторинга отчетов, откройте ее <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="cbf10-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="cbf10-108">Отчет о соединителях</span><span class="sxs-lookup"><span data-stu-id="cbf10-108">Connector report</span></span>

<span data-ttu-id="cbf10-109">В **отчете о соединителе** отображаются действия потока обработки почты для [входящих и исходящих соединителей](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) , настроенных для Организации.</span><span class="sxs-lookup"><span data-stu-id="cbf10-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="cbf10-110">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите пункт " **отчет о соединителе**".</span><span class="sxs-lookup"><span data-stu-id="cbf10-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="cbf10-111">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="cbf10-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Мини-приложение "отчет о соединителе" на панели мониторинга отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="cbf10-113">Представление отчета для соединителя</span><span class="sxs-lookup"><span data-stu-id="cbf10-113">Report view for the Connector report</span></span>

<span data-ttu-id="cbf10-114">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="cbf10-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="cbf10-115">**Просмотр данных по: почтовые потоки**: на этой диаграмме показано количество входящих и исходящих сообщений, упорядоченных по следующим адресам:</span><span class="sxs-lookup"><span data-stu-id="cbf10-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="cbf10-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="cbf10-116">**Total**</span></span>
  - <span data-ttu-id="cbf10-117">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="cbf10-118">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="cbf10-119">Указанный соединитель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="cbf10-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="cbf10-120">Чтобы изолировать данные на диаграмме, используйте параметр **Показать данные для** управления, чтобы выбрать один из этих параметров или **весь процесс обработки почты**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных с помощью почтовых ящиков в отчете о соединителях](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="cbf10-122">**Просмотр данных по: использование TLS**: на этой диаграмме показан процент использования протокола TLS для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="cbf10-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="cbf10-123">Чтобы изолировать данные на диаграмме, используйте элемент управления **Показать данные для** выбора одного из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="cbf10-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="cbf10-124">**Весь процесс обработки почты**</span><span class="sxs-lookup"><span data-stu-id="cbf10-124">**All mail flow**</span></span>
  - <span data-ttu-id="cbf10-125">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="cbf10-126">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="cbf10-127">Указанный соединитель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="cbf10-127">A specific connector that you've configured.</span></span>

  ![Просмотр данных по использованию TLS в отчете о соединителях](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="cbf10-129">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="cbf10-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="cbf10-130">Представление таблицы сведений о соединителе</span><span class="sxs-lookup"><span data-stu-id="cbf10-130">Details table view for the Connector report</span></span>

<span data-ttu-id="cbf10-131">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="cbf10-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="cbf10-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="cbf10-132">**Date**</span></span>
- <span data-ttu-id="cbf10-133">**Направление и имя соединителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-133">**Connector direction and name**</span></span>
- <span data-ttu-id="cbf10-134">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-134">**Connector type**</span></span>
- <span data-ttu-id="cbf10-135">**Принудительное TLS?**: значение **true** или **false**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="cbf10-136">**Без TLS** (%)</span><span class="sxs-lookup"><span data-stu-id="cbf10-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="cbf10-137">**TLS 1,0** (%)</span><span class="sxs-lookup"><span data-stu-id="cbf10-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="cbf10-138">**TLS 1,1** (%)</span><span class="sxs-lookup"><span data-stu-id="cbf10-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="cbf10-139">**TLS 1,2** (%)</span><span class="sxs-lookup"><span data-stu-id="cbf10-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="cbf10-140">**Volume**: количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="cbf10-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="cbf10-141">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cbf10-142">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="cbf10-143">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="cbf10-143">Exchange transport rule report</span></span>

<span data-ttu-id="cbf10-144">В **отчете о правиле транспорта Exchange** показано, как правила обработки почты (также называемые правилами транспорта) применяются к входящим и исходящим сообщениям в Организации.</span><span class="sxs-lookup"><span data-stu-id="cbf10-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="cbf10-145">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **правило транспорта Exchange**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="cbf10-146">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="cbf10-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Мини-приложение правил транспорта Exchange в панели мониторинга отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="cbf10-148">Представление отчета для отчета о правиле транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="cbf10-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="cbf10-149">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="cbf10-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="cbf10-150">**Просмотр данных по: правила** \> транспорта Exchange **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта.</span><span class="sxs-lookup"><span data-stu-id="cbf10-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="cbf10-151">**Просмотр данных по: правила** \> транспорта Exchange **Разбить на: степень серьезности**: на этой диаграмме показано количество сообщений с **высокой степенью серьезности** и **средней**серьезности, а также сообщения о **низком уровне** серьезности.</span><span class="sxs-lookup"><span data-stu-id="cbf10-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="cbf10-152">Уровень серьезности задается как действие в правиле (**аудит этого правила со степенью серьезности** или _сетаудитсеверити_).</span><span class="sxs-lookup"><span data-stu-id="cbf10-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="cbf10-153">Дополнительные сведения см. [в разделе действие правил обработки почты в Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="cbf10-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="cbf10-154">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="cbf10-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="cbf10-155">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="cbf10-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="cbf10-156">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="cbf10-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="cbf10-157">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="cbf10-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="cbf10-158">**Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**</span><span class="sxs-lookup"><span data-stu-id="cbf10-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="cbf10-159">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: в этом представлении отображается количество **высоких** и **средних**уровней серьезности, а также сообщения о **низком** уровне, на которые влияют правила транспорта DLP.</span><span class="sxs-lookup"><span data-stu-id="cbf10-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="cbf10-160">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="cbf10-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="cbf10-161">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="cbf10-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="cbf10-162">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="cbf10-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="cbf10-163">**Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**</span><span class="sxs-lookup"><span data-stu-id="cbf10-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="cbf10-164">Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров::</span><span class="sxs-lookup"><span data-stu-id="cbf10-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="cbf10-165">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="cbf10-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="cbf10-166">Значения направления</span><span class="sxs-lookup"><span data-stu-id="cbf10-166">Direction values</span></span>
- <span data-ttu-id="cbf10-167">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="cbf10-167">Severity values</span></span>

![Представление отчета в отчете о правиле транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="cbf10-169">Представление таблицы сведений для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="cbf10-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="cbf10-170">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="cbf10-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cbf10-171">**Просмотр данных по: правила транспорта Exchange**:</span><span class="sxs-lookup"><span data-stu-id="cbf10-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="cbf10-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="cbf10-172">**Date**</span></span>
  - <span data-ttu-id="cbf10-173">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="cbf10-173">**Transport rule**</span></span>
  - <span data-ttu-id="cbf10-174">**Тема**</span><span class="sxs-lookup"><span data-stu-id="cbf10-174">**Subject**</span></span>
  - <span data-ttu-id="cbf10-175">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-175">**Sender address**</span></span>
  - <span data-ttu-id="cbf10-176">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-176">**Recipient address**</span></span>
  - <span data-ttu-id="cbf10-177">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="cbf10-177">**Severity**</span></span>
  - <span data-ttu-id="cbf10-178">**Направление**</span><span class="sxs-lookup"><span data-stu-id="cbf10-178">**Direction**</span></span>

- <span data-ttu-id="cbf10-179">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных**:</span><span class="sxs-lookup"><span data-stu-id="cbf10-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="cbf10-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="cbf10-180">**Date**</span></span>
  - <span data-ttu-id="cbf10-181">**Политика защиты от потери данных**</span><span class="sxs-lookup"><span data-stu-id="cbf10-181">**DLP policy**</span></span>
  - <span data-ttu-id="cbf10-182">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="cbf10-182">**Transport rule**</span></span>
  - <span data-ttu-id="cbf10-183">**Тема**</span><span class="sxs-lookup"><span data-stu-id="cbf10-183">**Subject**</span></span>
  - <span data-ttu-id="cbf10-184">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-184">**Sender address**</span></span>
  - <span data-ttu-id="cbf10-185">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-185">**Recipient address**</span></span>
  - <span data-ttu-id="cbf10-186">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="cbf10-186">**Severity**</span></span>
  - <span data-ttu-id="cbf10-187">**Направление**</span><span class="sxs-lookup"><span data-stu-id="cbf10-187">**Direction**</span></span>

<span data-ttu-id="cbf10-188">Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="cbf10-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cbf10-189">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="cbf10-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="cbf10-190">Значения направления</span><span class="sxs-lookup"><span data-stu-id="cbf10-190">Direction values</span></span>
- <span data-ttu-id="cbf10-191">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="cbf10-191">Severity values</span></span>

<span data-ttu-id="cbf10-192">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="cbf10-193">Отчет о переадресации</span><span class="sxs-lookup"><span data-stu-id="cbf10-193">Forwarding report</span></span>

<span data-ttu-id="cbf10-194">**Отчет о переадресации** показывает автоматически перенаправляемые сообщения вашей организации на внешние домены из почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cbf10-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="cbf10-195">Пересылаемые сообщения могут представлять угрозу безопасности или соответствия требованиям и могут указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="cbf10-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="cbf10-196">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **Пересылка отчета**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="cbf10-197">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="cbf10-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Мини-приложение "пересылка отчетов" на панели мониторинга отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="cbf10-199">Представление отчета для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="cbf10-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="cbf10-200">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="cbf10-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cbf10-201">**Показать данные для: методы пересылки**: показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="cbf10-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="cbf10-202">**Правило транспорта**: также называется " [правила для поток обработки почты](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)".</span><span class="sxs-lookup"><span data-stu-id="cbf10-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="cbf10-203">**Правило почтовых ящиков**: также называются [правилами для папки "Входящие"](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="cbf10-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Способы пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="cbf10-205">**Показать данные для: пересылка доменов**: в этом представлении отображаются домены получателей, которые являются конечными объектами для переадресации.</span><span class="sxs-lookup"><span data-stu-id="cbf10-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Просмотр пересылаемых доменов в отчете о перенаправлении](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="cbf10-207">**Показать данные для: серверы пересылки**: отображаются следующие серверы пересылки:</span><span class="sxs-lookup"><span data-stu-id="cbf10-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="cbf10-208">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="cbf10-208">**Transport rule**</span></span>
  - <span data-ttu-id="cbf10-209">Почтовый ящик, который содержит правило пересылки папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="cbf10-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Представление пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="cbf10-211">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="cbf10-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="cbf10-212">Представление таблицы сведений для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="cbf10-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="cbf10-213">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="cbf10-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="cbf10-214">**Серверы пересылки**: **правило транспорта** или почтовый ящик, который содержит правило пересылки папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="cbf10-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="cbf10-215">**Тип перенаправления**: **правило почтового ящика** значения или **правило транспорта**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="cbf10-216">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="cbf10-216">**Recipient name**</span></span>
- <span data-ttu-id="cbf10-217">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="cbf10-217">**Recipient domain**</span></span>
- <span data-ttu-id="cbf10-218">**Details**: это значение GUID почтового процесса или значение рулеидентити правила для папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="cbf10-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="cbf10-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="cbf10-219">**Count**</span></span>
- <span data-ttu-id="cbf10-220">**Дата первой пересылки**</span><span class="sxs-lookup"><span data-stu-id="cbf10-220">**First forward date**</span></span>

<span data-ttu-id="cbf10-221">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cbf10-222">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="cbf10-223">Отчет о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="cbf10-223">Mailflow status report</span></span>

<span data-ttu-id="cbf10-224">**Отчет о состоянии Mailflow** похож на отчет о [отправленных и полученных сообщениях электронной почты](#sent-and-received-email-report)с дополнительными сведениями об электронной почте, разрешенной или заблокированной для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="cbf10-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="cbf10-225">Это единственный отчет, содержащий сведения о защите от краев, а также показывает, сколько электронной почты блокируется до того, как она будет разрешена для оценки службой Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="cbf10-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="cbf10-226">Важно понимать, что если сообщение отправлено пяти получателям, оно подсчитано как пять разных сообщений, а не одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="cbf10-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>  
<span data-ttu-id="cbf10-227">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **отчет о состоянии Mailflow**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="cbf10-228">Чтобы перейти непосредственно к **отчету о состоянии почтового процесса**, откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="cbf10-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Мини-приложение "отчет о состоянии Mailflow" на панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="cbf10-230">Тип представления для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="cbf10-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="cbf10-231">При открытии отчета по умолчанию выбирается вкладка **тип** .</span><span class="sxs-lookup"><span data-stu-id="cbf10-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="cbf10-232">По умолчанию это представление содержит диаграмму и таблицу данных, настроенную со следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="cbf10-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="cbf10-233">**Дата**: последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="cbf10-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="cbf10-234">**Направление**:</span><span class="sxs-lookup"><span data-stu-id="cbf10-234">**Direction**:</span></span>

  - <span data-ttu-id="cbf10-235">**Получение**</span><span class="sxs-lookup"><span data-stu-id="cbf10-235">**Inbound**</span></span>
  - <span data-ttu-id="cbf10-236">**Прав**</span><span class="sxs-lookup"><span data-stu-id="cbf10-236">**Outbound**</span></span>
  - <span data-ttu-id="cbf10-237">**Внутри организации**: Этот счетчик предназначен для сообщений в клиенте, т. е.</span><span class="sxs-lookup"><span data-stu-id="cbf10-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="cbf10-238">Отправитель abc@domain.com отправляет получателю xyz@domain.com (учитывается отдельно от **входящих** и **исходящих**).</span><span class="sxs-lookup"><span data-stu-id="cbf10-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="cbf10-239">**Тип**:</span><span class="sxs-lookup"><span data-stu-id="cbf10-239">**Type**:</span></span>

  - <span data-ttu-id="cbf10-240">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="cbf10-240">**Good mail**</span></span>
  - <span data-ttu-id="cbf10-241">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="cbf10-241">**Malware**</span></span>
  - <span data-ttu-id="cbf10-242">**Спам**</span><span class="sxs-lookup"><span data-stu-id="cbf10-242">**Spam**</span></span>
  - <span data-ttu-id="cbf10-243">**Защита пограничной системы**</span><span class="sxs-lookup"><span data-stu-id="cbf10-243">**Edge protection**</span></span>
  - <span data-ttu-id="cbf10-244">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="cbf10-244">**Rule messages**</span></span>
  - <span data-ttu-id="cbf10-245">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="cbf10-245">**Phishing email**</span></span>

<span data-ttu-id="cbf10-246">Диаграмма организована по значениям **типов** .</span><span class="sxs-lookup"><span data-stu-id="cbf10-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="cbf10-247">Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="cbf10-247">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="cbf10-248">Таблица данных содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="cbf10-248">The data table contains the following information:</span></span>

- <span data-ttu-id="cbf10-249">**Направление**</span><span class="sxs-lookup"><span data-stu-id="cbf10-249">**Direction**</span></span>
- <span data-ttu-id="cbf10-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="cbf10-250">**Type**</span></span>
- <span data-ttu-id="cbf10-251">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="cbf10-251">**24 hours**</span></span>
- <span data-ttu-id="cbf10-252">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="cbf10-252">**3 days**</span></span>
- <span data-ttu-id="cbf10-253">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="cbf10-253">**7 days**</span></span>
- <span data-ttu-id="cbf10-254">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="cbf10-254">**15 days**</span></span>
- <span data-ttu-id="cbf10-255">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="cbf10-255">**30 days**</span></span>

<span data-ttu-id="cbf10-256">Если щелкнуть **выбрать категорию для получения дополнительных сведений**, можно выбрать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="cbf10-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="cbf10-257">**Фишинг-сообщение**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="cbf10-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="cbf10-258">**Вредоносные программы в электронной почте**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="cbf10-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="cbf10-259">**Обнаружения нежелательной почты**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="cbf10-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="cbf10-260">**Нежелательная почта с пограничным**сервером: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="cbf10-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="cbf10-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="cbf10-261">**Export**:</span></span>

<span data-ttu-id="cbf10-262">Для подробного представления можно экспортировать данные только один день.</span><span class="sxs-lookup"><span data-stu-id="cbf10-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="cbf10-263">Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="cbf10-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="cbf10-264">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="cbf10-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="cbf10-265">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="cbf10-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="cbf10-266">Введите View в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="cbf10-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="cbf10-267">Представление "направление" для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="cbf10-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="cbf10-268">При нажатии вкладки **направление** используются те же фильтры по умолчанию из представления **тип** .</span><span class="sxs-lookup"><span data-stu-id="cbf10-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="cbf10-269">Диаграмма организована по значениям **направления** .</span><span class="sxs-lookup"><span data-stu-id="cbf10-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="cbf10-270">Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="cbf10-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="cbf10-271">Используются те же фильтры из представления **типа** .</span><span class="sxs-lookup"><span data-stu-id="cbf10-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="cbf10-272">Таблица данных содержит одну и ту же информацию из представления **типа** .</span><span class="sxs-lookup"><span data-stu-id="cbf10-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="cbf10-273">**Для получения дополнительных сведений выберите категорию** , которая совпадает с представлением " **тип** ".</span><span class="sxs-lookup"><span data-stu-id="cbf10-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="cbf10-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="cbf10-274">**Export**:</span></span>

<span data-ttu-id="cbf10-275">Для подробного представления можно экспортировать данные только один день.</span><span class="sxs-lookup"><span data-stu-id="cbf10-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="cbf10-276">Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="cbf10-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="cbf10-277">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="cbf10-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="cbf10-278">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="cbf10-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="cbf10-279">Представление "направление" в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="cbf10-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="cbf10-280">Отчет о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="cbf10-280">Sent and received email report</span></span>

<span data-ttu-id="cbf10-281">Отчет о **отправленных и полученных сообщениях** — это интеллектуальный отчет, в котором отображаются сведения о входящих и исходящих сообщениях электронной почты, в том числе об обнаружении нежелательной почты, вредоносных программах и сообщениях электронной почты, определенных</span><span class="sxs-lookup"><span data-stu-id="cbf10-281">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="cbf10-282">Разница между этим отчетом и [отчетом о состоянии Mailflow](#mailflow-status-report) : этот отчет не содержит данные о сообщениях, заблокированных службой защиты от краев.</span><span class="sxs-lookup"><span data-stu-id="cbf10-282">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="cbf10-283">Сводное представление и подробное представление отчета допускают 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="cbf10-283">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="cbf10-284">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите **Отправленные и полученные сообщения электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-284">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="cbf10-285">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="cbf10-285">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Мини-приложение "Отправленные и полученные сообщения электронной почты" в панели мониторинга отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="cbf10-287">Представление отчета для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="cbf10-287">Report view for the Sent and received email report</span></span>

<span data-ttu-id="cbf10-288">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="cbf10-288">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cbf10-289">**Разбить на: тип**: на диаграмме отображаются все доступные категории:</span><span class="sxs-lookup"><span data-stu-id="cbf10-289">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="cbf10-290">**Total**</span><span class="sxs-lookup"><span data-stu-id="cbf10-290">**Total**</span></span>
  - <span data-ttu-id="cbf10-291">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="cbf10-291">**Good mail**</span></span>
  - <span data-ttu-id="cbf10-292">**Вредоносные программы (защита от вредоносных программ)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="cbf10-292">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="cbf10-293">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="cbf10-293">**Spam detections**</span></span>
  - <span data-ttu-id="cbf10-294">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="cbf10-294">**Rule messages**</span></span>
  - <span data-ttu-id="cbf10-295">**Расширенная вредоносная программа** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="cbf10-295">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="cbf10-296">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.</span><span class="sxs-lookup"><span data-stu-id="cbf10-296">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Введите View в отчет о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="cbf10-298">**Разбейте на: направление**: на диаграмме показаны **Общие**, **Входящие**и **Исходящие** данные.</span><span class="sxs-lookup"><span data-stu-id="cbf10-298">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="cbf10-299">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.</span><span class="sxs-lookup"><span data-stu-id="cbf10-299">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление "направление" в отчете о отправленных и полученных сообщениях](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="cbf10-301">**Детализация по** \> **Вредоносные программы (защита от вредоносных программ)**: при выборе этого параметра осуществляется [Поиск вредоносных программ в отчете по электронной почте](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="cbf10-301">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="cbf10-302">**Детализация по** \> **Обнаружения нежелательной почты)**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="cbf10-302">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="cbf10-303">Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="cbf10-303">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cbf10-304">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="cbf10-304">**Start date** and **End date**</span></span>
- <span data-ttu-id="cbf10-305">Значения направления</span><span class="sxs-lookup"><span data-stu-id="cbf10-305">Direction values</span></span>
- <span data-ttu-id="cbf10-306">Значения типов</span><span class="sxs-lookup"><span data-stu-id="cbf10-306">Type values</span></span>

<span data-ttu-id="cbf10-307">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-307">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="cbf10-308">Представление таблицы сведений для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="cbf10-308">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="cbf10-309">Если вы нажимайте кнопку **Просмотреть таблицу сведений** в разделе " **разделить вниз: направление** или" **разбивка на:** представление "направление", отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="cbf10-309">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="cbf10-310">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="cbf10-310">**Date (UTC)**</span></span>
- <span data-ttu-id="cbf10-311">**Type**</span><span class="sxs-lookup"><span data-stu-id="cbf10-311">**Type**</span></span>
- <span data-ttu-id="cbf10-312">**Направление**</span><span class="sxs-lookup"><span data-stu-id="cbf10-312">**Direction**</span></span>
- <span data-ttu-id="cbf10-313">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="cbf10-313">**Message count**</span></span>

<span data-ttu-id="cbf10-314">Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="cbf10-314">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cbf10-315">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="cbf10-315">**Start date** and **End date**</span></span>
- <span data-ttu-id="cbf10-316">Значения направления</span><span class="sxs-lookup"><span data-stu-id="cbf10-316">Direction values</span></span>
- <span data-ttu-id="cbf10-317">Значения типов</span><span class="sxs-lookup"><span data-stu-id="cbf10-317">Type values</span></span>

<span data-ttu-id="cbf10-318">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-318">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="cbf10-319">Отчет по основным отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="cbf10-319">Top senders and recipients report</span></span>

<span data-ttu-id="cbf10-320">Отчет по **основным отправителям и получателям** — это круговая диаграмма, в которой показаны лучшие отправители и получатели сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cbf10-320">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="cbf10-321">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **наиболее отправители и получатели**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-321">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="cbf10-322">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="cbf10-322">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Мини-приложение "лучшие отправители и получатели" в панели мониторинга отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="cbf10-324">Представление отчета для отчета по верхним отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="cbf10-324">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="cbf10-325">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="cbf10-325">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cbf10-326">**Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**</span><span class="sxs-lookup"><span data-stu-id="cbf10-326">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="cbf10-327">**Отображение данных для \> наиболее популярных получателей почты**</span><span class="sxs-lookup"><span data-stu-id="cbf10-327">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="cbf10-328">**Отображение данных для \> самых популярных нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="cbf10-328">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="cbf10-329">**Показать данные для \> Первые получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="cbf10-329">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="cbf10-330">**Показать данные для \> Первые получатели вредоносных программ (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="cbf10-330">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="cbf10-331">Структура круговой диаграммы изменяется в зависимости от выбранных вариантов.</span><span class="sxs-lookup"><span data-stu-id="cbf10-331">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="cbf10-332">При наведении указателя на сектор на круговой диаграмме можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="cbf10-332">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="cbf10-333">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="cbf10-333">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Круговая диаграмма в представлении отчета в отчете по верхним отправителям и получателям](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="cbf10-335">Представление таблицы "сведения" для отчета по верхним отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="cbf10-335">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="cbf10-336">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="cbf10-336">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cbf10-337">**Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**</span><span class="sxs-lookup"><span data-stu-id="cbf10-337">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="cbf10-338">**Сообщения верхнего уровня**</span><span class="sxs-lookup"><span data-stu-id="cbf10-338">**Top mail senders**</span></span>
  - <span data-ttu-id="cbf10-339">**Count**</span><span class="sxs-lookup"><span data-stu-id="cbf10-339">**Count**</span></span>

- <span data-ttu-id="cbf10-340">**Отображение данных для \> наиболее популярных получателей почты**</span><span class="sxs-lookup"><span data-stu-id="cbf10-340">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="cbf10-341">**Самые популярные Получатели почты**</span><span class="sxs-lookup"><span data-stu-id="cbf10-341">**Top mail recipients**</span></span>
  - <span data-ttu-id="cbf10-342">**Count**</span><span class="sxs-lookup"><span data-stu-id="cbf10-342">**Count**</span></span>

- <span data-ttu-id="cbf10-343">**Отображение данных для \> самых популярных нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="cbf10-343">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="cbf10-344">**Самые распространенные получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="cbf10-344">**Top spam recipients**</span></span>
  - <span data-ttu-id="cbf10-345">**Count**</span><span class="sxs-lookup"><span data-stu-id="cbf10-345">**Count**</span></span>

- <span data-ttu-id="cbf10-346">**Показать данные для \> Первые получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="cbf10-346">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="cbf10-347">**Самые популярные получатели вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="cbf10-347">**Top malware recipients**</span></span>
  - <span data-ttu-id="cbf10-348">**Count**</span><span class="sxs-lookup"><span data-stu-id="cbf10-348">**Count**</span></span>

- <span data-ttu-id="cbf10-349">**Показать данные для \> Первые получатели вредоносных программ (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="cbf10-349">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="cbf10-350">**Первые получатели вредоносных программ (ATP)**</span><span class="sxs-lookup"><span data-stu-id="cbf10-350">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="cbf10-351">**Count**</span><span class="sxs-lookup"><span data-stu-id="cbf10-351">**Count**</span></span>

<span data-ttu-id="cbf10-352">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-352">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cbf10-353">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="cbf10-353">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="cbf10-354">Какие разрешения необходимы для просмотра отчетов?</span><span class="sxs-lookup"><span data-stu-id="cbf10-354">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="cbf10-355">Для просмотра и использования отчетов необходимо быть членом указанной группы ролей в центре безопасности & соответствия требованиям **и** в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cbf10-355">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="cbf10-356">В центре безопасности & соответствия требованиям необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="cbf10-356">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="cbf10-357">-Управление организацией — администратор безопасности (это можно также сделать в [центре администрирования Azure Active Directory](https://aad.portal.azure.com) — средство чтения безопасности</span><span class="sxs-lookup"><span data-stu-id="cbf10-357">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="cbf10-358">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="cbf10-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="cbf10-359">В Exchange Online необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="cbf10-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="cbf10-360">— Управление организацией — Управление организацией только для просмотра — "только просмотр получателей" — Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="cbf10-360">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="cbf10-361">Дополнительные сведения см в разделе [разрешения в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) и [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="cbf10-361">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cbf10-362">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cbf10-362">Related topics</span></span>

[<span data-ttu-id="cbf10-363">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cbf10-363">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="cbf10-364">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cbf10-364">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="cbf10-365">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cbf10-365">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="cbf10-366">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="cbf10-366">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
