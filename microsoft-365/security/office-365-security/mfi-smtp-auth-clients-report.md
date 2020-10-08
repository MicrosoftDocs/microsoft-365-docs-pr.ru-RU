---
title: Проверка подлинности клиентов проверки подлинности SMTP и отчета в панели мониторинга почтового процесса
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
description: Администраторы могут узнать, как использовать аналитическую проверку подлинности SMTP и отчет в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям для отслеживания отправителей электронной почты в Организации, использующих протокол SMTP с проверкой подлинности (SMTP AUTH) для отправки сообщений электронной почты.
ms.openlocfilehash: 7ca673e5ecc92c28996a976c26a38ae570f16203
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199245"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="7cb34-103">Проверка подлинности клиентов проверки подлинности SMTP и составление отчетов в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7cb34-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7cb34-104">**Клиенты проверки подлинности SMTP** просматриваются в [панели мониторинга почтовых ящиков](mail-flow-insights-v2.md) и сопоставленных с ним [клиентов проверки подлинности SMTP](#smtp-auth-clients-report) в [центре безопасности & соответствия требованиям](https://protection.office.com) выделите использование протокола отправки SMTP-протокола проверки подлинности SMTP пользователями или системными учетными записями в Организации.</span><span class="sxs-lookup"><span data-stu-id="7cb34-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="7cb34-105">Этот устаревший протокол (использующий конечную точку smtp.office365.com) обеспечивает только обычную проверку подлинности и может использоваться скомпрометированными учетными записями для отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7cb34-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="7cb34-106">В отчете об отправку и отчете можно проверить необычные действия для отправки сообщений с проверкой подлинности SMTP.</span><span class="sxs-lookup"><span data-stu-id="7cb34-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="7cb34-107">В нем также отображаются данные об использовании TLS для клиентов или устройств с использованием проверки подлинности SMTP.</span><span class="sxs-lookup"><span data-stu-id="7cb34-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="7cb34-108">Мини-приложение указывает количество пользователей или учетных записей служб, которые использовали протокол проверки подлинности SMTP за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="7cb34-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Мини-приложение "клиенты проверки подлинности SMTP" в панели мониторинга "почта" в центре безопасности & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="7cb34-110">Если щелкнуть число сообщений в мини-приложении, появится всплывающее окно **почтовых клиентов проверки подлинности SMTP** .</span><span class="sxs-lookup"><span data-stu-id="7cb34-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="7cb34-111">Всплывающее окно содержит сводное представление об использовании и томах TLS за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="7cb34-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Всплывающее меню "сведения" после щелчка мини-приложения "клиенты проверки подлинности SMTP" на панели мониторинга обработки почты](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="7cb34-113">Вы можете щелкнуть ссылку **отчет о клиентах проверки подлинности SMTP** , чтобы перейти к отчету проверки подлинности SMTP, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="7cb34-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="7cb34-114">Отчет о клиентах проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="7cb34-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="7cb34-115">Представление отчета для отчета по клиентам проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="7cb34-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="7cb34-116">По умолчанию в отчете отображаются данные за последние 7 дней, но данные доступны в течение последних 90 дней.</span><span class="sxs-lookup"><span data-stu-id="7cb34-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="7cb34-117">Раздел Обзор содержит следующие диаграммы:</span><span class="sxs-lookup"><span data-stu-id="7cb34-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="7cb34-118">**Просмотр данных: отправка тома**: по умолчанию на диаграмме показано количество сообщений клиентов проверки подлинности SMTP, отправленных из всех доменов (**Показать данные для: все домены отправителя** выбраны по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7cb34-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="7cb34-119">Вы можете отфильтровать результаты в определенном домене отправителя, нажав кнопку **Показать данные** и выбрав домен отправителя из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7cb34-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="7cb34-120">При наведении курсора на определенную точку данных (день) отображается количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="7cb34-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Отправка представления громкости в отчете о клиентах проверки подлинности SMTP в центре безопасности & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="7cb34-122">**Просмотр данных по: использование TLS**: на диаграмме показан процент использования TLS для всех сообщений клиентов проверки подлинности SMTP в течение выбранного периода времени.</span><span class="sxs-lookup"><span data-stu-id="7cb34-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="7cb34-123">Эта диаграмма позволяет определять и выполнять действия с пользователями и системными учетными записями, которые все еще используют старые версии протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="7cb34-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Представление использования TLS в отчете по проверке подлинности SMTP в центре безопасности & соответствия требованиям](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="7cb34-125">Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.</span><span class="sxs-lookup"><span data-stu-id="7cb34-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="7cb34-126">Щелкните **запросить отчет** , чтобы получить более подробную версию отчета в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7cb34-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="7cb34-127">Вы можете указать диапазон дат и получателей, которые будут получать отчет.</span><span class="sxs-lookup"><span data-stu-id="7cb34-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="7cb34-128">Представление таблицы сведений для отчета по клиентам проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="7cb34-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="7cb34-129">Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="7cb34-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7cb34-130">**Просмотр данных: отправка тома**: в таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="7cb34-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="7cb34-131">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="7cb34-131">**Sender address**</span></span>
  - <span data-ttu-id="7cb34-132">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="7cb34-132">**Message count**</span></span>

  <span data-ttu-id="7cb34-133">Если выбрана строка, в всплывающем меню отображаются те же сведения.</span><span class="sxs-lookup"><span data-stu-id="7cb34-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="7cb34-134">**Просмотр данных по: использование TLS**: в таблице показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="7cb34-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="7cb34-135">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="7cb34-135">**Sender address**</span></span>
  - <span data-ttu-id="7cb34-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7cb34-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="7cb34-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7cb34-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="7cb34-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7cb34-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="7cb34-139">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="7cb34-139">**Message count**</span></span>

  <span data-ttu-id="7cb34-140"><sup>\*</sup> В этом столбце показаны процентное отношение и количество сообщений от отправителя.</span><span class="sxs-lookup"><span data-stu-id="7cb34-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="7cb34-141">Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.</span><span class="sxs-lookup"><span data-stu-id="7cb34-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="7cb34-142">Если выбрана строка, похожие сведения отображаются в всплывающем меню:</span><span class="sxs-lookup"><span data-stu-id="7cb34-142">If you select a row, similar details are shown in a flyout:</span></span>

![Всплывающее окно со сведениями из таблицы "сведения" в представлении "Использование TLS" в отчете о клиентах проверки подлинности SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="7cb34-144">Щелкните **запросить отчет** , чтобы получить более подробную версию отчета в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7cb34-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="7cb34-145">Вы можете указать диапазон дат и получателей, которые будут получать отчет.</span><span class="sxs-lookup"><span data-stu-id="7cb34-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="7cb34-146">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="7cb34-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7cb34-147">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7cb34-147">Related topics</span></span>

<span data-ttu-id="7cb34-148">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="7cb34-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
