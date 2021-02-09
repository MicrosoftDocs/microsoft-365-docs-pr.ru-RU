---
title: Отчет о не принятых доменах на панели мониторинга потока почты
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
description: Администраторы могут узнать, как использовать отчет о не принятых доменах на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для отслеживания сообщений из локальной организации, в которой домен отправитель не настроен в Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150824"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="a754f-103">Отчет о не принятых доменах в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a754f-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a754f-104">**Относится к**</span><span class="sxs-lookup"><span data-stu-id="a754f-104">**Applies to**</span></span>
- [<span data-ttu-id="a754f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a754f-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="a754f-106">Microsoft Defender для Office 365 (план 1) и план 2</span><span class="sxs-lookup"><span data-stu-id="a754f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="a754f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a754f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a754f-108">Отчет о не принятых [](mail-flow-insights-v2.md) доменах на [](https://protection.office.com) панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & отображает сведения о сообщениях из локальной почтовой организации, в которых домен отправитель не настроен в качестве принятого домена в организации Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="a754f-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="a754f-109">Microsoft 365 может подавлять эти сообщения, если у нас есть данные для того, чтобы подтвердить, что эти сообщения вредоносны.</span><span class="sxs-lookup"><span data-stu-id="a754f-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="a754f-110">Поэтому важно понимать, что происходит, и устранять проблему.</span><span class="sxs-lookup"><span data-stu-id="a754f-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Не принятый виджет домена на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="a754f-112">Представление отчета о не принятых доменах</span><span class="sxs-lookup"><span data-stu-id="a754f-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="a754f-113">Щелкнув диаграмму в **мини-виджете** "Не принятый домен", вы йдите в отчет о не **принятых доменах.**</span><span class="sxs-lookup"><span data-stu-id="a754f-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="a754f-114">По умолчанию отображается действие для всех затронутых соединитеев.</span><span class="sxs-lookup"><span data-stu-id="a754f-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="a754f-115">Если нажать **кнопку "Показать данные",** можно выбрать определенный соединителей в выпадаемом окне.</span><span class="sxs-lookup"><span data-stu-id="a754f-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="a754f-116">Если наведите указатель мыши на точку данных (день) на диаграмме, вы увидите общее количество сообщений для соединители.</span><span class="sxs-lookup"><span data-stu-id="a754f-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Представление отчета в отчете о не принятых доменах](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="a754f-118">Представление таблицы сведений для отчета о не принятых доменах</span><span class="sxs-lookup"><span data-stu-id="a754f-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="a754f-119">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a754f-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a754f-120">**Дата**</span><span class="sxs-lookup"><span data-stu-id="a754f-120">**Date**</span></span>
- <span data-ttu-id="a754f-121">**Имя входящие соединители**</span><span class="sxs-lookup"><span data-stu-id="a754f-121">**Inbound connector name**</span></span>
- <span data-ttu-id="a754f-122">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="a754f-122">**Sender domain**</span></span>
- <span data-ttu-id="a754f-123">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="a754f-123">**Message count**</span></span>
- <span data-ttu-id="a754f-124">**Примеры сообщений:** ИД сообщения с образцом затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="a754f-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="a754f-125">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="a754f-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a754f-126">Чтобы отправить отчет по электронной почте для определенного диапазона дат одному или более получателям, нажмите кнопку **"Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="a754f-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="a754f-127">При выборе строки в таблице появится flyout со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="a754f-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="a754f-128">**Дата**</span><span class="sxs-lookup"><span data-stu-id="a754f-128">**Date**</span></span>
- <span data-ttu-id="a754f-129">**Имя входящие соединители**</span><span class="sxs-lookup"><span data-stu-id="a754f-129">**Inbound connector name**</span></span>
- <span data-ttu-id="a754f-130">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="a754f-130">**Sender domain**</span></span>
- <span data-ttu-id="a754f-131">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="a754f-131">**Message count**</span></span>
- <span data-ttu-id="a754f-132">**Примеры сообщений:** можно щелкнуть "Просмотреть **примеры** сообщений", чтобы просмотреть результаты трассировки для примера затронутых сообщений. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="a754f-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Flyout Details after selecting a row in Details table view in the Non-accepted domain report](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="a754f-134">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a754f-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a754f-135">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a754f-135">Related topics</span></span>

<span data-ttu-id="a754f-136">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a754f-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
