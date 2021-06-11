---
title: Экспорт и скачивание контента из дела core eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Описывает, как экспортировать и скачивать контент из дела core eDiscovery в Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310846"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="d9bb8-103">Экспорт содержимого из дела Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d9bb8-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="d9bb8-104">После успешного запуска поиска, связанного с делом core eDiscovery, можно экспортировать результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="d9bb8-105">При экспорте результатов поиска элементы почтовых ящиков загружаются в PST-файлы или в качестве отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="d9bb8-106">При экспорте контента SharePoint OneDrive для бизнеса сайтов экспортируются копии Office и других документов.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="d9bb8-107">Также экспортируется Results.csv, содержащий сведения о каждом экспортируемом элементе и файл манифеста (в формате XML), содержащий сведения о каждом результате поиска.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="d9bb8-108">Экспорт результатов поиска</span><span class="sxs-lookup"><span data-stu-id="d9bb8-108">Export search results</span></span>

1. <span data-ttu-id="d9bb8-109">Перейдите и войдите в использование учетных данных учетных записей пользователей, которые были назначены соответствующие разрешения на [https://compliance.microsoft.com](https://compliance.microsoft.com) открытие электронных данных.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="d9bb8-110">В левой области навигации центра Microsoft 365 нажмите кнопку **Показать** все, а затем нажмите **кнопку eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="d9bb8-111">На странице **Core eDiscovery** щелкните имя случая, в который необходимо создать удержание.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="d9bb8-112">На **домашней странице** для дела щелкните вкладку **Поиск.**</span><span class="sxs-lookup"><span data-stu-id="d9bb8-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="d9bb8-113">В меню **Действия** в нижней части страницы вылетов нажмите кнопку **Экспорт результатов**.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![Параметр Экспорт результатов в меню Действия](../media/ActionMenuExportResults.png)

   <span data-ttu-id="d9bb8-115">Рабочий процесс по экспорту результатов поиска, связанного с делом об обнаружении основных электронных обнаружений, является таким же, как экспорт результатов поиска для поиска на странице поиска **контента.**</span><span class="sxs-lookup"><span data-stu-id="d9bb8-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="d9bb8-116">Пошаговая инструкция см. в инструкции [по экспорту результатов поиска контента.](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="d9bb8-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d9bb8-117">При экспорте результатов поиска у вас есть возможность включить дублирование, чтобы экспортировать только одну копию сообщения электронной почты, несмотря на то, что несколько экземпляров одного и того же сообщения можно было найти в почтовых ящиках, которые искали.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="d9bb8-118">Дополнительные сведения о де-дублировании и выявлении дублирующих элементов см. в статьи [De-duplication in eDiscovery search results.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="d9bb8-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="d9bb8-119">После начала экспорта результаты поиска будут готовы к загрузке, а это значит, что они будут переданы в служба хранилища Azure microsoft в облаке Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="d9bb8-120">Щелкните **вкладку Экспорт** в этом случае, чтобы отобразить список заданий экспорта.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Экспорт заданий на вкладке Экспорт в случае core eDiscovery](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="d9bb8-122">Возможно, вам придется нажать **кнопку Обновить,** чтобы обновить список рабочих мест экспорта, чтобы он отображал созданное задание экспорта.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="d9bb8-123">Задания экспорта имеют то же имя, что и соответствующий **поиск** с _Export к имени поиска.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="d9bb8-124">Щелкните задание экспорта, созданное для отображения сведений о состоянии на странице вылетов.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="d9bb8-125">Эта информация включает процент элементов, которые были переданы в служба хранилища Azure расположение.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="d9bb8-126">После переноса всех элементов нажмите **кнопку Скачать результаты,** чтобы скачать результаты поиска на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="d9bb8-127">Дополнительные сведения о загрузке результатов поиска см. в шаге 2 в [экспорте результатов поиска контента](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="d9bb8-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="d9bb8-128">Дополнительные сведения об экспорте поисковых запросов из дела</span><span class="sxs-lookup"><span data-stu-id="d9bb8-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="d9bb8-129">Дополнительные сведения об экспортных файлах, включенных при экспорте результатов поиска, см. в отчете по экспорту поиска [контента.](export-a-content-search-report.md#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="d9bb8-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="d9bb8-130">При перезапуске экспорта любые изменения в запросах поисковых запросов, которые составляют задание экспорта, не повлияют на полученные результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="d9bb8-131">При перезапуске экспорта будет снова запускаться одно и то же совместное задание запроса поиска, которое было создано при экспорте.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="d9bb8-132">Кроме того, при перезапуске экспорта результаты поиска, скопированные в служба хранилища Azure, перезаписывать предыдущие результаты.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="d9bb8-133">Предыдущие скопированные результаты будут недоступны для скачивания.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-133">The previous results that were copied won't be available to be downloaded.</span></span>
