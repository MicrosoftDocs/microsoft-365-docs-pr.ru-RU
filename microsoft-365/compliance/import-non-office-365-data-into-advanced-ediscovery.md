---
title: Импорт контента, отличного от Microsoft 365, для расширенного анализа обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: Инструкции по импорту контента, не хранящегося в Microsoft 365, в большой двоичный объект Azure, чтобы его можно было проанализировать с помощью АЕД
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636956"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="ccc68-103">Импорт контента, отличного от Microsoft 365, для расширенного анализа обнаружения электронных данных (классический)</span><span class="sxs-lookup"><span data-stu-id="ccc68-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="ccc68-104">Не все документы, которые может потребоваться проанализировать с помощью расширенного обнаружения электронных данных, будут находиться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ccc68-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="ccc68-105">С помощью функции импорта содержимого, отличной от Microsoft 365, в Advanced eDiscovery вы можете отправлять документы, не входящие в состав Microsoft 365 (за исключением PST-файлов), в объект, связанный с хранилищем Azure, и анализировать их с помощью расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ccc68-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="ccc68-106">В этой процедуре показано, как перенести документы, не относящиеся к Microsoft 365, в Расширенное обнаружение электронных данных для анализа.</span><span class="sxs-lookup"><span data-stu-id="ccc68-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ccc68-p102">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ccc68-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ccc68-109">Вы можете приобрести расширенную подписку на надстройку хранилища данных eDiscovery для вашего контента, отличного от Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="ccc68-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="ccc68-110">Этот параметр доступен только для контента, который необходимо проанализировать с помощью расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ccc68-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="ccc68-111">Выполните действия, описанные в статье [Покупка или изменение надстройки для Microsoft 365 для бизнеса](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) , и приобретите расширенную надстройку для хранения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ccc68-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="ccc68-112">Требования к отправке контента, отличного от Office 365</span><span class="sxs-lookup"><span data-stu-id="ccc68-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="ccc68-113">Для использования функции отправки, отличной от Office 365, описанной в этой процедуре, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="ccc68-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="ccc68-114">Office 365 E3 с дополнительным подпискум на надстройку или на дополнительные требования.</span><span class="sxs-lookup"><span data-stu-id="ccc68-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="ccc68-115">Все custodians, для которых содержимое, не относящееся к Office 365, должно быть отправлено в виде E3 с дополнительными лицензиями на надстройку или для установки и возврата.</span><span class="sxs-lookup"><span data-stu-id="ccc68-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="ccc68-116">Существующее дело обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ccc68-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="ccc68-117">Все файлы для отправки собраны в папки, для которых в одной папке есть папка хранитель, а имя папки в этом формате  *Alias@domainname*  .</span><span class="sxs-lookup"><span data-stu-id="ccc68-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="ccc68-118">*Alias@domainname* должны быть пользователями псевдонимов Office 365 и домена.</span><span class="sxs-lookup"><span data-stu-id="ccc68-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="ccc68-119">Вы можете собрать все  *Alias@domainname*  папки в корневую папку.</span><span class="sxs-lookup"><span data-stu-id="ccc68-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="ccc68-120">Корневая папка может содержать только папки  *Alias@domainname*  , но в корневой папке не должно быть свободных файлов.</span><span class="sxs-lookup"><span data-stu-id="ccc68-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="ccc68-121">Учетная запись, которая является диспетчером обнаружения электронных данных или администратором обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ccc68-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="ccc68-122">[Средства Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) , установленные на компьютере, который имеет доступ к структуре папки контента, отличной от Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccc68-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="ccc68-123">Отправка контента, отличного от Office 365, в Расширенное обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="ccc68-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="ccc68-124">В качестве диспетчера обнаружения электронных данных или администратора eDiscovery откройте объект **обнаружения электронных**данных и откройте ситуацию, в которую будут отправлены данные, не относящиеся к Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccc68-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="ccc68-125">Если вам нужно создать обращение, ознакомьтесь со статьей [Управление вариантами обнаружения электронных &amp; данных в центре безопасности и соответствия требованиям](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="ccc68-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="ccc68-126">Нажмите кнопку **переключиться на дополнительные функции обнаружения электронных**данных.</span><span class="sxs-lookup"><span data-stu-id="ccc68-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="ccc68-127">В меню выберите пункт **Просмотр наборов** .</span><span class="sxs-lookup"><span data-stu-id="ccc68-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="ccc68-128">Выберите существующий набор рецензирования или нажмите **Добавить набор рецензирования**.</span><span class="sxs-lookup"><span data-stu-id="ccc68-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="ccc68-129">Выберите **Управление набором рецензирования**.</span><span class="sxs-lookup"><span data-stu-id="ccc68-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="ccc68-130">В карточке данных, отличной от Office 365, выберите команду **Просмотреть отправки**.</span><span class="sxs-lookup"><span data-stu-id="ccc68-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="ccc68-131">Нажмите кнопку **отправить файлы** , чтобы запустить мастер отправки файлов.</span><span class="sxs-lookup"><span data-stu-id="ccc68-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="ccc68-132">Первая вкладка — **1. Этап подготовки**.</span><span class="sxs-lookup"><span data-stu-id="ccc68-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="ccc68-133">Нажмите кнопку **Далее: отправьте файлы**.</span><span class="sxs-lookup"><span data-stu-id="ccc68-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="ccc68-134">В разделе **2. Вкладка "Отправка файлов** " вам будет предложено скачать AzCopy.exe, если это еще не сделано, а затем указать путь к расположению файла.</span><span class="sxs-lookup"><span data-stu-id="ccc68-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="ccc68-135">Например, `C:\Upload`  вы получите команду для выполнения AzCopy.exe.</span><span class="sxs-lookup"><span data-stu-id="ccc68-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="ccc68-136">С помощью `C:\Upload` вы увидите:</span><span class="sxs-lookup"><span data-stu-id="ccc68-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="ccc68-137">Откройте окно командной строки и выполните команду AzCopy.exe, чтобы импортировать данные в Azure.</span><span class="sxs-lookup"><span data-stu-id="ccc68-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="ccc68-138">После загрузки всех данных нажмите кнопку **Далее: обработка файлов**.</span><span class="sxs-lookup"><span data-stu-id="ccc68-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="ccc68-139">Следующая вкладка — **3. Обработка файлов** , в которых вы увидите custodians с данными, связанными с ними, и покажет ход выполнения импорта данных.</span><span class="sxs-lookup"><span data-stu-id="ccc68-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="ccc68-140">Более подробную информацию о синтаксисе Azcopy можно узнать в статье [Transfer Data](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)in the Azcopy in Windows.</span><span class="sxs-lookup"><span data-stu-id="ccc68-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="ccc68-141">Более подробную информацию о расширенной обработке обнаружения электронных данных можно найти [в статье запуск модуля процесса и загрузка данных в Advanced eDiscovery (классический)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="ccc68-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ccc68-142">Для каждого пользователя должна быть только одна корневая папка, а имя папки должно быть в формате <b>Alias@domainname</b>  .</span><span class="sxs-lookup"><span data-stu-id="ccc68-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="ccc68-143">После успешной обработки контейнера в Advanced eDiscovery вы больше не сможете добавлять новые материалы в хранилище SAS в Azure.</span><span class="sxs-lookup"><span data-stu-id="ccc68-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="ccc68-144">Если вы собираете дополнительный контент и хотите добавить его в дело с расширенным анализом обнаружения электронных данных, необходимо создать новый контейнер данных, не относящийся к **Office 365** , и повторить эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="ccc68-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="ccc68-145">Если  *не удается обработать контейнер из-за проблем с именованием папок*  , а затем устранены проблемы, то все равно потребуется создать новый контейнер, а затем повторно подключиться и отправить его с помощью процедур, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ccc68-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
