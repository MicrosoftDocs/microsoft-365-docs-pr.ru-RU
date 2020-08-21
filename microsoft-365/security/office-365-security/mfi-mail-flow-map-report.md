---
title: Схема потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут научиться использовать карту потока обработки почты на панели мониторинга потока обработки почты в Центре безопасности & для визуализации и отслеживания потока почты в организации через соединители, не используя соединители.
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827005"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="2521d-103">Карта потока обработки почты в Центре безопасности & безопасности</span><span class="sxs-lookup"><span data-stu-id="2521d-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="2521d-104">Карта **потока обработки почты** на [панели](mail-flow-insights-v2.md) мониторинга потока обработки почты в Центре безопасности & дает представление о потоке обработки почты в организации.</span><span class="sxs-lookup"><span data-stu-id="2521d-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="2521d-105">Эти сведения можно использовать для изучения шаблонов, идентификации аномалий и устранения проблем по мере их возникновения.</span><span class="sxs-lookup"><span data-stu-id="2521d-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Мини-приложение «Карта потока обработки почты) на информационной панели потока обработки почты в Центре соответствия требованиям & требованиям](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="2521d-107">По умолчанию виджет показывает шаблон потока обработки почты за предыдущий день на диаграмме, называемой *диаграммой Sankey.*</span><span class="sxs-lookup"><span data-stu-id="2521d-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="2521d-108">Для отображения информации от разных дней можно использовать стрелки ![ влево и ](../../media/scc-left-arrow.png) стрелки ![ ](../../media/scc-right-arrow.png) вправо.</span><span class="sxs-lookup"><span data-stu-id="2521d-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="2521d-109">Каждый цвет представляет поток обработки почты через разные входящие или исходящие соединители (или без использования соединителей).</span><span class="sxs-lookup"><span data-stu-id="2521d-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="2521d-110">Если навести курсор на определенный цвет, для соединителя этого типа отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="2521d-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="2521d-111">Представление отчетов для карты потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="2521d-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="2521d-112">Если щелкнуть **мини-приложение "Карта** потока обработки почты", откроется **отчет сопоставления потока обработки** почты.</span><span class="sxs-lookup"><span data-stu-id="2521d-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="2521d-113">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="2521d-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2521d-114">**Отображение данных для: Обзор**— по существу, это более масштабное представление мини-приложения.</span><span class="sxs-lookup"><span data-stu-id="2521d-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="2521d-115">Если навести курсор на определенный цвет, для соединителя этого типа отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="2521d-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Обзорное представление в отчете о карте потока обработки почты](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="2521d-117">**Показать данные для: Подробности.** В этом представлении отображаются сведения о соединителях и доменах назначения.</span><span class="sxs-lookup"><span data-stu-id="2521d-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="2521d-118">В списке указаны верхние домены отправителя и получателя, остальные — в **других.**</span><span class="sxs-lookup"><span data-stu-id="2521d-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="2521d-119">Если наведите указатель мыши на определенный цвет и раздел, отображается число сообщений.</span><span class="sxs-lookup"><span data-stu-id="2521d-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Подробное представление в отчете о карте потока обработки почты](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="2521d-121">При выборе **фильтров в представлении** отчета можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="2521d-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2521d-122">Чтобы отправлять отчету отчету в заданный диапазон дат одному или нескольким получателям, нажмите **кнопку "Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="2521d-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="2521d-123">Содержащаяся аналитика отображается под схемой потока обработки почты, если они доступны (например, [исправить возможный источник данных о почтовом цикле).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="2521d-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="2521d-124">Представление таблицы "Сведения" для карты потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="2521d-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="2521d-125">При нажатии **кнопки "Просмотр таблицы** сведений" в представлении отчета отобразятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="2521d-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="2521d-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="2521d-126">**Date**</span></span>
- <span data-ttu-id="2521d-127">**Категория**</span><span class="sxs-lookup"><span data-stu-id="2521d-127">**Category**</span></span>
- <span data-ttu-id="2521d-128">**Соединитель или сторонний поставщик служб**</span><span class="sxs-lookup"><span data-stu-id="2521d-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="2521d-129">**Домен отправителя или получателя**</span><span class="sxs-lookup"><span data-stu-id="2521d-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="2521d-130">**Число сообщений**</span><span class="sxs-lookup"><span data-stu-id="2521d-130">**Message count**</span></span>

<span data-ttu-id="2521d-131">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="2521d-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2521d-132">При выборе строки похожие сведения будут показаны во всплывающем окне:</span><span class="sxs-lookup"><span data-stu-id="2521d-132">If you select a row, similar details are shown in a flyout:</span></span>

![Всплывающем элементе "Сведения" таблицы "Сведения" на карте потока обработки почты](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="2521d-134">Чтобы отправлять отчету отчету в заданный диапазон дат одному или нескольким получателям, нажмите **кнопку "Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="2521d-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="2521d-135">Чтобы вернуться в представление отчетов, нажмите **кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="2521d-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2521d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="2521d-136">See also</span></span>

<span data-ttu-id="2521d-137">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="2521d-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
