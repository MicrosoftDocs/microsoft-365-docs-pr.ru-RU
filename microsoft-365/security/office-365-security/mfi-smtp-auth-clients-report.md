---
title: Аналитика клиентов проверки подлинности SMTP и отчетности на панели мониторинга потока обработки почты
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
description: Администраторы могут научиться использовать аналитические сведения о проверке подлинности SMTP (Sight) и создавать отчеты на панели мониторинга потока обработки почты в Центре соответствия требованиям безопасности & для отслеживания отправителей электронной почты в своей организации, использующих проверку подлинности SMTP AUTH для отправки электронных сообщений.
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826873"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="a9d23-103">аналитические сведения клиентов проверки подлинности SMTP и отчетности в Центре безопасности & соответствия требованиям;</span><span class="sxs-lookup"><span data-stu-id="a9d23-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="a9d23-104">Клиенты **проверки подлинности SMTP Auth** стали доступны на панели [мониторинга потока](mail-flow-insights-v2.md) обработки почты и связанных [клиентах SMTP Auth,](#smtp-auth-clients-report) которые используют в вашей организации протокол клиентской отправки с проверкой подлинности SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="a9d23-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="a9d23-105">Этот устаревший протокол (использующий конечную точку smtp.office365.com) предлагает только обычную проверку подлинности и подумает возможность использования скомпрометированными учетными записями для отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a9d23-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="a9d23-106">С помощью аналитических данных и отчетности можно проверить необычной активность при отправке электронной почты с проверкой подлинности SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="a9d23-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="a9d23-107">Здесь также показаны данные об использовании TLS для клиентов или устройств, использующих проверку подлинности SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="a9d23-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="a9d23-108">Мини-приложение указывает количество пользователей или учетных записей служб, которые за последние 7 дней использовали протокол проверки подлинности SMTP.</span><span class="sxs-lookup"><span data-stu-id="a9d23-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Мини-приложение SMTP Auth клиентов на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="a9d23-110">Если вы щелкнете количество сообщений, на странице "Мини-приложение" **появятся всплывающие** элементы клиентов проверки подлинности SMTP.</span><span class="sxs-lookup"><span data-stu-id="a9d23-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="a9d23-111">Во всплывающем элементе собрано сводное представление об использовании TLS и томах за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="a9d23-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Всплывающие элементы после щелчка мини-приложения клиентов проверки подлинности SMTP на панели мониторинга потока обработки почты](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="a9d23-113">Вы можете **щелкнуть ссылку на отчет о клиентах** проверки подлинности SMTP, чтобы перейти к отчету о клиентах проверки подлинности SMTP, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="a9d23-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="a9d23-114">Отчет о клиентах проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="a9d23-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="a9d23-115">Представление отчета для клиентов проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="a9d23-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="a9d23-116">По умолчанию в отчете отображаются данные за последние 7 дней, однако данные доступны за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="a9d23-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="a9d23-117">Раздел "Обзор" содержит следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="a9d23-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="a9d23-118">**Просмотр данных по тому: по**умолчанию на диаграмме показано количество клиентских сообщений для проверки подлинности SMTP, отправленных из всех доменов **(Показать данные для: "По** умолчанию выбраны все домены отправителей").</span><span class="sxs-lookup"><span data-stu-id="a9d23-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="a9d23-119">Вы можете отфильтровать результаты, выбрав их, **щелкнув "Показать данные** для" и выбрав домен отправителя из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a9d23-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="a9d23-120">Если наведите курсор определенной точки данных (день), отобразится количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="a9d23-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Отправка представления томов в отчет клиентах проверки подлинности SMTP в Центре безопасности & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="a9d23-122">**Просмотр данных по: использованию TLS**— на диаграмме показан процент использования TLS для всех клиентских сообщений с проверкой подлинности SMTP за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="a9d23-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="a9d23-123">На этой диаграмме можно выявлять пользователей и системные учетные записи, которые до этого используют более ранние версии TLS.</span><span class="sxs-lookup"><span data-stu-id="a9d23-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Представление использования TLS в отчете "Клиенты проверки подлинности SMTP" в Центре & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="a9d23-125">При выборе **фильтров в представлении** отчета можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="a9d23-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a9d23-126">Щелкните **"Запрос"** для получения более подробной версии отчета в электронном письме.</span><span class="sxs-lookup"><span data-stu-id="a9d23-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="a9d23-127">Вы можете указать диапазон дат и получателей для получения отчета.</span><span class="sxs-lookup"><span data-stu-id="a9d23-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="a9d23-128">Представление таблицы подробностей для отчета о клиентах проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="a9d23-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="a9d23-129">При нажатии **кнопки "Просмотр таблицы**сведений" показанная информация зависит от диаграммы, на которую вы ищете:</span><span class="sxs-lookup"><span data-stu-id="a9d23-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a9d23-130">**Просмотр данных по: отправка тома:** в таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d23-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="a9d23-131">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="a9d23-131">**Sender address**</span></span>
  - <span data-ttu-id="a9d23-132">**Число сообщений**</span><span class="sxs-lookup"><span data-stu-id="a9d23-132">**Message count**</span></span>

  <span data-ttu-id="a9d23-133">Если выбрана строка, то такие же сведения отобразятся во всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="a9d23-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="a9d23-134">**Просмотр данных по: использованию TLS.** В таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a9d23-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="a9d23-135">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="a9d23-135">**Sender address**</span></span>
  - <span data-ttu-id="a9d23-136">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9d23-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a9d23-137">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9d23-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a9d23-138">**TLS1.2 %**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9d23-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a9d23-139">**Число сообщений**</span><span class="sxs-lookup"><span data-stu-id="a9d23-139">**Message count**</span></span>

  <span data-ttu-id="a9d23-140"><sup>\*</sup> В этом столбце отображаются как количество сообщений от отправителя, так и количество сообщений от отправителя.</span><span class="sxs-lookup"><span data-stu-id="a9d23-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="a9d23-141">При выборе **фильтров в представлении** таблицы сведений можно указать диапазон дат с **начальной** и **конечной датами.**</span><span class="sxs-lookup"><span data-stu-id="a9d23-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a9d23-142">При выборе строки похожие сведения будут показаны во всплывающем окне:</span><span class="sxs-lookup"><span data-stu-id="a9d23-142">If you select a row, similar details are shown in a flyout:</span></span>

![Всплывающую информацию из таблицы "Сведения" представления использования TLS в отчете о клиентах проверки подлинности SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="a9d23-144">Щелкните **"Запрос"** для получения более подробной версии отчета в электронном письме.</span><span class="sxs-lookup"><span data-stu-id="a9d23-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="a9d23-145">Вы можете указать диапазон дат и получателей для получения отчета.</span><span class="sxs-lookup"><span data-stu-id="a9d23-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="a9d23-146">Чтобы вернуться в представление отчетов, нажмите **кнопку "Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="a9d23-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9d23-147">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a9d23-147">Related topics</span></span>

<span data-ttu-id="a9d23-148">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a9d23-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
