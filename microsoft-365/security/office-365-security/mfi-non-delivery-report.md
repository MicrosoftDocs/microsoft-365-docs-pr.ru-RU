---
title: Отчет о недоставке на панели мониторинга потока обработки почты
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
description: Администраторы могут научиться использовать отчет о недоставке на панели мониторинга потока обработки почты в Центре соответствия требованиям безопасности & для отслеживания наиболее часто возникающих ошибок в отчетах о недоставке (также называемых сообщениями о недоставке) от отправителей в вашей организации.
ms.openlocfilehash: bdc2a2a16f76f4e6ada629c82b86423422ab56c9
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826921"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="dd0fd-103">Отчет о недоставке в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dd0fd-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="dd0fd-104">Отчет **о недоставке на панели мониторинга** [потока](mail-flow-insights-v2.md) обработки почты в Центре безопасности & показывает коды ошибок в отчетах о недоставке (также известных как сообщения о недоставке) для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="dd0fd-105">Этот отчет содержит подробные сведения об отчетах о недоставке электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Мини-приложение с отчетом о недоставке на панели мониторинга потока обработки почты в Центре безопасности & Compliance Center](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="dd0fd-107">Представление отчета о недоставке</span><span class="sxs-lookup"><span data-stu-id="dd0fd-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="dd0fd-108">Если щелкнуть **мини-приложение отчетов** о недоставке, откроется отчет **о недоставке.**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="dd0fd-109">По умолчанию отображается активность для всех кодов ошибок.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="dd0fd-110">Если щелкнуть **"Показать данные",** можно выбрать в раскрывающемся списке определенный код ошибки.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="dd0fd-111">Если наведите указатель мыши на определенный цвет (код ошибки) на конкретном дне диаграммы, вы увидите общее количество сообщений для ошибки.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Просмотр отчетов в отчете о необслуживаемом домене](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="dd0fd-113">Представление таблицы подробностей для отчета о недоставке</span><span class="sxs-lookup"><span data-stu-id="dd0fd-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="dd0fd-114">При нажатии **кнопки "Просмотр таблицы** сведений" в представлении отчета отобразятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dd0fd-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dd0fd-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-115">**Date**</span></span>
- <span data-ttu-id="dd0fd-116">**Код отчета о недоставке**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="dd0fd-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-117">**Count**</span></span>
- <span data-ttu-id="dd0fd-118">**Примеры сообщений:** идентификаторы примера соответствующих сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="dd0fd-119">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dd0fd-120">Чтобы отправлять отчету отчету в заданный диапазон дат одному или нескольким получателям, нажмите **кнопку "Запросить загрузку".**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="dd0fd-121">Когда вы выбираете строку в таблице, появится всплывающее окно со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="dd0fd-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="dd0fd-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-122">**Date**</span></span>
- <span data-ttu-id="dd0fd-123">**Код отчета о недоставке. С**помощью ссылки можно получить дополнительные сведения о причинах и решениях конкретных ошибок.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="dd0fd-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="dd0fd-124">**Count**</span></span>
- <span data-ttu-id="dd0fd-125">**Примеры сообщений:** можно нажать **кнопку "Просмотреть примеры** сообщений", [чтобы](message-trace-scc.md) просмотреть результаты трассировки для примера затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd0fd-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Всплывающие элементы подробности после выбора строки в представлении таблицы "Сведения" в отчете о недоставке](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="dd0fd-127">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="dd0fd-127">Related topics</span></span>

<span data-ttu-id="dd0fd-128">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dd0fd-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
