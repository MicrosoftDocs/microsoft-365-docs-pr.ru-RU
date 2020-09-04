---
title: Отчет о необслуживаемых доменах в панели мониторинга почтового процесса
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
description: Администраторы могут узнать, как использовать отчет о непринятых доменах в панели мониторинга "почтовые ящики" в центре безопасности & соответствия требованиям для отслеживания сообщений из локальной организации, где домен отправителя не настроен в Microsoft 365.
ms.openlocfilehash: 02692fbded20aa5062ce8add83925fb65c116630
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358582"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="7c716-103">Отчет о необслуживаемом домене в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7c716-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="7c716-104">Отчет о **непринятом домене** в [панели мониторинга "почтовый](mail-flow-insights-v2.md) индекс" в [центре безопасности & соответствия требованиям](https://protection.office.com) отображает сведения об сообщениях из локальной организации электронной почты, в которых домен отправителя не настроен как обслуживаемый домен в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7c716-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="7c716-105">Microsoft 365 может регулировать эти сообщения, если у нас есть данные для подтверждения того, что назначение этих сообщений является вредоносным.</span><span class="sxs-lookup"><span data-stu-id="7c716-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="7c716-106">Поэтому важно понимать, что происходит и как устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="7c716-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Необслуживаемый мини-приложение домена на панели мониторинга "почтовый ящик" в центре безопасности & соответствия требованиям](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="7c716-108">Представление отчета для отчета о непринятом домене</span><span class="sxs-lookup"><span data-stu-id="7c716-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="7c716-109">Если щелкнуть диаграмму в мини **-приложении необслуживаемого домена** , вы перейдете к отчету о **непринятом домене** .</span><span class="sxs-lookup"><span data-stu-id="7c716-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="7c716-110">По умолчанию отображается действие для всех затронутых соединителей.</span><span class="sxs-lookup"><span data-stu-id="7c716-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="7c716-111">Если нажать кнопку **Показать данные для**, вы можете выбрать конкретный соединитель из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7c716-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="7c716-112">При наведении курсора на точку данных (день) на диаграмме отображается общее число сообщений для соединителя.</span><span class="sxs-lookup"><span data-stu-id="7c716-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Представление отчета в отчете о необслуживаемом домене](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="7c716-114">Представление таблицы сведений для отчета о непринятом домене</span><span class="sxs-lookup"><span data-stu-id="7c716-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="7c716-115">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="7c716-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="7c716-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="7c716-116">**Date**</span></span>
- <span data-ttu-id="7c716-117">**Имя входящего соединителя**</span><span class="sxs-lookup"><span data-stu-id="7c716-117">**Inbound connector name**</span></span>
- <span data-ttu-id="7c716-118">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="7c716-118">**Sender domain**</span></span>
- <span data-ttu-id="7c716-119">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="7c716-119">**Message count**</span></span>
- <span data-ttu-id="7c716-120">**Примеры сообщений**: идентификаторы сообщений с примерами затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="7c716-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="7c716-121">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="7c716-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="7c716-122">Чтобы отправить отчет по определенному диапазону дат одному или нескольким получателям, щелкните **запросить скачивание**.</span><span class="sxs-lookup"><span data-stu-id="7c716-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="7c716-123">При выборе строки в таблице появляется раскрывающееся меню со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="7c716-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="7c716-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="7c716-124">**Date**</span></span>
- <span data-ttu-id="7c716-125">**Имя входящего соединителя**</span><span class="sxs-lookup"><span data-stu-id="7c716-125">**Inbound connector name**</span></span>
- <span data-ttu-id="7c716-126">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="7c716-126">**Sender domain**</span></span>
- <span data-ttu-id="7c716-127">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="7c716-127">**Message count**</span></span>
- <span data-ttu-id="7c716-128">**Примеры сообщений**: вы можете щелкнуть **Просмотреть примеры сообщений** , чтобы просмотреть результаты [трассировки сообщений](message-trace-scc.md) для примера затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="7c716-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Всплывающее меню сведений после выбора строки в представлении таблицы сведений в отчете о неодобренном домене](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="7c716-130">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="7c716-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c716-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7c716-131">Related topics</span></span>

<span data-ttu-id="7c716-132">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="7c716-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
