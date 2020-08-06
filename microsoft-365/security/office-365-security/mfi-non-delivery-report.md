---
title: Отчет о недоставке на панели мониторинга почтового процесса
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
description: Администраторы могут узнать, как использовать отчет о недоставке в панели мониторинга "почта" в центре безопасности & соответствия требованиям для отслеживания наиболее часто встречающихся кодов ошибок в отчетах о недоставке (также известных как отчеты о недоставке или сообщениях Bounce) от отправителей в вашей организации.
ms.openlocfilehash: d45382ab5c7e0d0a73487740544f20b9c25a3ad1
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577436"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="1e99b-103">Отчет о недоставке в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="1e99b-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="1e99b-104">**Отчет о недоставке** в [панели мониторинга "почтовый ящик](mail-flow-insights-v2.md) " в центре безопасности & соответствия требованиям показывает наиболее часто встречающиеся коды ошибок в отчетах о недоставке (также известных как отчеты о недоставке или сообщениях Bounce) для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="1e99b-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="1e99b-105">В этом отчете представлены сведения о отчетах о недоставке для устранения проблем с доставкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1e99b-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Мини-приложение отчетов о недоставке в панели мониторинга "почтовые ящики" в центре безопасности & соответствия требованиям](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="1e99b-107">Представление отчета для отчета о недоставке</span><span class="sxs-lookup"><span data-stu-id="1e99b-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="1e99b-108">Если щелкнуть мини **-приложение отчета о недоставке** , вы перейдете к **отчету о недоставке**.</span><span class="sxs-lookup"><span data-stu-id="1e99b-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="1e99b-109">По умолчанию отображается действие для всех кодов ошибок.</span><span class="sxs-lookup"><span data-stu-id="1e99b-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="1e99b-110">Если нажать кнопку **Показать данные для**, вы можете выбрать определенный код ошибки из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="1e99b-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="1e99b-111">При наведении указателя на определенный цвет (код ошибки) в определенный день на диаграмме отображается общее количество сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1e99b-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Представление отчета в отчете о необслуживаемом домене](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="1e99b-113">Представление таблицы сведений для отчета о недоставке</span><span class="sxs-lookup"><span data-stu-id="1e99b-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="1e99b-114">Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1e99b-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="1e99b-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="1e99b-115">**Date**</span></span>
- <span data-ttu-id="1e99b-116">**Код отчета о недоставке**</span><span class="sxs-lookup"><span data-stu-id="1e99b-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="1e99b-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="1e99b-117">**Count**</span></span>
- <span data-ttu-id="1e99b-118">**Примеры сообщений**: идентификаторы сообщений с примерами затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="1e99b-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="1e99b-119">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="1e99b-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1e99b-120">Чтобы отправить отчет по определенному диапазону дат одному или нескольким получателям, щелкните **запросить скачивание**.</span><span class="sxs-lookup"><span data-stu-id="1e99b-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="1e99b-121">При выборе строки в таблице появляется раскрывающееся меню со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="1e99b-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="1e99b-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="1e99b-122">**Date**</span></span>
- <span data-ttu-id="1e99b-123">**Код отчета о недоставке**: вы можете щелкнуть ссылку, чтобы найти дополнительные сведения о причинах и решениях для конкретного кода ошибки.</span><span class="sxs-lookup"><span data-stu-id="1e99b-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="1e99b-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="1e99b-124">**Count**</span></span>
- <span data-ttu-id="1e99b-125">**Примеры сообщений**: вы можете щелкнуть **Просмотреть примеры сообщений** , чтобы просмотреть результаты [трассировки сообщений](message-trace-scc.md) для примера затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="1e99b-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Всплывающее меню сведений после выбора строки в представлении таблицы сведений в отчете о недоставке](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="1e99b-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1e99b-127">Related topics</span></span>

<span data-ttu-id="1e99b-128">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="1e99b-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
