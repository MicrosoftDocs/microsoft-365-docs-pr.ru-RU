---
title: Анализ и отчеты клиентов smTP Auth на панели мониторинга потока почты
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
description: Администраторы могут узнать, как использовать анализ и отчет проверки подлинности SMTP на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для отслеживания отправителей электронной почты в организации, которые используют протокол SMTP с проверкой подлинности (SMTP AUTH) для отправки сообщений электронной почты.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: afceb767f6ebfeed96deb6362e05bb088b548c3d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029166"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="604c3-103">Анализ и отчеты клиентов ПРОВЕРКИ SMTP в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="604c3-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="604c3-104">Анализ клиентов проверки почты [](mail-flow-insights-v2.md) **SMTP** на информационной панели потока обработки почты и связанный отчет о клиентах проверки почты [в](#smtp-auth-clients-report) Центре безопасности и соответствия требованиям & освещает использование протокола клиентской отправки SMTP AUTH пользователями или системные учетные записи в организации. [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="604c3-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="604c3-105">Этот устаревший протокол (использующий конечную точку smtp.office365.com) предлагает только базовую проверку подлинности и может использоваться скомпрометированными учетными записями для отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="604c3-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="604c3-106">Анализ и отчет позволяют проверить необычные действия для отправки электронной почты с проверкой SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="604c3-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="604c3-107">Здесь также показаны данные об использовании TLS для клиентов или устройств, использующих AUTH SMTP.</span><span class="sxs-lookup"><span data-stu-id="604c3-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="604c3-108">Виджет указывает количество пользователей или учетных записей служб, которые использовали протокол smTP Auth за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="604c3-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Мини-приложения клиентов проверки почты SMTP на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="604c3-110">Если щелкнуть количество сообщений в виджете, появится элемент **клиента auth SMTP.**</span><span class="sxs-lookup"><span data-stu-id="604c3-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="604c3-111">Этот flyout предоставляет сводное представление об использовании TLS и томах за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="604c3-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Flyout Details after clicking on the SMTP Auth clients widget in the Mail flow dashboard](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="604c3-113">Вы можете щелкнуть ссылку на отчет **smTP Auth клиентов,** чтобы перейти к отчету о клиентах auth SMTP, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="604c3-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="604c3-114">Отчет о клиентах проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="604c3-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="604c3-115">Представление отчета для отчетов клиентов smTP Auth</span><span class="sxs-lookup"><span data-stu-id="604c3-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="604c3-116">По умолчанию в отчете показаны данные за последние 7 дней, но данные доступны за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="604c3-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="604c3-117">Обзорный раздел содержит следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="604c3-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="604c3-118">Просмотр данных **по:** объем отправки: по умолчанию на диаграмме показано количество клиентских сообщений smTP Auth, отправленных со всех доменов ( Показать данные **для:** все домены отправитель выбран по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="604c3-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="604c3-119">Вы можете отфильтровать результаты по определенному домену отправитель, нажав кнопку **"Показать** данные" и выбрав домен отправитель в списке.</span><span class="sxs-lookup"><span data-stu-id="604c3-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="604c3-120">При наведении указателя на определенную точку данных (день) отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="604c3-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Отправка представления тома в отчете клиентов проверки безопасности SMTP в Центре & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="604c3-122">**Просмотр данных с помощью: использование TLS**: диаграмма показывает процент использования TLS для всех клиентских сообщений smTP Auth в течение выбранного периода времени.</span><span class="sxs-lookup"><span data-stu-id="604c3-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="604c3-123">Эта диаграмма позволяет определять пользователей и системные учетные записи, которые по-прежнему используют более старые версии TLS, и принимать с них меры.</span><span class="sxs-lookup"><span data-stu-id="604c3-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Представление использования TLS в отчете клиентов проверки безопасности SMTP в Центре & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="604c3-125">Если **щелкнуть "Фильтры"** в представлении отчета, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="604c3-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="604c3-126">Щелкните **"Отчет о** запросах", чтобы получить более подробную версию отчета в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="604c3-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="604c3-127">Можно указать диапазон дат и получателей для получения отчета.</span><span class="sxs-lookup"><span data-stu-id="604c3-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="604c3-128">Представление таблицы сведений для отчета клиентов smTP Auth</span><span class="sxs-lookup"><span data-stu-id="604c3-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="604c3-129">Если **щелкнуть таблицу "Просмотр** сведений", показанная информация зависит от диаграммы, на которую вы просматривали:</span><span class="sxs-lookup"><span data-stu-id="604c3-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="604c3-130">**Просмотр данных по: объем отправки**: в таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="604c3-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="604c3-131">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="604c3-131">**Sender address**</span></span>
  - <span data-ttu-id="604c3-132">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="604c3-132">**Message count**</span></span>

  <span data-ttu-id="604c3-133">Если выбрать строку, эти же сведения будут показаны во flyout.</span><span class="sxs-lookup"><span data-stu-id="604c3-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="604c3-134">**Просмотр данных по: использование TLS**: в таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="604c3-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="604c3-135">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="604c3-135">**Sender address**</span></span>
  - <span data-ttu-id="604c3-136">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="604c3-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="604c3-137">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="604c3-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="604c3-138">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="604c3-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="604c3-139">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="604c3-139">**Message count**</span></span>

  <span data-ttu-id="604c3-140"><sup>\*</sup> В этом столбце показан процент и количество сообщений от отправитель.</span><span class="sxs-lookup"><span data-stu-id="604c3-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="604c3-141">Если **щелкнуть "Фильтры"** в представлении таблицы сведений, можно указать диапазон дат с датой **начала** и **датой окончания.**</span><span class="sxs-lookup"><span data-stu-id="604c3-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="604c3-142">Если выбрать строку, аналогичные сведения будут показаны во flyout:</span><span class="sxs-lookup"><span data-stu-id="604c3-142">If you select a row, similar details are shown in a flyout:</span></span>

![Flyout details from the details table of the TLS usage view in the SMTP Auth clients report](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="604c3-144">Щелкните **"Отчет о** запросах", чтобы получить более подробную версию отчета в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="604c3-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="604c3-145">Можно указать диапазон дат и получателей для получения отчета.</span><span class="sxs-lookup"><span data-stu-id="604c3-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="604c3-146">Чтобы вернуться в представление отчетов, щелкните **"Просмотреть отчет".**</span><span class="sxs-lookup"><span data-stu-id="604c3-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="604c3-147">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="604c3-147">Related topics</span></span>

<span data-ttu-id="604c3-148">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="604c3-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
