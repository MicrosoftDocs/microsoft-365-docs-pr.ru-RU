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
ms.openlocfilehash: be49e7d44c56988baa3cdc718498a03ee4acd50b
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214543"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="7615d-103">Импорт контента, отличного от Microsoft 365, для расширенного анализа обнаружения электронных данных (классический)</span><span class="sxs-lookup"><span data-stu-id="7615d-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="7615d-104">Не все документы, которые может потребоваться проанализировать с помощью расширенного обнаружения электронных данных, будут находиться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7615d-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="7615d-105">С помощью функции импорта содержимого, отличной от Microsoft 365, в Advanced eDiscovery вы можете отправлять документы, не входящие в состав Microsoft 365 (за исключением PST-файлов), в объект, связанный с хранилищем Azure, и анализировать их с помощью расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="7615d-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="7615d-106">В этой процедуре показано, как перенести документы, не относящиеся к Microsoft 365, в Расширенное обнаружение электронных данных для анализа.</span><span class="sxs-lookup"><span data-stu-id="7615d-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7615d-p102">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="7615d-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7615d-109">Вы можете приобрести расширенную подписку на надстройку хранилища данных eDiscovery для вашего контента, отличного от Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="7615d-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="7615d-110">Этот параметр доступен только для контента, который необходимо проанализировать с помощью расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="7615d-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="7615d-111">Выполните действия, описанные в статье [Покупка или изменение надстройки для Microsoft 365 для бизнеса](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) , и приобретите расширенную надстройку для хранения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="7615d-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="7615d-112">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7615d-112">Before you begin</span></span>

<span data-ttu-id="7615d-113">Для использования функции отправки, отличной от Office 365, описанной в этой процедуре, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="7615d-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="7615d-114">Office 365 E3 с расширенной подпиской на надстройку с расширенным соответствием</span><span class="sxs-lookup"><span data-stu-id="7615d-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="7615d-115">Все custodians, для которых содержимое, не относящееся к Office 365, должно быть отправлено в соответствии с дополнительными лицензиями на надстройку</span><span class="sxs-lookup"><span data-stu-id="7615d-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="7615d-116">Существующее дело обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="7615d-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="7615d-117">Все файлы для отправки собраны в папки, для которых в одной папке есть папка хранитель, а имя папки в этом формате *Alias@domainname* .</span><span class="sxs-lookup"><span data-stu-id="7615d-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="7615d-118">*Alias@domainname* должны быть пользователями псевдонимов Office 365 и домена.</span><span class="sxs-lookup"><span data-stu-id="7615d-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="7615d-119">Вы можете собрать все *Alias@domainname* папки в корневую папку.</span><span class="sxs-lookup"><span data-stu-id="7615d-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="7615d-120">Корневая папка может содержать только папки *Alias@domainname* , в корневой папке не должно быть свободных файлов.</span><span class="sxs-lookup"><span data-stu-id="7615d-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="7615d-121">Учетная запись, которая является диспетчером обнаружения электронных данных или администратором обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="7615d-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="7615d-122">[Средства Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) , установленные на компьютере, который имеет доступ к структуре папки контента, отличной от Office 365.</span><span class="sxs-lookup"><span data-stu-id="7615d-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="7615d-123">Отправка контента, отличного от Office 365, в Расширенное обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="7615d-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="7615d-124">В качестве диспетчера обнаружения электронных данных или администратора eDiscovery откройте объект **обнаружения электронных**данных и откройте ситуацию, в которую будут отправлены данные, не относящиеся к Office 365.</span><span class="sxs-lookup"><span data-stu-id="7615d-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="7615d-125">Если вам нужно создать обращение, ознакомьтесь со статьей [Управление вариантами обнаружения электронных &amp; данных в центре безопасности и соответствия требованиям](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="7615d-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="7615d-126">Нажмите кнопку **переключиться на расширенные функции обнаружения электронных** данных</span><span class="sxs-lookup"><span data-stu-id="7615d-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="7615d-127">В разделе **тип источника** выберите **данные, отличные от Office 365**.</span><span class="sxs-lookup"><span data-stu-id="7615d-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="7615d-128">Нажмите кнопку **добавить контейнер**.</span><span class="sxs-lookup"><span data-stu-id="7615d-128">Click **Add container**.</span></span> <span data-ttu-id="7615d-129">Назовите контейнер и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="7615d-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="7615d-130">Выберите только что добавленный контейнер из списка контейнер и скопируйте URL-адрес, который отображается в области сведений о контейнере, а затем закройте область.</span><span class="sxs-lookup"><span data-stu-id="7615d-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="7615d-131">Откройте командную строку от имени администратора и измените каталог на папку, в которой установлен AzCopy..</span><span class="sxs-lookup"><span data-stu-id="7615d-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="7615d-132">Создайте командную строку AzCopy, чтобы отправить файлы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7615d-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="7615d-133">AzCopy/Source: " *полный путь к корневой папке на локальном компьютере* "/Дест: " *URL-адрес контейнера, но не включает?*</span><span class="sxs-lookup"><span data-stu-id="7615d-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="7615d-134">"/Дестсас:" *оставшаяся часть URL-адреса контейнера из поля "?" в конец* "/с.</span><span class="sxs-lookup"><span data-stu-id="7615d-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="7615d-135">Например, используйте следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7615d-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="7615d-136">Корневая папка — данные К:\коллектед</span><span class="sxs-lookup"><span data-stu-id="7615d-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="7615d-137">URL-адрес контейнера- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp ; SR = c &amp; Si = NonOfficeData15% 7C0 &amp; SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D</span><span class="sxs-lookup"><span data-stu-id="7615d-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="7615d-138">синтаксис командной строки AzCopy:</span><span class="sxs-lookup"><span data-stu-id="7615d-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="7615d-139">Для получения дополнительных сведений о синтаксисе Azcopy [перенесите данные с помощью Azcopy в Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span><span class="sxs-lookup"><span data-stu-id="7615d-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7615d-140">Для каждого пользователя должна быть только одна корневая папка, а имя папки должно быть в формате *Alias@domainname* .</span><span class="sxs-lookup"><span data-stu-id="7615d-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="7615d-141">После завершения отправки папок переключитесь обратно на Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7615d-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="7615d-142">Содержимое загруженных вами папок теперь готово для обработки в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7615d-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="7615d-143">Выберите контейнер и нажмите кнопку Process (обработать).</span><span class="sxs-lookup"><span data-stu-id="7615d-143">Select the container and click the Process button.</span></span> <span data-ttu-id="7615d-144">Дополнительные сведения о расширенной обработке обнаружения электронных данных см. [запустите модуль Process и загрузите данные в Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="7615d-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7615d-145">После успешной обработки контейнера в Advanced eDiscovery вы больше не сможете добавлять новые материалы в хранилище SAS в Azure.</span><span class="sxs-lookup"><span data-stu-id="7615d-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="7615d-146">Если вы собираете дополнительный контент и хотите добавить его в дело с расширенным анализом обнаружения электронных данных, необходимо создать новый контейнер данных, не относящийся к **Office 365** , и повторить эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="7615d-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="7615d-147">Если *не удается обработать контейнер из-за проблем с именованием папок* , а затем устранены проблемы, то все равно потребуется создать новый контейнер, а затем повторно подключиться и отправить его с помощью процедур, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7615d-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
