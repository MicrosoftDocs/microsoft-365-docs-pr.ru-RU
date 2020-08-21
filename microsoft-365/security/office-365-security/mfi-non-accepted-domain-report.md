---
title: Отчет о необслуживаемом домене на панели мониторинга потока обработки почты
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
description: Администраторы могут научиться использовать отчет о необслуживаемом домене на панели мониторинга потока обработки почты в Центре соответствия требованиям безопасности & для отслеживания сообщений из локальной организации, если домен отправителя не настроен в Microsoft 365.
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826945"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="dc57c-103">Отчет о необслуживаемом домене в Центре безопасности & требованиям</span><span class="sxs-lookup"><span data-stu-id="dc57c-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="dc57c-104">Отчет **о необслуживаемом** домене на [панели мониторинга](mail-flow-insights-v2.md) потока обработки почты в Центре соответствия требованиям безопасности & отображает сведения о сообщениях из локальной организации электронной почты, если домен отправителя не настроен в качестве обслуживаемого домена в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc57c-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="dc57c-105">Microsoft 365 может регулизовать эти сообщения, если у нас есть данные, чтобы подтвердить, что эти сообщения вредоносные.</span><span class="sxs-lookup"><span data-stu-id="dc57c-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="dc57c-106">Поэтому важно понять, что происходит и нужно устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="dc57c-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Мини-приложение домена в необслуживаемом домене на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dc57c-108">Просмотр отчетов по отчетам о необслуживаемых доменах</span><span class="sxs-lookup"><span data-stu-id="dc57c-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="dc57c-109">Щелкнув диаграмму на **мини-приложении** доменов в необслуживаемом домене, вы перейдете к **отчету о необслуживаемом домене.**</span><span class="sxs-lookup"><span data-stu-id="dc57c-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="dc57c-110">По умолчанию отображается активность для всех затронутых соединителей.</span><span class="sxs-lookup"><span data-stu-id="dc57c-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="dc57c-111">Если щелкнуть **"Показать данные",** вы можете выбрать в раскрывающемся списке определенный соединитель.</span><span class="sxs-lookup"><span data-stu-id="dc57c-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="dc57c-112">При наведении курсора мыши на точку данных (день) на диаграмме вы увидите общее количество сообщений для соединителя.</span><span class="sxs-lookup"><span data-stu-id="dc57c-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Просмотр отчетов в отчете о необслуживаемом домене](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dc57c-114">Представление таблицы подробностей для отчета о необслуживаемом домене</span><span class="sxs-lookup"><span data-stu-id="dc57c-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="dc57c-115">При нажатии **кнопки "Просмотр таблицы** сведений" в представлении отчета отобразятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dc57c-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dc57c-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="dc57c-116">**Date**</span></span>
- <span data-ttu-id="dc57c-117">**Имя входящего соединителя**</span><span class="sxs-lookup"><span data-stu-id="dc57c-117">**Inbound connector name**</span></span>
- <span data-ttu-id="dc57c-118">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="dc57c-118">**Sender domain**</span></span>
- <span data-ttu-id="dc57c-119">**Число сообщений**</span><span class="sxs-lookup"><span data-stu-id="dc57c-119">**Message count**</span></span>
- <span data-ttu-id="dc57c-120">**Примеры сообщений:** идентификаторы примера соответствующих сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc57c-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="dc57c-121">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="dc57c-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dc57c-122">Чтобы отправлять отчету отчету в заданный диапазон дат одному или нескольким получателям, нажмите **кнопку "Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="dc57c-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="dc57c-123">Когда вы выбираете строку в таблице, появится всплывающее окно со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="dc57c-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="dc57c-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="dc57c-124">**Date**</span></span>
- <span data-ttu-id="dc57c-125">**Имя входящего соединителя**</span><span class="sxs-lookup"><span data-stu-id="dc57c-125">**Inbound connector name**</span></span>
- <span data-ttu-id="dc57c-126">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="dc57c-126">**Sender domain**</span></span>
- <span data-ttu-id="dc57c-127">**Число сообщений**</span><span class="sxs-lookup"><span data-stu-id="dc57c-127">**Message count**</span></span>
- <span data-ttu-id="dc57c-128">**Примеры сообщений:** можно нажать **кнопку "Просмотреть примеры** сообщений", [чтобы](message-trace-scc.md) просмотреть результаты трассировки для примера затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc57c-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Всплывающий элемент "Сведения" после выбора строки в представлении таблицы "Сведения" в отчете о необслуживаемом домене](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="dc57c-130">Чтобы вернуться в представление отчетов, нажмите **кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="dc57c-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc57c-131">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="dc57c-131">Related topics</span></span>

<span data-ttu-id="dc57c-132">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dc57c-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
