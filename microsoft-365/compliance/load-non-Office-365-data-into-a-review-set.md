---
title: Загрузка не относящихся к Office 365 данных в набор для проверки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Импорт данных, отличных от Office 365, в набор проверки в расширенном случае обнаружения электронных данных.
ms.openlocfilehash: d839457824420c32a7acd006ae4218008c11b25e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41585688"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="169e4-103">Загрузка не относящихся к Office 365 данных в набор для проверки</span><span class="sxs-lookup"><span data-stu-id="169e4-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="169e4-104">Не все документы, которые необходимо проанализировать в Advanced eDiscovery, расположены в Office 365.</span><span class="sxs-lookup"><span data-stu-id="169e4-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="169e4-105">С помощью функции импорта данных, отличной от Office 365, в Advanced eDiscovery можно отправлять документы, не размещенные в Office 365, в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="169e4-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="169e4-106">В этой статье показано, как перенести документы, не относящиеся к Office 365, в Расширенное обнаружение электронных данных для анализа.</span><span class="sxs-lookup"><span data-stu-id="169e4-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="169e4-107">Для расширенного обнаружения электронных данных требуется подписка на Microsoft 365 или Office 365 в вашей организации или в подписке на Office с дополнительным соответствием.</span><span class="sxs-lookup"><span data-stu-id="169e4-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="169e4-108">Если у вас нет этого плана и вы хотите попытаться использовать Расширенное обнаружение электронных данных, вы можете зарегистрироваться в пробной версии Office 365 Enterprise ~.</span><span class="sxs-lookup"><span data-stu-id="169e4-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="169e4-109">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="169e4-109">Before you begin</span></span>

<span data-ttu-id="169e4-110">Для использования функции отправки, отличной от Office 365, описанной в этой статье, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="169e4-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="169e4-111">Все custodians, которые необходимо связать с содержимым, отличным от Office 365, должны быть назначены лицензией или лицензией E3 с дополнительными лицензиями на надстройку соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="169e4-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="169e4-112">Существующее расширенное дело обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="169e4-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="169e4-113">Custodians необходимо добавить в дело, прежде чем вы сможете отправлять и связывать с ними данные, не относящиеся к Office 365.</span><span class="sxs-lookup"><span data-stu-id="169e4-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="169e4-114">Данные не в Office 365 должны иметь тип файлов, поддерживаемый расширенным обнаружением электронных данных.</span><span class="sxs-lookup"><span data-stu-id="169e4-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="169e4-115">Для получения дополнительных сведений см. [Поддерживаемые типы файлов в Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="169e4-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="169e4-116">Все файлы, которые передаются в набор проверки, должны находиться в папках, в которых каждая папка связана с определенным хранитель.</span><span class="sxs-lookup"><span data-stu-id="169e4-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="169e4-117">Имена этих папок должны иметь следующий формат имен: *Alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="169e4-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="169e4-118">Alias@domainname должен быть псевдонимом Office 365 и доменом пользователя.</span><span class="sxs-lookup"><span data-stu-id="169e4-118">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="169e4-119">Вы можете собирать все alias@domainname папки в корневой папке.</span><span class="sxs-lookup"><span data-stu-id="169e4-119">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="169e4-120">Корневая папка может содержать только папки alias@domainname.</span><span class="sxs-lookup"><span data-stu-id="169e4-120">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="169e4-121">Свободные файлы в корневой папке не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="169e4-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="169e4-122">Структура папок для данных 365, которые вы хотите отправить, будет выглядеть так, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="169e4-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="169e4-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="169e4-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="169e4-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="169e4-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="169e4-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="169e4-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="169e4-126">Где abraham.mcmahon@contoso.com, jewell.gordon@contoso.com и staci.gonzalez@contoso.com — это SMTP-адреса custodians в случае.</span><span class="sxs-lookup"><span data-stu-id="169e4-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Структура папок отправки данных, отличных от Office 365](media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="169e4-128">Учетная запись, назначенная группе ролей диспетчера обнаружения электронных данных (и добавленная как администратор обнаружения электронных данных).</span><span class="sxs-lookup"><span data-stu-id="169e4-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="169e4-129">Средство AzCopy v 8.1, установленное на компьютере, который имеет доступ к структуре папки контента, отличной от Office 365.</span><span class="sxs-lookup"><span data-stu-id="169e4-129">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="169e4-130">Чтобы установить AzCopy, ознакомьтесь [со статьей Transfer Data with a AzCopy v 8.1 в Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="169e4-130">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="169e4-131">Обязательно установите AzCopy в расположении по умолчанию: **% ProgramFiles (x86)% \ Microsoft сдкс\азуре\азкопи**.</span><span class="sxs-lookup"><span data-stu-id="169e4-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="169e4-132">Необходимо использовать AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="169e4-132">You must use AzCopy v8.1.</span></span> <span data-ttu-id="169e4-133">Другие версии AzCopy могут не работать при загрузке данных 365, не относящихся к Office, в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="169e4-133">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="169e4-134">Отправка контента, отличного от Office 365, в Расширенное обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="169e4-134">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="169e4-135">В качестве диспетчера обнаружения электронных данных или администратора eDiscovery откройте компонент Advanced eDiscovery, а затем в случае отправки данных, отличных от Office 365.</span><span class="sxs-lookup"><span data-stu-id="169e4-135">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="169e4-136">Нажмите кнопку **Обзор наборов**, а затем выберите набор проверок для отправки данных 365, отличных от Office.</span><span class="sxs-lookup"><span data-stu-id="169e4-136">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="169e4-137">Если у вас нет набора рецензирования, его можно создать.</span><span class="sxs-lookup"><span data-stu-id="169e4-137">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="169e4-138">В наборе проверки щелкните **Управление набором проверки**, а затем нажмите кнопку **Просмотреть отправки** на плитке **данных, отличной от Office 365** .</span><span class="sxs-lookup"><span data-stu-id="169e4-138">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="169e4-139">Нажмите кнопку **отправить файлы** , чтобы запустить мастер импорта данных, не относящийся к Office 365.</span><span class="sxs-lookup"><span data-stu-id="169e4-139">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![Отправка файлов](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="169e4-141">Первый шаг мастера подготавливает безопасное расположение хранилища Azure, предоставленное Майкрософт, для отправки файлов в.</span><span class="sxs-lookup"><span data-stu-id="169e4-141">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="169e4-142">После завершения подготовки кнопка **Далее: Отправка файлов** становится активной.</span><span class="sxs-lookup"><span data-stu-id="169e4-142">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Импорт, не относящийся к Office 365: подготовка](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="169e4-144">Нажмите кнопку **Далее: Отправка файлов**.</span><span class="sxs-lookup"><span data-stu-id="169e4-144">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="169e4-145">На странице **Отправка файлов** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="169e4-145">On the **Upload files** page, do the following:</span></span>

   ![Импорт файлов, отличных от Office 365: Отправка файлов](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="169e4-147">а)</span><span class="sxs-lookup"><span data-stu-id="169e4-147">a.</span></span> <span data-ttu-id="169e4-148">В поле **путь к расположению файлов** проверьте или введите расположение корневой папки, в которой хранятся данные, не относящиеся к Office 365, которые требуется отправить.</span><span class="sxs-lookup"><span data-stu-id="169e4-148">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="169e4-149">Например, для расположения примеров файлов, показанных в **разделе до начала**работы, введите **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="169e4-149">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="169e4-150">Правильное расположение позволяет убедиться, что команда AzCopy, отображаемая в поле под путем, правильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="169e4-150">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="169e4-151">б)</span><span class="sxs-lookup"><span data-stu-id="169e4-151">b.</span></span> <span data-ttu-id="169e4-152">Нажмите кнопку **Копировать в буфер обмена** , чтобы скопировать команду, которая отображается в поле.</span><span class="sxs-lookup"><span data-stu-id="169e4-152">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="169e4-153">Запустите командную строку Windows, вставьте команду, скопированную на предыдущем шаге, а затем нажмите клавишу **Ввод** , чтобы запустить команду AzCopy.</span><span class="sxs-lookup"><span data-stu-id="169e4-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="169e4-154">После запуска команды файлы, не относящиеся к Office 365, будут отправлены в место хранения Azure, подготовленное на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="169e4-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Импорт, не относящийся к Office 365: AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="169e4-156">Как было сказано ранее, для успешного использования команды, которая указана на странице " **Отправка файлов** ", необходимо использовать AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="169e4-156">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="169e4-157">Если предоставленная команда AzCopy не удалась, обратитесь к разделу [Устранение неполадок AzCopy в Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="169e4-157">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="169e4-158">Вернитесь в центр безопасности & соответствия требованиям и нажмите кнопку **Далее: обработка файлов** в мастере.</span><span class="sxs-lookup"><span data-stu-id="169e4-158">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="169e4-159">Это инициирует обработку, извлечение текста и индексирование файлов, не относящихся к Office 365, которые были отправлены в место хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="169e4-159">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="169e4-160">Отслеживание хода обработки файлов, не относящихся к Office 365, на странице " **файлы процесса** " или на вкладке " **задания** " путем просмотра задания с именем " **Добавление данных, отличных от Office 365, в набор проверки**".</span><span class="sxs-lookup"><span data-stu-id="169e4-160">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="169e4-161">После завершения задания новые файлы будут доступны в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="169e4-161">After the job is finished, the new files will be available in the review set.</span></span>

   ![Импорт, не относящийся к Office 365: файлы процесса](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="169e4-163">После завершения обработки можно закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="169e4-163">After the processing is finished, you can close the wizard.</span></span>