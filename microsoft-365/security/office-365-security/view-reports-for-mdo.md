---
title: Просмотр отчетов Defender для Office 365 отчетов в панели мониторинга отчетов
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Поиск и использование отчетов для Microsoft Defender для Office 365 на портале Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5c45f58ee83de11712b198c85a8e423314289bf
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930232"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="59a39-103">Просмотр отчетов Defender для Office 365 отчетов на панели мониторинга отчетов на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59a39-103">View Defender for Office 365 reports in the Reports dashboard in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="59a39-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="59a39-104">**Applies to**</span></span>
- [<span data-ttu-id="59a39-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="59a39-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="59a39-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59a39-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="59a39-107">Microsoft Defender для Office 365 организаций (например, Microsoft 365 E5 подписки или Microsoft Defender для Office 365 Plan 1 или Microsoft Defender для надстройки Office 365 Plan 2) содержат различные отчеты, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="59a39-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="59a39-108">Если у вас есть [необходимые](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)разрешения, эти отчеты можно просмотреть на  портале Microsoft 365 Defender, переехав в отчеты о совместной работе электронной почты. \>  \> </span><span class="sxs-lookup"><span data-stu-id="59a39-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email collaboration** \> **Email collaboration reports**.</span></span> <span data-ttu-id="59a39-109">Чтобы перейти непосредственно к панели мониторинга Отчетов, откройте <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="59a39-109">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Панель мониторинга отчетов на портале Microsoft 365 Defender](../../media/user-reported-messages.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="59a39-111">отчет о типах файлов Defender для Office 365;</span><span class="sxs-lookup"><span data-stu-id="59a39-111">Defender for Office 365 file types report</span></span>

<span data-ttu-id="59a39-112">Отчет **о типах Office 365** Defender для файлов показывает тип файлов, обнаруженных как вредоносные Сейф [вложения.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="59a39-112">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](safe-attachments.md).</span></span>

 <span data-ttu-id="59a39-113">Совокупное представление отчета позволяет фильтровать в течение 90 дней, в то время как представление детализации позволяет фильтровать только 10 дней.</span><span class="sxs-lookup"><span data-stu-id="59a39-113">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="59a39-114">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите на панель мониторинга отчетов и выберите  \>  Defender для Office 365 **типов файлов.**</span><span class="sxs-lookup"><span data-stu-id="59a39-114">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="59a39-115">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="59a39-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Виджет defender для Office 365 типов файлов в панели мониторинга Отчетов](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="59a39-117">Сведения в этом отчете также доступны в отчете [Defender для Office 365 сообщения](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="59a39-117">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="59a39-118">Представление отчета для отчета о типах Office 365 Defender для</span><span class="sxs-lookup"><span data-stu-id="59a39-118">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="59a39-119">Доступны перечисленные ниже представления.</span><span class="sxs-lookup"><span data-stu-id="59a39-119">The following views are available:</span></span>

- <span data-ttu-id="59a39-120">**Просмотр данных по: Файл**: Диаграмма содержит следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="59a39-120">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="59a39-121">**Вредоносные Excel вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-121">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="59a39-122">**Вредоносные flash-вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-122">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="59a39-123">**Вредоносные вложения PDF**</span><span class="sxs-lookup"><span data-stu-id="59a39-123">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="59a39-124">**Вредоносные PowerPoint вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-124">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="59a39-125">**Вредоносные URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="59a39-125">**Malicious URLs**</span></span>
  - <span data-ttu-id="59a39-126">**Вредоносные вложения Word**</span><span class="sxs-lookup"><span data-stu-id="59a39-126">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="59a39-127">**Вредоносные исполняемые вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-127">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="59a39-128">**Другие**</span><span class="sxs-lookup"><span data-stu-id="59a39-128">**Others**</span></span>

  <span data-ttu-id="59a39-129">При наведении в течение определенного дня (точки данных) можно увидеть разбивку типов вредоносных файлов, обнаруженных Сейф вложениями и защитой от вредоносных программ в [EOP](anti-malware-protection.md). [](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="59a39-129">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Представление файла в отчете о типах Office 365 Defender](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="59a39-131">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-131">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-132">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-132">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-133">Те же значения типа файлов, которые видны на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="59a39-133">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="59a39-134">**Просмотр данных по: Сообщение:** диаграмма содержит следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="59a39-134">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="59a39-135">**Заблокировать доступ**</span><span class="sxs-lookup"><span data-stu-id="59a39-135">**Block access**</span></span>
  - <span data-ttu-id="59a39-136">**Заменены сообщения**</span><span class="sxs-lookup"><span data-stu-id="59a39-136">**Messages replaced**</span></span>
  - <span data-ttu-id="59a39-137">**Мониторинг сообщений**</span><span class="sxs-lookup"><span data-stu-id="59a39-137">**Messages monitored**</span></span>
  - <span data-ttu-id="59a39-138">**Заменено динамической доставкой** электронной почты. Дополнительные сведения см. в приложении [Dynamic Delivery в Сейф вложениях.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="59a39-138">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Представление сообщения в отчете о типах Office 365 Defender](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="59a39-140">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-140">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-141">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-141">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-142">Те же значения диспозиции сообщений, которые доступны на диаграмме, и дополнительные значения **сообщений.**</span><span class="sxs-lookup"><span data-stu-id="59a39-142">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="59a39-143">Представление таблицы сведений для отчета о типах Office 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59a39-143">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="59a39-144">Если щелкнуть таблицу **Просмотр** сведений, в отчете предоставляется представление в режиме почти реального времени всех щелчков, которые происходят в организации за последние 10 дней.</span><span class="sxs-lookup"><span data-stu-id="59a39-144">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="59a39-145">Показанные сведения зависят от диаграммы, которую вы искали:</span><span class="sxs-lookup"><span data-stu-id="59a39-145">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="59a39-146">**Просмотр данных по: Файл**:</span><span class="sxs-lookup"><span data-stu-id="59a39-146">**View data by: File**:</span></span>

  - <span data-ttu-id="59a39-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="59a39-147">**Date**</span></span>
  - <span data-ttu-id="59a39-148">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="59a39-148">**Recipient address**</span></span>
  - <span data-ttu-id="59a39-149">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="59a39-149">**Sender address**</span></span>
  - <span data-ttu-id="59a39-150">**ID сообщения.** Доступно в **поле заглавной области Message-ID** в загонах сообщений и должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="59a39-150">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="59a39-151">Например, значение `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="59a39-151">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="59a39-152">**Файл**</span><span class="sxs-lookup"><span data-stu-id="59a39-152">**File**</span></span>

  <span data-ttu-id="59a39-153">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-153">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-154">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-154">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-155">Те же значения типа файлов, которые видны на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="59a39-155">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="59a39-156">**Просмотр данных по: Сообщение**:</span><span class="sxs-lookup"><span data-stu-id="59a39-156">**View data by: Message**:</span></span>

  - <span data-ttu-id="59a39-157">**Date**</span><span class="sxs-lookup"><span data-stu-id="59a39-157">**Date**</span></span>
  - <span data-ttu-id="59a39-158">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="59a39-158">**Recipient address**</span></span>
  - <span data-ttu-id="59a39-159">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="59a39-159">**Sender address**</span></span>
  - <span data-ttu-id="59a39-160">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="59a39-160">**Message ID**</span></span>
  - <span data-ttu-id="59a39-161">**Файл**</span><span class="sxs-lookup"><span data-stu-id="59a39-161">**File**</span></span>
  - <span data-ttu-id="59a39-162">**Тема**</span><span class="sxs-lookup"><span data-stu-id="59a39-162">**Subject**</span></span>

  <span data-ttu-id="59a39-163">При **нажатии фильтров** можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-163">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="59a39-164">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-164">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-165">Те же значения диспозиции сообщений, которые доступны на диаграмме, и дополнительные значения **сообщений.**</span><span class="sxs-lookup"><span data-stu-id="59a39-165">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="59a39-166">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="59a39-166">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="59a39-167">отчет о действиях с сообщениями в Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="59a39-167">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="59a39-168">В **отчете о диспозиции** сообщений ATP показаны действия, принятые для сообщений электронной почты, которые были обнаружены как вредоносные содержимые.</span><span class="sxs-lookup"><span data-stu-id="59a39-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="59a39-169">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и выберите расположение Office 365  \>  \>  Defender.</span><span class="sxs-lookup"><span data-stu-id="59a39-169">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="59a39-170">Чтобы перейти непосредственно к отчету, откройте <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="59a39-170">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Виджет Office 365 расположения сообщений в панели мониторинга Отчетов](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="59a39-172">Сведения в этом отчете также доступны в отчете о типах [файлов Defender для Office 365 файлов.](#defender-for-office-365-file-types-report)</span><span class="sxs-lookup"><span data-stu-id="59a39-172">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="59a39-173">Представление отчета для отчета о диспозиции Office 365 Defender для сообщения</span><span class="sxs-lookup"><span data-stu-id="59a39-173">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="59a39-174">Доступны перечисленные ниже представления.</span><span class="sxs-lookup"><span data-stu-id="59a39-174">The following views are available:</span></span>

- <span data-ttu-id="59a39-175">**Просмотр данных по: Сообщение:** диаграмма содержит следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="59a39-175">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="59a39-176">**Заблокировать доступ**</span><span class="sxs-lookup"><span data-stu-id="59a39-176">**Block access**</span></span>
  - <span data-ttu-id="59a39-177">**Заменены сообщения**</span><span class="sxs-lookup"><span data-stu-id="59a39-177">**Messages replaced**</span></span>
  - <span data-ttu-id="59a39-178">**Мониторинг сообщений**</span><span class="sxs-lookup"><span data-stu-id="59a39-178">**Messages monitored**</span></span>
  - <span data-ttu-id="59a39-179">**Заменено динамической доставкой** электронной почты. Дополнительные сведения см. в приложении [Dynamic Delivery в Сейф вложениях.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="59a39-179">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Представление сообщения в отчете о типах Office 365 Defender](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="59a39-181">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-181">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-182">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-182">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-183">Те же значения диспозиции сообщений, которые доступны на диаграмме, и дополнительные значения **сообщений.**</span><span class="sxs-lookup"><span data-stu-id="59a39-183">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="59a39-184">**Просмотр данных по: Файл**: Диаграмма содержит следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="59a39-184">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="59a39-185">**Вредоносные Excel вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-185">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="59a39-186">**Вредоносные flash-вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-186">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="59a39-187">**Вредоносные вложения PDF**</span><span class="sxs-lookup"><span data-stu-id="59a39-187">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="59a39-188">**Вредоносные PowerPoint вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-188">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="59a39-189">**Вредоносные URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="59a39-189">**Malicious URLs**</span></span>
  - <span data-ttu-id="59a39-190">**Вредоносные вложения Word**</span><span class="sxs-lookup"><span data-stu-id="59a39-190">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="59a39-191">**Вредоносные исполняемые вложения**</span><span class="sxs-lookup"><span data-stu-id="59a39-191">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="59a39-192">**Другие**</span><span class="sxs-lookup"><span data-stu-id="59a39-192">**Others**</span></span>

  <span data-ttu-id="59a39-193">При наведении в течение определенного дня (точки данных) можно увидеть разбивку типов вредоносных файлов, обнаруженных Сейф вложениями и защитой от вредоносных программ в [EOP](anti-malware-protection.md). [](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="59a39-193">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Представление файла в отчете о типах Office 365 Defender](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="59a39-195">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-195">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-196">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-196">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-197">Те же значения типа файлов, которые видны на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="59a39-197">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="59a39-198">Представление таблицы подробных сведений для отчета Office 365 диспозиции сообщения Defender</span><span class="sxs-lookup"><span data-stu-id="59a39-198">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="59a39-199">Если щелкнуть таблицу **Просмотр** сведений, в отчете предоставляется представление в режиме почти реального времени всех щелчков, которые происходят в организации за последние 10 дней.</span><span class="sxs-lookup"><span data-stu-id="59a39-199">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="59a39-200">Показанные сведения зависят от диаграммы, которую вы искали:</span><span class="sxs-lookup"><span data-stu-id="59a39-200">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="59a39-201">**Просмотр данных по: Сообщение**:</span><span class="sxs-lookup"><span data-stu-id="59a39-201">**View data by: Message**:</span></span>

  - <span data-ttu-id="59a39-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="59a39-202">**Date**</span></span>
  - <span data-ttu-id="59a39-203">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="59a39-203">**Recipient address**</span></span>
  - <span data-ttu-id="59a39-204">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="59a39-204">**Sender address**</span></span>
  - <span data-ttu-id="59a39-205">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="59a39-205">**Message ID**</span></span>
  - <span data-ttu-id="59a39-206">**Файл**</span><span class="sxs-lookup"><span data-stu-id="59a39-206">**File**</span></span>
  - <span data-ttu-id="59a39-207">**Тема**</span><span class="sxs-lookup"><span data-stu-id="59a39-207">**Subject**</span></span>

  <span data-ttu-id="59a39-208">При **нажатии фильтров** можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-208">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="59a39-209">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-209">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-210">Те же значения диспозиции сообщений, которые доступны на диаграмме, и дополнительные значения **сообщений.**</span><span class="sxs-lookup"><span data-stu-id="59a39-210">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="59a39-211">**Просмотр данных по: Файл**:</span><span class="sxs-lookup"><span data-stu-id="59a39-211">**View data by: File**:</span></span>

  - <span data-ttu-id="59a39-212">**Date**</span><span class="sxs-lookup"><span data-stu-id="59a39-212">**Date**</span></span>
  - <span data-ttu-id="59a39-213">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="59a39-213">**Recipient address**</span></span>
  - <span data-ttu-id="59a39-214">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="59a39-214">**Sender address**</span></span>
  - <span data-ttu-id="59a39-215">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="59a39-215">**Message ID**</span></span>
  - <span data-ttu-id="59a39-216">**Файл**</span><span class="sxs-lookup"><span data-stu-id="59a39-216">**File**</span></span>

  <span data-ttu-id="59a39-217">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-217">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-218">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-218">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-219">Те же значения типа файлов, которые видны на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="59a39-219">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="59a39-220">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="59a39-220">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="59a39-221">Отчет о задержке почты</span><span class="sxs-lookup"><span data-stu-id="59a39-221">Mail latency report</span></span>

<span data-ttu-id="59a39-222">В **отчете о задержке** почты показано совокупное представление задержки доставки почты и детонации в организации.</span><span class="sxs-lookup"><span data-stu-id="59a39-222">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="59a39-223">Время доставки почты в службе зависит от ряда факторов, и абсолютное время доставки в секундах часто не является хорошим показателем успешности или проблемы.</span><span class="sxs-lookup"><span data-stu-id="59a39-223">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="59a39-224">Медленное время доставки в один день можно считать средним временем доставки в другой день или наоборот.</span><span class="sxs-lookup"><span data-stu-id="59a39-224">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="59a39-225">Отчет **о задержке** почты пытается квалифицировать доставку сообщений на основе статистических данных о наблюдаемом времени доставки других сообщений:</span><span class="sxs-lookup"><span data-stu-id="59a39-225">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="59a39-226">**50-й процентиль.** Это среднее время доставки сообщений.</span><span class="sxs-lookup"><span data-stu-id="59a39-226">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="59a39-227">Это значение можно рассматривать как среднее время доставки.</span><span class="sxs-lookup"><span data-stu-id="59a39-227">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="59a39-228">**90-й процентиль.** Это указывает на высокую задержку доставки сообщений.</span><span class="sxs-lookup"><span data-stu-id="59a39-228">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="59a39-229">Только 10% сообщений занимает больше времени, чем это значение для доставки.</span><span class="sxs-lookup"><span data-stu-id="59a39-229">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="59a39-230">**99-й процентиль.** Это указывает на наивысшую задержку доставки сообщений.</span><span class="sxs-lookup"><span data-stu-id="59a39-230">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="59a39-231">Клиентская сторона и задержка сети не включаются.</span><span class="sxs-lookup"><span data-stu-id="59a39-231">Client side and network latency are not included.</span></span>

<span data-ttu-id="59a39-232">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите на отчеты электронной почты & совместной работы & отчеты о совместной работе и щелкните Сведения о просмотре в отчете о задержке  \>  \>  **почты.** </span><span class="sxs-lookup"><span data-stu-id="59a39-232">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Mail latency report**.</span></span> <span data-ttu-id="59a39-233">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="59a39-233">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![Виджет отчета о задержке почты в панели мониторинга отчетов](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="59a39-235">Представление отчета для отчета о задержке почты</span><span class="sxs-lookup"><span data-stu-id="59a39-235">Report view for the Mail latency report</span></span>

<span data-ttu-id="59a39-236">При открывании отчета по умолчанию выбирается вкладка **50-й** процентили.</span><span class="sxs-lookup"><span data-stu-id="59a39-236">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="59a39-237">По умолчанию это представление содержит диаграмму, настроенную с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-237">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="59a39-238">**Дата:** последние 7 дней</span><span class="sxs-lookup"><span data-stu-id="59a39-238">**Date**: The last 7 days</span></span>
- <span data-ttu-id="59a39-239">**Просмотр сообщений:**</span><span class="sxs-lookup"><span data-stu-id="59a39-239">**Message View**:</span></span>
  - <span data-ttu-id="59a39-240">Взорванные сообщения</span><span class="sxs-lookup"><span data-stu-id="59a39-240">Detonated messages</span></span>

<span data-ttu-id="59a39-241">На этой диаграмме показаны сообщения, организованные в следующие категории:</span><span class="sxs-lookup"><span data-stu-id="59a39-241">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="59a39-242">**Задержка доставки почты**</span><span class="sxs-lookup"><span data-stu-id="59a39-242">**Mail delivery latency**</span></span>
- <span data-ttu-id="59a39-243">**Задержка детонации**</span><span class="sxs-lookup"><span data-stu-id="59a39-243">**Detonation latency**</span></span>

<span data-ttu-id="59a39-244">При наведении над категорией на диаграмме можно увидеть разбивку задержки в каждой категории.</span><span class="sxs-lookup"><span data-stu-id="59a39-244">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Отчет о задержке почты](../../media/mail-latency-report.png)

<span data-ttu-id="59a39-246">При **нажатии фильтра** в представлении отчета можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-246">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="59a39-247">Все сообщения;</span><span class="sxs-lookup"><span data-stu-id="59a39-247">All messages</span></span>
- <span data-ttu-id="59a39-248">Сообщения, содержащие вложения или URL-адреса</span><span class="sxs-lookup"><span data-stu-id="59a39-248">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="59a39-249">Если щелкнуть **вкладку 90-й** процентили или **вкладку 99-й** процентили, используются те же фильтры по умолчанию из представления **50-го** процентиля.</span><span class="sxs-lookup"><span data-stu-id="59a39-249">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="59a39-250">Представление таблицы сведений для отчета о задержке почты</span><span class="sxs-lookup"><span data-stu-id="59a39-250">Details table view for the Mail latency report</span></span>

<span data-ttu-id="59a39-251">В представлении таблицы сведений показаны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="59a39-251">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="59a39-252">**Date**</span><span class="sxs-lookup"><span data-stu-id="59a39-252">**Date**</span></span>
- <span data-ttu-id="59a39-253">**Percentiles**</span><span class="sxs-lookup"><span data-stu-id="59a39-253">**Percentiles**</span></span>
- <span data-ttu-id="59a39-254">**Количество сообщений**</span><span class="sxs-lookup"><span data-stu-id="59a39-254">**Message count**</span></span>
- <span data-ttu-id="59a39-255">**Общая задержка**</span><span class="sxs-lookup"><span data-stu-id="59a39-255">**Overall latency**</span></span>

![Сведения о задержке почты](../../media/mail-latency-report-details.png)

<span data-ttu-id="59a39-257">Выше показано, что 14 ноября средняя задержка для всех сообщений, доставленных и взорванных, была **108,033** секунды.</span><span class="sxs-lookup"><span data-stu-id="59a39-257">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="59a39-258">Таблица сведений содержит одинаковые сведения на каждой вкладке.</span><span class="sxs-lookup"><span data-stu-id="59a39-258">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="59a39-259">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="59a39-259">Threat protection status report</span></span>

<span data-ttu-id="59a39-260">Отчет **о состоянии** защиты от угроз представляет собой одно представление, которое объединяет сведения о вредоносном контенте и вредоносной электронной почте, обнаруженной и заблокированной Exchange Online Protection (EOP) и Microsoft Defender для Office 365. [](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="59a39-260">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="59a39-261">Дополнительные сведения см. в [отчете о состоянии защиты от угроз.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="59a39-261">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="59a39-262">Отчет об угрозе URL-адреса</span><span class="sxs-lookup"><span data-stu-id="59a39-262">URL threat protection report</span></span>

<span data-ttu-id="59a39-263">В **отчете об угрозе** URL-адресов содержится сводка и представления тенденций для обнаруженных угроз и действия, принятые на щелчках [URL-адресов в Сейф ссылки.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="59a39-263">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="59a39-264">В этом отчете не будут щелкать данные пользователей,  Сейф применяемая политика ссылок имеет выбранный параметр Не отслеживать щелчки пользователя.</span><span class="sxs-lookup"><span data-stu-id="59a39-264">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="59a39-265">Чтобы просмотреть отчет, откройте портал [Microsoft 365 Defender,](https://security.microsoft.com)перейдите в отчеты электронной почты & совместной & отчеты о совместной работе и щелкните Сведения о просмотре в отчете о защите  \>  \>  **URL-адресов.** </span><span class="sxs-lookup"><span data-stu-id="59a39-265">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **URL protection report**.</span></span> <span data-ttu-id="59a39-266">Чтобы перейти непосредственно к отчету, откройте <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="59a39-266">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![Виджет отчета о защите URL-адресов в панели мониторинга отчетов](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="59a39-268">Это отчет *тенденции защиты,* то есть данные представляют тенденции в большом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="59a39-268">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="59a39-269">В результате данные в совокупном представлении здесь недоступны в режиме реального времени, но данные в представлении таблицы сведений имеются, поэтому между этими двумя представлениями может возникнуть небольшое несоответствие.</span><span class="sxs-lookup"><span data-stu-id="59a39-269">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="59a39-270">Представление отчета для отчета об угрозе URL-адреса</span><span class="sxs-lookup"><span data-stu-id="59a39-270">Report view for the URL threat protection report</span></span>

<span data-ttu-id="59a39-271">Отчет **об угрозе URL-адресов** имеет два агрегированных представления, которые обновляются один раз в четыре часа, отображая данные за последние 90 дней:</span><span class="sxs-lookup"><span data-stu-id="59a39-271">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="59a39-272">**Действие защиты url-адресов:** показывает количество нажатий URL-адресов пользователями в организации и результаты щелчка:</span><span class="sxs-lookup"><span data-stu-id="59a39-272">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="59a39-273">**Заблокировано** (пользователю было заблокировано перемещение по URL-адресу)</span><span class="sxs-lookup"><span data-stu-id="59a39-273">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="59a39-274">**Заблокировано и щелкнуло** (пользователь решил продолжить навигацию по URL-адресу)</span><span class="sxs-lookup"><span data-stu-id="59a39-274">**Blocked and clicked through** (the user has chosen to continue navigating to the URL)</span></span>
  - <span data-ttu-id="59a39-275">**Щелкнув во время сканирования** (пользователь щелкнул по ссылке до завершения сканирования)</span><span class="sxs-lookup"><span data-stu-id="59a39-275">**Clicked through during scan** (the user has clicked on the link before the scan was complete)</span></span>

  <span data-ttu-id="59a39-276">Щелчком мыши указывается, что пользователь щелкнул по странице блокировки на вредоносный веб-сайт (администраторы могут отключить щелчок в Сейф ссылки).</span><span class="sxs-lookup"><span data-stu-id="59a39-276">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="59a39-277">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-277">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-278">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-278">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-279">Доступные действия по защите щелчка, а также допустимые **значения** (пользователю было разрешено перемещаться по URL-адресу).</span><span class="sxs-lookup"><span data-stu-id="59a39-279">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL-адрес щелкните представление действия защиты в отчете об угрозе URL-адреса](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="59a39-281">**URL-адрес щелкните** по приложению: отображает количество нажатий URL-адресов приложениями, поддерживаюми Сейф ссылки:</span><span class="sxs-lookup"><span data-stu-id="59a39-281">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="59a39-282">**Клиент электронной почты**</span><span class="sxs-lookup"><span data-stu-id="59a39-282">**Email client**</span></span>
  - <span data-ttu-id="59a39-283">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="59a39-283">**PowerPoint**</span></span>
  - <span data-ttu-id="59a39-284">**Word**</span><span class="sxs-lookup"><span data-stu-id="59a39-284">**Word**</span></span>
  - <span data-ttu-id="59a39-285">**Excel**</span><span class="sxs-lookup"><span data-stu-id="59a39-285">**Excel**</span></span>
  - <span data-ttu-id="59a39-286">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="59a39-286">**OneNote**</span></span>
  - <span data-ttu-id="59a39-287">**Visio**</span><span class="sxs-lookup"><span data-stu-id="59a39-287">**Visio**</span></span>
  - <span data-ttu-id="59a39-288">**Teams**</span><span class="sxs-lookup"><span data-stu-id="59a39-288">**Teams**</span></span>
  - <span data-ttu-id="59a39-289">**Other**</span><span class="sxs-lookup"><span data-stu-id="59a39-289">**Other**</span></span>

  <span data-ttu-id="59a39-290">При **нажатии фильтров** можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="59a39-290">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="59a39-291">**Дата начала и** **дата окончания**</span><span class="sxs-lookup"><span data-stu-id="59a39-291">**Start date** and **End date**</span></span>
  - <span data-ttu-id="59a39-292">Доступные приложения.</span><span class="sxs-lookup"><span data-stu-id="59a39-292">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="59a39-293">Представление таблицы сведений для отчета об угрозе URL-адреса</span><span class="sxs-lookup"><span data-stu-id="59a39-293">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="59a39-294">Если вы **щелкните** таблицу Просмотр сведений, в отчете предоставляется представление в режиме почти реального времени всех щелчков, которые происходят в организации в течение последних 7 дней со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="59a39-294">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="59a39-295">**Время щелчка**</span><span class="sxs-lookup"><span data-stu-id="59a39-295">**Click time**</span></span>
- <span data-ttu-id="59a39-296">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="59a39-296">**User**</span></span>
- <span data-ttu-id="59a39-297">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="59a39-297">**URL**</span></span>
- <span data-ttu-id="59a39-298">**Действие**</span><span class="sxs-lookup"><span data-stu-id="59a39-298">**Action**</span></span>
- <span data-ttu-id="59a39-299">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="59a39-299">**App**</span></span>

<span data-ttu-id="59a39-300">Если щелкнуть **фильтры** в представлении таблицы сведений, можно фильтровать по  тем  же критериям, что и в представлении отчета, а также по доменам или получателям, разделенным запятой.</span><span class="sxs-lookup"><span data-stu-id="59a39-300">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

> [!NOTE]
> <span data-ttu-id="59a39-301">Фильтр **доменов** относится к домену URL-адресов, перечисленным в результатах отчета.</span><span class="sxs-lookup"><span data-stu-id="59a39-301">The **Domains** filter refers to the URL domain listed in the report results.</span></span> 

<span data-ttu-id="59a39-302">Чтобы вернуться к представлению отчетов, нажмите **кнопку Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="59a39-302">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="59a39-303">Дополнительные отчеты для просмотра</span><span class="sxs-lookup"><span data-stu-id="59a39-303">Additional reports to view</span></span>

<span data-ttu-id="59a39-304">Помимо отчетов, описанных в этой статье, доступны еще несколько отчетов, описанных в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="59a39-304">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="59a39-305">Отчет</span><span class="sxs-lookup"><span data-stu-id="59a39-305">Report</span></span>|<span data-ttu-id="59a39-306">Тема</span><span class="sxs-lookup"><span data-stu-id="59a39-306">Topic</span></span>|
|---|---|
|<span data-ttu-id="59a39-307">**Explorer** (Microsoft Defender для Office 365 Plan 2) или обнаружения в режиме реального времени **(Microsoft** Defender для Office 365 Plan 1)</span><span class="sxs-lookup"><span data-stu-id="59a39-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="59a39-308">Обозреватель угроз (и обнаружение в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="59a39-308">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="59a39-309">**Отчеты о безопасности** электронной почты, такие как отчеты о главных отправителей и получателях, почтовый отчет Spoof и отчет о обнаружениях нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="59a39-309">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="59a39-310">Просмотр отчетов о безопасности электронной почты на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59a39-310">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="59a39-311">**Отчеты о потоке** почты, такие как отчет о перенаправе, отчет о состоянии почтового потока и отчет о главных отправителей и получателях.</span><span class="sxs-lookup"><span data-stu-id="59a39-311">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="59a39-312">Просмотр отчетов о потоке почты на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59a39-312">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="59a39-313">**Трассировка URL Сейф ссылки** (только PowerShell).</span><span class="sxs-lookup"><span data-stu-id="59a39-313">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="59a39-314">На выходе этого комлета показаны результаты действий Сейф ссылки за последние семь дней.</span><span class="sxs-lookup"><span data-stu-id="59a39-314">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="59a39-315">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="59a39-315">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="59a39-316">**Результаты трафика почты для EOP** и Microsoft Defender для Office 365 (только PowerShell).</span><span class="sxs-lookup"><span data-stu-id="59a39-316">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="59a39-317">Выход этого комлета содержит сведения о домене, дате, типе события, направлении, действии и графе сообщений.</span><span class="sxs-lookup"><span data-stu-id="59a39-317">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="59a39-318">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="59a39-318">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="59a39-319">**Отчеты о подробностях почты** для EOP и Defender для Office 365 обнаружения (только PowerShell).</span><span class="sxs-lookup"><span data-stu-id="59a39-319">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="59a39-320">Выход этого комлета содержит сведения о вредоносных файлах или URL-адресах, попытках фишинга, обезличив себя и других потенциальных угрозах в электронной почте или файлах.</span><span class="sxs-lookup"><span data-stu-id="59a39-320">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="59a39-321">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="59a39-321">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="59a39-322">Какие разрешения необходимы для просмотра отчетов Defender для Office 365?</span><span class="sxs-lookup"><span data-stu-id="59a39-322">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="59a39-323">Чтобы просмотреть и использовать отчеты, описанные в этой статье, необходимо быть членом одной из следующих групп ролей на портале Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="59a39-323">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="59a39-324">**Управление организацией**</span><span class="sxs-lookup"><span data-stu-id="59a39-324">**Organization Management**</span></span>
- <span data-ttu-id="59a39-325">**Администратор безопасности**</span><span class="sxs-lookup"><span data-stu-id="59a39-325">**Security Administrator**</span></span>
- <span data-ttu-id="59a39-326">**Считыватель безопасности**</span><span class="sxs-lookup"><span data-stu-id="59a39-326">**Security Reader**</span></span>
- <span data-ttu-id="59a39-327">**Глобальный читатель**</span><span class="sxs-lookup"><span data-stu-id="59a39-327">**Global Reader**</span></span>

<span data-ttu-id="59a39-328">Дополнительные сведения см. [в сайте Permissions in the Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="59a39-328">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="59a39-329">**Примечание.** Добавление пользователей к соответствующей роли Azure Active Directory в центре администрирования Microsoft 365 предоставляет пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59a39-329">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="59a39-330">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="59a39-330">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="59a39-331">Что делать, если отчеты не отображают данные?</span><span class="sxs-lookup"><span data-stu-id="59a39-331">What if the reports aren't showing data?</span></span>

<span data-ttu-id="59a39-332">Если в отчете Defender не Office 365 данные, убедитесь, что политики настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="59a39-332">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="59a39-333">Ваша организация должна [иметь Сейф ссылки](set-up-safe-links-policies.md) и политики Сейф вложения, определенные для того, чтобы для defender Office 365 была установлена защита. [](set-up-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="59a39-333">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="59a39-334">Также [см. защиту от нежелательной почты и](anti-spam-and-anti-malware-protection.md)защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="59a39-334">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="59a39-335">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="59a39-335">Related topics</span></span>

[<span data-ttu-id="59a39-336">Интеллектуальные отчеты и сведения на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59a39-336">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="59a39-337">Разрешения на роль (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="59a39-337">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
