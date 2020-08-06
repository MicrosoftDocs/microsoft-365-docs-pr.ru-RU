---
title: Карта почтовых ящиков
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать карту потока обработки почты в панели мониторинга потока обработки почты в центре безопасности & соответствия требованиям, чтобы визуализировать и отслеживать обмен сообщениями между организациями и их организациями, а не с помощью соединителей.
ms.openlocfilehash: 2996227de3e0141635522ada4e41f2e8e65e9040
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577722"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="6732a-103">Карта почтовых ящиков в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6732a-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="6732a-104">**Схема потока обработки почты** на [панели мониторинга "поток обработки почты](mail-flow-insights-v2.md) " в центре безопасности & соответствия требованиям позволяет понять, как почтовые сообщения проходят через организацию.</span><span class="sxs-lookup"><span data-stu-id="6732a-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="6732a-105">Вы можете использовать эти сведения для изучения шаблонов, выявления аномалий и устранения проблем по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="6732a-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Мини-приложение "карта почтовых ящиков" на панели мониторинга "Управление почтой" в центре безопасности & соответствия требованиям](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="6732a-107">По умолчанию мини-приложение показывает шаблон почтового процесса с предыдущего дня в диаграмме, которая называется схемой *Санкэй* .</span><span class="sxs-lookup"><span data-stu-id="6732a-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="6732a-108">С помощью стрелок влево Стрелка влево и стрелка вправо можно ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) Показать информацию с разных дней.</span><span class="sxs-lookup"><span data-stu-id="6732a-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="6732a-109">Каждый другой цвет представляет потока обработки почты для различных входящих или исходящих соединителей (или без использования соединителей).</span><span class="sxs-lookup"><span data-stu-id="6732a-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="6732a-110">Если навести указатель мыши на определенный цвет, для этого типа соединителя отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="6732a-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="6732a-111">Представление отчета для карты почтовых почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="6732a-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="6732a-112">Щелкнув мини-приложение **карты почтовых ящиков** , вы перейдете к отчету **карты процесса обработки почты** .</span><span class="sxs-lookup"><span data-stu-id="6732a-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="6732a-113">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="6732a-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="6732a-114">**Показать данные для: обзор**: в основном это более крупное представление мини-приложения.</span><span class="sxs-lookup"><span data-stu-id="6732a-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="6732a-115">Если навести указатель мыши на определенный цвет, для этого типа соединителя отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="6732a-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Представление "Обзор" в отчете карты почтовых ящиков](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="6732a-117">**Показать данные для: Detail: в**этом представлении отображаются сведения о соединителях и конечных доменах.</span><span class="sxs-lookup"><span data-stu-id="6732a-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="6732a-118">Отображаются домены верхнего отправителя и получателя, и остальные домены помещаются в **другие**.</span><span class="sxs-lookup"><span data-stu-id="6732a-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="6732a-119">Если навести указатель мыши на определенный цвет и раздел, отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="6732a-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Подробное представление в отчете о схеме почтового процесса](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="6732a-121">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="6732a-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6732a-122">Чтобы отправить отчет по определенному диапазону дат одному или нескольким получателям, щелкните **запросить скачивание**.</span><span class="sxs-lookup"><span data-stu-id="6732a-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="6732a-123">Информация, связанная с аналитическим представлением, отображается под картой почтовых процессов, если они доступны (например, [исправление возможных почтовых циклов почты](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="6732a-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="6732a-124">Представление таблицы "сведения" для карты почтовых почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="6732a-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="6732a-125">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="6732a-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6732a-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="6732a-126">**Date**</span></span>
- <span data-ttu-id="6732a-127">**Категория**</span><span class="sxs-lookup"><span data-stu-id="6732a-127">**Category**</span></span>
- <span data-ttu-id="6732a-128">**Соединитель/сторонний поставщик услуг**</span><span class="sxs-lookup"><span data-stu-id="6732a-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="6732a-129">**Домен отправителя или получателя**</span><span class="sxs-lookup"><span data-stu-id="6732a-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="6732a-130">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="6732a-130">**Message count**</span></span>

<span data-ttu-id="6732a-131">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="6732a-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6732a-132">Если выбрана строка, похожие сведения отображаются в всплывающем меню:</span><span class="sxs-lookup"><span data-stu-id="6732a-132">If you select a row, similar details are shown in a flyout:</span></span>

![Всплывающее меню сведений из таблицы сведений в карте почтового процесса](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="6732a-134">Чтобы отправить отчет по определенному диапазону дат одному или нескольким получателям, щелкните **запросить скачивание**.</span><span class="sxs-lookup"><span data-stu-id="6732a-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="6732a-135">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="6732a-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6732a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="6732a-136">See also</span></span>

<span data-ttu-id="6732a-137">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="6732a-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
