---
title: Просмотр отчетов о движении почты на панели мониторинга отчетов
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
description: Администраторы могут узнать о отчетах о движении по почте, доступных в панели мониторинга отчетов в центре безопасности & соответствия требованиям.
ms.custom: ''
ms.openlocfilehash: 840b9920fc3f994140702eae0bf5ddbdeac4b465
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357927"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="0ea6d-103">Просмотр отчетов о движении почты в панели мониторинга отчетов в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0ea6d-104">В дополнение к отчетам о почтовых процессах, доступным в [панели мониторинга "почтовый ящик](mail-flow-insights-v2.md) " в центре безопасности & соответствия требованиям, в панели мониторинга отчетов доступны различные дополнительные отчеты о почтовых сообщениях, которые помогут вам отслеживать свою организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="0ea6d-105">Если у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-these-reports), вы можете просмотреть эти отчеты в [центре безопасности & соответствия требованиям](https://office.protection.com) , перейдя на **Reports** \> **панель мониторинга** отчетов.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="0ea6d-106">Чтобы перейти непосредственно к панели мониторинга отчетов, откройте ее <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="0ea6d-108">Отчет о соединителях</span><span class="sxs-lookup"><span data-stu-id="0ea6d-108">Connector report</span></span>

<span data-ttu-id="0ea6d-109">В **отчете о соединителе** отображаются действия потока обработки почты для [входящих и исходящих соединителей](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) , настроенных для Организации.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="0ea6d-110">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите пункт " **отчет о соединителе**".</span><span class="sxs-lookup"><span data-stu-id="0ea6d-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="0ea6d-111">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Мини-приложение "отчет о соединителе" на панели мониторинга отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="0ea6d-113">Представление отчета для соединителя</span><span class="sxs-lookup"><span data-stu-id="0ea6d-113">Report view for the Connector report</span></span>

<span data-ttu-id="0ea6d-114">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="0ea6d-115">**Просмотр данных по: почтовые потоки**: на этой диаграмме показано количество входящих и исходящих сообщений, упорядоченных по следующим адресам:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="0ea6d-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-116">**Total**</span></span>
  - <span data-ttu-id="0ea6d-117">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="0ea6d-118">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="0ea6d-119">Указанный соединитель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="0ea6d-120">Чтобы изолировать данные на диаграмме, используйте параметр **Показать данные для** управления, чтобы выбрать один из этих параметров или **весь процесс обработки почты**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных с помощью почтовых ящиков в отчете о соединителях](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="0ea6d-122">**Просмотр данных по: использование TLS**: на этой диаграмме показан процент использования протокола TLS для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="0ea6d-123">Чтобы изолировать данные на диаграмме, используйте элемент управления **Показать данные для** выбора одного из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="0ea6d-124">**Весь процесс обработки почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-124">**All mail flow**</span></span>
  - <span data-ttu-id="0ea6d-125">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="0ea6d-126">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="0ea6d-127">Указанный соединитель, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-127">A specific connector that you've configured.</span></span>

  ![Просмотр данных по использованию TLS в отчете о соединителях](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="0ea6d-129">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным** датами.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="0ea6d-130">Представление таблицы сведений о соединителе</span><span class="sxs-lookup"><span data-stu-id="0ea6d-130">Details table view for the Connector report</span></span>

<span data-ttu-id="0ea6d-131">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="0ea6d-132">**Дата**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-132">**Date**</span></span>
- <span data-ttu-id="0ea6d-133">**Направление и имя соединителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-133">**Connector direction and name**</span></span>
- <span data-ttu-id="0ea6d-134">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-134">**Connector type**</span></span>
- <span data-ttu-id="0ea6d-135">**Принудительное TLS?**: значение **true** или **false**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="0ea6d-136">**Без TLS** (%)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="0ea6d-137">**TLS 1,0** (%)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="0ea6d-138">**TLS 1,1** (%)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="0ea6d-139">**TLS 1,2** (%)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="0ea6d-140">**Volume**: количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="0ea6d-141">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="0ea6d-142">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="0ea6d-143">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="0ea6d-143">Exchange transport rule report</span></span>

<span data-ttu-id="0ea6d-144">В **отчете о правиле транспорта Exchange** показано, как правила обработки почты (также называемые правилами транспорта) применяются к входящим и исходящим сообщениям в Организации.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="0ea6d-145">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **правило транспорта Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="0ea6d-146">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Мини-приложение правил транспорта Exchange в панели мониторинга отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="0ea6d-148">Представление отчета для отчета о правиле транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="0ea6d-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="0ea6d-149">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="0ea6d-150">**Просмотр данных по: правила** \> транспорта Exchange **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="0ea6d-151">**Просмотр данных по: правила** \> транспорта Exchange **Разбить на: степень серьезности**: на этой диаграмме показано количество сообщений с **высокой степенью серьезности** и **средней** серьезности, а также сообщения о **низком уровне** серьезности.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="0ea6d-152">Уровень серьезности задается как действие в правиле (**аудит этого правила со степенью серьезности** или _сетаудитсеверити_).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="0ea6d-153">Дополнительные сведения см. [в разделе действие правил обработки почты в Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="0ea6d-154">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="0ea6d-155">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="0ea6d-156">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="0ea6d-157">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="0ea6d-158">**Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="0ea6d-159">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: в этом представлении отображается количество **высоких** и **средних** уровней серьезности, а также сообщения о **низком** уровне, на которые влияют правила транспорта DLP.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="0ea6d-160">Вы можете уточнить диаграмму, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="0ea6d-161">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="0ea6d-162">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="0ea6d-163">**Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="0ea6d-164">Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров::</span><span class="sxs-lookup"><span data-stu-id="0ea6d-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="0ea6d-165">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="0ea6d-166">Значения направления</span><span class="sxs-lookup"><span data-stu-id="0ea6d-166">Direction values</span></span>
- <span data-ttu-id="0ea6d-167">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="0ea6d-167">Severity values</span></span>

![Представление отчета в отчете о правиле транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="0ea6d-169">Представление таблицы сведений для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="0ea6d-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="0ea6d-170">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="0ea6d-171">**Просмотр данных по: правила транспорта Exchange**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="0ea6d-172">**Дата**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-172">**Date**</span></span>
  - <span data-ttu-id="0ea6d-173">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-173">**Transport rule**</span></span>
  - <span data-ttu-id="0ea6d-174">**Тема**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-174">**Subject**</span></span>
  - <span data-ttu-id="0ea6d-175">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-175">**Sender address**</span></span>
  - <span data-ttu-id="0ea6d-176">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-176">**Recipient address**</span></span>
  - <span data-ttu-id="0ea6d-177">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-177">**Severity**</span></span>
  - <span data-ttu-id="0ea6d-178">**Направление**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-178">**Direction**</span></span>

- <span data-ttu-id="0ea6d-179">**Просмотр данных по: правила транспорта Exchange для защиты от потери данных**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="0ea6d-180">**Дата**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-180">**Date**</span></span>
  - <span data-ttu-id="0ea6d-181">**Политика защиты от потери данных**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-181">**DLP policy**</span></span>
  - <span data-ttu-id="0ea6d-182">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-182">**Transport rule**</span></span>
  - <span data-ttu-id="0ea6d-183">**Тема**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-183">**Subject**</span></span>
  - <span data-ttu-id="0ea6d-184">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-184">**Sender address**</span></span>
  - <span data-ttu-id="0ea6d-185">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-185">**Recipient address**</span></span>
  - <span data-ttu-id="0ea6d-186">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-186">**Severity**</span></span>
  - <span data-ttu-id="0ea6d-187">**Направление**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-187">**Direction**</span></span>

<span data-ttu-id="0ea6d-188">Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="0ea6d-189">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="0ea6d-190">Значения направления</span><span class="sxs-lookup"><span data-stu-id="0ea6d-190">Direction values</span></span>
- <span data-ttu-id="0ea6d-191">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="0ea6d-191">Severity values</span></span>

<span data-ttu-id="0ea6d-192">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="0ea6d-193">Отчет о переадресации</span><span class="sxs-lookup"><span data-stu-id="0ea6d-193">Forwarding report</span></span>

<span data-ttu-id="0ea6d-194">**Отчет о переадресации** показывает автоматически перенаправляемые сообщения вашей организации на внешние домены из почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="0ea6d-195">Пересылаемые сообщения могут представлять угрозу безопасности или соответствия требованиям и могут указывать на скомпрометированную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="0ea6d-196">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **Пересылка отчета**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="0ea6d-197">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Мини-приложение "пересылка отчетов" на панели мониторинга отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="0ea6d-199">Представление отчета для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="0ea6d-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="0ea6d-200">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="0ea6d-201">**Показать данные для: методы пересылки**: показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="0ea6d-202">**Правило транспорта**: также называется " [правила для поток обработки почты](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)".</span><span class="sxs-lookup"><span data-stu-id="0ea6d-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="0ea6d-203">**Правило почтовых ящиков**: также называются [правилами для папки "Входящие"](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Способы пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="0ea6d-205">**Показать данные для: пересылка доменов**: в этом представлении отображаются домены получателей, которые являются конечными объектами для переадресации.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Просмотр пересылаемых доменов в отчете о перенаправлении](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="0ea6d-207">**Показать данные для: серверы пересылки**: отображаются следующие серверы пересылки:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="0ea6d-208">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-208">**Transport rule**</span></span>
  - <span data-ttu-id="0ea6d-209">Почтовый ящик, который содержит правило пересылки папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="0ea6d-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Представление пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="0ea6d-211">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным** датами.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="0ea6d-212">Представление таблицы сведений для отчета о перенаправлении</span><span class="sxs-lookup"><span data-stu-id="0ea6d-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="0ea6d-213">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="0ea6d-214">**Серверы пересылки**: **правило транспорта** или почтовый ящик, который содержит правило пересылки папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="0ea6d-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="0ea6d-215">**Тип перенаправления**: **правило почтового ящика** значения или **правило транспорта**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="0ea6d-216">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-216">**Recipient name**</span></span>
- <span data-ttu-id="0ea6d-217">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-217">**Recipient domain**</span></span>
- <span data-ttu-id="0ea6d-218">**Details**: это значение GUID почтового процесса или значение рулеидентити правила для папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="0ea6d-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="0ea6d-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-219">**Count**</span></span>
- <span data-ttu-id="0ea6d-220">**Дата первой пересылки**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-220">**First forward date**</span></span>

<span data-ttu-id="0ea6d-221">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="0ea6d-222">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="0ea6d-223">Отчет о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-223">Mailflow status report</span></span>

<span data-ttu-id="0ea6d-224">**Отчет о состоянии Mailflow** похож на отчет о [отправленных и полученных сообщениях электронной почты](#sent-and-received-email-report)с дополнительными сведениями об электронной почте, разрешенной или заблокированной для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="0ea6d-225">Это единственный отчет, содержащий сведения о защите от краев, а также показывает, сколько электронной почты блокируется до того, как она будет разрешена для оценки службой Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="0ea6d-226">Важно понимать, что если сообщение отправлено пяти получателям, оно подсчитано как пять разных сообщений, а не одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="0ea6d-227">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **отчет о состоянии Mailflow**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="0ea6d-228">Чтобы перейти непосредственно к **отчету о состоянии почтового процесса**, откройте <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Мини-приложение "отчет о состоянии Mailflow" на панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ea6d-230">Тип представления для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="0ea6d-231">При открытии отчета по умолчанию выбирается вкладка **тип** .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="0ea6d-232">По умолчанию это представление содержит диаграмму и таблицу данных, настроенную со следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="0ea6d-233">**Дата**: последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="0ea6d-234">**Направление**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-234">**Direction**:</span></span>

  - <span data-ttu-id="0ea6d-235">**Получение**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-235">**Inbound**</span></span>
  - <span data-ttu-id="0ea6d-236">**Прав**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-236">**Outbound**</span></span>
  - <span data-ttu-id="0ea6d-237">**Внутри организации**: Этот счетчик предназначен для сообщений в клиенте, т. е.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="0ea6d-238">Отправитель abc@domain.com отправляет получателю xyz@domain.com (учитывается отдельно от **входящих** и **исходящих**).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="0ea6d-239">**Тип**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-239">**Type**:</span></span>

  - <span data-ttu-id="0ea6d-240">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-240">**Good mail**</span></span>
  - <span data-ttu-id="0ea6d-241">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-241">**Malware**</span></span>
  - <span data-ttu-id="0ea6d-242">**Спам**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-242">**Spam**</span></span>
  - <span data-ttu-id="0ea6d-243">**Защита пограничной системы**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-243">**Edge protection**</span></span>
  - <span data-ttu-id="0ea6d-244">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-244">**Rule messages**</span></span>
  - <span data-ttu-id="0ea6d-245">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-245">**Phishing email**</span></span>

<span data-ttu-id="0ea6d-246">Диаграмма организована по значениям **типов** .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="0ea6d-247">Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="0ea6d-248">Таблица данных содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-248">The data table contains the following information:</span></span>

- <span data-ttu-id="0ea6d-249">**Направление**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-249">**Direction**</span></span>
- <span data-ttu-id="0ea6d-250">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-250">**Type**</span></span>
- <span data-ttu-id="0ea6d-251">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-251">**24 hours**</span></span>
- <span data-ttu-id="0ea6d-252">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-252">**3 days**</span></span>
- <span data-ttu-id="0ea6d-253">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-253">**7 days**</span></span>
- <span data-ttu-id="0ea6d-254">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-254">**15 days**</span></span>
- <span data-ttu-id="0ea6d-255">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-255">**30 days**</span></span>

<span data-ttu-id="0ea6d-256">Если щелкнуть **выбрать категорию для получения дополнительных сведений**, можно выбрать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="0ea6d-257">**Фишинг-сообщение**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="0ea6d-258">**Вредоносные программы в электронной почте**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="0ea6d-259">**Обнаружения нежелательной почты**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="0ea6d-260">**Нежелательная почта с пограничным** сервером: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="0ea6d-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-261">**Export**:</span></span>

<span data-ttu-id="0ea6d-262">Для подробного представления можно экспортировать данные только один день.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="0ea6d-263">Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="0ea6d-264">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ea6d-265">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="0ea6d-266">Введите View в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ea6d-267">Представление "направление" для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="0ea6d-268">При нажатии вкладки **направление** используются те же фильтры по умолчанию из представления **тип** .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="0ea6d-269">Диаграмма организована по значениям **направления** .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="0ea6d-270">Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="0ea6d-271">Используются те же фильтры из представления **типа** .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="0ea6d-272">Таблица данных содержит одну и ту же информацию из представления **типа** .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="0ea6d-273">**Для получения дополнительных сведений выберите категорию** , которая совпадает с представлением " **тип** ".</span><span class="sxs-lookup"><span data-stu-id="0ea6d-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="0ea6d-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-274">**Export**:</span></span>

<span data-ttu-id="0ea6d-275">Для подробного представления можно экспортировать данные только один день.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="0ea6d-276">Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="0ea6d-277">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ea6d-278">Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="0ea6d-279">Представление "направление" в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ea6d-280">Режим воронки для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="0ea6d-281">В представлении **воронки** показано, как функции защиты от угроз электронной почты Майкрософт отфильтровать входящую и исходящую почту в Организации.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="0ea6d-282">Он предоставляет подробные сведения об общем количестве сообщений электронной почты, а также о том, как в этом счетчике влияют настроенные функции защиты от угроз, включая защиту от пограничного сервера, защиту от вредоносных программ, защиту от фишинга, защиту от нежелательной почты и подмены.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="0ea6d-283">Если щелкнуть вкладку **воронка** , то по умолчанию это представление содержит диаграмму и таблицу данных, настроенную со следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="0ea6d-284">**Дата**: последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="0ea6d-285">**Направление**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-285">**Direction**:</span></span>

  - <span data-ttu-id="0ea6d-286">**Получение**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-286">**Inbound**</span></span>
  - <span data-ttu-id="0ea6d-287">**Прав**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-287">**Outbound**</span></span>
  - <span data-ttu-id="0ea6d-288">**Внутри организации**: это количество для сообщений, отправляемых в клиенте; Например, отправитель abc@domain.com отправляется получателю xyz@domain.com (учитывается отдельно от входящих и исходящих).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="0ea6d-289">Сводное представление и таблица данных допускают 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="0ea6d-290">Если нажать кнопку **Фильтр**, вы можете отфильтровать как диаграмму, так и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="0ea6d-291">На этой диаграмме показаны счетчики электронной почты, упорядоченные по:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="0ea6d-292">**Общий адрес электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-292">**Total email**</span></span>
- <span data-ttu-id="0ea6d-293">**Электронная почта после защиты от пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-293">**Email after edge protection**</span></span>
- <span data-ttu-id="0ea6d-294">**Электронная почта после защиты от вредоносных программ, репутации файлов, блока типов файлов**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="0ea6d-295">**Электронная почта после защиты от фишинга, репутации URL-адресов, олицетворения, средства защиты от мошенничества**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="0ea6d-296">**Электронная почта после защиты от нежелательной почты, массовая фильтрация почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="0ea6d-297">**Электронная почта после олицетворения пользователя и домена**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0ea6d-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="0ea6d-298">**Электронная почта после файла и URL-адреса детонации**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0ea6d-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="0ea6d-299">**Сообщение электронной почты было признано неблагоприятным после защиты от повторной доставки (URL-адрес — защита от времени)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="0ea6d-300"><sup>1</sup> защитник для Office 365</span><span class="sxs-lookup"><span data-stu-id="0ea6d-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="0ea6d-301">Для просмотра сообщений электронной почты, отфильтрованных по EOP или защитнику для Office 365, щелкните значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="0ea6d-302">Таблица данных содержит следующие сведения, показанные в порядке убывания дат:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="0ea6d-303">**Дата**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-303">**Date**</span></span>
- <span data-ttu-id="0ea6d-304">**Общий адрес электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-304">**Total email**</span></span>
- <span data-ttu-id="0ea6d-305">**Защита пограничной системы**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-305">**Edge protection**</span></span>
- <span data-ttu-id="0ea6d-306">**Защита от вредоносных программ, репутация файлов, Блокировка типов файлов**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="0ea6d-307">**Репутация файлов**: сообщения, отфильтрованные из-за идентификации вложенного файла другими клиентами корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="0ea6d-308">**Блок типов файлов**: сообщения, отфильтрованные из-за типа вредоносного файла, указанного в сообщении.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="0ea6d-309">**Защита от фишинга, репутации URL-адресов, олицетворения, средства защиты от** незаконного мошенничества.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="0ea6d-310">**Репутация URL-адресов**: сообщения, отфильтрованные из-за идентификации URL-адреса другими клиентами корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="0ea6d-311">**Олицетворение для фирменного стиля**: сообщения, отфильтрованные из-за сообщения, поступающего от хорошо известных фирменных отправителей.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="0ea6d-312">**Защита от спуфинга**: сообщения, отфильтрованные из-за того, что сообщение попыталось подменить домен, к которому принадлежит получатель, или домен, который не владеет отправителем сообщения.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="0ea6d-313">**Фильтрация нежелательной почты, массовая фильтрация почты**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="0ea6d-314">**Массовая фильтрация почты**: сообщения, отфильтрованные из-за попытки доставить массовую почту получателям.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="0ea6d-315">**Олицетворение пользователя и домена (защитник для Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="0ea6d-316">**Олицетворение пользователя**: сообщения, отфильтрованные из-за попытки олицетворения пользователя (отправителя сообщения), определенного в параметрах защиты от олицетворения политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="0ea6d-317">**Олицетворение домена**: сообщения, отфильтрованные из-за попытки олицетворения домена, определенного в параметрах защиты от олицетворения политики защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="0ea6d-318">**Детонации файлов и URL-адресов (защитник для Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="0ea6d-319">**Файл детонации**: сообщения, отфильтрованные политикой безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="0ea6d-320">**URL-адрес детонации**: сообщение, фильтруемое политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="0ea6d-321">**Защита после доставки и ZAP (ATP) или ZAP (EOP)**: ZAP указывает на автоматическую очистку с нулевым часовым значением.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="0ea6d-322">Если выбрать строку в таблице данных, в всплывающем меню будут отображаться дополнительные сведения о счетчиках электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="0ea6d-323">**Export**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-323">**Export**:</span></span>

<span data-ttu-id="0ea6d-324">После нажатия кнопки **Экспорт** в разделе **Параметры** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="0ea6d-325">**Сводка (с данными за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="0ea6d-326">**Сведения (с данными за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="0ea6d-327">В разделе **Дата** выберите диапазон, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="0ea6d-328">Данные для текущих фильтров будут экспортированы в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="0ea6d-329">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ea6d-330">Если данные содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="0ea6d-331">Вид воронки в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ea6d-332">Технический вид для отчета о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="0ea6d-333">**Техническое представление** аналогично представлению **воронки** и предоставляет более детальные сведения о настроенных функциях защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="0ea6d-334">На диаграмме показано, как сообщения классифицируются по разным стадиям защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="0ea6d-335">Если вы настроили вкладку **технического представления** , то по умолчанию это представление содержит диаграмму и таблицу данных, настроенную со следующими фильтрами:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="0ea6d-336">**Дата**: последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="0ea6d-337">**Направление**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-337">**Direction**:</span></span>

  - <span data-ttu-id="0ea6d-338">**Получение**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-338">**Inbound**</span></span>
  - <span data-ttu-id="0ea6d-339">**Прав**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-339">**Outbound**</span></span>
  - <span data-ttu-id="0ea6d-340">**Внутри организации**: Этот счетчик предназначен для сообщений в клиенте, т. е.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="0ea6d-341">Отправитель abc@domain.com отправляет получателю xyz@domain.com (учитывается отдельно от входящих и исходящих).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="0ea6d-342">Сводное представление и таблица данных допускают 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="0ea6d-343">Если нажать кнопку **Фильтр**, вы можете отфильтровать как диаграмму, так и таблицу данных.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="0ea6d-344">На этой диаграмме показаны сообщения, упорядоченные по следующим категориям:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="0ea6d-345">**Общий адрес электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-345">**Total email**</span></span>
- <span data-ttu-id="0ea6d-346">Разрешающая и **пограничная фильтрация** **пограничных серверов**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="0ea6d-347">**Не вредоносные программы**, **Обнаружение безопасных вложений** <sup>\*</sup> , **Обнаружение модуля защиты от вредоносных программ** и **сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="0ea6d-348">**Отказ** от **фишинга**, dMarc, **Обнаружение олицетворения**, **обнаружение подделки** и **Обнаружение фишинга**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="0ea6d-349">**Обнаружение с URL-адресом детонации** и **URL-адресом детонации** не обнаружено <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ea6d-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="0ea6d-350">**Нежелательная почта** и  **Нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="0ea6d-351">**Невредоносные сообщения электронной почты**, **Обнаружение безопасных ссылок** <sup>\*</sup> и **ZAP**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="0ea6d-352"><sup>\*</sup> Защитник для Office 365</span><span class="sxs-lookup"><span data-stu-id="0ea6d-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="0ea6d-353">При наведении указателя мыши на категорию в диаграмме отображается количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="0ea6d-354">Таблица данных содержит следующие сведения, показанные в порядке убывания дат:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="0ea6d-355">**Дата**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-355">**Date**</span></span>
- <span data-ttu-id="0ea6d-356">**Общий адрес электронной почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-356">**Total email**</span></span>
- <span data-ttu-id="0ea6d-357">**Фильтр пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-357">**Edge filtered**</span></span>
- <span data-ttu-id="0ea6d-358">**Механизм защиты от вредоносных программ, безопасные вложения, правило отфильтрованы**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="0ea6d-359">**Правило отфильтровано**: сообщения, отфильтрованные из-за правил обработки почтового процесса (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="0ea6d-360">**DMarc, олицетворение, подделка, фильтрация фишинга**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="0ea6d-361">**DMARC**: сообщения, отфильтрованные из-за сообщения, не прошли проверку подлинности DMARC.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="0ea6d-362">**Обнаружение детонации URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-362">**URL detonation detection**</span></span>
- <span data-ttu-id="0ea6d-363">**Фильтр защиты от нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="0ea6d-364">**Удален ZAP**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-364">**ZAP removed**</span></span>
- <span data-ttu-id="0ea6d-365">**Обнаружение по безопасным связям**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="0ea6d-366">Если выбрать строку в таблице данных, в всплывающем меню будут отображаться дополнительные сведения о счетчиках электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="0ea6d-367">**Export**:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-367">**Export**:</span></span>

<span data-ttu-id="0ea6d-368">При нажатии кнопки **Экспорт** в разделе **Параметры** можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="0ea6d-369">**Сводка (с данными за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="0ea6d-370">**Сведения (с данными за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="0ea6d-371">В разделе **Дата** выберите диапазон, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="0ea6d-372">Данные для текущих фильтров будут экспортированы в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="0ea6d-373">Каждый экспортированный CSV-файл может иметь не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ea6d-374">Если данные содержат более 150 000 строк, будет создано несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="0ea6d-375">Технический вид в отчете о состоянии Mailflow</span><span class="sxs-lookup"><span data-stu-id="0ea6d-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="0ea6d-376">Отчет о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="0ea6d-376">Sent and received email report</span></span>

<span data-ttu-id="0ea6d-377">Отчет о **отправленных и полученных сообщениях** — это интеллектуальный отчет, в котором отображаются сведения о входящих и исходящих сообщениях электронной почты, в том числе об обнаружении нежелательной почты, вредоносных программах и сообщениях электронной почты, определенных</span><span class="sxs-lookup"><span data-stu-id="0ea6d-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="0ea6d-378">Разница между этим отчетом и [отчетом о состоянии Mailflow](#mailflow-status-report) : этот отчет не содержит данные о сообщениях, заблокированных службой защиты от краев. Важно понимать, что если сообщение отправлено пяти получателям, оно подсчитано как одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="0ea6d-379">Сводное представление и подробное представление отчета допускают 90 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="0ea6d-380">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите **Отправленные и полученные сообщения электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="0ea6d-381">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Мини-приложение "Отправленные и полученные сообщения электронной почты" в панели мониторинга отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="0ea6d-383">Представление отчета для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="0ea6d-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="0ea6d-384">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="0ea6d-385">**Разбить на: тип**: на диаграмме отображаются все доступные категории:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="0ea6d-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-386">**Total**</span></span>
  - <span data-ttu-id="0ea6d-387">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-387">**Good mail**</span></span>
  - <span data-ttu-id="0ea6d-388">**Вредоносные программы (защита от вредоносных программ)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="0ea6d-389">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-389">**Spam detections**</span></span>
  - <span data-ttu-id="0ea6d-390">**Сообщения правил**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-390">**Rule messages**</span></span>
  - <span data-ttu-id="0ea6d-391">**Расширенное вредоносное** по (защитник Майкрософт для Office 365)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="0ea6d-392">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Введите View в отчет о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="0ea6d-394">**Разбейте на: направление**: на диаграмме показаны **Общие**, **Входящие** и **Исходящие** данные.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="0ea6d-395">Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление "направление" в отчете о отправленных и полученных сообщениях](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="0ea6d-397">**Детализация по** \> **Вредоносные программы (защита от вредоносных программ)**: при выборе этого параметра осуществляется [Поиск вредоносных программ в отчете по электронной почте](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="0ea6d-398">**Детализация по** \> **Обнаружения нежелательной почты)**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="0ea6d-399">Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="0ea6d-400">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="0ea6d-401">Значения направления</span><span class="sxs-lookup"><span data-stu-id="0ea6d-401">Direction values</span></span>
- <span data-ttu-id="0ea6d-402">Значения типов</span><span class="sxs-lookup"><span data-stu-id="0ea6d-402">Type values</span></span>

<span data-ttu-id="0ea6d-403">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="0ea6d-404">Представление таблицы сведений для отчета о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="0ea6d-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="0ea6d-405">Если вы нажимайте кнопку **Просмотреть таблицу сведений** в разделе " **разделить вниз: направление** или" **разбивка на:** представление "направление", отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="0ea6d-406">**Дата (UTC)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-406">**Date (UTC)**</span></span>
- <span data-ttu-id="0ea6d-407">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-407">**Type**</span></span>
- <span data-ttu-id="0ea6d-408">**Направление**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-408">**Direction**</span></span>
- <span data-ttu-id="0ea6d-409">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-409">**Message count**</span></span>

<span data-ttu-id="0ea6d-410">Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="0ea6d-411">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="0ea6d-412">Значения направления</span><span class="sxs-lookup"><span data-stu-id="0ea6d-412">Direction values</span></span>
- <span data-ttu-id="0ea6d-413">Значения типов</span><span class="sxs-lookup"><span data-stu-id="0ea6d-413">Type values</span></span>

<span data-ttu-id="0ea6d-414">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="0ea6d-415">Отчет по основным отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-415">Top senders and recipients report</span></span>

<span data-ttu-id="0ea6d-416">Отчет по **основным отправителям и получателям** — это круговая диаграмма, в которой показаны лучшие отправители и получатели сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="0ea6d-417">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **наиболее отправители и получатели**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="0ea6d-418">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="0ea6d-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Мини-приложение "лучшие отправители и получатели" в панели мониторинга отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="0ea6d-420">Представление отчета для отчета по верхним отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="0ea6d-421">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="0ea6d-422">**Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="0ea6d-423">**Отображение данных для \> наиболее популярных получателей почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="0ea6d-424">**Отображение данных для \> самых популярных нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="0ea6d-425">**Показать данные для \> Первые получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="0ea6d-426">**Отображение данных для \> получателей самых популярных вредоносных программ (защитник для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="0ea6d-427">Структура круговой диаграммы изменяется в зависимости от выбранных вариантов.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="0ea6d-428">При наведении указателя на сектор на круговой диаграмме можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="0ea6d-429">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным** датами.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Круговая диаграмма в представлении отчета в отчете по верхним отправителям и получателям](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="0ea6d-431">Представление таблицы "сведения" для отчета по верхним отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="0ea6d-432">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="0ea6d-433">**Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="0ea6d-434">**Сообщения верхнего уровня**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-434">**Top mail senders**</span></span>
  - <span data-ttu-id="0ea6d-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-435">**Count**</span></span>

- <span data-ttu-id="0ea6d-436">**Отображение данных для \> наиболее популярных получателей почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="0ea6d-437">**Самые популярные Получатели почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="0ea6d-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-438">**Count**</span></span>

- <span data-ttu-id="0ea6d-439">**Отображение данных для \> самых популярных нежелательных получателей**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="0ea6d-440">**Самые распространенные получатели нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="0ea6d-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-441">**Count**</span></span>

- <span data-ttu-id="0ea6d-442">**Показать данные для \> Первые получатели вредоносных программ** (EOP)</span><span class="sxs-lookup"><span data-stu-id="0ea6d-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="0ea6d-443">**Самые популярные получатели вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="0ea6d-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-444">**Count**</span></span>

- <span data-ttu-id="0ea6d-445">**Отображение данных для \> получателей самых популярных вредоносных программ (защитник для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="0ea6d-446">**Самые популярные получатели вредоносных программ (защитник для Office 365)**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="0ea6d-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="0ea6d-447">**Count**</span></span>

<span data-ttu-id="0ea6d-448">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="0ea6d-449">Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="0ea6d-450">Какие разрешения необходимы для просмотра отчетов?</span><span class="sxs-lookup"><span data-stu-id="0ea6d-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="0ea6d-451">Для просмотра и использования отчетов необходимо быть членом указанной группы ролей в центре безопасности & соответствия требованиям **и** в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0ea6d-451">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="0ea6d-452">В центре безопасности & соответствия требованиям необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-452">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="0ea6d-453">-Управление организацией — администратор безопасности (это можно также сделать в [центре администрирования Azure Active Directory](https://aad.portal.azure.com) — средство чтения безопасности</span><span class="sxs-lookup"><span data-stu-id="0ea6d-453">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="0ea6d-454">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-454">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0ea6d-455">В Exchange Online необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="0ea6d-455">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="0ea6d-456">— Управление организацией — Управление организацией только для просмотра — "только просмотр получателей" — Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-456">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="0ea6d-457">Дополнительные сведения см в разделе [разрешения в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) и [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="0ea6d-457">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ea6d-458">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0ea6d-458">Related topics</span></span>

[<span data-ttu-id="0ea6d-459">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-459">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="0ea6d-460">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-460">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="0ea6d-461">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0ea6d-461">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="0ea6d-462">Просмотр отчетов для защитника Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="0ea6d-462">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
