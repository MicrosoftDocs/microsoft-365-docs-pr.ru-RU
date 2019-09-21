---
title: Просмотр использования меток с помощью аналитики меток
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: После создания меток хранения и меток конфиденциальности рекомендуется просматривать, как они используется в клиенте. С помощью аналитики меток в Центре соответствия требованиям Microsoft 365 и Центре безопасности Microsoft 365 можно быстро просмотреть, какие метки используются чаще всего и где они применяются.
ms.openlocfilehash: 297987d420b5ed05bf4fdeb86513bc7c4ddec609
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090330"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="1243f-104">Просмотр использования меток с помощью аналитики меток</span><span class="sxs-lookup"><span data-stu-id="1243f-104">View label usage with label analytics</span></span>

<span data-ttu-id="1243f-105">После создания меток хранения и меток конфиденциальности рекомендуется просматривать, как они используется в клиенте.</span><span class="sxs-lookup"><span data-stu-id="1243f-105">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="1243f-106">С помощью аналитики меток в Центре соответствия требованиям Microsoft 365 и Центре безопасности Microsoft 365 можно быстро просмотреть, какие метки используются чаще всего и где они применяются.</span><span class="sxs-lookup"><span data-stu-id="1243f-106">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="1243f-107">Например, с помощью аналитики меток можно просмотреть:</span><span class="sxs-lookup"><span data-stu-id="1243f-107">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="1243f-108">Общее количество меток хранения и меток конфиденциальности, примененных к содержимому.</span><span class="sxs-lookup"><span data-stu-id="1243f-108">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="1243f-109">Часто используемые метки и число применений каждой метки.</span><span class="sxs-lookup"><span data-stu-id="1243f-109">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="1243f-110">Расположения, где применяются метки, и общее число для каждого расположения.</span><span class="sxs-lookup"><span data-stu-id="1243f-110">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="1243f-111">Число файлов и папок, для которых изменены или удалены метки хранения.</span><span class="sxs-lookup"><span data-stu-id="1243f-111">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="1243f-112">Аналитику меток можно найти в [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/labelanalytics) или [Центре безопасности Microsoft 365](https://security.microsoft.com/labelanalytics) > **Классификация** > **Аналитика меток**.</span><span class="sxs-lookup"><span data-stu-id="1243f-112">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![Страница "Аналитика меток"](media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="1243f-114">Использование меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="1243f-114">Sensitivity label usage</span></span>

<span data-ttu-id="1243f-115">Данные об использовании меток конфиденциальности извлекаются из отчетов для Azure Information Protection. Дополнительные сведения см. в статье [Центр отчетов для Azure Information Protection](https://docs.microsoft.com/ru-RU/azure/information-protection/reports-aip).</span><span class="sxs-lookup"><span data-stu-id="1243f-115">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/ru-RU/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="1243f-116">Обратите внимание, что отчеты Azure Information Protection имеют [предварительные требования](https://docs.microsoft.com/ru-RU/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics), которые также применяются к аналитике меток в отношении меток конфиденциальности в Центре соответствия требованиям Microsoft 365 и Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1243f-116">Note that the Azure Information Protection reports have [prerequisites](https://docs.microsoft.com/ru-RU/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="1243f-117">Например, требуется подписка на Azure, включающая журнал аналитики, так как эти отчеты являются результатом отправки событий аудита защиты сведений из клиентов и сканеров Azure Information Protection в централизованное расположение на основе службы Azure Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="1243f-117">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="1243f-118">При использовании меток конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="1243f-118">For sensitivity label usage:</span></span>

- <span data-ttu-id="1243f-119">Задержка данных отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1243f-119">There is no latency in the data.</span></span> <span data-ttu-id="1243f-120">Это отчет в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="1243f-120">This is a real-time report.</span></span>
- <span data-ttu-id="1243f-121">Чтобы просмотреть подсчет для каждой популярной метки, наведите указатель мыши на гистограмму и прочитайте появившуюся подсказку.</span><span class="sxs-lookup"><span data-stu-id="1243f-121">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="1243f-122">Отчет отображает место применения меток конфиденциальности по приложениям (а для меток хранения — по расположениям).</span><span class="sxs-lookup"><span data-stu-id="1243f-122">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![Отчет об использовании меток конфиденциальности](media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="1243f-124">Использование меток хранения</span><span class="sxs-lookup"><span data-stu-id="1243f-124">Retention label usage</span></span>

<span data-ttu-id="1243f-125">Этот отчет предоставляет обзор часто используемых меток и областей их применения.</span><span class="sxs-lookup"><span data-stu-id="1243f-125">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="1243f-126">Дополнительные сведения о присвоении меток к содержимому в SharePoint и OneDrive см. в статье [Просмотр действий с метками для документов](view-label-activity-for-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1243f-126">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="1243f-127">При использовании меток хранения:</span><span class="sxs-lookup"><span data-stu-id="1243f-127">For retention label usage:</span></span>

- <span data-ttu-id="1243f-128">Данные собираются еженедельно, поэтому может потребоваться до семи дней для появления данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="1243f-128">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="1243f-129">Чтобы просмотреть подсчет для каждой популярной метки, наведите указатель мыши на гистограмму и прочитайте появившуюся подсказку.</span><span class="sxs-lookup"><span data-stu-id="1243f-129">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="1243f-130">Отчет отображает место применения меток хранения по расположениям (а для меток конфиденциальности — по приложениям).</span><span class="sxs-lookup"><span data-stu-id="1243f-130">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="1243f-131">Для меток хранения это является сводкой данных за все время в клиенте; они не фильтруются по определенному диапазону дат.</span><span class="sxs-lookup"><span data-stu-id="1243f-131">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="1243f-132">Напротив, [Обозреватель действий с метками](view-label-activity-for-documents.md) отображает данные только за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1243f-132">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![Отчет об использовании меток хранения](media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="1243f-134">Просмотр всего содержимого с определенной меткой хранения</span><span class="sxs-lookup"><span data-stu-id="1243f-134">View all content with a specific retention label</span></span>

<span data-ttu-id="1243f-135">В отчете об использовании меток хранения можно быстро просмотреть все содержимое с определенной присвоенной меткой.</span><span class="sxs-lookup"><span data-stu-id="1243f-135">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="1243f-136">(Обратите внимание, что в настоящее время мы работаем над этой функцией, чтобы требовалось меньше действий для просмотра всего содержимого с меткой.)</span><span class="sxs-lookup"><span data-stu-id="1243f-136">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="1243f-137">Сначала выберите параметр **Просмотр сведений** в нижней части отчета.</span><span class="sxs-lookup"><span data-stu-id="1243f-137">First, choose **View Details** at the bottom of the report.</span></span>

![Параметр "Просмотр сведений" в нижней части отчета об использовании меток хранения](media/retention-label-usage-view-details.png)

<span data-ttu-id="1243f-139">Затем выберите метку хранения > **Обзор элементов** в области справа.</span><span class="sxs-lookup"><span data-stu-id="1243f-139">Then choose a retention label > **Explore items** in the right pane.</span></span>

![Параметр "Обзор элементов" в области справа](media/retention-label-usage-explore-items.png)

<span data-ttu-id="1243f-141">Для этой метки можно выбрать вкладку **Действие**, чтобы просмотреть количество элементов с этой меткой по расположениям.</span><span class="sxs-lookup"><span data-stu-id="1243f-141">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![Вкладка "Действие" для метки хранения](media/retention-label-usage-activity-tab.png)

<span data-ttu-id="1243f-143">Вы также можете выбрать вкладку **Элементы с этой меткой**. Затем можно перейти в определенные расположения:</span><span class="sxs-lookup"><span data-stu-id="1243f-143">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="1243f-144">Для Exchange Online появится список почтовых ящиков с числом помеченных элементов в каждом из них.</span><span class="sxs-lookup"><span data-stu-id="1243f-144">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="1243f-145">Для SharePoint Online и OneDrive для бизнеса появится список семейств веб-сайтов и учетных записей OneDrive с числом помеченных элементов в каждом расположении.</span><span class="sxs-lookup"><span data-stu-id="1243f-145">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="1243f-146">При выборе почтового ящика или семейства веб-сайтов, вы можете просмотреть список элементов с этой меткой хранения в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="1243f-146">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![Вкладка "Элементы с этой меткой", отображающая все элементы с соответствующей меткой хранения](media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="1243f-148">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1243f-148">Permissions</span></span>

<span data-ttu-id="1243f-149">Чтобы просматривать аналитику меток, вам должна быть присвоена одна из следующих ролей в Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="1243f-149">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="1243f-150">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="1243f-150">Global administrator</span></span>
- <span data-ttu-id="1243f-151">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="1243f-151">Compliance administrator</span></span>
- <span data-ttu-id="1243f-152">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="1243f-152">Security administrator</span></span>
- <span data-ttu-id="1243f-153">Читатель безопасности</span><span class="sxs-lookup"><span data-stu-id="1243f-153">Security reader</span></span>

<span data-ttu-id="1243f-154">Также обратите внимание, что эти отчеты используют Azure Monitor для хранения данных в рабочей области Log Analytics, принадлежащей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1243f-154">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="1243f-155">Поэтому пользователя следует добавить как читателя в рабочую область Azure Monitoring, содержащую данные. Дополнительные сведения см. в разделе [Разрешения, необходимые для средств аналитики Azure Information Protection](https://docs.microsoft.com/ru-RU/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span><span class="sxs-lookup"><span data-stu-id="1243f-155">Therefore, the user should be added as a reader to the Azure Monitoring worksapce that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/ru-RU/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>

