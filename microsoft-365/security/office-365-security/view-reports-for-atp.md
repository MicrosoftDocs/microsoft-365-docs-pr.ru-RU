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
ms.openlocfilehash: c71bef11e574593d821b992f3a5037dbf127d5d2
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936999"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="a64f5-103">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="a64f5-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="a64f5-104">Если в Организации имеется [Office 365 Advanced Threat protection](office-365-atp.md) (ATP), и у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-the-atp-reports), вы можете использовать несколько отчетов ATP в центре безопасности и &amp; соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a64f5-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a64f5-105">(Перейдите в раздел **отчеты** \> **Панель мониторинга**.)</span><span class="sxs-lookup"><span data-stu-id="a64f5-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![&amp;Информационная панель центра соответствия требованиям безопасности поможет вам узнать, где работает Расширенная защита от угроз](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="a64f5-107">К отчетам ATP относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="a64f5-107">ATP reports include the following:</span></span>

- <span data-ttu-id="a64f5-108">[отчет о состоянии защиты от угроз](#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="a64f5-108">[Threat Protection Status report](#threat-protection-status-report)</span></span>
- <span data-ttu-id="a64f5-109">[отчет о типах файлов ATP](#atp-file-types-report);</span><span class="sxs-lookup"><span data-stu-id="a64f5-109">[ATP File Types report](#atp-file-types-report)</span></span>
- <span data-ttu-id="a64f5-110">[отчет о действиях с сообщениями в ATP](#atp-message-disposition-report);</span><span class="sxs-lookup"><span data-stu-id="a64f5-110">[ATP Message Disposition report](#atp-message-disposition-report)</span></span>
- <span data-ttu-id="a64f5-111">[Обнаружение или проводник в режиме реального времени](threat-explorer.md) (в зависимости от того, установлен ли для Office 365 ATP 1 (план 1) или 2)</span><span class="sxs-lookup"><span data-stu-id="a64f5-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="a64f5-112">... [и многое другое](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="a64f5-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="a64f5-113">В этой статье приводятся общие сведения об отчетах ATP и способах их использования.</span><span class="sxs-lookup"><span data-stu-id="a64f5-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="a64f5-114">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="a64f5-114">Threat Protection Status report</span></span>

<span data-ttu-id="a64f5-115">Отчет **о состоянии защиты от угроз** — это единое представление, объединяющее сведения о вредоносном содержимом и вредоносных сообщениях, обнаруженных и заблокированных службой [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) и [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="a64f5-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="a64f5-116">Этот отчет полезен для просмотра обнаружений с течением времени (до 90 дней), а также позволяет администраторам безопасности определять тенденции или определять необходимость внесения изменений в политики.</span><span class="sxs-lookup"><span data-stu-id="a64f5-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="a64f5-117">В отчете представлено общее количество уникальных сообщений электронной почты с вредоносным содержимым, такими как файлы или адреса веб-сайтов (URL-адреса), которые были заблокированы ядром защиты от вредоносных программ, функции [автоматического очистки (ZAP)](zero-hour-auto-purge.md)и ATP, такие как [безопасные ссылки](atp-safe-links.md)ATP, [безопасные вложения ATP](atp-safe-attachments.md)и [антифишинговые](set-up-anti-phishing-policies.md)функции ATP.</span><span class="sxs-lookup"><span data-stu-id="a64f5-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="a64f5-118">Фильтры и разбиения данных позволяют более детально классифицировать информацию, приведенную в этом отчете.</span><span class="sxs-lookup"><span data-stu-id="a64f5-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="a64f5-119">В частности, есть меню "разбивка по", включенное для просмотров **электронной почты** \> **Phish** и **Email** \> **вредоносных программ**электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a64f5-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="a64f5-120">Данные будут разбиты на следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="a64f5-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="a64f5-121">По типу политики</span><span class="sxs-lookup"><span data-stu-id="a64f5-121">By policy type</span></span>|<span data-ttu-id="a64f5-122">Какая политика позволила бы перехватывать эти угрозы?</span><span class="sxs-lookup"><span data-stu-id="a64f5-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="a64f5-123">По технологии обнаружения</span><span class="sxs-lookup"><span data-stu-id="a64f5-123">By detection technology</span></span>|<span data-ttu-id="a64f5-124">Какова базовая технология Майкрософт, которая перехватила угрозу?</span><span class="sxs-lookup"><span data-stu-id="a64f5-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="a64f5-125">По состоянию доставки</span><span class="sxs-lookup"><span data-stu-id="a64f5-125">By delivery status</span></span>|<span data-ttu-id="a64f5-126">Каково Последнее состояние доставки сообщений электронной почты, обнаруженных как угрозы?</span><span class="sxs-lookup"><span data-stu-id="a64f5-126">What was the final delivery status of email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="a64f5-127">Электронная почта > фишинг | Представления вредоносных программ имеют детализированные разбивки на отображаемые технологии обнаружения, а также такие категории, как *репутация файлов, генерируемые atpми*, *файлы детонации*, *URL-адреса детонации*, *Защита от подделки: DMARC сбой*, например, полезные сведения о том, какой компонент в вашей организации перехватывает угрозы.</span><span class="sxs-lookup"><span data-stu-id="a64f5-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Раскрывающийся отчет о состоянии защиты от угроз, покрывающийся на "разрыв вниз".](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="a64f5-129">В этих представлениях можно экспортировать с помощью нажатия кнопки (в phishing- **Email** \> **атаках**электронной **Email** почты, \> **вредоносных программ**и **контентных** \> **вредоносных** программ).</span><span class="sxs-lookup"><span data-stu-id="a64f5-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="a64f5-130">Объединенные данные, экспортированные на компьютер, можно открыть в Excel.</span><span class="sxs-lookup"><span data-stu-id="a64f5-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![На этом рисунке показана функция "экспортировать как" в меню для представления вредоносных программ, непосредственно между созданием расписания и отчетом запроса.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

> [!NOTE]
> <span data-ttu-id="a64f5-132">Максимальное число записей, которые можно экспортировать для **фишинга** и **вредоносных программ** , находится в разделе 10000.</span><span class="sxs-lookup"><span data-stu-id="a64f5-132">The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="a64f5-133">При экспорте представления экспортируются только самые последние записи 10000.</span><span class="sxs-lookup"><span data-stu-id="a64f5-133">If you export a view, only the most recent 10000 entries are exported.</span></span> <span data-ttu-id="a64f5-134">В экспортированных данных столбец _число сообщений_ представляет количество сообщений, обнаруженных технологией обнаружения и типом политики.</span><span class="sxs-lookup"><span data-stu-id="a64f5-134">On the exported data, the _message count_ column represents the number of messages detected by the detection technology and policy type.</span></span>    

<span data-ttu-id="a64f5-135">В представлениях "Обзор" и "Электронная почта" отображаются данные в течение часов обработки, а не через 24 часа (требование повтора.</span><span class="sxs-lookup"><span data-stu-id="a64f5-135">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="a64f5-136">При увеличении скорости получается сигнал очистки.</span><span class="sxs-lookup"><span data-stu-id="a64f5-136">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="a64f5-137">Отчет о состоянии защиты от угроз доступен клиентам, у которых есть [Office 365 ATP](office-365-atp.md) или [Exchange Online Protection](exchange-online-protection-overview.md)(EOP); Однако сведения, отображаемые в отчете о состоянии защиты от угроз для клиентов ATP, скорее всего, будут содержать данные, отличные от данных, которые могут видеть пользователи EOP.</span><span class="sxs-lookup"><span data-stu-id="a64f5-137">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-overview.md)) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="a64f5-138">Например, отчет о состоянии защиты от угроз для клиентов ATP будет содержать сведения о [вредоносных файлах, обнаруженных в SharePoint Online, OneDrive или Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a64f5-138">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="a64f5-139">Такие сведения относятся к ATP, поэтому клиенты, у которых есть EOP, но не ATP, не увидят эти сведения в отчете о состоянии защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="a64f5-139">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="a64f5-140">Чтобы просмотреть отчет о состоянии защиты от угроз, в [центре безопасности и &amp; соответствия требованиям](https://protection.office.com)выберите **Reports** \> **Dashboard** \> **состояние защиты от угроз**для отчетов.</span><span class="sxs-lookup"><span data-stu-id="a64f5-140">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![Отчет о состоянии защиты от угроз для ATP](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="a64f5-142">Чтобы получить подробные сведения о состоянии дня, наведите указатель на диаграмму.</span><span class="sxs-lookup"><span data-stu-id="a64f5-142">To get detailed status for a day, hover over the graph.</span></span>

![Данные о состоянии ATP Threat protection за день](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="a64f5-144">По умолчанию в отчете о состоянии защиты от угроз отображаются данные за прошедшие семь дней.</span><span class="sxs-lookup"><span data-stu-id="a64f5-144">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="a64f5-145">Тем не менее, вы можете выбрать **фильтры** и изменить диапазон дат для просмотра данных в течение до 90 дней для представления "Статистическое представление" и 30 дней для подробного представления.</span><span class="sxs-lookup"><span data-stu-id="a64f5-145">However, you can choose **Filters** and change the date range to view data for up to 90 days for the aggregate view and 30 days for the detail view.</span></span> <span data-ttu-id="a64f5-146">(Если вы используете пробную подписку, вы можете использовать не более 30 дней данных.)</span><span class="sxs-lookup"><span data-stu-id="a64f5-146">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![Фильтры состояния защиты от угроз ATP](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="a64f5-148">Вы также можете использовать меню **Просмотр данных,** чтобы изменить сведения, отображаемые в отчете.</span><span class="sxs-lookup"><span data-stu-id="a64f5-148">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![Параметры просмотра для отчета о состоянии защиты от угроз для ATP](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="a64f5-150">Отчет о состоянии защиты URL-адресов</span><span class="sxs-lookup"><span data-stu-id="a64f5-150">URL Protection Status report</span></span>

<span data-ttu-id="a64f5-151">В этом отчете собраны данные на основе данных, и обнаружены угрозы для каждого щелчка (в то время как большинство других отчетов по электронной почте относятся к данным одного сообщения).</span><span class="sxs-lookup"><span data-stu-id="a64f5-151">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="a64f5-152">Этот отчет предназначен для отображения угроз, которые поступают из гиперссылок в сообщениях электронной почты и документы по щелчку.</span><span class="sxs-lookup"><span data-stu-id="a64f5-152">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="a64f5-153">Существует два представления:</span><span class="sxs-lookup"><span data-stu-id="a64f5-153">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="a64f5-154">Действие по защите URL-адресов</span><span class="sxs-lookup"><span data-stu-id="a64f5-154">URL click protection action</span></span>|<span data-ttu-id="a64f5-155">Просмотр числа заблокированных, заблокированных, заблокированных и переопределяемых пользователями URL-адресов, которые переопределяются с помощью команды "нажми" и разрешены пользователем.</span><span class="sxs-lookup"><span data-stu-id="a64f5-155">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="a64f5-156">URL-адрес щелчка по приложению</span><span class="sxs-lookup"><span data-stu-id="a64f5-156">URL click by application</span></span>|<span data-ttu-id="a64f5-157">Просмотрите приложение, из которого был выбран URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="a64f5-157">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="a64f5-158">В таблице сведения вы сможете просмотреть дополнительные сведения о времени и сведениях о пользователях.</span><span class="sxs-lookup"><span data-stu-id="a64f5-158">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="a64f5-159">Наконец, обратите внимание, что в отчете о состоянии защиты URL-адресов отображается функция защиты от безопасных ссылок ATP, поэтому для пользователей с включенными безопасными ссылками на ATP будут отображаться данные, отраженные в этом отчете.</span><span class="sxs-lookup"><span data-stu-id="a64f5-159">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="a64f5-160">Это отчет по *тенденциям защиты*, то есть данные представляют тенденции в более крупном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="a64f5-160">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="a64f5-161">В результате данные в статистическом представлении не доступны в режиме реального времени, но данные в представлении таблицы сведений имеют значение, поэтому вы можете увидеть небольшое расхождение между двумя представлениями.</span><span class="sxs-lookup"><span data-stu-id="a64f5-161">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="a64f5-162">отчет о типах файлов ATP;</span><span class="sxs-lookup"><span data-stu-id="a64f5-162">ATP File Types report</span></span>

<span data-ttu-id="a64f5-163">В отчете " **типы файлов ATP** " отображаются типы файлов, обнаруженных в качестве вредоносных при [безопасном вложении ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="a64f5-163">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="a64f5-164">Чтобы просмотреть этот отчет, в [центре безопасности и &amp; соответствия требованиям](https://protection.office.com)перейдите к **Reports** \> типам файлов **панели мониторинга** отчетов \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="a64f5-164">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![отчет о типах файлов ATP;](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="a64f5-166">Если навести указатель мыши на определенный день, можно увидеть разбивку типов вредоносных файлов, обнаруженных [безопасными вложениями ATP](atp-safe-attachments.md) и [ &amp; защитой от нежелательной почты](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a64f5-166">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span> <span data-ttu-id="a64f5-167">Сводное представление отчета поддерживает 90 дней фильтрации, в то время как в подробном представлении допускается не более десяти дней фильтрации.</span><span class="sxs-lookup"><span data-stu-id="a64f5-167">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span> 
  
![Данные о типах файлов ATP в день](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="a64f5-169">отчет о действиях с сообщениями в ATP;</span><span class="sxs-lookup"><span data-stu-id="a64f5-169">ATP Message Disposition report</span></span>

<span data-ttu-id="a64f5-170">В отчете об **ликвидации сообщений ATP** отображаются действия, предпринятые для сообщений электронной почты, которые были обнаружены как вредоносный контент.</span><span class="sxs-lookup"><span data-stu-id="a64f5-170">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="a64f5-171">Чтобы просмотреть этот отчет, в [центре безопасности и &amp; соответствия требованиям](https://protection.office.com)перейдите к разделу **Reports** \> **панель мониторинга** отчетов \> **ATP Message Disposition**.</span><span class="sxs-lookup"><span data-stu-id="a64f5-171">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![Отчет об ликвидации сообщений ATP](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="a64f5-173">При наведении указателя мыши на полоску на диаграмме можно просмотреть, какие действия были предприняты для обнаруженных сообщений электронной почты в этот день.</span><span class="sxs-lookup"><span data-stu-id="a64f5-173">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![Данные отчета об ликвидации сообщений ATP за день](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="a64f5-175">Дополнительные отчеты для просмотра</span><span class="sxs-lookup"><span data-stu-id="a64f5-175">Additional reports to view</span></span>

<span data-ttu-id="a64f5-176">Помимо отчетов ATP, описанных в этой статье, доступны некоторые другие отчеты, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a64f5-176">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="a64f5-177">**Отчет (ы)**</span><span class="sxs-lookup"><span data-stu-id="a64f5-177">**Report(s)**</span></span>|<span data-ttu-id="a64f5-178">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a64f5-178">**Details**</span></span>|
|<span data-ttu-id="a64f5-179">**Проводника** или **Обнаружение в режиме реального времени**: (Office 365 ATP, план 2, у пользователей есть Explorer; Пользователи Office 365 ATP 1 (план 1) имеют обнаружение в режиме реального времени.)</span><span class="sxs-lookup"><span data-stu-id="a64f5-179">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="a64f5-180">Обозреватель угроз (и обнаружение в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="a64f5-180">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="a64f5-181">**Отчеты о безопасности электронной почты**, например отчет о самых отправителях и получателях, отчет о поддельной почте и отчет об обнаружении нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a64f5-181">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="a64f5-182">Просмотр отчетов о безопасности электронной почты в &amp; центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a64f5-182">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="a64f5-183">**Трассировка URL-адресов для безопасных ссылок ATP**: (это отчет, созданный с помощью PowerShell.) В этом отчете представлены результаты действий безопасных ссылок ATP за прошедшие семь (7) дней.</span><span class="sxs-lookup"><span data-stu-id="a64f5-183">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="a64f5-184">Справочные материалы по командлету Get – Урлтраце</span><span class="sxs-lookup"><span data-stu-id="a64f5-184">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="a64f5-185">**Результаты EOP и ATP**: (это настраиваемый отчет, созданный с помощью PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a64f5-185">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="a64f5-186">Этот отчет содержит такие сведения, как домен, Дата, тип события, направление, действие и количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="a64f5-186">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="a64f5-187">Справочные материалы по командлету Get – Маилтраффикатпрепорт</span><span class="sxs-lookup"><span data-stu-id="a64f5-187">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="a64f5-188">**Обнаружения EOP и ATP**: (это настраиваемый отчет, созданный с помощью PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a64f5-188">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="a64f5-189">Этот отчет содержит сведения о вредоносных файлах или URL-адресах, фишинговых попытках, олицетворении и других потенциальных угрозах в электронной почте или файлах.</span><span class="sxs-lookup"><span data-stu-id="a64f5-189">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="a64f5-190">Справочные материалы по командлету Get – Маилдетаилатпрепорт</span><span class="sxs-lookup"><span data-stu-id="a64f5-190">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="a64f5-191">Какие разрешения необходимы для просмотра отчетов ATP?</span><span class="sxs-lookup"><span data-stu-id="a64f5-191">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="a64f5-192">Для просмотра и использования отчетов, описанных в этой статье, **необходимо назначить соответствующую роль для &amp; центра безопасности и центра администрирования Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a64f5-192">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="a64f5-193">Для &amp; центра соответствия требованиям безопасности необходимо назначить одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="a64f5-193">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="a64f5-194">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="a64f5-194">Organization Management</span></span>
  - <span data-ttu-id="a64f5-195">Администратор безопасности (это можно назначить в центре администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )).</span><span class="sxs-lookup"><span data-stu-id="a64f5-195">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="a64f5-196">Оператор безопасности (это можно назначить в центре администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )).</span><span class="sxs-lookup"><span data-stu-id="a64f5-196">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="a64f5-197">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="a64f5-197">Security Reader</span></span>

- <span data-ttu-id="a64f5-198">Для Exchange Online необходимо назначить одну из следующих ролей в центре администрирования Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) или с помощью командлетов PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="a64f5-198">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="a64f5-199">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="a64f5-199">Organization Management</span></span>
  - <span data-ttu-id="a64f5-200">Управление организацией с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="a64f5-200">View-only Organization Management</span></span>
  - <span data-ttu-id="a64f5-201">Роль получателей с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="a64f5-201">View-Only Recipients role</span></span>
  - <span data-ttu-id="a64f5-202">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="a64f5-202">Compliance Management</span></span>

<span data-ttu-id="a64f5-203">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="a64f5-203">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="a64f5-204">Разрешения в центре безопасности и &amp; соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a64f5-204">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="a64f5-205">Разрешения компонентов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a64f5-205">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="a64f5-206">Что делать, если в отчетах данные не отображаются?</span><span class="sxs-lookup"><span data-stu-id="a64f5-206">What if the reports aren't showing data?</span></span>

<span data-ttu-id="a64f5-207">Если вы не видите данные в отчетах ATP, дважды проверьте правильность настройки политик.</span><span class="sxs-lookup"><span data-stu-id="a64f5-207">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="a64f5-208">Для вашей организации должны быть определены политики [безопасных ссылок ATP](set-up-atp-safe-links-policies.md) и [политики безопасных вложений ATP](set-up-atp-safe-attachments-policies.md) для обеспечения безопасности ATP.</span><span class="sxs-lookup"><span data-stu-id="a64f5-208">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="a64f5-209">Кроме того, вы можете увидеть [защиту от нежелательной почты и вредоносных программ в Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a64f5-209">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a64f5-210">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a64f5-210">Related topics</span></span>

[<span data-ttu-id="a64f5-211">Отчеты и аналитика в центре безопасности и &amp; соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a64f5-211">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="a64f5-212">Разрешения ролей (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a64f5-212">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
