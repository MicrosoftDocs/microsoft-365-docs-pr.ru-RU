---
title: Сведения и отчеты клиентов SMTP Auth на панели мониторинга потока почты
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
description: Администраторы могут узнать, как использовать анализ SMTP Auth и отчет в панели мониторинга потока почты в Центре соответствия требованиям & безопасности для мониторинга отправителей электронной почты в своей организации, которые используют проверку подлинности SMTP (SMTP AUTH) для отправки сообщений электронной почты.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205288"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="1ff9b-103">Сведения и отчеты клиентов SMTP Auth в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="1ff9b-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ff9b-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-104">**Applies to**</span></span>
- [<span data-ttu-id="1ff9b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ff9b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1ff9b-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="1ff9b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1ff9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ff9b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1ff9b-108">Сведения о клиентах **SMTP Auth** в панели мониторинга потока почты [](https://protection.office.com) и связанном отчете клиентов [](mail-flow-insights-v2.md) [SMTP Auth](#smtp-auth-clients-report) в Центре соответствия требованиям & безопасности подчеркивают использование протокола отправки клиентов SMTP AUTH пользователями или системных учетных записей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="1ff9b-109">Этот устаревший протокол (в котором используется конечная точка smtp.office365.com) предлагает только базовую проверку подлинности и может использоваться скомпрометированными учетными записями для отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="1ff9b-110">Анализ и отчет позволяют проверить необычные действия для отправки электронной почты SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="1ff9b-111">В нем также показаны данные об использовании TLS для клиентов или устройств с использованием SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="1ff9b-112">Виджет указывает количество пользователей или учетных записей служб, которые использовали протокол SMTP Auth за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Виджет клиентов SMTP Auth в панели мониторинга потока почты в Центре & безопасности](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="1ff9b-114">Если щелкнуть число сообщений в виджете, появится **вылет клиентов SMTP Auth.**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="1ff9b-115">В вылете предоставляется сводное представление об использовании TLS и томах за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Подробные сведения о вылете после нажатия на виджет клиентов SMTP Auth в панели мониторинга потока почты](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="1ff9b-117">Чтобы перейти к отчету о клиентах **SMTP Auth,** как описано в следующем разделе, вы можете нажать ссылку smTP Auth.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="1ff9b-118">Отчет о клиентах проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="1ff9b-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="1ff9b-119">Представление отчета для отчета клиентов SMTP Auth</span><span class="sxs-lookup"><span data-stu-id="1ff9b-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="1ff9b-120">По умолчанию в отчете показаны данные за последние 7 дней, но данные доступны за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="1ff9b-121">Раздел обзор содержит следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="1ff9b-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="1ff9b-122">Просмотр данных **по:** Отправка тома. По умолчанию на диаграмме показано количество клиентских сообщений SMTP Auth, отправленных из всех доменов (Показать данные **для:** Все домены отправитель выбирается по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1ff9b-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="1ff9b-123">Вы можете фильтровать результаты в определенный домен отправитель, щелкнув **показать** данные для и выбрав домен отправитель из списка выпаданий.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="1ff9b-124">Если зависать в определенной точке данных (день), отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Отправка представления тома в отчете клиентов SMTP Auth в Центре & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="1ff9b-126">**Просмотр данных по: Использование TLS.** На диаграмме показан процент использования TLS для всех клиентских сообщений SMTP Auth в течение выбранного периода времени.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="1ff9b-127">Эта диаграмма позволяет выявлять и принимать меры для пользователей и системных учетных записей, которые по-прежнему используют более старые версии TLS.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Представление об использовании TLS в отчете клиентов SMTP Auth в Центре & безопасности](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="1ff9b-129">Если щелкнуть **фильтры** в представлении отчета, можно указать диапазон дат **с** датой начала и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1ff9b-130">Щелкните **отчет Запрос,** чтобы получить более подробную версию отчета в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="1ff9b-131">Вы можете указать диапазон дат и получателей для получения отчета.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="1ff9b-132">Представление таблицы сведений для отчета клиентов SMTP Auth</span><span class="sxs-lookup"><span data-stu-id="1ff9b-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="1ff9b-133">Если **щелкнуть таблицу Просмотр** сведений, показанные сведения зависят от диаграммы, на которую вы смотрите:</span><span class="sxs-lookup"><span data-stu-id="1ff9b-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1ff9b-134">**Просмотр данных по: Объем отправки:** в таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1ff9b-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="1ff9b-135">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-135">**Sender address**</span></span>
  - <span data-ttu-id="1ff9b-136">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-136">**Message count**</span></span>

  <span data-ttu-id="1ff9b-137">Если выбрать строку, в вылете показано одно и то же.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="1ff9b-138">**Просмотр данных по: Использование TLS:** в таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1ff9b-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="1ff9b-139">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-139">**Sender address**</span></span>
  - <span data-ttu-id="1ff9b-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1ff9b-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="1ff9b-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1ff9b-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="1ff9b-142">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1ff9b-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="1ff9b-143">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-143">**Message count**</span></span>

  <span data-ttu-id="1ff9b-144"><sup>\*</sup> В этом столбце показан процент и количество сообщений от отправитель.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="1ff9b-145">Если щелкнуть **Фильтры** в представлении таблицы сведений, можно указать диапазон дат с датой начала и  **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="1ff9b-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="1ff9b-146">Если вы выбираете строку, аналогичные сведения показаны в вылете:</span><span class="sxs-lookup"><span data-stu-id="1ff9b-146">If you select a row, similar details are shown in a flyout:</span></span>

![Сведения о вылете из таблицы сведений представления использования TLS в отчете клиентов SMTP Auth](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="1ff9b-148">Щелкните **отчет Запрос,** чтобы получить более подробную версию отчета в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="1ff9b-149">Вы можете указать диапазон дат и получателей для получения отчета.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="1ff9b-150">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1ff9b-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1ff9b-151">Related topics</span></span>

<span data-ttu-id="1ff9b-152">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="1ff9b-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
