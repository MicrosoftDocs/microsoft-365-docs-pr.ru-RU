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
ms.openlocfilehash: 401d566158ca3f730af94fab60c471484e244a16
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029850"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="e5e33-103">Отчет о не принятых доменах в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e5e33-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e5e33-104">Отчет о не принятых [](mail-flow-insights-v2.md) доменах на [](https://protection.office.com) панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & отображает сведения о сообщениях из локальной почтовой организации, в которых домен отправитель не настроен как принятый домен в вашей организации Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="e5e33-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="e5e33-105">Microsoft 365 может подавлять эти сообщения, если у нас есть данные для того, чтобы подтвердить, что эти сообщения вредоносны.</span><span class="sxs-lookup"><span data-stu-id="e5e33-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="e5e33-106">Поэтому важно понимать, что происходит, и устранять проблему.</span><span class="sxs-lookup"><span data-stu-id="e5e33-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Не принятый виджет домена на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="e5e33-108">Представление отчета о не принятых доменах</span><span class="sxs-lookup"><span data-stu-id="e5e33-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="e5e33-109">Щелкнув диаграмму в **мини-виджете** "Не принятый домен", вы йдите в отчет о не **принятых доменах.**</span><span class="sxs-lookup"><span data-stu-id="e5e33-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="e5e33-110">По умолчанию отображается действие для всех затронутых соединитеев.</span><span class="sxs-lookup"><span data-stu-id="e5e33-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="e5e33-111">Если вы **нажмете кнопку "Показать данные"** для, можно выбрать определенный соединителей из dropdown.</span><span class="sxs-lookup"><span data-stu-id="e5e33-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="e5e33-112">Если наведите указатель мыши на точку данных (день) на диаграмме, вы увидите общее количество сообщений для соединители.</span><span class="sxs-lookup"><span data-stu-id="e5e33-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Представление отчета в отчете о не принятых доменах](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="e5e33-114">Представление таблицы сведений для отчета о не принятых доменах</span><span class="sxs-lookup"><span data-stu-id="e5e33-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="e5e33-115">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e5e33-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e5e33-116">**Дата**</span><span class="sxs-lookup"><span data-stu-id="e5e33-116">**Date**</span></span>
- <span data-ttu-id="e5e33-117">**Имя входящие соединители**</span><span class="sxs-lookup"><span data-stu-id="e5e33-117">**Inbound connector name**</span></span>
- <span data-ttu-id="e5e33-118">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="e5e33-118">**Sender domain**</span></span>
- <span data-ttu-id="e5e33-119">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="e5e33-119">**Message count**</span></span>
- <span data-ttu-id="e5e33-120">**Примеры сообщений:** ИД сообщения с образцом затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="e5e33-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="e5e33-121">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="e5e33-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e5e33-122">Чтобы отправить отчет по электронной почте для определенного диапазона дат одному или более получателям, нажмите кнопку **"Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="e5e33-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e5e33-123">При выборе строки в таблице появится flyout со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="e5e33-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="e5e33-124">**Дата**</span><span class="sxs-lookup"><span data-stu-id="e5e33-124">**Date**</span></span>
- <span data-ttu-id="e5e33-125">**Имя входящие соединители**</span><span class="sxs-lookup"><span data-stu-id="e5e33-125">**Inbound connector name**</span></span>
- <span data-ttu-id="e5e33-126">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="e5e33-126">**Sender domain**</span></span>
- <span data-ttu-id="e5e33-127">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="e5e33-127">**Message count**</span></span>
- <span data-ttu-id="e5e33-128">**Примеры сообщений:** вы можете щелкнуть [](message-trace-scc.md) "Просмотреть **образцы** сообщений", чтобы просмотреть результаты трассировки для примера затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="e5e33-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Flyout Details after selecting a row in Details table view in the Non-accepted domain report](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="e5e33-130">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="e5e33-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5e33-131">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e5e33-131">Related topics</span></span>

<span data-ttu-id="e5e33-132">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e5e33-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
