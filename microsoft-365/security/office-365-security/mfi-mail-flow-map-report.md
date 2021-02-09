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
description: Администраторы могут узнать, как использовать карту потока обработки почты на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для визуализации и отслеживания потока обработки почты в организации через соединители и без использования соединители.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87a5780bd2485ba6ad3b295c09a30a4d7fc34277
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150564"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="41456-103">Карта потока обработки почты в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="41456-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41456-104">**Относится к**</span><span class="sxs-lookup"><span data-stu-id="41456-104">**Applies to**</span></span>
- [<span data-ttu-id="41456-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41456-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="41456-106">Microsoft Defender для Office 365 (план 1) и план 2</span><span class="sxs-lookup"><span data-stu-id="41456-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="41456-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41456-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="41456-108">Карта **потока обработки почты** на [](https://protection.office.com) панели мониторинга потока обработки почты в Центре & соответствия требованиям позволяет понять, как почта проходит через организацию. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="41456-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="41456-109">Эти сведения можно использовать для получения сведений о шаблонах, выявления аномалий и устранения неполадок по мере их возникновения.</span><span class="sxs-lookup"><span data-stu-id="41456-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Мини-приложения карты потока обработки почты на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="41456-111">По умолчанию мини-приложения показывает шаблон потока почты из предыдущего дня на диаграмме, известной как *схема Sankey.*</span><span class="sxs-lookup"><span data-stu-id="41456-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="41456-112">Вы можете использовать стрелку влево и стрелку вправо, чтобы показать ![ ](../../media/scc-left-arrow.png) сведения из ![ ](../../media/scc-right-arrow.png) разных дней.</span><span class="sxs-lookup"><span data-stu-id="41456-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="41456-113">Каждый цвет представляет поток почты через разные входящие или исходящие соединители (или без использования соединители).</span><span class="sxs-lookup"><span data-stu-id="41456-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="41456-114">Если навести курсор на определенный цвет, отображается количество сообщений для соединители этого типа.</span><span class="sxs-lookup"><span data-stu-id="41456-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="41456-115">Представление отчета для карты потока почты</span><span class="sxs-lookup"><span data-stu-id="41456-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="41456-116">Щелкнув **мини-виджет "Карта** потока почты", вы йдите в отчет о карте **потока почты.**</span><span class="sxs-lookup"><span data-stu-id="41456-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="41456-117">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="41456-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="41456-118">**Показать данные для: обзор**: это, по сути, большее представление виджета.</span><span class="sxs-lookup"><span data-stu-id="41456-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="41456-119">Если навести курсор на определенный цвет, для этого типа соединители будет отображаться количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="41456-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Обзор представления в отчете о карте потока почты](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="41456-121">**Показать данные для: подробности :** в этом представлении показаны сведения о соединители и домены назначения.</span><span class="sxs-lookup"><span data-stu-id="41456-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="41456-122">В списке указаны домены верхнего отправитель и получатель, а остальные находятся в **списке "Другие".**</span><span class="sxs-lookup"><span data-stu-id="41456-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="41456-123">Если наведите курсор на определенный цвет и раздел, отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="41456-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Подробное представление в отчете о карте потока почты](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="41456-125">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="41456-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="41456-126">Чтобы отправить отчет по электронной почте для определенного диапазона дат одному или более получателям, нажмите кнопку **"Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="41456-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="41456-127">Связанные сведения показаны под картой потока почты, если они доступны (например, анализ возможного почтового [цикла исправления).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="41456-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="41456-128">Представление таблицы сведений для карты потока почты</span><span class="sxs-lookup"><span data-stu-id="41456-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="41456-129">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="41456-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="41456-130">**Дата**</span><span class="sxs-lookup"><span data-stu-id="41456-130">**Date**</span></span>
- <span data-ttu-id="41456-131">**Категория**</span><span class="sxs-lookup"><span data-stu-id="41456-131">**Category**</span></span>
- <span data-ttu-id="41456-132">**Соединители / сторонний поставщик услуг**</span><span class="sxs-lookup"><span data-stu-id="41456-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="41456-133">**Домен отправитель/получатель**</span><span class="sxs-lookup"><span data-stu-id="41456-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="41456-134">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="41456-134">**Message count**</span></span>

<span data-ttu-id="41456-135">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="41456-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="41456-136">Если выбрать строку, аналогичные сведения будут показаны во flyout:</span><span class="sxs-lookup"><span data-stu-id="41456-136">If you select a row, similar details are shown in a flyout:</span></span>

![Flyout Details from the details table in the Mail flow map](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="41456-138">Чтобы отправить отчет по электронной почте для определенного диапазона дат одному или более получателям, нажмите кнопку **"Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="41456-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="41456-139">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="41456-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="41456-140">См. также</span><span class="sxs-lookup"><span data-stu-id="41456-140">See also</span></span>

<span data-ttu-id="41456-141">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="41456-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
