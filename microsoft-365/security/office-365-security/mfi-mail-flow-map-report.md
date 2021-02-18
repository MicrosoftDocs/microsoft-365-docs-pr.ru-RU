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
description: Администраторы могут научиться использовать карту потока обработки почты на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для визуализации и отслеживания потока обработки почты в организации через соединители и без использования соединители.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290589"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="ed3c2-103">Карта потока обработки почты в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ed3c2-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ed3c2-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-104">**Applies to**</span></span>
- [<span data-ttu-id="ed3c2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ed3c2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ed3c2-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ed3c2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ed3c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3c2-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ed3c2-108">Карта **потока обработки почты** на [](https://protection.office.com) панели мониторинга потока обработки почты в Центре & соответствия требованиям позволяет понять, как почта проходит через организацию. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ed3c2-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="ed3c2-109">Эти сведения можно использовать для получения сведений о шаблонах, выявления аномалий и устранения неполадок по мере их возникновения.</span><span class="sxs-lookup"><span data-stu-id="ed3c2-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Мини-виджет карты потока обработки почты на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="ed3c2-111">По умолчанию мини-приложения показывает шаблон потока почты из предыдущего дня на диаграмме, известной как *схема Sankey.*</span><span class="sxs-lookup"><span data-stu-id="ed3c2-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="ed3c2-112">Вы можете использовать стрелку влево и стрелку вправо, чтобы показать ![ ](../../media/scc-left-arrow.png) сведения из ![ ](../../media/scc-right-arrow.png) разных дней.</span><span class="sxs-lookup"><span data-stu-id="ed3c2-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="ed3c2-113">Каждый цвет представляет поток почты через разные входящие или исходящие соединители (или без использования соединители).</span><span class="sxs-lookup"><span data-stu-id="ed3c2-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="ed3c2-114">Если навести курсор на определенный цвет, для этого типа соединители будет отображаться количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed3c2-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="ed3c2-115">Представление отчета для карты потока почты</span><span class="sxs-lookup"><span data-stu-id="ed3c2-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="ed3c2-116">Щелкнув **мини-виджет "Карта** потока почты", вы йдите в отчет **о карте потока почты.**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="ed3c2-117">В представлении отчета доступны следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="ed3c2-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ed3c2-118">**Показать данные для: обзор**: это, по сути, большее представление виджета.</span><span class="sxs-lookup"><span data-stu-id="ed3c2-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="ed3c2-119">Если навести курсор на определенный цвет, для этого типа соединители будет отображаться количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed3c2-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Обзор представления в отчете о карте потока почты](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="ed3c2-121">**Показать данные для: подробности :** в этом представлении показаны сведения о соединители и домены назначения.</span><span class="sxs-lookup"><span data-stu-id="ed3c2-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="ed3c2-122">В списке указаны домены верхнего отправитель и получатель, а остальные находятся в **списке "Другие".**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="ed3c2-123">Если наведите курсор на определенный цвет и раздел, отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed3c2-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Подробное представление в отчете о карте потока почты](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="ed3c2-125">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ed3c2-126">Чтобы отправить отчет по электронной почте для определенного диапазона дат одному или более получателям, нажмите кнопку **"Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="ed3c2-127">Связанные сведения показаны под картой потока почты, если они доступны (например, сведения о возможном почтовом [цикле "Исправить").](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="ed3c2-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="ed3c2-128">Представление таблицы сведений для карты потока почты</span><span class="sxs-lookup"><span data-stu-id="ed3c2-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="ed3c2-129">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ed3c2-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="ed3c2-130">**Дата**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-130">**Date**</span></span>
- <span data-ttu-id="ed3c2-131">**Категория**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-131">**Category**</span></span>
- <span data-ttu-id="ed3c2-132">**Соединители / сторонний поставщик услуг**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="ed3c2-133">**Домен отправитель/получатель**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="ed3c2-134">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-134">**Message count**</span></span>

<span data-ttu-id="ed3c2-135">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ed3c2-136">Если выбрать строку, аналогичные сведения будут показаны во flyout:</span><span class="sxs-lookup"><span data-stu-id="ed3c2-136">If you select a row, similar details are shown in a flyout:</span></span>

![Flyout Details from the details table in the Mail flow map](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="ed3c2-138">Чтобы отправить отчет по электронной почте для определенного диапазона дат одному или более получателям, нажмите кнопку **"Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="ed3c2-139">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="ed3c2-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed3c2-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ed3c2-140">See also</span></span>

<span data-ttu-id="ed3c2-141">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ed3c2-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
