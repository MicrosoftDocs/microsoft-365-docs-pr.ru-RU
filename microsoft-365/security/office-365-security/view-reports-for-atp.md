---
title: Просмотр отчетов для Office 365 Advanced Threat protection
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
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
description: Узнайте, как найти и использовать отчеты для Office 365 Advanced Threat Protection в центре безопасности &amp; и соответствия требованиям.
ms.openlocfilehash: d5f0958d199684a9d6ca6bfe4ed01c0ab9102a2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091516"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="1afce-103">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="1afce-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="1afce-104">Если в Организации имеется [Office 365 Advanced Threat protection](office-365-atp.md) (ATP), и у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-the-atp-reports), вы можете использовать несколько отчетов ATP в центре &amp; безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1afce-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1afce-105">(Перейдите в \*\*\*\* \> **панель мониторинга**отчетов.)</span><span class="sxs-lookup"><span data-stu-id="1afce-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![Информационная &amp; панель центра соответствия требованиям безопасности поможет вам узнать, где работает Расширенная защита от угроз](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="1afce-107">К отчетам ATP относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="1afce-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="1afce-108">Отчет о состоянии защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="1afce-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="1afce-109">Отчет о типах файлов ATP</span><span class="sxs-lookup"><span data-stu-id="1afce-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="1afce-110">Отчет об ликвидации сообщений ATP</span><span class="sxs-lookup"><span data-stu-id="1afce-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="1afce-111">[Обнаружение или проводник в режиме реального времени](threat-explorer.md) (в зависимости от того, установлен ли для Office 365 ATP 1 (план 1) или 2)</span><span class="sxs-lookup"><span data-stu-id="1afce-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="1afce-112">... [и многое другое](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="1afce-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="1afce-113">В этой статье приводятся общие сведения об отчетах ATP и способах их использования.</span><span class="sxs-lookup"><span data-stu-id="1afce-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="1afce-114">Отчет о состоянии защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="1afce-114">Threat Protection Status report</span></span>

<span data-ttu-id="1afce-115">Отчет **о состоянии защиты от угроз** — это единое представление, объединяющее сведения о вредоносном содержимом и вредоносных сообщениях, обнаруженных и заблокированных службой [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) и [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="1afce-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="1afce-116">Этот отчет полезен для просмотра обнаружений с течением времени (до 90 дней), а также позволяет администраторам безопасности определять тенденции или определять необходимость внесения изменений в политики.</span><span class="sxs-lookup"><span data-stu-id="1afce-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="1afce-117">В отчете о состоянии защиты от угроз представлено общее количество уникальных сообщений электронной почты с вредоносным содержимым, например файлов или адресов веб-сайтов (URL-адресов), которые были заблокированы ядром защиты от вредоносных программ, функции [автоматического очистки (ZAP)](zero-hour-auto-purge.md)и ATP, такие как [Безопасные ссылки ATP](atp-safe-links.md), [безопасные вложения ATP](atp-safe-attachments.md)и [возможности защиты от фишинга](atp-anti-phishing.md)ATP.</span><span class="sxs-lookup"><span data-stu-id="1afce-117">The Threat Protection Status report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="1afce-118">Отчет о состоянии защиты от угроз доступен клиентам, у которых есть [Office 365 ATP](office-365-atp.md) или [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); Однако сведения, отображаемые в отчете о состоянии защиты от угроз для клиентов ATP, скорее всего, будут содержать данные, отличные от данных, которые могут видеть пользователи EOP.</span><span class="sxs-lookup"><span data-stu-id="1afce-118">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="1afce-119">Например, отчет о состоянии защиты от угроз для клиентов ATP будет содержать сведения о [вредоносных файлах, обнаруженных в SharePoint Online, OneDrive или Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1afce-119">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="1afce-120">Такие сведения относятся к ATP, поэтому клиенты, у которых есть EOP, но не ATP, не увидят эти сведения в отчете о состоянии защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="1afce-120">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="1afce-121">Чтобы просмотреть отчет о состоянии защиты **от угроз,** \> в [центре &amp; безопасности и соответствия требованиям](https://protection.office.com)выберите **состояние защиты от угроз**для **отчетов** \> .</span><span class="sxs-lookup"><span data-stu-id="1afce-121">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Отчет о состоянии защиты от угроз для ATP](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="1afce-123">Чтобы получить подробные сведения о состоянии дня, наведите указатель на диаграмму.</span><span class="sxs-lookup"><span data-stu-id="1afce-123">To get detailed status for a day, hover over the graph.</span></span>
  
![Данные о состоянии ATP Threat protection за день](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="1afce-125">По умолчанию в отчете о состоянии защиты от угроз отображаются данные за прошедшие семь дней.</span><span class="sxs-lookup"><span data-stu-id="1afce-125">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="1afce-126">Тем не менее, вы можете выбрать **фильтры** и изменить диапазон дат для просмотра данных в течение до 90 дней.</span><span class="sxs-lookup"><span data-stu-id="1afce-126">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="1afce-127">(Если вы используете пробную подписку, вы можете использовать не более 30 дней данных.)</span><span class="sxs-lookup"><span data-stu-id="1afce-127">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![Фильтры состояния защиты от угроз ATP](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="1afce-129">Вы также можете использовать меню **Просмотр данных,** чтобы изменить сведения, отображаемые в отчете.</span><span class="sxs-lookup"><span data-stu-id="1afce-129">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Параметры просмотра для отчета о состоянии защиты от угроз для ATP](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="1afce-131">Отчет о типах файлов ATP</span><span class="sxs-lookup"><span data-stu-id="1afce-131">ATP File Types report</span></span>

<span data-ttu-id="1afce-132">В отчете " **типы файлов ATP** " отображаются типы файлов, обнаруженных в качестве вредоносных при [безопасном вложении ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="1afce-132">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="1afce-133">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)перейдите к **типам файлов** **панели мониторинга** \> **отчетов** \> ATP.</span><span class="sxs-lookup"><span data-stu-id="1afce-133">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Отчет о типах файлов ATP](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="1afce-135">Если навести указатель мыши на определенный день, можно увидеть разбивку типов вредоносных файлов, обнаруженных [безопасными вложениями ATP](atp-safe-attachments.md) и [защитой от &amp; нежелательной почты в Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1afce-135">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Данные о типах файлов ATP в день](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="1afce-137">Отчет об ликвидации сообщений ATP</span><span class="sxs-lookup"><span data-stu-id="1afce-137">ATP Message Disposition report</span></span>

<span data-ttu-id="1afce-138">В отчете об **ликвидации сообщений ATP** отображаются действия, предпринятые для сообщений электронной почты, которые были обнаружены как вредоносный контент.</span><span class="sxs-lookup"><span data-stu-id="1afce-138">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="1afce-139">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)перейдите к разделу **панель мониторинга** \> **отчетов** \> **ATP Message Disposition**.</span><span class="sxs-lookup"><span data-stu-id="1afce-139">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Отчет об ликвидации сообщений ATP](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="1afce-141">При наведении указателя мыши на полоску на диаграмме можно просмотреть, какие действия были предприняты для обнаруженных сообщений электронной почты в этот день.</span><span class="sxs-lookup"><span data-stu-id="1afce-141">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Данные отчета об ликвидации сообщений ATP за день](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="1afce-143">Дополнительные отчеты для просмотра</span><span class="sxs-lookup"><span data-stu-id="1afce-143">Additional reports to view</span></span>

<span data-ttu-id="1afce-144">Помимо отчетов ATP, описанных в этой статье, доступны некоторые другие отчеты, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1afce-144">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="1afce-145">Отчет (ы)</span><span class="sxs-lookup"><span data-stu-id="1afce-145">Report(s)</span></span>  |<span data-ttu-id="1afce-146">Сведения</span><span class="sxs-lookup"><span data-stu-id="1afce-146">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="1afce-147">**Проводник** или **Обнаружение в режиме реального времени** (Office 365 ATP, план 2, у пользователей есть Explorer; Пользователи Office 365 ATP 1 (план 1) имеют обнаружение в режиме реального времени.)</span><span class="sxs-lookup"><span data-stu-id="1afce-147">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="1afce-148">Обозреватель угроз (и обнаружение в режиме реального времени)</span><span class="sxs-lookup"><span data-stu-id="1afce-148">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="1afce-149">**Отчеты о безопасности электронной почты**, например отчет о самых отправителях и получателях, отчет о поддельной почте и отчет об обнаружении нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="1afce-149">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="1afce-150">Просмотр отчетов о безопасности электронной почты в &amp; центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="1afce-150">View email security reports in the Security &amp; Compliance Center</span></span>](../../compliance/view-email-security-reports.md)        |
|<span data-ttu-id="1afce-151">**Трассировка URL-адресов для безопасных ссылок ATP** (Это отчет, созданный с помощью PowerShell.) В этом отчете представлены результаты действий безопасных ссылок ATP за прошедшие семь (7) дней.</span><span class="sxs-lookup"><span data-stu-id="1afce-151">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="1afce-152">Справочные материалы по командлету Get – Урлтраце</span><span class="sxs-lookup"><span data-stu-id="1afce-152">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|<span data-ttu-id="1afce-153">**Результаты EOP и ATP** (Это настраиваемый отчет, созданный с помощью PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1afce-153">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="1afce-154">Этот отчет содержит такие сведения, как домен, Дата, тип события, направление, действие и количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="1afce-154">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="1afce-155">Справочные материалы по командлету Get – Маилтраффикатпрепорт</span><span class="sxs-lookup"><span data-stu-id="1afce-155">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="1afce-156">**Обнаружения EOP и ATP** (Это настраиваемый отчет, созданный с помощью PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1afce-156">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="1afce-157">Этот отчет содержит сведения о вредоносных файлах или URL-адресах, фишинговых попытках, олицетворении и других потенциальных угрозах в электронной почте или файлах.</span><span class="sxs-lookup"><span data-stu-id="1afce-157">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="1afce-158">Справочные материалы по командлету Get – Маилдетаилатпрепорт</span><span class="sxs-lookup"><span data-stu-id="1afce-158">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="1afce-159">Какие разрешения необходимы для просмотра отчетов ATP?</span><span class="sxs-lookup"><span data-stu-id="1afce-159">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="1afce-160">Для просмотра и использования отчетов, описанных в этой статье, **необходимо назначить соответствующую роль для центра безопасности &amp; и центра администрирования Exchange**.</span><span class="sxs-lookup"><span data-stu-id="1afce-160">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="1afce-161">Для центра соответствия &amp; требованиям безопасности необходимо назначить одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="1afce-161">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="1afce-162">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="1afce-162">Organization Management</span></span>
    - <span data-ttu-id="1afce-163">Администратор безопасности (это можно назначить в центре администрирования Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))).</span><span class="sxs-lookup"><span data-stu-id="1afce-163">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="1afce-164">Средство чтения безопасности</span><span class="sxs-lookup"><span data-stu-id="1afce-164">Security Reader</span></span>

- <span data-ttu-id="1afce-165">Для Exchange Online необходимо назначить одну из следующих ролей в центре администрирования Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) или с помощью командлетов PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="1afce-165">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="1afce-166">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="1afce-166">Organization Management</span></span>
    - <span data-ttu-id="1afce-167">Управление организацией с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="1afce-167">View-only Organization Management</span></span>
    - <span data-ttu-id="1afce-168">Роль получателей с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="1afce-168">View-Only Recipients role</span></span>
    - <span data-ttu-id="1afce-169">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="1afce-169">Compliance Management</span></span>

<span data-ttu-id="1afce-170">Чтобы узнать больше, ознакомьтесь со следующими материалами:</span><span class="sxs-lookup"><span data-stu-id="1afce-170">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="1afce-171">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1afce-171">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="1afce-172">Разрешения компонентов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1afce-172">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1afce-173">Что делать, если в отчетах данные не отображаются?</span><span class="sxs-lookup"><span data-stu-id="1afce-173">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1afce-174">Если вы не видите данные в отчетах ATP, дважды проверьте правильность настройки политик.</span><span class="sxs-lookup"><span data-stu-id="1afce-174">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1afce-175">Для вашей организации должны быть определены политики [безопасных ссылок ATP](set-up-atp-safe-links-policies.md) и [политики безопасных вложений ATP](set-up-atp-safe-attachments-policies.md) для обеспечения безопасности ATP.</span><span class="sxs-lookup"><span data-stu-id="1afce-175">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="1afce-176">Кроме того, вы можете увидеть [защиту от нежелательной почты и вредоносных программ в Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1afce-176">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1afce-177">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1afce-177">Related topics</span></span>

[<span data-ttu-id="1afce-178">Отчеты и аналитика в центре безопасности &amp; и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="1afce-178">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="1afce-179">Создание расписания для отчета в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="1afce-179">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="1afce-180">Настройка и загрузка настраиваемого отчета в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="1afce-180">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

