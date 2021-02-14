---
title: Загрузка данных, не относяхся к Microsoft 365, в набор для проверки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как импортировать данные, не относя такие как Microsoft 365, в набор для анализа в случае Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad70207bdc015107a5aba074e2df06a42c0618b3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285865"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="ad48a-103">Загрузка данных, не относяхся к Microsoft 365, в набор для проверки</span><span class="sxs-lookup"><span data-stu-id="ad48a-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="ad48a-104">Не все документы, которые необходимо проанализировать в Advanced eDiscovery, расположены в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad48a-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="ad48a-105">С помощью функции импорта данных, не от microsoft 365 в Advanced eDiscovery, вы можете отправить документы, не расположенные в Microsoft 365, в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="ad48a-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="ad48a-106">В этой статье показано, как внести документы, не в microsoft 365, в Advanced eDiscovery для анализа.</span><span class="sxs-lookup"><span data-stu-id="ad48a-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="ad48a-107">Требования к отправке содержимого, не относяного к Office 365</span><span class="sxs-lookup"><span data-stu-id="ad48a-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="ad48a-108">Для использования функции отправки, которая не является microsoft 365, описанной в этой статье, требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="ad48a-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="ad48a-109">Всем хранителям, которые вы хотите связать контент, не относячий к Microsoft 365, должна быть назначена соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="ad48a-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="ad48a-110">Дополнительные сведения [см. в поддомене "Начало работы с Advanced eDiscovery".](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)</span><span class="sxs-lookup"><span data-stu-id="ad48a-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="ad48a-111">Существующее дело Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ad48a-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="ad48a-112">Хранителей необходимо добавить в дело, прежде чем вы сможете отправить и связать с ними данные, не относячие к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad48a-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="ad48a-113">Данные, не относячие к Microsoft 365, должны быть типом файлов, поддерживаемым Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ad48a-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="ad48a-114">Дополнительные сведения [см. в поддерживаемых типах файлов в Advanced eDiscovery.](supported-filetypes-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="ad48a-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="ad48a-115">Все файлы, отложенные в набор для проверки, должны быть расположены в папках, где каждая папка связана с определенным хранителями.</span><span class="sxs-lookup"><span data-stu-id="ad48a-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="ad48a-116">Имена этих папок должны иметь следующий формат имен: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="ad48a-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="ad48a-117">В alias@domainname должен быть псевдоним и домен Microsoft 365 пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad48a-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="ad48a-118">Вы можете собрать все alias@domainname папки в корневой папке.</span><span class="sxs-lookup"><span data-stu-id="ad48a-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="ad48a-119">Корневая папка может содержать только alias@domainname папок.</span><span class="sxs-lookup"><span data-stu-id="ad48a-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="ad48a-120">Свободные файлы в корневой папке не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ad48a-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="ad48a-121">Структура папок для данных, не относяхся к Microsoft 365, которые вы хотите отправить, будет примерно такой же, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ad48a-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="ad48a-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad48a-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="ad48a-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad48a-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="ad48a-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad48a-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="ad48a-125">Где abraham.mcmahon@contoso.com, jewell.gordon@contoso.com и staci.gonzalez@contoso.com smTP-адреса хранителей в данном случае.</span><span class="sxs-lookup"><span data-stu-id="ad48a-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Структура папок отправки данных, не относясь к Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="ad48a-127">Учетная запись, назначенная группе ролей "Руководитель eDiscovery" (и добавленная в качестве администратора для eDiscovery).</span><span class="sxs-lookup"><span data-stu-id="ad48a-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="ad48a-128">Средство AzCopy 8.1, установленное на компьютере, который имеет доступ к структуре папок контента, не относячеству к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad48a-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="ad48a-129">Чтобы установить AzCopy, см. сведения о передаче [данных с AzCopy версии 8.1 в Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="ad48a-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="ad48a-130">Обязательно установите AzCopy в расположение по умолчанию% **ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.**</span><span class="sxs-lookup"><span data-stu-id="ad48a-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="ad48a-131">Необходимо использовать AzCopy 8.1.</span><span class="sxs-lookup"><span data-stu-id="ad48a-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="ad48a-132">Другие версии AzCopy могут не работать при загрузке данных, не влияющих на Microsoft 365, в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ad48a-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="ad48a-133">Отправка содержимого, не относяого к Microsoft 365, в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ad48a-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="ad48a-134">В качестве менеджера по обнаружению электронных данных или администратора eDiscovery откройте Advanced eDiscovery и перейдите к делу, в которое будут загружены данные, не относя такие как Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad48a-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="ad48a-135">Щелкните **наборы для** проверки и выберите набор для отправки данных, не вложенных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad48a-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="ad48a-136">Если у вас нет набора для проверки, вы можете создать его.</span><span class="sxs-lookup"><span data-stu-id="ad48a-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="ad48a-137">В наборе для проверки щелкните  "Управление набором для проверки", а затем выберите "Просмотр отправляемых данных" на плитке данных, не относящой к Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="ad48a-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="ad48a-138">Нажмите **кнопку "Отправить файлы",** чтобы запустить мастер импорта данных.</span><span class="sxs-lookup"><span data-stu-id="ad48a-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Отправка файлов](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="ad48a-140">На первом этапе мастера подготавливается безопасное хранилище Azure, предоставленное Корпорацией Майкрософт, для отправки файлов.</span><span class="sxs-lookup"><span data-stu-id="ad48a-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="ad48a-141">После завершения подготовки активна кнопка **"Далее:** отправка файлов".</span><span class="sxs-lookup"><span data-stu-id="ad48a-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Импорт не Из Microsoft 365: подготовка](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="ad48a-143">Нажмите **кнопку "Далее": отправка файлов.**</span><span class="sxs-lookup"><span data-stu-id="ad48a-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="ad48a-144">На странице **"Отправка файлов"** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ad48a-144">On the **Upload files** page, do the following:</span></span>

   ![Импорт не Microsoft 365: отправка файлов](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="ad48a-146">а.</span><span class="sxs-lookup"><span data-stu-id="ad48a-146">a.</span></span> <span data-ttu-id="ad48a-147">В поле **"Путь** к расположению файлов" проверьте или введите расположение корневой папки, в которой сохранены данные, не относявшиеся к Microsoft 365, которые вы хотите отправить.</span><span class="sxs-lookup"><span data-stu-id="ad48a-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="ad48a-148">Например, для расположения примеров файлов, показанных в разделе "Перед началом **работы",** необходимо ввести **%USERPROFILE\Downloads\nonO365.**</span><span class="sxs-lookup"><span data-stu-id="ad48a-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="ad48a-149">Правильное расположение обеспечивает правильное обновление команды AzCopy, отображаемой в поле под путем.</span><span class="sxs-lookup"><span data-stu-id="ad48a-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="ad48a-150">б.</span><span class="sxs-lookup"><span data-stu-id="ad48a-150">b.</span></span> <span data-ttu-id="ad48a-151">Щелкните **"Копировать" в буфер** обмена, чтобы скопировать команду, отображаемую в поле.</span><span class="sxs-lookup"><span data-stu-id="ad48a-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="ad48a-152">Запустите командную подсказку Windows, введите команду, скопированную  на предыдущем шаге, а затем нажмите ввод, чтобы запустить команду AzCopy.</span><span class="sxs-lookup"><span data-stu-id="ad48a-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="ad48a-153">После запуска команды файлы, не вложенные в Microsoft 365, будут загружены в хранилище Azure, подготовленное на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="ad48a-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Импорт не Из Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="ad48a-155">Как было сказано ранее, для успешного использования команды, предоставленной на странице  "Отправка файлов", необходимо использовать AzCopy 8.1.</span><span class="sxs-lookup"><span data-stu-id="ad48a-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="ad48a-156">Если сбой предоставленной команды AzCopy, см. "Устранение неполадок [AzCopy в Advanced eDiscovery".](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="ad48a-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="ad48a-157">Снова в Центр безопасности & соответствия требованиям и нажмите кнопку **"Далее: обработка файлов** в мастере".</span><span class="sxs-lookup"><span data-stu-id="ad48a-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="ad48a-158">Это инициирует обработку, извлечение текста и индексацию файлов, не вложенных в Microsoft 365, которые были загружены в хранилище Azure.</span><span class="sxs-lookup"><span data-stu-id="ad48a-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="ad48a-159">Отслеживайте ход обработки файлов  на странице "Файлы процесса" или на вкладке **"Задания",** просмотрев задание с именем "Добавление данных, не относяющихся к Microsoft **365",** в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="ad48a-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="ad48a-160">После завершения задания новые файлы будут доступны в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="ad48a-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Импорт не Из Microsoft 365: файлы процессов](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="ad48a-162">После завершения обработки можно закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="ad48a-162">After the processing is finished, you can close the wizard.</span></span>
