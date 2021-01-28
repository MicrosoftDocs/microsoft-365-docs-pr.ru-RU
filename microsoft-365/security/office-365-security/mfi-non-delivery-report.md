---
title: Отчет о не доставке на панели мониторинга потока почты
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
description: Администраторы могут узнать, как использовать отчет о неотвечающих сообщениях на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для отслеживания наиболее часто встречающихся кодов ошибок в отчетах о доставке (также известных как сообщения о возврате) от отправителей в организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029838"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="21de8-103">Отчет о не доставке в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="21de8-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="21de8-104">Отчет  о не доставке на панели [](https://protection.office.com) мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & показывает наиболее часто встречавались коды ошибок в отчетах о не доставке (также известных как сообщения о возврате) для пользователей в организации. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="21de8-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="21de8-105">В этом отчете показаны подробные отчеты о отчетах о доставке, с которыми можно устранять проблемы с доставкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="21de8-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Мини-приложения отчетов о не доставке на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="21de8-107">Представление отчета о невыдаваемом сообщении</span><span class="sxs-lookup"><span data-stu-id="21de8-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="21de8-108">Щелкнув **мини-виджет** "Отчет о доставке", вы йдите в отчет о **доставке.**</span><span class="sxs-lookup"><span data-stu-id="21de8-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="21de8-109">По умолчанию отображается действие для всех кодов ошибок.</span><span class="sxs-lookup"><span data-stu-id="21de8-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="21de8-110">Если нажать **кнопку "Показать данные",** можно выбрать определенный код ошибки из dropdown.</span><span class="sxs-lookup"><span data-stu-id="21de8-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="21de8-111">Если наведите курсор на определенный цвет (код ошибки) в определенный день диаграммы, вы увидите общее количество сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="21de8-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Представление отчета в отчете о не принятых доменах](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="21de8-113">Представление таблицы сведений для отчета о не доставке</span><span class="sxs-lookup"><span data-stu-id="21de8-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="21de8-114">Если **щелкнуть "Просмотреть таблицу сведений"** в представлении отчета, будут показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="21de8-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="21de8-115">**Дата**</span><span class="sxs-lookup"><span data-stu-id="21de8-115">**Date**</span></span>
- <span data-ttu-id="21de8-116">**Код отчета о не доставке**</span><span class="sxs-lookup"><span data-stu-id="21de8-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="21de8-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="21de8-117">**Count**</span></span>
- <span data-ttu-id="21de8-118">**Примеры сообщений:** ИД сообщения с образцом затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="21de8-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="21de8-119">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="21de8-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="21de8-120">Чтобы отправить отчет по электронной почте для определенного диапазона дат одному или более получателям, нажмите кнопку **"Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="21de8-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="21de8-121">При выборе строки в таблице появится flyout со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="21de8-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="21de8-122">**Дата**</span><span class="sxs-lookup"><span data-stu-id="21de8-122">**Date**</span></span>
- <span data-ttu-id="21de8-123">**Код отчета о не** доставке: вы можете щелкнуть ссылку, чтобы найти дополнительные сведения о причинах и решениях определенного кода ошибки.</span><span class="sxs-lookup"><span data-stu-id="21de8-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="21de8-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="21de8-124">**Count**</span></span>
- <span data-ttu-id="21de8-125">**Примеры сообщений:** можно щелкнуть "Просмотреть **примеры** сообщений", чтобы просмотреть результаты трассировки для примера затронутых сообщений. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="21de8-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Flyout Details after selecting a row in Details table view in the Non-delivery report](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="21de8-127">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="21de8-127">Related topics</span></span>

<span data-ttu-id="21de8-128">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="21de8-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
