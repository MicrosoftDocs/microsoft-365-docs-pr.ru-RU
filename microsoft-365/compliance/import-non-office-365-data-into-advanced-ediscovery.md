---
title: Импорт контента, не относяного к Microsoft 365, для анализа Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Как импортировать контент, не хранимый в Microsoft 365, в большой большой объем Azure, чтобы его можно было проанализировать с помощью AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662904"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="a8fff-103">Импорт содержимого, не относяного к Microsoft 365, для анализа Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="a8fff-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="a8fff-104">Не все документы, которые вам может потребоваться проанализировать с помощью Advanced eDiscovery, будут размещены в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8fff-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="a8fff-105">С помощью функции импорта содержимого, не от microsoft 365 в Advanced eDiscovery, вы можете отправить документы, не хранимые в Microsoft 365 (кроме PST-файлов), в дело, связанное с хранилищем Azure, и проанализировать их с помощью Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8fff-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="a8fff-106">В этой процедуре показано, как свести документы, не относясь к Microsoft 365, в Advanced eDiscovery для анализа.</span><span class="sxs-lookup"><span data-stu-id="a8fff-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8fff-p102">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a8fff-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a8fff-109">Вы можете приобрести подписку на надстройку для хранения данных Advanced eDiscovery для контента за исключением Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8fff-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="a8fff-110">Эта возможность доступна только для контента, который необходимо проанализировать с помощью Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8fff-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="a8fff-111">Выполните действия, которые необходимо предпринять при покупке или редактировании надстройки [для Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) для бизнеса, и приобрети надстройку для хранения Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8fff-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="a8fff-112">Требования к отправке содержимого, не относяного к Office 365</span><span class="sxs-lookup"><span data-stu-id="a8fff-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="a8fff-113">Для использования функции отправки не из Office 365, как описано в этой процедуре, требуется:</span><span class="sxs-lookup"><span data-stu-id="a8fff-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="a8fff-114">Надстройка Office 365 E3 с дополнительным соответствием требованиям или подписка E5.</span><span class="sxs-lookup"><span data-stu-id="a8fff-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="a8fff-115">Все хранители, содержимое которых не из Office 365 будет загружено, должны иметь лицензии на надстройки E3 с расширенным соответствием требованиям или E5.</span><span class="sxs-lookup"><span data-stu-id="a8fff-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="a8fff-116">Существующее дело eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8fff-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="a8fff-117">Все файлы для отправки собираются в папки, в которых на одного хранителя есть одна папка, а имя папки в этом формате *alias@domainname.*</span><span class="sxs-lookup"><span data-stu-id="a8fff-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="a8fff-118">В  *alias@domainname*  должны быть пользователи с псевдонимом и доменом Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8fff-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="a8fff-119">Вы можете собрать  *все*  alias@domainname в корневую папку.</span><span class="sxs-lookup"><span data-stu-id="a8fff-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="a8fff-120">Корневая папка может  содержать только alias@domainname, в ней не должно быть свободных файлов.</span><span class="sxs-lookup"><span data-stu-id="a8fff-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="a8fff-121">Учетная запись, которая является либо диспетчером eDiscovery, либо администратором eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8fff-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="a8fff-122">[Средства хранения Microsoft Azure,](https://aka.ms/downloadazcopy) установленные на компьютере, который имеет доступ к структуре папок контента, не относячеству к Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8fff-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="a8fff-123">Отправка не из Office 365 содержимого в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a8fff-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="a8fff-124">В качестве менеджера по обнаружению электронных данных или администратора eDiscovery откройте **eDiscovery** и откройте дело, в которое будут загружены данные, не относя такие как Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8fff-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="a8fff-125">Если вам нужно создать дело, см. "Управление делами [eDiscovery" в Центре соответствия &amp; требованиям безопасности.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="a8fff-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="a8fff-126">Нажмите **кнопку "Переключиться на Advanced eDiscovery".**</span><span class="sxs-lookup"><span data-stu-id="a8fff-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="a8fff-127">Выберите **"Просмотр наборов"** в меню.</span><span class="sxs-lookup"><span data-stu-id="a8fff-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="a8fff-128">Выберите существующий набор для проверки или выберите **"Добавить набор для проверки".**</span><span class="sxs-lookup"><span data-stu-id="a8fff-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="a8fff-129">Выберите **"Управление набором для проверки".**</span><span class="sxs-lookup"><span data-stu-id="a8fff-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="a8fff-130">В карточке с данными, не относякой к Office 365, выберите **"Просмотреть отправки".**</span><span class="sxs-lookup"><span data-stu-id="a8fff-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="a8fff-131">Выберите **"Отправить файлы",** чтобы запустить мастер отправки файлов.</span><span class="sxs-lookup"><span data-stu-id="a8fff-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="a8fff-132">Первая вкладка — **1. Подготовка шага**.</span><span class="sxs-lookup"><span data-stu-id="a8fff-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="a8fff-133">Выберите **"Далее": отправка файлов.**</span><span class="sxs-lookup"><span data-stu-id="a8fff-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="a8fff-134">На **2. На вкладке** "Отправка файлов" вам будет предложено скачать AzCopy.exe, если вы еще этого не сделали, а затем укать путь к расположению файла.</span><span class="sxs-lookup"><span data-stu-id="a8fff-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="a8fff-135">Например, команда будет выполняться `C:\Upload`  AzCopy.exe.</span><span class="sxs-lookup"><span data-stu-id="a8fff-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="a8fff-136">Используя, `C:\Upload` вы увидите:</span><span class="sxs-lookup"><span data-stu-id="a8fff-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="a8fff-137">Откройте окно командной AzCopy.exe, чтобы импортировать данные в Azure.</span><span class="sxs-lookup"><span data-stu-id="a8fff-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="a8fff-138">После загрузки всех данных выберите **"Далее: файлы обработки".**</span><span class="sxs-lookup"><span data-stu-id="a8fff-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="a8fff-139">Следующая вкладка **— 3. Обработать файлы,** в которых вы увидите хранителей с данными, связанными с ними, а также покажет ход выполнения импортируемых данных.</span><span class="sxs-lookup"><span data-stu-id="a8fff-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="a8fff-140">Дополнительные сведения о синтаксис Azcopy см. в сведениях о передаче данных с [помощью AzCopy в Windows.](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="a8fff-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="a8fff-141">Дополнительные сведения о advanced eDiscovery Processing см. в модуле "Процесс" и загрузке данных в [Advanced eDiscovery (классическая).](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="a8fff-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8fff-142">На пользователя должна быть одна корневая папка, <b></b> имя папки должно быть в alias@domainname формате.</span><span class="sxs-lookup"><span data-stu-id="a8fff-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="a8fff-143">После успешной обработки контейнера в Advanced eDiscovery вы больше не сможете добавлять новое содержимое в хранилище SAS в Azure.</span><span class="sxs-lookup"><span data-stu-id="a8fff-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="a8fff-144">Если вы собираете дополнительный контент и хотите добавить его в дело для анализа Advanced eDiscovery, необходимо создать новый контейнер данных, не относячий к **Office 365,** и повторить эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="a8fff-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="a8fff-145">Если контейнер  не будет успешно обработаться из-за проблем с именами папок, а затем устранить проблемы, вам все равно придется создать новый контейнер, повторно подключиться и снова отправить его, используя процедуры, которые данной статьи.</span><span class="sxs-lookup"><span data-stu-id="a8fff-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
