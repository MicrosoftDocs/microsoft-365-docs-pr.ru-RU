---
title: Схема потока обработки почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать карту потока почты в панели мониторинга потока почты в Центре соответствия требованиям & безопасности, чтобы визуализировать и отслеживать, как почта передается в их организацию через соединители и не использует соединители.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206958"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="e11c6-103">Карта потока почты в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="e11c6-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e11c6-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="e11c6-104">**Applies to**</span></span>
- [<span data-ttu-id="e11c6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e11c6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e11c6-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="e11c6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e11c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e11c6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e11c6-108">Карта **потока почты** в панели [](https://protection.office.com) мониторинга потока почты в Центре & безопасности дает представление о том, как почта проходит через организацию. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e11c6-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="e11c6-109">Эти сведения можно использовать для получения шаблонов, выявления аномалий и устранения неполадок по мере их возникновения.</span><span class="sxs-lookup"><span data-stu-id="e11c6-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Виджет карты потока почты в панели мониторинга потока почты в центре & соответствия требованиям](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="e11c6-111">По умолчанию виджет отображает шаблон потока почты по сравнению с предыдущим днем на диаграмме, известной как *диаграмма Sankey.*</span><span class="sxs-lookup"><span data-stu-id="e11c6-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="e11c6-112">Вы можете использовать левую стрелку левой стрелки и правую стрелку правой стрелки, ![ чтобы показать информацию из ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) разных дней.</span><span class="sxs-lookup"><span data-stu-id="e11c6-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="e11c6-113">Каждый другой цвет представляет поток почты по другому входящий или исходящие соединители (или без использования соединители).</span><span class="sxs-lookup"><span data-stu-id="e11c6-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="e11c6-114">Если наведите курсор над определенным цветом, для этого типа соединитетеля отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="e11c6-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="e11c6-115">Представление отчета для карты потока почты</span><span class="sxs-lookup"><span data-stu-id="e11c6-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="e11c6-116">Щелкнув **виджет карты потока почты,** вы сможете найти отчет о карте **потока** почты.</span><span class="sxs-lookup"><span data-stu-id="e11c6-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="e11c6-117">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="e11c6-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e11c6-118">**Показать данные для: Обзор:** Это в основном большее представление виджета.</span><span class="sxs-lookup"><span data-stu-id="e11c6-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="e11c6-119">Если наведите курсор над определенным цветом, для этого типа соединитетеля отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="e11c6-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Представление обзоров в отчете о карте потока почты](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="e11c6-121">**Показать данные для: Подробно.** В этом представлении показаны сведения о соединители и домены назначения.</span><span class="sxs-lookup"><span data-stu-id="e11c6-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="e11c6-122">Перечислены главные домены отправитель и получатель, остальные — в **Другие.**</span><span class="sxs-lookup"><span data-stu-id="e11c6-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="e11c6-123">Если наведите курсор на определенный цвет и раздел, отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="e11c6-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Представление подробной информации в отчете о карте потока почты](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="e11c6-125">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="e11c6-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e11c6-126">Чтобы отправить отчет для определенного диапазона дат одному или несколько получателей, нажмите кнопку **Запрос скачать**.</span><span class="sxs-lookup"><span data-stu-id="e11c6-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e11c6-127">Соответствующие сведения показаны под картой потока почты, если они доступны (например, сведения о возможном устранении [циклов почты).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="e11c6-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="e11c6-128">Представление таблицы сведений для карты потока почты</span><span class="sxs-lookup"><span data-stu-id="e11c6-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="e11c6-129">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="e11c6-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e11c6-130">**Date**</span><span class="sxs-lookup"><span data-stu-id="e11c6-130">**Date**</span></span>
- <span data-ttu-id="e11c6-131">**Категория**</span><span class="sxs-lookup"><span data-stu-id="e11c6-131">**Category**</span></span>
- <span data-ttu-id="e11c6-132">**Поставщик услуг Connector / Сторонний поставщик услуг**</span><span class="sxs-lookup"><span data-stu-id="e11c6-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="e11c6-133">**Домен Sender/Recipient**</span><span class="sxs-lookup"><span data-stu-id="e11c6-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="e11c6-134">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="e11c6-134">**Message count**</span></span>

<span data-ttu-id="e11c6-135">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="e11c6-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e11c6-136">Если вы выбираете строку, аналогичные сведения показаны в вылете:</span><span class="sxs-lookup"><span data-stu-id="e11c6-136">If you select a row, similar details are shown in a flyout:</span></span>

![Сведения о вылете из таблицы сведений на карте потока почты](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="e11c6-138">Чтобы отправить отчет для определенного диапазона дат одному или несколько получателей, нажмите кнопку **Запрос скачать**.</span><span class="sxs-lookup"><span data-stu-id="e11c6-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e11c6-139">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="e11c6-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e11c6-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e11c6-140">See also</span></span>

<span data-ttu-id="e11c6-141">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="e11c6-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
