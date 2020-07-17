---
title: Увеличение скорости скачивания при экспорте результатов поиска обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как настроить реестр Windows, чтобы увеличить пропускную способность данных при загрузке результатов поиска и данных.
ms.openlocfilehash: a68a616d2dced4a3dd70580e1b258c95a0b5e39e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817678"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results"></a><span data-ttu-id="a3b3c-103">Увеличение скорости скачивания при экспорте результатов поиска обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="a3b3c-103">Increase the download speed when exporting eDiscovery search results</span></span>

<span data-ttu-id="a3b3c-104">При использовании средства экспорта eDiscovery для загрузки результатов поиска контента в центре безопасности & соответствия требованиям или загрузки данных из расширенного обнаружения электронных данных средство запускает определенное количество параллельных операций экспорта для загрузки данных на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-104">When you use the eDiscovery Export tool to download the results of a Content Search in the Security & Compliance Center or download data from Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer.</span></span> <span data-ttu-id="a3b3c-105">По умолчанию количество одновременных операций равно 8, а число ядер на компьютере, используемом для загрузки данных, равно 8.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-105">By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data.</span></span> <span data-ttu-id="a3b3c-106">Например, если у вас есть двухъядерный компьютер (то есть два центральных процессора на одной микросхеме), по умолчанию количество параллельных операций экспорта равно 16.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-106">For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16.</span></span> <span data-ttu-id="a3b3c-107">Чтобы увеличить пропускную способность и скорость загрузки данных, можно увеличить количество одновременных операций, настроив параметр реестра Windows на компьютере, который используется для скачивания результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-107">To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results.</span></span> <span data-ttu-id="a3b3c-108">Чтобы ускорить процесс загрузки, рекомендуется начать с параметра 24 одновременные операции.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-108">To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="a3b3c-109">Если вы скачиваете результаты поиска по сети с низкой пропускной способностью, увеличение этого параметра может негативно повлиять на работу.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-109">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact.</span></span> <span data-ttu-id="a3b3c-110">Кроме того, вы можете увеличить значение параметра до более 24 одновременных операций в сети с высокой пропускной способностью (максимальное число параллельных операций — 48).</span><span class="sxs-lookup"><span data-stu-id="a3b3c-110">Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 48).</span></span> <span data-ttu-id="a3b3c-111">После настройки этого параметра реестра может потребоваться изменить его, чтобы найти оптимальное количество параллельных операций для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-111">After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="a3b3c-112">Создание параметра реестра для изменения числа параллельных операций при экспорте данных</span><span class="sxs-lookup"><span data-stu-id="a3b3c-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="a3b3c-113">Выполните следующую процедуру на компьютере, который будет использоваться для загрузки результатов поиска из центра безопасности & соответствия требованиям или данных из расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-113">Perform the following procedure on the computer that you'll use to download search results from the Security & Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="a3b3c-114">Закройте средство экспорта eDiscovery, если оно открыто.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-114">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="a3b3c-115">Сохраните приведенный ниже текст в файле реестра Window с использованием суффикса имени файла reg; Например, Конкуррентоператионс. reg.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="a3b3c-116">Как показано выше, рекомендуется начать с 24 параллельных операций, а затем изменить этот параметр соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="a3b3c-117">В проводнике Windows щелкните или дважды щелкните файл. reg, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="a3b3c-118">В окне управления доступом пользователей нажмите кнопку **Да** , чтобы разрешить редактору реестра внести изменения.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="a3b3c-119">При появлении запроса на продолжение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="a3b3c-120">Редактор реестра выводит сообщение о том, что параметр был успешно добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="a3b3c-121">Вы можете повторить шаги 2-5, чтобы изменить значение `DownloadConcurrency` параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3b3c-122">После создания или изменения `DownloadConcurrency` параметра реестра обязательно создайте новое задание экспорта или перезапустите существующее задание экспорта для результатов поиска или данных, которые требуется скачать.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-122">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download.</span></span> <span data-ttu-id="a3b3c-123">Для получения дополнительных сведений см раздел " [Дополнительные сведения](#more-information) ".</span><span class="sxs-lookup"><span data-stu-id="a3b3c-123">See the [More information](#more-information) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="a3b3c-124">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3b3c-124">More information</span></span>

- <span data-ttu-id="a3b3c-125">Новый раздел реестра создается при первом запуске REG-файла, созданного в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-125">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="a3b3c-126">После этого `DownloadConcurrency` параметр реестра изменяется при каждом изменении и повторном запуске REG-файла редактирования.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-126">Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="a3b3c-127">Средство экспорта eDiscovery использует средство [Azure AzCopy](https://go.microsoft.com/fwlink/?linkid=849949) для загрузки данных поиска из центра безопасности & соответствия требованиям или из расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-127">The eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security & Compliance Center or from Advanced eDiscovery.</span></span> <span data-ttu-id="a3b3c-128">Настройка `DownloadConcurrency` параметра реестра аналогична использованию параметра **/НК** при запуске служебной программы AzCopy.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-128">Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility.</span></span> <span data-ttu-id="a3b3c-129">Таким образом, параметр реестра `"DownloadConcurrency=24"` будет иметь то же самое, что и значение параметра `/NC:24` с помощью служебной программы AzCopy.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-129">So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="a3b3c-130">Если вы остановите загрузку экспорта, а затем перезапустите ее (попытайтесь скачать результаты поиска повторно), средство экспорта eDiscovery попытается возобновить ту же самую загрузку.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-130">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the eDiscovery Export tool will attempt to resume the same download.</span></span> <span data-ttu-id="a3b3c-131">Поэтому, если вы запускаете загрузку, остановите ее, а затем измените `DownloadConcurrency` параметры реестра, Загрузка, скорее всего, завершится с ошибками, если вы перезапустите ее (щелкнув **загрузить экспортированные результаты**).</span><span class="sxs-lookup"><span data-stu-id="a3b3c-131">So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**).</span></span> <span data-ttu-id="a3b3c-132">Это связано с тем, что средство экспорта будет пытаться возобновить предыдущую загрузку с использованием недопустимых параметров, так как вы изменили параметр реестра.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-132">This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="a3b3c-133">Поэтому после изменения `DownloadConcurrency` параметра реестра не забудьте перезапустить задание экспорта (выбрав команду **перезапустить экспорт**) в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-133">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security & Compliance Center.</span></span> <span data-ttu-id="a3b3c-134">После этого вы сможете скачать экспортированные результаты.</span><span class="sxs-lookup"><span data-stu-id="a3b3c-134">Then you can download the exported results.</span></span> <span data-ttu-id="a3b3c-135">Дополнительные сведения об экспорте результатов поиска и данных можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="a3b3c-135">For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="a3b3c-136">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="a3b3c-136">Export Content Search results</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="a3b3c-137">Экспорт результатов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a3b3c-137">Export results in Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
