---
title: Отчет о невывозе в панели мониторинга потока почты
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
description: Администраторы могут узнать, как использовать отчет о невывозе сведений в панели мониторинга потока почты в Центре соответствия требованиям & безопасности для мониторинга наиболее часто встречающихся кодов ошибок в отчетах о невывозе (также известных как NDRs или отказов сообщений) от отправителей в вашей организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206318"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="78ad4-103">Отчет о невывозе в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="78ad4-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="78ad4-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="78ad4-104">**Applies to**</span></span>
- [<span data-ttu-id="78ad4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="78ad4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="78ad4-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="78ad4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="78ad4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78ad4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="78ad4-108">Отчет  о невывозе в панели [](https://protection.office.com) мониторинга потока почты в Центре соответствия требованиям & безопасности показывает наиболее часто встречаемые коды ошибок в отчетах о невывозе (также известных как NDRs или сообщения отказов) для пользователей в вашей организации. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="78ad4-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="78ad4-109">В этом отчете показаны сведения о NDRs, чтобы устранить проблемы с доставкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="78ad4-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Виджет отчета о невывозе в панели мониторинга потока почты в Центре & безопасности](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="78ad4-111">Представление отчета для отчета о невывозе</span><span class="sxs-lookup"><span data-stu-id="78ad4-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="78ad4-112">Нажав на виджет **отчета** о невывозе, вы сможете получить отчет **о невывозе.**</span><span class="sxs-lookup"><span data-stu-id="78ad4-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="78ad4-113">По умолчанию отображается действие для всех кодов ошибок.</span><span class="sxs-lookup"><span data-stu-id="78ad4-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="78ad4-114">Если вы **нажмете показать данные** для, вы можете выбрать определенный код ошибки из отсев.</span><span class="sxs-lookup"><span data-stu-id="78ad4-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="78ad4-115">Если наведите курсор на определенный цвет (код ошибки) в определенный день на диаграмме, вы увидите общее количество сообщений для ошибки.</span><span class="sxs-lookup"><span data-stu-id="78ad4-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Представление отчета в отчете о не принятых доменах](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="78ad4-117">Представление таблицы сведений для отчета о невывозе</span><span class="sxs-lookup"><span data-stu-id="78ad4-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="78ad4-118">Если **щелкнуть таблицу Просмотр** сведений в представлении отчета, показано следующее:</span><span class="sxs-lookup"><span data-stu-id="78ad4-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="78ad4-119">**Date**</span><span class="sxs-lookup"><span data-stu-id="78ad4-119">**Date**</span></span>
- <span data-ttu-id="78ad4-120">**Код отчета о невывозе**</span><span class="sxs-lookup"><span data-stu-id="78ad4-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="78ad4-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="78ad4-121">**Count**</span></span>
- <span data-ttu-id="78ad4-122">**Пример сообщений:** ID сообщений образца затронутых сообщений.</span><span class="sxs-lookup"><span data-stu-id="78ad4-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="78ad4-123">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="78ad4-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="78ad4-124">Чтобы отправить отчет для определенного диапазона дат одному или несколько получателей, нажмите кнопку **Запрос скачать**.</span><span class="sxs-lookup"><span data-stu-id="78ad4-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="78ad4-125">При выборе строки в таблице вылет появляется со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="78ad4-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="78ad4-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="78ad4-126">**Date**</span></span>
- <span data-ttu-id="78ad4-127">**Код отчета о** невывозе. Вы можете нажать на ссылку, чтобы найти дополнительные сведения о причинах и решениях для определенного кода ошибок.</span><span class="sxs-lookup"><span data-stu-id="78ad4-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="78ad4-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="78ad4-128">**Count**</span></span>
- <span data-ttu-id="78ad4-129">**Примеры сообщений.** Вы можете нажать **просмотреть примеры** сообщений, чтобы просмотреть результаты трассировки сообщений для примера затронутых сообщений. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="78ad4-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Сведения о вылете после выбора строки в представлении таблицы Details в отчете о невывозе](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="78ad4-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="78ad4-131">Related topics</span></span>

<span data-ttu-id="78ad4-132">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="78ad4-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
