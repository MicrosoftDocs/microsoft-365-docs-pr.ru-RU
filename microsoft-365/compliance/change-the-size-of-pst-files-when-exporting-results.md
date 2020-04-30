---
title: Изменение размера PST-файлов при экспорте результатов поиска с обнаружением электронных данных
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
description: Вы можете изменить размер PST-файлов по умолчанию, которые будут загружаться на компьютер при экспорте результатов поиска обнаружения электронных данных.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942922"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="a9715-103">Изменение размера PST-файлов при экспорте результатов поиска с обнаружением электронных данных</span><span class="sxs-lookup"><span data-stu-id="a9715-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="a9715-104">При использовании средства экспорта eDiscovery для экспорта результатов поиска с обнаружением электронных данных из различных средств обнаружения электронных данных Майкрософт размер PST-файла по умолчанию, который можно экспортировать, составляет 10 ГБ.</span><span class="sxs-lookup"><span data-stu-id="a9715-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="a9715-105">Если вы хотите изменить размер по умолчанию, вы можете изменить реестр Windows на компьютере, который будет использоваться для экспорта результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="a9715-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="a9715-106">Одной из причин этого является PST-файл, который можно разместить на съемном носителе, таком как DVD-диск, компакт-диск или USB-диск.</span><span class="sxs-lookup"><span data-stu-id="a9715-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a9715-107">Средство экспорта eDiscovery используется для экспорта результатов поиска при использовании средства "поиск контента" в центре безопасности & соответствия требованиям, обнаружения электронных данных на месте в Exchange Online и центра обнаружения электронных данных в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a9715-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="a9715-108">Создание параметра реестра для изменения размера PST-файлов при экспорте результатов поиска обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="a9715-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="a9715-109">Выполните следующую процедуру на компьютере, который будет использоваться для экспорта результатов поиска обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="a9715-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="a9715-110">Закройте средство экспорта eDiscovery, если оно открыто.</span><span class="sxs-lookup"><span data-stu-id="a9715-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="a9715-111">Сохраните приведенный ниже текст в файле реестра Window с использованием суффикса имени файла reg; Например, Пстекспортсизе. reg.</span><span class="sxs-lookup"><span data-stu-id="a9715-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="a9715-112">В приведенном выше примере `PstSizeLimitInBytes` значение задается равным 1 073 741 824 байт или примерно 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="a9715-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="a9715-113">Ниже приведены другие примеры значений для этого `PstSizeLimitInBytes` параметра.</span><span class="sxs-lookup"><span data-stu-id="a9715-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="a9715-114">**Размер в ГБ (приблизительный)**</span><span class="sxs-lookup"><span data-stu-id="a9715-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="a9715-115">**Размер в байтах**</span><span class="sxs-lookup"><span data-stu-id="a9715-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a9715-116">0,7 ГБ (700 МБ)</span><span class="sxs-lookup"><span data-stu-id="a9715-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="a9715-117">751619277</span><span class="sxs-lookup"><span data-stu-id="a9715-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="a9715-118">2 ГБ</span><span class="sxs-lookup"><span data-stu-id="a9715-118">2 GB</span></span>  <br/> |<span data-ttu-id="a9715-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="a9715-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="a9715-120">4 ГБ</span><span class="sxs-lookup"><span data-stu-id="a9715-120">4 GB</span></span>  <br/> |<span data-ttu-id="a9715-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="a9715-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="a9715-122">8 ГБ</span><span class="sxs-lookup"><span data-stu-id="a9715-122">8 GB</span></span>  <br/> |<span data-ttu-id="a9715-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="a9715-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="a9715-124">Измените `PstSizeLimitInBytes` значение на требуемый максимальный размер PST-файла при экспорте результатов поиска и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="a9715-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="a9715-125">В проводнике Windows щелкните или дважды щелкните файл. reg, созданный на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="a9715-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="a9715-126">В окне управления доступом пользователей нажмите кнопку **Да** , чтобы разрешить редактору реестра внести изменения.</span><span class="sxs-lookup"><span data-stu-id="a9715-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="a9715-127">При появлении запроса на продолжение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="a9715-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="a9715-128">Редактор реестра выводит сообщение о том, что параметр был успешно добавлен в реестр.</span><span class="sxs-lookup"><span data-stu-id="a9715-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="a9715-129">Вы можете повторить шаги 3-6, чтобы изменить значение параметра `PstSizeLimitInBytes` реестра.</span><span class="sxs-lookup"><span data-stu-id="a9715-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="a9715-130">Часто задаваемые вопросы об изменении размера PST-файлов по умолчанию при экспорте результатов поиска обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="a9715-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="a9715-131">**Почему размер по умолчанию равен 10 ГБ?**</span><span class="sxs-lookup"><span data-stu-id="a9715-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="a9715-132">Размер по умолчанию 10 ГБ основан на отзывах пользователей; 10 ГБ является хорошим балансом между оптимальным объемом контента в пределах одного PST-файла и минимальной вероятностью повреждения файлов.</span><span class="sxs-lookup"><span data-stu-id="a9715-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="a9715-133">**Следует ли увеличить или уменьшить размер PST-файлов по умолчанию?**</span><span class="sxs-lookup"><span data-stu-id="a9715-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="a9715-134">Клиенты могут уменьшить предельный размер, чтобы результаты поиска поместились на съемных носителях, которые могут физически отгружаться в другие места в Организации.</span><span class="sxs-lookup"><span data-stu-id="a9715-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="a9715-135">Не рекомендуется увеличивать размер по умолчанию, так как при наличии PST-файлов размером более 10 ГБ могут возникнуть проблемы с повреждением.</span><span class="sxs-lookup"><span data-stu-id="a9715-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="a9715-136">**На каком компьютере необходимо сделать это?**</span><span class="sxs-lookup"><span data-stu-id="a9715-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="a9715-137">Необходимо изменить параметр реестра на любом локальном компьютере, на котором запущено средство экспорта eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a9715-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="a9715-138">**Когда я изменяю этот параметр, нужно перезагрузить компьютер?**</span><span class="sxs-lookup"><span data-stu-id="a9715-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="a9715-139">Нет, перезагружать компьютер не требуется.</span><span class="sxs-lookup"><span data-stu-id="a9715-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="a9715-140">Но если средство экспорта eDiscovery запущено, его необходимо закрыть и перезапустить после изменения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="a9715-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="a9715-141">**Редактируется ли существующий раздел реестра или создается новый ключ?**</span><span class="sxs-lookup"><span data-stu-id="a9715-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="a9715-142">Новый раздел реестра создается при первом запуске REG-файла, созданного в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="a9715-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="a9715-143">После этого параметры будут изменены при каждом изменении и повторном запуске REG-файла редактирования.</span><span class="sxs-lookup"><span data-stu-id="a9715-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
