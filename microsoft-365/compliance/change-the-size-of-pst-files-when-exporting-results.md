---
title: Изменение размера PST-файлов при экспорте результатов поиска eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Вы можете изменить размер PST-файлов по умолчанию, скачаемых на компьютер при экспорте результатов поиска по eDiscovery.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942922"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="77829-103">Изменение размера PST-файлов при экспорте результатов поиска eDiscovery</span><span class="sxs-lookup"><span data-stu-id="77829-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="77829-104">При использовании средства экспорта электронных данных для экспорта результатов поиска электронной почты из различных средств электронного поиска Майкрософт размер PST-файла, экспортируемого по умолчанию, составляет 10 ГБ.</span><span class="sxs-lookup"><span data-stu-id="77829-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="77829-105">Если вы хотите изменить этот размер по умолчанию, вы можете изменить Windows реестра на компьютере, который используется для экспорта результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="77829-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="77829-106">Одна из причин этого заключается в том, что PST-файл может поместиться на съемном носите, таком DVD, компакт-диске или USB-диске.</span><span class="sxs-lookup"><span data-stu-id="77829-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="77829-107">Средство экспорта электронных данных используется для экспорта результатов поиска при использовании средства поиска контента в Центре соответствия требованиям безопасности &, In-Place eDiscovery в Exchange Online и Центре поиска электронных данных в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="77829-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="77829-108">Создание параметра реестра для изменения размера PST-файлов при экспорте результатов поиска по электронным данным.</span><span class="sxs-lookup"><span data-stu-id="77829-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="77829-109">Выполните следующую процедуру на компьютере, который будет использовать для экспорта результатов поиска по электронным данным.</span><span class="sxs-lookup"><span data-stu-id="77829-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="77829-110">Закрой средство экспорта электронных открытий, если оно открыто.</span><span class="sxs-lookup"><span data-stu-id="77829-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="77829-111">Сохраните следующий текст в файл реестра окна с помощью суффикса .reg; например, PstExportSize.reg.</span><span class="sxs-lookup"><span data-stu-id="77829-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="77829-112">В примере выше значение установлено до  `PstSizeLimitInBytes` 1 073 741 824 bytes или приблизительно 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="77829-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="77829-113">Вот некоторые другие примерные значения для  `PstSizeLimitInBytes` параметра.</span><span class="sxs-lookup"><span data-stu-id="77829-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="77829-114">**Размер в ГБ (около.)**</span><span class="sxs-lookup"><span data-stu-id="77829-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="77829-115">**Размер в bytes**</span><span class="sxs-lookup"><span data-stu-id="77829-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77829-116">0,7 ГБ (700 МБ)</span><span class="sxs-lookup"><span data-stu-id="77829-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="77829-117">751619277</span><span class="sxs-lookup"><span data-stu-id="77829-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="77829-118">2 ГБ</span><span class="sxs-lookup"><span data-stu-id="77829-118">2 GB</span></span>  <br/> |<span data-ttu-id="77829-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="77829-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="77829-120">4 ГБ</span><span class="sxs-lookup"><span data-stu-id="77829-120">4 GB</span></span>  <br/> |<span data-ttu-id="77829-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="77829-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="77829-122">8 ГБ</span><span class="sxs-lookup"><span data-stu-id="77829-122">8 GB</span></span>  <br/> |<span data-ttu-id="77829-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="77829-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="77829-124">Измените значение до нужного максимального размера PST-файла при экспорте результатов поиска `PstSizeLimitInBytes` и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="77829-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="77829-125">В Windows Explorer щелкните или дважды щелкните файл .reg, созданный в предыдущих действиях.</span><span class="sxs-lookup"><span data-stu-id="77829-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="77829-126">В окне Управления доступом пользователей щелкните **Да,** чтобы редактор реестра внести изменения.</span><span class="sxs-lookup"><span data-stu-id="77829-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="77829-127">Если вам будет предложено продолжить, нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="77829-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="77829-128">Редактор реестра отображает сообщение о том, что параметр успешно добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="77829-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="77829-129">Можно повторить действия 3 - 6, чтобы изменить значение для  `PstSizeLimitInBytes` параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="77829-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="77829-130">Часто задающиеся вопросы об изменении размера PST-файлов по умолчанию при экспорте результатов поиска по eDiscovery</span><span class="sxs-lookup"><span data-stu-id="77829-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="77829-131">**Почему размер по умолчанию 10 ГБ?**</span><span class="sxs-lookup"><span data-stu-id="77829-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="77829-132">Размер по умолчанию 10 ГБ был основан на отзывах клиентов; 10 ГБ — это хороший баланс между оптимальным количеством контента в одном PST и минимальными шансами на повреждения файлов.</span><span class="sxs-lookup"><span data-stu-id="77829-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="77829-133">**Следует ли увеличивать или уменьшать размер PST-файлов по умолчанию?**</span><span class="sxs-lookup"><span data-stu-id="77829-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="77829-134">Клиенты, как правило, уменьшают ограничение размера, так что результаты поиска будут соответствовать съемным носителю, чтобы они могли физически отгрузки в другие места в своей организации.</span><span class="sxs-lookup"><span data-stu-id="77829-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="77829-135">Мы не рекомендуем увеличивать размер по умолчанию, так как у PST-файлов размером более 10 ГБ могут возникнуть проблемы с коррупцией.</span><span class="sxs-lookup"><span data-stu-id="77829-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="77829-136">**На каком компьютере я должен это сделать?**</span><span class="sxs-lookup"><span data-stu-id="77829-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="77829-137">Необходимо изменить параметр реестра на любом локальном компьютере, на который вы запустите средство экспорта электронных открытий.</span><span class="sxs-lookup"><span data-stu-id="77829-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="77829-138">**После изменения этого параметра необходимо ли перезагружать компьютер?**</span><span class="sxs-lookup"><span data-stu-id="77829-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="77829-139">Нет, не нужно перезагружать компьютер.</span><span class="sxs-lookup"><span data-stu-id="77829-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="77829-140">Но если средство экспорта электронных обнаружений запущено, его необходимо закрыть и перезапустить после изменения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="77829-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="77829-141">**Редактируется ли существующий ключ реестра или создается новый ключ?**</span><span class="sxs-lookup"><span data-stu-id="77829-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="77829-142">При первом запуске файла .reg, созданного в этой процедуре, создается новый ключ реестра.</span><span class="sxs-lookup"><span data-stu-id="77829-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="77829-143">Затем параметр редактируется при каждом изменении и повторном повторе файла редактирования .reg.</span><span class="sxs-lookup"><span data-stu-id="77829-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
