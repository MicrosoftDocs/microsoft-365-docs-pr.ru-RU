---
title: Не принятый отчет о домене в панели мониторинга потока почты
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
description: Администраторы могут узнать, как использовать не принятый отчет о домене в панели мониторинга потока почты в Центре соответствия требованиям & безопасности для мониторинга сообщений из локальной организации, где домен отправитель не настроен в Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206337"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="10705-103">Не принятый отчет о домене в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="10705-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="10705-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="10705-104">**Applies to**</span></span>
- [<span data-ttu-id="10705-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="10705-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="10705-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="10705-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="10705-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10705-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="10705-108">Отчет о неприятии [](mail-flow-insights-v2.md) домена в [](https://protection.office.com) панели мониторинга потока почты в Центре соответствия требованиям & безопасности отображает сведения о сообщениях из локальной организации электронной почты, где домен отправитель не настроен как принятый домен в организации Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="10705-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="10705-109">Microsoft 365 может затормачить эти сообщения, если у нас есть данные, которые доказывают, что намерения этих сообщений вредоносны.</span><span class="sxs-lookup"><span data-stu-id="10705-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="10705-110">Поэтому важно понять, что происходит, и устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="10705-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Не принятый виджет домена в панели мониторинга потока почты в Центре & соответствия требованиям](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="10705-112">Представление отчета для отчета о не принятых доменах</span><span class="sxs-lookup"><span data-stu-id="10705-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="10705-113">Щелкнув диаграмму  на виджете не принятого домена, вы сможете получить отчет о не **принятых доменах.**</span><span class="sxs-lookup"><span data-stu-id="10705-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="10705-114">По умолчанию отображается действие для всех затронутых соединители.</span><span class="sxs-lookup"><span data-stu-id="10705-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="10705-115">Если вы **нажмете показать данные** для, вы можете выбрать определенный соединителей из отсев.</span><span class="sxs-lookup"><span data-stu-id="10705-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="10705-116">Если наведите курсор на точку данных (день) на диаграмме, вы увидите общее количество сообщений для соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="10705-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Представление отчета в отчете о не принятых доменах](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="10705-118">Представление таблицы сведений для отчета о не принятых доменах</span><span class="sxs-lookup"><span data-stu-id="10705-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="10705-119">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="10705-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="10705-120">**Дата**</span><span class="sxs-lookup"><span data-stu-id="10705-120">**Date**</span></span>
- <span data-ttu-id="10705-121">**Имя входящие соединители**</span><span class="sxs-lookup"><span data-stu-id="10705-121">**Inbound connector name**</span></span>
- <span data-ttu-id="10705-122">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="10705-122">**Sender domain**</span></span>
- <span data-ttu-id="10705-123">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="10705-123">**Message count**</span></span>
- <span data-ttu-id="10705-124">**Пример сообщений:** ID сообщений образца затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="10705-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="10705-125">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="10705-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="10705-126">Чтобы отправить отчет для определенного диапазона дат одному или несколько получателей, нажмите кнопку **Запрос скачать**.</span><span class="sxs-lookup"><span data-stu-id="10705-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="10705-127">При выборе строки в таблице вылет появляется со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="10705-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="10705-128">**Дата**</span><span class="sxs-lookup"><span data-stu-id="10705-128">**Date**</span></span>
- <span data-ttu-id="10705-129">**Имя входящие соединители**</span><span class="sxs-lookup"><span data-stu-id="10705-129">**Inbound connector name**</span></span>
- <span data-ttu-id="10705-130">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="10705-130">**Sender domain**</span></span>
- <span data-ttu-id="10705-131">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="10705-131">**Message count**</span></span>
- <span data-ttu-id="10705-132">**Примеры сообщений.** Вы можете нажать **просмотреть примеры** сообщений, чтобы просмотреть результаты трассировки сообщений для примера затронутых сообщений. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="10705-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Сведения о вылете после выбора строки в представлении таблицы Details в отчете о не принятых доменах](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="10705-134">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="10705-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10705-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="10705-135">Related topics</span></span>

<span data-ttu-id="10705-136">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="10705-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
