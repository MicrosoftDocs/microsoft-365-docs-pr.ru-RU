---
title: Просмотр отчетов потока обработки почты на панели мониторинга "Отчеты"
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
description: Администраторы могут изучить отчеты потока обработки почты, доступные на панели мониторинга "Отчеты" в Центре безопасности & соответствия требованиям.
ms.custom: ''
ms.openlocfilehash: 9e9249eab5d3519dac0e33acf40d600d471b7cb2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826461"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="caea4-103">Просмотр отчетов потока обработки почты на панели мониторинга "Отчеты" в Центре безопасности & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="caea4-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="caea4-104">Кроме отчетов потока обработки почты, доступных на панели [мониторинга потока](mail-flow-insights-v2.md) обработки почты в Центре соответствия требованиям безопасности &, на панели мониторинга "Отчеты" доступно несколько дополнительных отчетов потока обработки почты, которые помогут вам отслеживать организацию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="caea4-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="caea4-105">Если у вас есть [необходимые разрешения, вы](#what-permissions-are-needed-to-view-these-reports)можете просматривать эти отчеты в [Центре безопасности & соответствия требованиям,](https://office.protection.com) перейдя в панель мониторинга **Reports** \> **отчетов.**</span><span class="sxs-lookup"><span data-stu-id="caea4-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="caea4-106">Чтобы перейти непосредственно к панели мониторинга "Отчеты", откройте <https://office.protection.office.com/insightdashboard> ее.</span><span class="sxs-lookup"><span data-stu-id="caea4-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в Центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="caea4-108">Отчет о соединителе</span><span class="sxs-lookup"><span data-stu-id="caea4-108">Connector report</span></span>

<span data-ttu-id="caea4-109">Отчет **о соединителе показывает** активность потока обработки почты на входящих и [исходящих](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) соединителях, настроенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="caea4-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="caea4-110">Чтобы просмотреть отчет, откройте Центр [безопасности & соответствия требованиям, перейдите](https://protection.office.com)в панель **мониторинга** \> **отчетов** и выберите отчет **"Соединитель".**</span><span class="sxs-lookup"><span data-stu-id="caea4-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="caea4-111">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ConnectorReport> его.</span><span class="sxs-lookup"><span data-stu-id="caea4-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Мини-приложение отчетов по соединителю на панели мониторинга "Отчеты"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="caea4-113">Представление отчета по соединителям</span><span class="sxs-lookup"><span data-stu-id="caea4-113">Report view for the Connector report</span></span>

<span data-ttu-id="caea4-114">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="caea4-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="caea4-115">**Поток обработки почты: на этой**диаграмме показано количество входящих и исходящих сообщений, организованных по следующему:</span><span class="sxs-lookup"><span data-stu-id="caea4-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="caea4-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="caea4-116">**Total**</span></span>
  - <span data-ttu-id="caea4-117">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="caea4-118">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="caea4-119">Конкретный настроенный соединитель.</span><span class="sxs-lookup"><span data-stu-id="caea4-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="caea4-120">Чтобы изолировать данные на **Show data for** диаграмме, выберите один из этих параметров или поток обработки почты с помощью команды "Показать **данные".**</span><span class="sxs-lookup"><span data-stu-id="caea4-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Просмотр данных по потоку обработки почты в отчете соединителя](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="caea4-122">**Просмотр данных по: использованию TLS.** На этой диаграмме показан процент использования версий протокола TLS для потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="caea4-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="caea4-123">Чтобы изолировать данные на диаграмме, используйте параметр **"Показать данные для управления",** чтобы выбрать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="caea4-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="caea4-124">**Поток обработки почты**</span><span class="sxs-lookup"><span data-stu-id="caea4-124">**All mail flow**</span></span>
  - <span data-ttu-id="caea4-125">**Из Интернета без соединителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="caea4-126">**В Интернет без соединителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="caea4-127">Конкретный настроенный соединитель.</span><span class="sxs-lookup"><span data-stu-id="caea4-127">A specific connector that you've configured.</span></span>

  ![Просмотр данных по использованию TLS в отчете соединителя](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="caea4-129">При выборе **фильтров в представлении** отчета можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="caea4-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="caea4-130">Представление таблицы "Сведения" для отчета о соединителях</span><span class="sxs-lookup"><span data-stu-id="caea4-130">Details table view for the Connector report</span></span>

<span data-ttu-id="caea4-131">При нажатии **кнопки "Просмотр таблицы** сведений" в представлении отчета отобразятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="caea4-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="caea4-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="caea4-132">**Date**</span></span>
- <span data-ttu-id="caea4-133">**Направление и имя соединителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-133">**Connector direction and name**</span></span>
- <span data-ttu-id="caea4-134">**Тип соединителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-134">**Connector type**</span></span>
- <span data-ttu-id="caea4-135">**Tls?** Значение **True** или **False.**</span><span class="sxs-lookup"><span data-stu-id="caea4-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="caea4-136">**Без TLS** (процент)</span><span class="sxs-lookup"><span data-stu-id="caea4-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="caea4-137">**TLS 1.0** (процент)</span><span class="sxs-lookup"><span data-stu-id="caea4-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="caea4-138">**TLS 1.1** (процент)</span><span class="sxs-lookup"><span data-stu-id="caea4-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="caea4-139">**TLS 1.2** (процент)</span><span class="sxs-lookup"><span data-stu-id="caea4-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="caea4-140">**Volume**( Количество сообщений).</span><span class="sxs-lookup"><span data-stu-id="caea4-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="caea4-141">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="caea4-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="caea4-142">Чтобы вернуться к представлению отчета, **нажмите кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="caea4-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="caea4-143">Отчет о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="caea4-143">Exchange transport rule report</span></span>

<span data-ttu-id="caea4-144">Отчет **о правилах транспорта Exchange содержит** эффект правил потока обработки почты (также называемых правилами транспорта) на входящие и исходящие сообщения в организации.</span><span class="sxs-lookup"><span data-stu-id="caea4-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="caea4-145">Чтобы просмотреть отчет, откройте Центр [безопасности & соответствия требованиям, перейдите](https://protection.office.com)в панель **мониторинга** \> **отчетов** и **выберите правило транспорта Exchange.**</span><span class="sxs-lookup"><span data-stu-id="caea4-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="caea4-146">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ETRRuleReport> его.</span><span class="sxs-lookup"><span data-stu-id="caea4-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Виджет правила транспорта Exchange на панели мониторинга "Отчеты"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="caea4-148">Представление отчета для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="caea4-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="caea4-149">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="caea4-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="caea4-150">**Просмотр данных с помощью: правил транспорта Exchange** \> **Разбиение вниз:** на этой диаграмме показано количество **входящих** **и исходящих** сообщений, для которых были затронуты правила транспорта.</span><span class="sxs-lookup"><span data-stu-id="caea4-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="caea4-151">**Просмотр данных с помощью: правил транспорта Exchange** \> **Детализация по: на**этой диаграмме отображаются сведения о количестве сообщений "Высокий **уровень серьезности"** и **"Средний"** и "Низкий уровень **серьезности".**</span><span class="sxs-lookup"><span data-stu-id="caea4-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="caea4-152">Уровень серьезности задается в правиле ( Проверяйте его с помощью степени**серьезности** _или SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="caea4-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="caea4-153">Дополнительные сведения см. в статье о [действиях правил обработки почтового потока в Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="caea4-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="caea4-154">**Просмотр данных с помощью: правил транспорта DLP Exchange** \> **Остановка вниз:** на этой диаграмме **Outbound** показано количество **входящих** и исходящих сообщений, для которых повлияли правила транспорта защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="caea4-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="caea4-155">Диаграмму можно уточнить, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="caea4-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="caea4-156">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="caea4-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="caea4-157">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="caea4-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="caea4-158">**Показать данные для: небольший объем обнаруженного содержимого Бизковый акт САР**</span><span class="sxs-lookup"><span data-stu-id="caea4-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="caea4-159">**Просмотр данных с помощью: правил транспорта DLP Exchange** \> **Детализация на:** в этом представлении отображается количество сообщений **Low severity** "Высокий **уровень серьезности"** и "Средний" и "Серьезность", заблокированных правилами транспорта DLP. **Medium severity**</span><span class="sxs-lookup"><span data-stu-id="caea4-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="caea4-160">Диаграмму можно уточнить, выбрав следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="caea4-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="caea4-161">**Показать данные для: все правила транспорта DLP**</span><span class="sxs-lookup"><span data-stu-id="caea4-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="caea4-162">**Показать данные для: скомпрометированных пользователей**</span><span class="sxs-lookup"><span data-stu-id="caea4-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="caea4-163">**Показать данные для: небольший объем обнаруженного содержимого Бизковый акт САР**</span><span class="sxs-lookup"><span data-stu-id="caea4-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="caea4-164">Если **щелкнуть фильтры** в представлении отчета, можно изменить результаты следующим и следующим фильтрам:</span><span class="sxs-lookup"><span data-stu-id="caea4-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="caea4-165">**Даты начала и** **окончания**</span><span class="sxs-lookup"><span data-stu-id="caea4-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="caea4-166">Значения направления</span><span class="sxs-lookup"><span data-stu-id="caea4-166">Direction values</span></span>
- <span data-ttu-id="caea4-167">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="caea4-167">Severity values</span></span>

![Представление отчета в отчете о правилах транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="caea4-169">Представление таблицы подробностей для отчета о правилах транспорта Exchange</span><span class="sxs-lookup"><span data-stu-id="caea4-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="caea4-170">При нажатии **кнопки "Просмотр таблицы**сведений" показанная информация зависит от диаграммы, на которую вы ищете:</span><span class="sxs-lookup"><span data-stu-id="caea4-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="caea4-171">**Просмотр данных по: правила транспорта Exchange:**</span><span class="sxs-lookup"><span data-stu-id="caea4-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="caea4-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="caea4-172">**Date**</span></span>
  - <span data-ttu-id="caea4-173">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="caea4-173">**Transport rule**</span></span>
  - <span data-ttu-id="caea4-174">**Тема**</span><span class="sxs-lookup"><span data-stu-id="caea4-174">**Subject**</span></span>
  - <span data-ttu-id="caea4-175">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-175">**Sender address**</span></span>
  - <span data-ttu-id="caea4-176">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="caea4-176">**Recipient address**</span></span>
  - <span data-ttu-id="caea4-177">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="caea4-177">**Severity**</span></span>
  - <span data-ttu-id="caea4-178">**Направление**</span><span class="sxs-lookup"><span data-stu-id="caea4-178">**Direction**</span></span>

- <span data-ttu-id="caea4-179">**Просмотр данных по: правила транспорта DLP:**</span><span class="sxs-lookup"><span data-stu-id="caea4-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="caea4-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="caea4-180">**Date**</span></span>
  - <span data-ttu-id="caea4-181">**Политика защиты от потери данных**</span><span class="sxs-lookup"><span data-stu-id="caea4-181">**DLP policy**</span></span>
  - <span data-ttu-id="caea4-182">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="caea4-182">**Transport rule**</span></span>
  - <span data-ttu-id="caea4-183">**Тема**</span><span class="sxs-lookup"><span data-stu-id="caea4-183">**Subject**</span></span>
  - <span data-ttu-id="caea4-184">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="caea4-184">**Sender address**</span></span>
  - <span data-ttu-id="caea4-185">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="caea4-185">**Recipient address**</span></span>
  - <span data-ttu-id="caea4-186">**Серьезность**</span><span class="sxs-lookup"><span data-stu-id="caea4-186">**Severity**</span></span>
  - <span data-ttu-id="caea4-187">**Направление**</span><span class="sxs-lookup"><span data-stu-id="caea4-187">**Direction**</span></span>

<span data-ttu-id="caea4-188">Если **щелкнуть фильтры** в представлении таблицы сведений, можно изменить результаты следующим и следующим фильтрам:</span><span class="sxs-lookup"><span data-stu-id="caea4-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="caea4-189">**Даты начала и** **окончания**</span><span class="sxs-lookup"><span data-stu-id="caea4-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="caea4-190">Значения направления</span><span class="sxs-lookup"><span data-stu-id="caea4-190">Direction values</span></span>
- <span data-ttu-id="caea4-191">Значения серьезности</span><span class="sxs-lookup"><span data-stu-id="caea4-191">Severity values</span></span>

<span data-ttu-id="caea4-192">Чтобы вернуться к представлению отчета, **нажмите кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="caea4-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="caea4-193">Отчет о пересылке</span><span class="sxs-lookup"><span data-stu-id="caea4-193">Forwarding report</span></span>

<span data-ttu-id="caea4-194">Отчет о **пересылке** содержит автоматически пересылаемые сообщения вашей организации на внешние домены из почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="caea4-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="caea4-195">Переадресованные сообщения могут представлять угрозу безопасности или соответствия требованиям, а также могут означать компрометацию учетной записи.</span><span class="sxs-lookup"><span data-stu-id="caea4-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="caea4-196">Чтобы просмотреть отчет, откройте Центр [безопасности & соответствия требованиям, перейдите](https://protection.office.com)в панель **мониторинга отчетов** \> **Dashboard** и выберите отчет **о пересылке.**</span><span class="sxs-lookup"><span data-stu-id="caea4-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="caea4-197">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=MailFlowForwarding> его.</span><span class="sxs-lookup"><span data-stu-id="caea4-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Пересылка виджета отчетов на панели мониторинга "Отчеты"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="caea4-199">Представление отчета о пересылке</span><span class="sxs-lookup"><span data-stu-id="caea4-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="caea4-200">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="caea4-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="caea4-201">**Показать данные для: методы**пересылки: показаны следующие методы:</span><span class="sxs-lookup"><span data-stu-id="caea4-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="caea4-202">**Правило транспорта:** также называемые [правилами потока обработки почты.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="caea4-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="caea4-203">**Правило для почтового ящика:** правила для папки ["Входящие".](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="caea4-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Представление методов пересылки в отчете о пересылке](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="caea4-205">**Показывать данные для: домены пересылки**. Это представление показывает домены получателей, являющиеся назначениями для переадресации.</span><span class="sxs-lookup"><span data-stu-id="caea4-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Представление доменов переадресации в отчете о пересылке](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="caea4-207">**Отображение данных для: "Пересылатели":** отображаются следующие серверы пересылки:</span><span class="sxs-lookup"><span data-stu-id="caea4-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="caea4-208">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="caea4-208">**Transport rule**</span></span>
  - <span data-ttu-id="caea4-209">Почтовый ящик, который содержит правило переадресации папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="caea4-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Представление "Пересылатели" в отчете о пересылке](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="caea4-211">При выборе **фильтров в представлении** отчета можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="caea4-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="caea4-212">Представление таблицы подробностей для отчета о пересылке</span><span class="sxs-lookup"><span data-stu-id="caea4-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="caea4-213">При нажатии **кнопки "Просмотр таблицы** сведений" в представлении отчета отобразятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="caea4-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="caea4-214">**Серверы пересылки:** значение **правила транспорта или** почтовый ящик, который содержит правило пересылки входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="caea4-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="caea4-215">**Тип пересылки:** значение **правила почтового ящика** **или правило транспорта.**</span><span class="sxs-lookup"><span data-stu-id="caea4-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="caea4-216">**Имя получателя**</span><span class="sxs-lookup"><span data-stu-id="caea4-216">**Recipient name**</span></span>
- <span data-ttu-id="caea4-217">**домен получателя;**</span><span class="sxs-lookup"><span data-stu-id="caea4-217">**Recipient domain**</span></span>
- <span data-ttu-id="caea4-218">**Details**: это значение GUID правила обработки почтового потока или значение RuleIdentity правила для папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="caea4-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="caea4-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="caea4-219">**Count**</span></span>
- <span data-ttu-id="caea4-220">**Дата первого переадресации**</span><span class="sxs-lookup"><span data-stu-id="caea4-220">**First forward date**</span></span>

<span data-ttu-id="caea4-221">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="caea4-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="caea4-222">Чтобы вернуться в представление отчетов, нажмите **кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="caea4-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="caea4-223">Отчет о состоянии потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="caea4-223">Mailflow status report</span></span>

<span data-ttu-id="caea4-224">Отчет **о состоянии потока обработки почты** аналогичен отчету о отправленных и [полученных сообщениях электронной почты](#sent-and-received-email-report)с дополнительными сведениями о разрешенных или заблокированных сообщениях на краю.</span><span class="sxs-lookup"><span data-stu-id="caea4-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="caea4-225">Это единственный отчет, содержащий информацию о защите пограничных серверов и содержит только блокируемые сообщения электронной почты, прежде чем станут доступны в службе для оценки с помощью Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="caea4-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="caea4-226">Важно понимать, что если сообщение отправляется пяти получателям, его значение составляетпно пять, а не одно.</span><span class="sxs-lookup"><span data-stu-id="caea4-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="caea4-227">Чтобы просмотреть отчет, откройте Центр [безопасности & соответствия требованиям, перейдите](https://protection.office.com)в панель **мониторинга отчетов** \> **Dashboard** и **выберите "Отчет о состоянии потока почты".**</span><span class="sxs-lookup"><span data-stu-id="caea4-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="caea4-228">Чтобы перейти непосредственно к отчету о **состоянии потока обработки почты,** откройте. <https://protection.office.com/mailflowStatusReport></span><span class="sxs-lookup"><span data-stu-id="caea4-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Мини-приложение, посвященный отчетам о состоянии потока почты, на панели мониторинга "Отчеты"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="caea4-230">Представление типа для отчета о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="caea4-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="caea4-231">При открытии отчета по умолчанию **выбрана** вкладка Тип.</span><span class="sxs-lookup"><span data-stu-id="caea4-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="caea4-232">По умолчанию это представление содержит диаграмму и таблицу данных, настроенную следующими фильтрами.</span><span class="sxs-lookup"><span data-stu-id="caea4-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="caea4-233">**Date**: the last 7 days.</span><span class="sxs-lookup"><span data-stu-id="caea4-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="caea4-234">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="caea4-234">**Direction**:</span></span>

  - <span data-ttu-id="caea4-235">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="caea4-235">**Inbound**</span></span>
  - <span data-ttu-id="caea4-236">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="caea4-236">**Outbound**</span></span>
  - <span data-ttu-id="caea4-237">**Intra-org**: это количество предназначено для сообщений в клиенте i.e</span><span class="sxs-lookup"><span data-stu-id="caea4-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="caea4-238">отправителю abc@domain.com, отправляемой xyz@domain.com (подсчитывается отдельно от **входящих и** **исходящих)**</span><span class="sxs-lookup"><span data-stu-id="caea4-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="caea4-239">**Type**:</span><span class="sxs-lookup"><span data-stu-id="caea4-239">**Type**:</span></span>

  - <span data-ttu-id="caea4-240">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="caea4-240">**Good mail**</span></span>
  - <span data-ttu-id="caea4-241">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="caea4-241">**Malware**</span></span>
  - <span data-ttu-id="caea4-242">**Спам**</span><span class="sxs-lookup"><span data-stu-id="caea4-242">**Spam**</span></span>
  - <span data-ttu-id="caea4-243">**Защита пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="caea4-243">**Edge protection**</span></span>
  - <span data-ttu-id="caea4-244">**Сообщения с правилами**</span><span class="sxs-lookup"><span data-stu-id="caea4-244">**Rule messages**</span></span>
  - <span data-ttu-id="caea4-245">**Фишинговое письмо**</span><span class="sxs-lookup"><span data-stu-id="caea4-245">**Phishing email**</span></span>

<span data-ttu-id="caea4-246">Диаграмма упорядочена по **значениям Type.**</span><span class="sxs-lookup"><span data-stu-id="caea4-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="caea4-247">Эти фильтры можно изменить, щелкнув **фильтр или** выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="caea4-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="caea4-248">Таблица данных содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="caea4-248">The data table contains the following information:</span></span>

- <span data-ttu-id="caea4-249">**Направление**</span><span class="sxs-lookup"><span data-stu-id="caea4-249">**Direction**</span></span>
- <span data-ttu-id="caea4-250">**Тип**</span><span class="sxs-lookup"><span data-stu-id="caea4-250">**Type**</span></span>
- <span data-ttu-id="caea4-251">**24 часа**</span><span class="sxs-lookup"><span data-stu-id="caea4-251">**24 hours**</span></span>
- <span data-ttu-id="caea4-252">**за 3 дня;**</span><span class="sxs-lookup"><span data-stu-id="caea4-252">**3 days**</span></span>
- <span data-ttu-id="caea4-253">**7 дней**</span><span class="sxs-lookup"><span data-stu-id="caea4-253">**7 days**</span></span>
- <span data-ttu-id="caea4-254">**15 дней**</span><span class="sxs-lookup"><span data-stu-id="caea4-254">**15 days**</span></span>
- <span data-ttu-id="caea4-255">**30 дней**</span><span class="sxs-lookup"><span data-stu-id="caea4-255">**30 days**</span></span>

<span data-ttu-id="caea4-256">Если нажать **категорию для получения дополнительных сведений,** можно выбрать одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="caea4-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="caea4-257">**Фишинговое письмо:** при выборе вы выбудете [отчет о состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="caea4-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="caea4-258">**Вредоносная**программа по электронной почте: при выборе при [выборе вы входите в отчет о состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="caea4-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="caea4-259">**Обнаружения нежелательной почты:** вы откроете выбранный параметр в отчет об [обнаружении спама.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="caea4-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="caea4-260">**Пограничный блокировавшей**нежелательную почту — при выборе вы [ведут к отчету об обнаружении спама.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="caea4-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="caea4-261">**Export**:</span><span class="sxs-lookup"><span data-stu-id="caea4-261">**Export**:</span></span>

<span data-ttu-id="caea4-262">В подробном представлении можно экспортировать данные только за один день.</span><span class="sxs-lookup"><span data-stu-id="caea4-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="caea4-263">Поэтому если вам нужно экспортировать данные в течение 7 дней, необходимо выполнить от7 других действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="caea4-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="caea4-264">Каждый экспортированный CSV-файл может быть не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="caea4-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="caea4-265">Если данные за этот день содержат более 150 000 строк, то необходимо создать несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="caea4-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="caea4-266">Представление типа в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="caea4-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="caea4-267">Представление направления для отчета о состоянии потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="caea4-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="caea4-268">При переходе на **вкладку Направления** используются те же фильтры по умолчанию из **представления "Тип".**</span><span class="sxs-lookup"><span data-stu-id="caea4-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="caea4-269">Диаграмма упорядочена по **значениям направления.**</span><span class="sxs-lookup"><span data-stu-id="caea4-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="caea4-270">Эти фильтры можно изменить, щелкнув **фильтр или** выбрав значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="caea4-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="caea4-271">Используются те же фильтры из **представления Type.**</span><span class="sxs-lookup"><span data-stu-id="caea4-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="caea4-272">Таблица данных содержит те же сведения из **представления "Тип".**</span><span class="sxs-lookup"><span data-stu-id="caea4-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="caea4-273">Выбор **категории для получения дополнительных сведений** о доступных выбранных фрагментах и поведении аналогично **представлению типов.**</span><span class="sxs-lookup"><span data-stu-id="caea4-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="caea4-274">**Export**:</span><span class="sxs-lookup"><span data-stu-id="caea4-274">**Export**:</span></span>

<span data-ttu-id="caea4-275">В подробном представлении можно экспортировать данные только за один день.</span><span class="sxs-lookup"><span data-stu-id="caea4-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="caea4-276">Поэтому если вам нужно экспортировать данные в течение 7 дней, необходимо выполнить от7 других действий экспорта.</span><span class="sxs-lookup"><span data-stu-id="caea4-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="caea4-277">Каждый экспортированный CSV-файл может быть не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="caea4-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="caea4-278">Если данные за этот день содержат более 150 000 строк, то необходимо создать несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="caea4-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="caea4-279">Представление направления в отчете о состоянии потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="caea4-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="caea4-280">Воронкое представление для отчета о состоянии потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="caea4-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="caea4-281">Представление **Funnel показывает,** как функции защиты от угроз Майкрософт фильтруют входящую и исходящую электронную почту в организации.</span><span class="sxs-lookup"><span data-stu-id="caea4-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="caea4-282">В ней представлены сведения об общем числе сообщений электронной почты и о том, как настроенные функции защиты от угроз, включая пограничную защиту, защиту от вредоносных программ, защиту от фишинга, защиту от спама и защиту от спуфинга, влияют на это значение.</span><span class="sxs-lookup"><span data-stu-id="caea4-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="caea4-283">Если вы **щелкнете вкладку "Воронка",** то это представление по умолчанию содержит диаграмму и таблицу данных, настроенную с помощью следующих фильтров.</span><span class="sxs-lookup"><span data-stu-id="caea4-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="caea4-284">**Date**: the last 7 days.</span><span class="sxs-lookup"><span data-stu-id="caea4-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="caea4-285">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="caea4-285">**Direction**:</span></span>

  - <span data-ttu-id="caea4-286">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="caea4-286">**Inbound**</span></span>
  - <span data-ttu-id="caea4-287">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="caea4-287">**Outbound**</span></span>
  - <span data-ttu-id="caea4-288">**Внутри организации:** это количество предназначено для сообщений, отправленных в клиенте; Т. е. отправитель abc@domain.com отправитель отправляется xyz@domain.com (подсчитывается отдельно от входящей и исходящей почты).</span><span class="sxs-lookup"><span data-stu-id="caea4-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="caea4-289">В агрегировании представления и табличных представлений можно выполнять фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="caea4-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="caea4-290">При выборе параметра **Filter**можно отфильтровать как диаграмму, так и по таблице данных.</span><span class="sxs-lookup"><span data-stu-id="caea4-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="caea4-291">На этой диаграмме показансчетчик писем, организованных по:</span><span class="sxs-lookup"><span data-stu-id="caea4-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="caea4-292">**Всего сообщения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="caea4-292">**Total email**</span></span>
- <span data-ttu-id="caea4-293">**Электронная почта после защиты пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="caea4-293">**Email after edge protection**</span></span>
- <span data-ttu-id="caea4-294">**Электронная почта после защиты от вредоносных программ, репутации файлов, блокировки типа файла**</span><span class="sxs-lookup"><span data-stu-id="caea4-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="caea4-295">**Электронная почта после защиты от фишинга, репутации URL-адреса, олицетворения фирменной символики, защита от подделок**</span><span class="sxs-lookup"><span data-stu-id="caea4-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="caea4-296">**Электронная почта после защиты от нежелательной почты, фильтрация массовых рассылок**</span><span class="sxs-lookup"><span data-stu-id="caea4-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="caea4-297">**Электронная почта после олицетворения пользователя и домена**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="caea4-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="caea4-298">**Электронная почта после получения адреса электронной почты и детонации URL-адреса**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="caea4-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="caea4-299">**Сообщения, признанные как бижется после проверки после доставки (защита от url-адреса щелчком)**</span><span class="sxs-lookup"><span data-stu-id="caea4-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="caea4-300"><sup>Только 1</sup> Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="caea4-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="caea4-301">Чтобы просмотреть электронную почту, отфильтрованную EOP или ATP, щелкните значение в условных обозначениях диаграммы.</span><span class="sxs-lookup"><span data-stu-id="caea4-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="caea4-302">В таблице данных содержатся следующие сведения, отображаемые в порядке убывания дат.</span><span class="sxs-lookup"><span data-stu-id="caea4-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="caea4-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="caea4-303">**Date**</span></span>
- <span data-ttu-id="caea4-304">**Всего сообщения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="caea4-304">**Total email**</span></span>
- <span data-ttu-id="caea4-305">**Защита пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="caea4-305">**Edge protection**</span></span>
- <span data-ttu-id="caea4-306">**Anti-malware, file reputation, file block**</span><span class="sxs-lookup"><span data-stu-id="caea4-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="caea4-307">**Защита от фишинга, репутация URL-адреса, олицетворение торговой марки, защита от подделок**</span><span class="sxs-lookup"><span data-stu-id="caea4-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="caea4-308">**Фильтрация нежелательной почты для защиты от нежелательной почты и массовых рассылок**</span><span class="sxs-lookup"><span data-stu-id="caea4-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="caea4-309">**Олицетворение пользователей и доменов (ATP)**</span><span class="sxs-lookup"><span data-stu-id="caea4-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="caea4-310">**Удаление файла и URL-адреса (ATP)**</span><span class="sxs-lookup"><span data-stu-id="caea4-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="caea4-311">**Защита после доставки, ZAP (ATP) или ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="caea4-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="caea4-312">При выборе строки в таблице данных во всплывающем элементе отобразятся дополнительные сведения о счетчиках сообщений.</span><span class="sxs-lookup"><span data-stu-id="caea4-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="caea4-313">**Export**:</span><span class="sxs-lookup"><span data-stu-id="caea4-313">**Export**:</span></span>

<span data-ttu-id="caea4-314">После нажатия **кнопки** **"Экспорт"** в разделе "Параметры" можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="caea4-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="caea4-315">**Сводка (с данными за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="caea4-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="caea4-316">**Подробности (с данными за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="caea4-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="caea4-317">В разделе **"Дата"** выберите диапазон и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="caea4-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="caea4-318">Данные для текущих фильтров экспортируются в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="caea4-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="caea4-319">Каждый экспортированный CSV-файл может быть не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="caea4-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="caea4-320">Если данные содержат более 150 000 строк, то можно создать несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="caea4-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="caea4-321">Представление Funnel в отчете о состоянии потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="caea4-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="caea4-322">Техническое представление для отчета о состоянии потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="caea4-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="caea4-323">Представление Tech View аналогично **представлению Воронкообразов,** предоставляя более подробные сведения о настроенных функциях защиты от угроз. **Tech view**</span><span class="sxs-lookup"><span data-stu-id="caea4-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="caea4-324">На диаграмме показано, как сообщения классифицированы на разных этапах защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="caea4-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="caea4-325">Если щелкнуть **вкладку «Главный** вид", то по умолчанию это представление содержит диаграмму и таблицу данных, настроенную следующими фильтрами.</span><span class="sxs-lookup"><span data-stu-id="caea4-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="caea4-326">**Date**: the last 7 days.</span><span class="sxs-lookup"><span data-stu-id="caea4-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="caea4-327">**Direction**:</span><span class="sxs-lookup"><span data-stu-id="caea4-327">**Direction**:</span></span>

  - <span data-ttu-id="caea4-328">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="caea4-328">**Inbound**</span></span>
  - <span data-ttu-id="caea4-329">**Исходящие**</span><span class="sxs-lookup"><span data-stu-id="caea4-329">**Outbound**</span></span>
  - <span data-ttu-id="caea4-330">**Intra-org**: это количество предназначено для сообщений в клиенте i.e</span><span class="sxs-lookup"><span data-stu-id="caea4-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="caea4-331">почтовый abc@domain.com отправителя отправляется xyz@domain.com (подсчитывается отдельно от входящих и исходящих)</span><span class="sxs-lookup"><span data-stu-id="caea4-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="caea4-332">В агрегировании представления и табличных представлений можно выполнять фильтрацию в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="caea4-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="caea4-333">При выборе параметра **Filter**можно отфильтровать как диаграмму, так и по таблице данных.</span><span class="sxs-lookup"><span data-stu-id="caea4-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="caea4-334">На этой диаграмме показаны сообщения, упорядоченные по следующим категориям:</span><span class="sxs-lookup"><span data-stu-id="caea4-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="caea4-335">**Всего сообщения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="caea4-335">**Total email**</span></span>
- <span data-ttu-id="caea4-336">**Разрешение пограничного сервера, отфильтрованные краями**</span><span class="sxs-lookup"><span data-stu-id="caea4-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="caea4-337">**Не вредоносная программа, обнаружение безопасных вложений (ATP), обнаружение модуля защиты от вредоносных программ, блокировка правил**</span><span class="sxs-lookup"><span data-stu-id="caea4-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="caea4-338">**Не фишинговый, сбой DMARC, обнаружение олицетворения, обнаружение спуфактов, обнаружение фишинга**</span><span class="sxs-lookup"><span data-stu-id="caea4-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="caea4-339">**Отсутствие обнаружения с помощью детонации URL-адреса, обнаруживания URL-адреса (ATP)**</span><span class="sxs-lookup"><span data-stu-id="caea4-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="caea4-340">**Not spam, spam, spam**</span><span class="sxs-lookup"><span data-stu-id="caea4-340">**Not spam, spam**</span></span>
- <span data-ttu-id="caea4-341">**Не вредоносная электронная почта, обнаружение безопасных ссылок (ATP), ZAP**</span><span class="sxs-lookup"><span data-stu-id="caea4-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="caea4-342">При наведении указателя мыши на категорию на диаграмме вы увидите количество сообщений в этой категории.</span><span class="sxs-lookup"><span data-stu-id="caea4-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="caea4-343">В таблице данных содержатся следующие сведения, отображаемые в порядке убывания дат.</span><span class="sxs-lookup"><span data-stu-id="caea4-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="caea4-344">**Date**</span><span class="sxs-lookup"><span data-stu-id="caea4-344">**Date**</span></span>
- <span data-ttu-id="caea4-345">**Всего сообщения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="caea4-345">**Total email**</span></span>
- <span data-ttu-id="caea4-346">**Отфильтрованные пограничные серверы**</span><span class="sxs-lookup"><span data-stu-id="caea4-346">**Edge filtered**</span></span>
- <span data-ttu-id="caea4-347">**Антивирусная программа, безопасные вложения, фильтр**</span><span class="sxs-lookup"><span data-stu-id="caea4-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="caea4-348">**DMARC, олицетворение, спуфорикация, фишинговые сообщения**</span><span class="sxs-lookup"><span data-stu-id="caea4-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="caea4-349">**Обнаружение ухудшения URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="caea4-349">**URL detonation detection**</span></span>
- <span data-ttu-id="caea4-350">**Фильтр нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="caea4-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="caea4-351">**ZAP удален**</span><span class="sxs-lookup"><span data-stu-id="caea4-351">**ZAP removed**</span></span>
- <span data-ttu-id="caea4-352">**Обнаружение с помощью безопасных ссылок**</span><span class="sxs-lookup"><span data-stu-id="caea4-352">**Detection by safe links**</span></span>

<span data-ttu-id="caea4-353">При выборе строки в таблице данных во всплывающем элементе отобразятся дополнительные сведения о счетчиках сообщений.</span><span class="sxs-lookup"><span data-stu-id="caea4-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="caea4-354">**Export**:</span><span class="sxs-lookup"><span data-stu-id="caea4-354">**Export**:</span></span>

<span data-ttu-id="caea4-355">Нажав **кнопку "Экспорт"** и **в** разделе "Параметры" можно выбрать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="caea4-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="caea4-356">**Сводка (с данными за последние 90 дней)**</span><span class="sxs-lookup"><span data-stu-id="caea4-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="caea4-357">**Подробности (с данными за последние 30 дней)**</span><span class="sxs-lookup"><span data-stu-id="caea4-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="caea4-358">В разделе **"Дата"** выберите диапазон и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="caea4-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="caea4-359">Данные для текущих фильтров экспортируются в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="caea4-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="caea4-360">Каждый экспортированный CSV-файл может быть не более 150 000 строк.</span><span class="sxs-lookup"><span data-stu-id="caea4-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="caea4-361">Если данные содержат более 150 000 строк, то можно создать несколько CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="caea4-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="caea4-362">Техническое представление в отчете о состоянии потока почты</span><span class="sxs-lookup"><span data-stu-id="caea4-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="caea4-363">Отчет об отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="caea4-363">Sent and received email report</span></span>

<span data-ttu-id="caea4-364">Отчет **об отправленных и полученных сообщениях** является смарт-отчетом, в котором содержатся сведения о входящей и исходящей почте, в том числе об обнаружении спама, вредоносных программах и письме, которые стали являться хорошими.</span><span class="sxs-lookup"><span data-stu-id="caea4-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="caea4-365">Различие между этим отчетом и [отчетом о состоянии потока обработки](#mailflow-status-report) почты заключается в том, что этот отчет не содержит данные о сообщениях, заблокированных пограничной защитой.</span><span class="sxs-lookup"><span data-stu-id="caea4-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="caea4-366">В сводном представлении и подробном представлении отчета можно фильтровать данные через 90 дней.</span><span class="sxs-lookup"><span data-stu-id="caea4-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="caea4-367">Чтобы просмотреть отчет, откройте Центр соответствия [требованиям безопасности &, перейдите](https://protection.office.com)в панель мониторинга **отчетов** \> **Dashboard** и выберите **"Отправлено и полученное сообщение электронной почты".**</span><span class="sxs-lookup"><span data-stu-id="caea4-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="caea4-368">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> его.</span><span class="sxs-lookup"><span data-stu-id="caea4-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Мини-приложение "Отправлено и полученное письмо" на панели мониторинга "Отчеты"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="caea4-370">Представление отчетов об отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="caea4-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="caea4-371">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="caea4-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="caea4-372">**По детализации по: тип диаграммы**показывает все доступные категории:</span><span class="sxs-lookup"><span data-stu-id="caea4-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="caea4-373">**Total**</span><span class="sxs-lookup"><span data-stu-id="caea4-373">**Total**</span></span>
  - <span data-ttu-id="caea4-374">**Хорошая почта**</span><span class="sxs-lookup"><span data-stu-id="caea4-374">**Good mail**</span></span>
  - <span data-ttu-id="caea4-375">**Вредоносная программа (защита от вредоносных программ)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="caea4-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="caea4-376">**Обнаружения нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="caea4-376">**Spam detections**</span></span>
  - <span data-ttu-id="caea4-377">**Сообщения с правилами**</span><span class="sxs-lookup"><span data-stu-id="caea4-377">**Rule messages**</span></span>
  - <span data-ttu-id="caea4-378">**Дополнительные вредоносные** программы (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="caea4-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="caea4-379">При наведении курсора на день (точка данных) на диаграмме можно просмотреть сведения для этого дня.</span><span class="sxs-lookup"><span data-stu-id="caea4-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Ввод в отчеты о полученной и получаемой электронной почте](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="caea4-381">**Побочным образом:** диаграмма отображает **данные об**исходящем трафике, "Входящие" **и "Исходящие** данные". **Inbound**</span><span class="sxs-lookup"><span data-stu-id="caea4-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="caea4-382">При наведении курсора на день (точка данных) на диаграмме можно просмотреть сведения для этого дня.</span><span class="sxs-lookup"><span data-stu-id="caea4-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Представление направления в отчете о полученных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="caea4-384">**Детализация по** \> **Вредоносные программы (защита от вредоносных программ):** при выборе вы будете перенаправлены [к обнаружению вредоносных программ в электронной почте.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="caea4-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="caea4-385">**Детализация по** \> **Обнаружения нежелательной почты:** вы в откуда вы ведите в отчет [об обнаружении спама.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="caea4-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="caea4-386">Если **щелкнуть фильтры** в представлении отчета, результаты можно изменить с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="caea4-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="caea4-387">**Даты начала и** **окончания**</span><span class="sxs-lookup"><span data-stu-id="caea4-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="caea4-388">Значения направления</span><span class="sxs-lookup"><span data-stu-id="caea4-388">Direction values</span></span>
- <span data-ttu-id="caea4-389">Значения типов</span><span class="sxs-lookup"><span data-stu-id="caea4-389">Type values</span></span>

<span data-ttu-id="caea4-390">Чтобы вернуться к представлению отчета, **нажмите кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="caea4-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="caea4-391">Представление таблицы сведений для отчета об отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="caea4-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="caea4-392">При выборе пункта **"Просмотр таблицы сведений"** в **разделе "Разбивка вниз по: Направление** вниз" или "Разбивка **по:** направление вниз" отобразятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="caea4-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="caea4-393">**Дата (время в формате UTC)**</span><span class="sxs-lookup"><span data-stu-id="caea4-393">**Date (UTC)**</span></span>
- <span data-ttu-id="caea4-394">**Тип**</span><span class="sxs-lookup"><span data-stu-id="caea4-394">**Type**</span></span>
- <span data-ttu-id="caea4-395">**Направление**</span><span class="sxs-lookup"><span data-stu-id="caea4-395">**Direction**</span></span>
- <span data-ttu-id="caea4-396">**Число сообщений**</span><span class="sxs-lookup"><span data-stu-id="caea4-396">**Message count**</span></span>

<span data-ttu-id="caea4-397">Если **щелкнуть фильтры** в представлении таблицы сведений, можно изменить результаты следующим и следующим фильтрам:</span><span class="sxs-lookup"><span data-stu-id="caea4-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="caea4-398">**Даты начала и** **окончания**</span><span class="sxs-lookup"><span data-stu-id="caea4-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="caea4-399">Значения направления</span><span class="sxs-lookup"><span data-stu-id="caea4-399">Direction values</span></span>
- <span data-ttu-id="caea4-400">Значения типов</span><span class="sxs-lookup"><span data-stu-id="caea4-400">Type values</span></span>

<span data-ttu-id="caea4-401">Чтобы вернуться к представлению отчета, **нажмите кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="caea4-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="caea4-402">Отчет о ведущих отправителях и получателях</span><span class="sxs-lookup"><span data-stu-id="caea4-402">Top senders and recipients report</span></span>

<span data-ttu-id="caea4-403">Отчет **о получателях и отправителях** — это мощная диаграмма, на которой показаны отправители и получатели электронной почты в верхнем и востребоваиваемом углубления.</span><span class="sxs-lookup"><span data-stu-id="caea4-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="caea4-404">Чтобы просмотреть отчет, откройте Центр [безопасности & соответствия требованиям, перейдите](https://protection.office.com)в панель **мониторинга** \> **отчетов** и выберите **"Отправители и получатели" в списке "Наиболее постоянные отправители" и "Получатели".**</span><span class="sxs-lookup"><span data-stu-id="caea4-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="caea4-405">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> его.</span><span class="sxs-lookup"><span data-stu-id="caea4-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![На информационной панели "Отчеты" высшего числа отправителей и получателей](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="caea4-407">Представление отчета для отчета об наивысащих пользователях и получателях</span><span class="sxs-lookup"><span data-stu-id="caea4-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="caea4-408">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="caea4-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="caea4-409">**Отображение данных для \> отправителей, которые выдана**</span><span class="sxs-lookup"><span data-stu-id="caea4-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="caea4-410">**Отображать данные для \> получателей, которые выдана**</span><span class="sxs-lookup"><span data-stu-id="caea4-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="caea4-411">**Отображение сведений для \> получателей нежелательной почты:**</span><span class="sxs-lookup"><span data-stu-id="caea4-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="caea4-412">**Показать данные для \> Получатели вредоносных программ: наивысшее** количество получателей вредоносных программ (EOP)</span><span class="sxs-lookup"><span data-stu-id="caea4-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="caea4-413">**Показать данные для \> Получатели вредоносных программ (ATP)** для постоянного постоянного постоянного поснения (ATP)</span><span class="sxs-lookup"><span data-stu-id="caea4-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="caea4-414">Состав фрагментовой диаграммы изменяется на основе выбранных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="caea4-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="caea4-415">При наведлении курсора мыши на скобку на панели вы можете увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="caea4-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="caea4-416">При выборе **фильтров в представлении** отчета можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="caea4-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Мощная диаграмма в отчете "Отчет о наивысшем" отчете "Основные отправители" и "Получатели"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="caea4-418">Представление таблицы подробностей для отчета об наиболее быдящих отправителях и получателях</span><span class="sxs-lookup"><span data-stu-id="caea4-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="caea4-419">При нажатии **кнопки "Просмотр таблицы**сведений" показанная информация зависит от диаграммы, на которую вы ищете:</span><span class="sxs-lookup"><span data-stu-id="caea4-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="caea4-420">**Отображение данных для \> отправителей, которые выдана**</span><span class="sxs-lookup"><span data-stu-id="caea4-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="caea4-421">**Отправители почты: высшее из которых**</span><span class="sxs-lookup"><span data-stu-id="caea4-421">**Top mail senders**</span></span>
  - <span data-ttu-id="caea4-422">**Count**</span><span class="sxs-lookup"><span data-stu-id="caea4-422">**Count**</span></span>

- <span data-ttu-id="caea4-423">**Отображать данные для \> получателей, которые выдана**</span><span class="sxs-lookup"><span data-stu-id="caea4-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="caea4-424">**Получатели почты: высшее количество**</span><span class="sxs-lookup"><span data-stu-id="caea4-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="caea4-425">**Count**</span><span class="sxs-lookup"><span data-stu-id="caea4-425">**Count**</span></span>

- <span data-ttu-id="caea4-426">**Отображение сведений для \> получателей нежелательной почты:**</span><span class="sxs-lookup"><span data-stu-id="caea4-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="caea4-427">**Получатели нежелательной почты: высшее количество**</span><span class="sxs-lookup"><span data-stu-id="caea4-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="caea4-428">**Count**</span><span class="sxs-lookup"><span data-stu-id="caea4-428">**Count**</span></span>

- <span data-ttu-id="caea4-429">**Показать данные для \> Получатели вредоносных программ: наивысшее** количество получателей вредоносных программ (EOP)</span><span class="sxs-lookup"><span data-stu-id="caea4-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="caea4-430">**Получатели вредоносных программ:**</span><span class="sxs-lookup"><span data-stu-id="caea4-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="caea4-431">**Count**</span><span class="sxs-lookup"><span data-stu-id="caea4-431">**Count**</span></span>

- <span data-ttu-id="caea4-432">**Показать данные для \> Получатели вредоносных программ (ATP)** для постоянного постоянного постоянного поснения (ATP)</span><span class="sxs-lookup"><span data-stu-id="caea4-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="caea4-433">**Получатели вредоносных программ : ведущие категории (ATP)**</span><span class="sxs-lookup"><span data-stu-id="caea4-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="caea4-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="caea4-434">**Count**</span></span>

<span data-ttu-id="caea4-435">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="caea4-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="caea4-436">Чтобы вернуться к представлению отчета, **нажмите кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="caea4-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="caea4-437">Какие разрешения необходимы для просмотра этих отчетов?</span><span class="sxs-lookup"><span data-stu-id="caea4-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="caea4-438">Чтобы просматривать и использовать отчеты, вы должны быть членом указанной группы ролей в Центре безопасности & и **Exchange** Online.</span><span class="sxs-lookup"><span data-stu-id="caea4-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="caea4-439">В Центре безопасности & вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="caea4-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="caea4-440">-Organization Management -Security Administrator (это также можно сделать в [Центре администрирования Azure Active Directory — читатель](https://aad.portal.azure.com) безопасности</span><span class="sxs-lookup"><span data-stu-id="caea4-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="caea4-441">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="caea4-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="caea4-442">В Exchange Online вам необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="caea4-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="caea4-443">-Organization Management -View-Only Organization Management -View-Only Recipients -Compliance Management</span><span class="sxs-lookup"><span data-stu-id="caea4-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="caea4-444">Дополнительные сведения см. в [разделах "Разрешения в Exchange Online" и](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) ["Управление группами ролей" в Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)</span><span class="sxs-lookup"><span data-stu-id="caea4-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="caea4-445">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="caea4-445">Related topics</span></span>

[<span data-ttu-id="caea4-446">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="caea4-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="caea4-447">Аналитика потока обработки почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="caea4-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="caea4-448">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="caea4-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="caea4-449">Просмотр отчетов для Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="caea4-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
