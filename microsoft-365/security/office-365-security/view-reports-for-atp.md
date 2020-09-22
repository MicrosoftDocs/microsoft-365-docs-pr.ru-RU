---
title: Просмотр отчетов для Advanced Threat protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Поиск и использование отчетов для Office 365 Advanced Threat Protection в центре безопасности и &amp; соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90da02c8aa3d50f62bdf4be8c466962da828b23d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196601"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="fee9b-103">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="fee9b-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fee9b-104">В организациях Office 365 Advanced Threat protection (ATP) (например, подписки Microsoft 365 в 1 или более, 1 или 2 надстройки для ATP) содержат различные отчеты, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="fee9b-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="fee9b-105">Если у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-the-atp-reports), вы можете просмотреть эти отчеты в центре безопасности & соответствия требованиям, перейдя **Reports** на \> **панель мониторинга**отчетов.</span><span class="sxs-lookup"><span data-stu-id="fee9b-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="fee9b-106">Чтобы перейти непосредственно к панели мониторинга отчетов, откройте ее <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="fee9b-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Панель мониторинга отчетов в центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="fee9b-108">отчет о типах файлов расширенной защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="fee9b-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="fee9b-109">В отчете " **Расширенные типы файлов для защиты от угроз** " отображаются типы файлов, обнаруженных в качестве вредоносных при [безопасном вложении ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="fee9b-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="fee9b-110">Сводное представление отчета поддерживает 90 дней фильтрации, в то время как в подробном представлении допускается не более 10 дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="fee9b-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="fee9b-111">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **типы файлов Office ATP**.</span><span class="sxs-lookup"><span data-stu-id="fee9b-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="fee9b-112">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="fee9b-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Мини-приложение "типы файлов Office ATP" в панели мониторинга отчетов](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fee9b-114">Сведения, приведенные в этом отчете, также доступны в [отчете об ликвидации сообщений Advanced Threat protection](#advanced-threat-protection-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="fee9b-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="fee9b-115">Представление отчета для отчета о типах файлов Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="fee9b-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="fee9b-116">Доступны следующие представления:</span><span class="sxs-lookup"><span data-stu-id="fee9b-116">The following views are available:</span></span>

- <span data-ttu-id="fee9b-117">**Просмотр данных: File**: диаграмма содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fee9b-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="fee9b-118">**Вредоносные вложения Excel**</span><span class="sxs-lookup"><span data-stu-id="fee9b-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="fee9b-119">**Вредоносные Flash-вложения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="fee9b-120">**Вредоносные вложения в формате PDF**</span><span class="sxs-lookup"><span data-stu-id="fee9b-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="fee9b-121">**Вредоносные вложения PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="fee9b-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="fee9b-122">**Вредоносные URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="fee9b-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="fee9b-123">**Вредоносные вложения Word**</span><span class="sxs-lookup"><span data-stu-id="fee9b-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="fee9b-124">**Вредоносные исполняемые файлы**</span><span class="sxs-lookup"><span data-stu-id="fee9b-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="fee9b-125">**Другие**</span><span class="sxs-lookup"><span data-stu-id="fee9b-125">**Others**</span></span>

  <span data-ttu-id="fee9b-126">Если навести указатель мыши на определенный день (точка данных), можно увидеть разбивку типов вредоносных файлов, обнаруженных [безопасными вложениями ATP](atp-safe-attachments.md) и [защитой от вредоносных программ в EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fee9b-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Представление "файл" в отчете о типах файлов ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="fee9b-128">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-129">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-130">Значения типов файлов, которые отображаются на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="fee9b-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="fee9b-131">**Просмотр данных по: Message**: на диаграмме представлены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fee9b-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="fee9b-132">**Заблокировать доступ**</span><span class="sxs-lookup"><span data-stu-id="fee9b-132">**Block access**</span></span>
  - <span data-ttu-id="fee9b-133">**Замененные сообщения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-133">**Messages replaced**</span></span>
  - <span data-ttu-id="fee9b-134">**Отслеживаемые сообщения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-134">**Messages monitored**</span></span>
  - <span data-ttu-id="fee9b-135">**Замещена динамической доставкой электронной почты**: Дополнительные сведения см [в разделе Динамическая Доставка и предварительный просмотр с безопасными вложениями ATP](dynamic-delivery-and-previewing.md).</span><span class="sxs-lookup"><span data-stu-id="fee9b-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![Представление сообщений в отчете о типах файлов ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="fee9b-137">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-138">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-139">Те же значения расстановки сообщений, которые доступны на диаграмме, и дополнительные **сообщения, переданные** по значению.</span><span class="sxs-lookup"><span data-stu-id="fee9b-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="fee9b-140">Представление таблицы сведений для отчета о типах файлов Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="fee9b-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="fee9b-141">Если вы нажмете кнопку **Просмотр сведений**, отчет предоставляет представление почти в режиме реального времени для всех щелчков, происходящих в Организации за последние 10 дней.</span><span class="sxs-lookup"><span data-stu-id="fee9b-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="fee9b-142">Отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="fee9b-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fee9b-143">**Просмотр данных: файл**:</span><span class="sxs-lookup"><span data-stu-id="fee9b-143">**View data by: File**:</span></span>

  - <span data-ttu-id="fee9b-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="fee9b-144">**Date**</span></span>
  - <span data-ttu-id="fee9b-145">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-145">**Recipient address**</span></span>
  - <span data-ttu-id="fee9b-146">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-146">**Sender address**</span></span>
  - <span data-ttu-id="fee9b-147">**Идентификатор сообщения**: доступен в поле заголовка **Message — ID** в заголовке сообщения и должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="fee9b-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="fee9b-148">Пример значения: `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="fee9b-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="fee9b-149">**File**</span><span class="sxs-lookup"><span data-stu-id="fee9b-149">**File**</span></span>

  <span data-ttu-id="fee9b-150">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-151">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-152">Значения типов файлов, которые отображаются на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="fee9b-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="fee9b-153">**Просмотр данных по: Message**:</span><span class="sxs-lookup"><span data-stu-id="fee9b-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="fee9b-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="fee9b-154">**Date**</span></span>
  - <span data-ttu-id="fee9b-155">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-155">**Recipient address**</span></span>
  - <span data-ttu-id="fee9b-156">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-156">**Sender address**</span></span>
  - <span data-ttu-id="fee9b-157">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-157">**Message ID**</span></span>
  - <span data-ttu-id="fee9b-158">**File**</span><span class="sxs-lookup"><span data-stu-id="fee9b-158">**File**</span></span>
  - <span data-ttu-id="fee9b-159">**Subject**</span><span class="sxs-lookup"><span data-stu-id="fee9b-159">**Subject**</span></span>

  <span data-ttu-id="fee9b-160">При нажатии кнопки **фильтры**можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="fee9b-161">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-162">Те же значения расстановки сообщений, которые доступны на диаграмме, и дополнительные **сообщения, переданные** по значению.</span><span class="sxs-lookup"><span data-stu-id="fee9b-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="fee9b-163">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="fee9b-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="fee9b-164">отчет о ликвидации сообщений расширенной защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="fee9b-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="fee9b-165">В отчете об **ликвидации сообщений ATP** отображаются действия, предпринятые для сообщений электронной почты, которые были обнаружены как вредоносный контент.</span><span class="sxs-lookup"><span data-stu-id="fee9b-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="fee9b-166">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите на **Reports** \> **панель мониторинга** отчетов и выберите вариант **обработки сообщений Office ATP**.</span><span class="sxs-lookup"><span data-stu-id="fee9b-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="fee9b-167">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="fee9b-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Мини-приложение "Расположение сообщений ATP" для Office 365 в панели мониторинга отчетов](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fee9b-169">Сведения, приведенные в этом отчете, также доступны в [отчете "типы файлов Advanced Threat protection](#advanced-threat-protection-file-types-report)".</span><span class="sxs-lookup"><span data-stu-id="fee9b-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="fee9b-170">Представление отчета о расстановке сообщений для расширенной защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="fee9b-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="fee9b-171">Доступны следующие представления:</span><span class="sxs-lookup"><span data-stu-id="fee9b-171">The following views are available:</span></span>

- <span data-ttu-id="fee9b-172">**Просмотр данных по: Message**: на диаграмме представлены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fee9b-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="fee9b-173">**Заблокировать доступ**</span><span class="sxs-lookup"><span data-stu-id="fee9b-173">**Block access**</span></span>
  - <span data-ttu-id="fee9b-174">**Замененные сообщения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-174">**Messages replaced**</span></span>
  - <span data-ttu-id="fee9b-175">**Отслеживаемые сообщения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-175">**Messages monitored**</span></span>
  - <span data-ttu-id="fee9b-176">**Замещена динамической доставкой электронной почты**: Дополнительные сведения см [в разделе Динамическая Доставка и предварительный просмотр с безопасными вложениями ATP](dynamic-delivery-and-previewing.md).</span><span class="sxs-lookup"><span data-stu-id="fee9b-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![Представление сообщений в отчете о типах файлов ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="fee9b-178">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-179">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-180">Те же значения расстановки сообщений, которые доступны на диаграмме, и дополнительные **сообщения, переданные** по значению.</span><span class="sxs-lookup"><span data-stu-id="fee9b-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="fee9b-181">**Просмотр данных: File**: диаграмма содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fee9b-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="fee9b-182">**Вредоносные вложения Excel**</span><span class="sxs-lookup"><span data-stu-id="fee9b-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="fee9b-183">**Вредоносные Flash-вложения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="fee9b-184">**Вредоносные вложения в формате PDF**</span><span class="sxs-lookup"><span data-stu-id="fee9b-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="fee9b-185">**Вредоносные вложения PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="fee9b-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="fee9b-186">**Вредоносные URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="fee9b-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="fee9b-187">**Вредоносные вложения Word**</span><span class="sxs-lookup"><span data-stu-id="fee9b-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="fee9b-188">**Вредоносные исполняемые файлы**</span><span class="sxs-lookup"><span data-stu-id="fee9b-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="fee9b-189">**Другие**</span><span class="sxs-lookup"><span data-stu-id="fee9b-189">**Others**</span></span>

  <span data-ttu-id="fee9b-190">Если навести указатель мыши на определенный день (точка данных), можно увидеть разбивку типов вредоносных файлов, обнаруженных [безопасными вложениями ATP](atp-safe-attachments.md) и [защитой от вредоносных программ в EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fee9b-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Представление "файл" в отчете о типах файлов ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="fee9b-192">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-193">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-194">Значения типов файлов, которые отображаются на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="fee9b-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="fee9b-195">Представление таблицы сведений для отчета об расстановке сообщений Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="fee9b-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="fee9b-196">Если вы нажмете кнопку **Просмотр сведений**, отчет предоставляет представление почти в режиме реального времени для всех щелчков, происходящих в Организации за последние 10 дней.</span><span class="sxs-lookup"><span data-stu-id="fee9b-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="fee9b-197">Отображаемая информация зависит от диаграммы, которую Вы искали:</span><span class="sxs-lookup"><span data-stu-id="fee9b-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fee9b-198">**Просмотр данных по: Message**:</span><span class="sxs-lookup"><span data-stu-id="fee9b-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="fee9b-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="fee9b-199">**Date**</span></span>
  - <span data-ttu-id="fee9b-200">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-200">**Recipient address**</span></span>
  - <span data-ttu-id="fee9b-201">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-201">**Sender address**</span></span>
  - <span data-ttu-id="fee9b-202">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-202">**Message ID**</span></span>
  - <span data-ttu-id="fee9b-203">**File**</span><span class="sxs-lookup"><span data-stu-id="fee9b-203">**File**</span></span>
  - <span data-ttu-id="fee9b-204">**Subject**</span><span class="sxs-lookup"><span data-stu-id="fee9b-204">**Subject**</span></span>

  <span data-ttu-id="fee9b-205">При нажатии кнопки **фильтры**можно изменить результаты с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="fee9b-206">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-207">Те же значения расстановки сообщений, которые доступны на диаграмме, и дополнительные **сообщения, переданные** по значению.</span><span class="sxs-lookup"><span data-stu-id="fee9b-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="fee9b-208">**Просмотр данных: файл**:</span><span class="sxs-lookup"><span data-stu-id="fee9b-208">**View data by: File**:</span></span>

  - <span data-ttu-id="fee9b-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="fee9b-209">**Date**</span></span>
  - <span data-ttu-id="fee9b-210">**Адрес получателя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-210">**Recipient address**</span></span>
  - <span data-ttu-id="fee9b-211">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="fee9b-211">**Sender address**</span></span>
  - <span data-ttu-id="fee9b-212">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="fee9b-212">**Message ID**</span></span>
  - <span data-ttu-id="fee9b-213">**File**</span><span class="sxs-lookup"><span data-stu-id="fee9b-213">**File**</span></span>

  <span data-ttu-id="fee9b-214">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-215">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-216">Значения типов файлов, которые отображаются на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="fee9b-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="fee9b-217">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="fee9b-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="fee9b-218">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="fee9b-218">Threat protection status report</span></span>

<span data-ttu-id="fee9b-219">Отчет **о состоянии защиты от угроз** — это единое представление, объединяющее сведения о вредоносном содержимом и вредоносных сообщениях, обнаруженных и заблокированных службой [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) и Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="fee9b-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="fee9b-220">Дополнительные сведения см. в разделе [отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="fee9b-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="fee9b-221">URL-адрес отчета о защите от угроз</span><span class="sxs-lookup"><span data-stu-id="fee9b-221">URL threat protection report</span></span>

<span data-ttu-id="fee9b-222">В **отчете защита от угроз URL** представлены сводные и трендовые представления для обнаруженных угроз и действий, выполняемых по URL-адресам в рамках [безопасных ссылок ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="fee9b-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="fee9b-223">В этот отчет не будут выбраны данные о пользователях, к которым применяется политика безопасных ссылок, выбран параметр **не отслеживать нажатия пользователем** .</span><span class="sxs-lookup"><span data-stu-id="fee9b-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="fee9b-224">Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **отчет по защите URL-адресов**.</span><span class="sxs-lookup"><span data-stu-id="fee9b-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="fee9b-225">Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="fee9b-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Мини-приложение отчета по защите URL-адресов в панели мониторинга отчетов](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fee9b-227">Это отчет по *тенденциям защиты*, то есть данные представляют тенденции в более крупном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="fee9b-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="fee9b-228">В результате данные в статистическом представлении не доступны в режиме реального времени, но данные в представлении таблицы сведений имеют значение, поэтому вы можете увидеть небольшое расхождение между двумя представлениями.</span><span class="sxs-lookup"><span data-stu-id="fee9b-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="fee9b-229">Представление отчета по URL-адресу отчета по защите от угроз</span><span class="sxs-lookup"><span data-stu-id="fee9b-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="fee9b-230">В отчете по **защите от угроз URL-адресов** имеется два агрегированных представления, которые обновляются каждые четыре часа, в которых отображаются данные за последние 90 дней:</span><span class="sxs-lookup"><span data-stu-id="fee9b-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="fee9b-231">**URL-адрес щелкните действие защиты**: показывает количество щелчков по пользователям в Организации, а также результаты щелчка мыши:</span><span class="sxs-lookup"><span data-stu-id="fee9b-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="fee9b-232">**Заблокировано** (пользователь заблокирован для перехода по URL-адресу)</span><span class="sxs-lookup"><span data-stu-id="fee9b-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="fee9b-233">**Заблокировано и нажато**</span><span class="sxs-lookup"><span data-stu-id="fee9b-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="fee9b-234">**Переход по нажатию во время сканирования**</span><span class="sxs-lookup"><span data-stu-id="fee9b-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="fee9b-235">Щелчок указывает на то, что пользователь выбрал страницу блокировки на вредоносный веб-сайт (администраторы могут отключить функцию "щелкать" в разделе политики безопасных ссылок).</span><span class="sxs-lookup"><span data-stu-id="fee9b-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="fee9b-236">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-237">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-238">Доступные действия по защите от щелчка, а также **разрешенное** значение (пользователю разрешено переходить по URL-адресу).</span><span class="sxs-lookup"><span data-stu-id="fee9b-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL-адрес — представление действий по защите в отчете по защите от угроз в URL-адресе](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="fee9b-240">**URL-адрес щелкните по приложению**: показывает количество щелчков URL-адресов в приложениях, поддерживающих безопасные ссылки Office 365 ATP:</span><span class="sxs-lookup"><span data-stu-id="fee9b-240">**URL click by application**: Shows the number of URL clicks by applications that support Office 365 ATP Safe Links:</span></span>

  - <span data-ttu-id="fee9b-241">**Клиент электронной почты**</span><span class="sxs-lookup"><span data-stu-id="fee9b-241">**Email client**</span></span>
  - <span data-ttu-id="fee9b-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="fee9b-242">**PowerPoint**</span></span>
  - <span data-ttu-id="fee9b-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="fee9b-243">**Word**</span></span>
  - <span data-ttu-id="fee9b-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="fee9b-244">**Excel**</span></span>
  - <span data-ttu-id="fee9b-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="fee9b-245">**OneNote**</span></span>
  - <span data-ttu-id="fee9b-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="fee9b-246">**Visio**</span></span>
  - <span data-ttu-id="fee9b-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="fee9b-247">**Teams**</span></span>
  - <span data-ttu-id="fee9b-248">**Other**</span><span class="sxs-lookup"><span data-stu-id="fee9b-248">**Other**</span></span>

  <span data-ttu-id="fee9b-249">При нажатии кнопки **фильтры**можно изменить отчет с помощью следующих фильтров:</span><span class="sxs-lookup"><span data-stu-id="fee9b-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fee9b-250">**Дата начала** и **Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="fee9b-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fee9b-251">Доступные приложения.</span><span class="sxs-lookup"><span data-stu-id="fee9b-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="fee9b-252">Представление таблицы сведений об URL-адресе защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="fee9b-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="fee9b-253">Если вы нажмете кнопку **Просмотр сведений**, отчет предоставляет представление почти в режиме реального времени для всех щелчков в Организации за последние 7 дней со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="fee9b-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="fee9b-254">**Щелкните время**</span><span class="sxs-lookup"><span data-stu-id="fee9b-254">**Click time**</span></span>
- <span data-ttu-id="fee9b-255">**User**</span><span class="sxs-lookup"><span data-stu-id="fee9b-255">**User**</span></span>
- <span data-ttu-id="fee9b-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="fee9b-256">**URL**</span></span>
- <span data-ttu-id="fee9b-257">**Действие**</span><span class="sxs-lookup"><span data-stu-id="fee9b-257">**Action**</span></span>
- <span data-ttu-id="fee9b-258">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="fee9b-258">**App**</span></span>

<span data-ttu-id="fee9b-259">Если щелкнуть **фильтры** в представлении Таблица сведений, можно отфильтровать по тем же критериям, что и в представлении отчета, а также по **доменам** или **получателям** , разделенным запятыми.</span><span class="sxs-lookup"><span data-stu-id="fee9b-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="fee9b-260">Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="fee9b-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="fee9b-261">Дополнительные отчеты для просмотра</span><span class="sxs-lookup"><span data-stu-id="fee9b-261">Additional reports to view</span></span>

<span data-ttu-id="fee9b-262">Помимо отчетов ATP, описанных в этом разделе, доступны некоторые другие отчеты, как описано в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="fee9b-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="fee9b-263">Отчет</span><span class="sxs-lookup"><span data-stu-id="fee9b-263">Report</span></span>|<span data-ttu-id="fee9b-264">Раздел</span><span class="sxs-lookup"><span data-stu-id="fee9b-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="fee9b-265">**Explorer** (план ATP 2) или **Обнаружение в режиме реального времени** (план ATP 1)</span><span class="sxs-lookup"><span data-stu-id="fee9b-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="fee9b-266">Обозреватель угроз (и обнаружение в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="fee9b-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="fee9b-267">**Отчеты о безопасности электронной почты**, например отчет о самых отправителях и получателях, отчет о поддельной почте и обнаружение нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="fee9b-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="fee9b-268">Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fee9b-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="fee9b-269">**Отчеты о движении по почте**, например отчет о перенаправлении, отчет о состоянии Mailflow и отчеты верхнего отправителя и получателей.</span><span class="sxs-lookup"><span data-stu-id="fee9b-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="fee9b-270">Просмотр отчетов о движении по почте в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fee9b-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="fee9b-271">**Трассировка URL-адресов для безопасных ссылок ATP** (только для PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fee9b-271">**URL trace for ATP Safe Links** (PowerShell only).</span></span> <span data-ttu-id="fee9b-272">Выходные данные этого командлета показывают результаты действий безопасных ссылок ATP за прошедшие семь дней.</span><span class="sxs-lookup"><span data-stu-id="fee9b-272">The output of this cmdlet shows you the results of ATP Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="fee9b-273">Get — Урлтраце</span><span class="sxs-lookup"><span data-stu-id="fee9b-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="fee9b-274">**Результаты почтового трафика для EOP и ATP** (только для PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fee9b-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="fee9b-275">Выходные данные этого командлета содержат сведения о домене, дате, типе события, направлении, действии и количестве сообщений.</span><span class="sxs-lookup"><span data-stu-id="fee9b-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="fee9b-276">Get — Маилтраффикатпрепорт</span><span class="sxs-lookup"><span data-stu-id="fee9b-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="fee9b-277">**Подробные отчеты об обнаружении EOP и ATP** (только для PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fee9b-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="fee9b-278">Выходные данные этого командлета содержат сведения о вредоносных файлах или URL-адресах, фишинговых попытках, олицетворении и других потенциальных угрозах в электронной почте или файлах.</span><span class="sxs-lookup"><span data-stu-id="fee9b-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="fee9b-279">Get — Маилдетаилатпрепорт</span><span class="sxs-lookup"><span data-stu-id="fee9b-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="fee9b-280">Какие разрешения необходимы для просмотра отчетов ATP?</span><span class="sxs-lookup"><span data-stu-id="fee9b-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="fee9b-281">Для просмотра и использования отчетов, описанных в этом разделе, **необходима соответствующая роль, назначенная для центра безопасности и центра &amp; администрирования Exchange**.</span><span class="sxs-lookup"><span data-stu-id="fee9b-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="fee9b-282">Для центра безопасности & соответствия требованиям необходимо назначить одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="fee9b-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="fee9b-283">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="fee9b-283">Organization Management</span></span>
  - <span data-ttu-id="fee9b-284">Администратор безопасности (это можно назначить в центре администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )).</span><span class="sxs-lookup"><span data-stu-id="fee9b-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="fee9b-285">Оператор безопасности (это можно назначить в центре администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )).</span><span class="sxs-lookup"><span data-stu-id="fee9b-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="fee9b-286">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="fee9b-286">Security Reader</span></span>

- <span data-ttu-id="fee9b-287">Для Exchange Online необходимо назначить одну из следующих ролей в центре администрирования Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) или с помощью командлетов PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="fee9b-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="fee9b-288">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="fee9b-288">Organization Management</span></span>
  - <span data-ttu-id="fee9b-289">Управление организацией с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="fee9b-289">View-only Organization Management</span></span>
  - <span data-ttu-id="fee9b-290">Роль получателей с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="fee9b-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="fee9b-291">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="fee9b-291">Compliance Management</span></span>

<span data-ttu-id="fee9b-292">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="fee9b-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="fee9b-293">Разрешения в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fee9b-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="fee9b-294">Разрешения компонентов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fee9b-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="fee9b-295">Что делать, если в отчетах данные не отображаются?</span><span class="sxs-lookup"><span data-stu-id="fee9b-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="fee9b-296">Если вы не видите данные в отчетах ATP, дважды проверьте правильность настройки политик.</span><span class="sxs-lookup"><span data-stu-id="fee9b-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="fee9b-297">Для вашей организации должны быть определены политики [безопасных ссылок ATP](set-up-atp-safe-links-policies.md) и [политики безопасных вложений ATP](set-up-atp-safe-attachments-policies.md) для обеспечения безопасности ATP.</span><span class="sxs-lookup"><span data-stu-id="fee9b-297">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="fee9b-298">Кроме того, вы можете увидеть [защиту от нежелательной почты и вредоносных программ в Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fee9b-298">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fee9b-299">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="fee9b-299">Related topics</span></span>

[<span data-ttu-id="fee9b-300">Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fee9b-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="fee9b-301">Разрешения ролей (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fee9b-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
