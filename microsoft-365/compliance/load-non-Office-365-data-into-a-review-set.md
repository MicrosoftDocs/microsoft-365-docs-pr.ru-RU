---
title: Загрузка данных, не относящихся к Microsoft 365, в набор для проверки
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
description: Узнайте, как импортировать Microsoft 365 в набор отзывов для анализа в Advanced eDiscovery случае.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903505"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="15b0b-103">Загрузка данных, не относящихся к Microsoft 365, в набор для проверки</span><span class="sxs-lookup"><span data-stu-id="15b0b-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="15b0b-104">Не все документы, которые необходимо проанализировать в Advanced eDiscovery, находятся в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15b0b-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="15b0b-105">В Advanced eDiscovery есть функция импорта данных, не относящихся к Microsoft 365, с помощью которой вы можете отправлять документы, расположенные вне Microsoft 365, в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="15b0b-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="15b0b-106">В этой статье показано, как внести Microsoft 365 документы в Advanced eDiscovery для анализа.</span><span class="sxs-lookup"><span data-stu-id="15b0b-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="15b0b-107">Требования к загрузке не Office 365 контента</span><span class="sxs-lookup"><span data-stu-id="15b0b-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="15b0b-108">Использование функции загрузки Microsoft 365, описанной в этой статье, требует, чтобы у вас было следующее:</span><span class="sxs-lookup"><span data-stu-id="15b0b-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="15b0b-109">Всем хранителям, которые необходимо связать Microsoft 365 контента, должна быть назначена соответствующая лицензия.</span><span class="sxs-lookup"><span data-stu-id="15b0b-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="15b0b-110">Дополнительные сведения см. в [Advanced eDiscovery.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)</span><span class="sxs-lookup"><span data-stu-id="15b0b-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="15b0b-111">Существующий Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15b0b-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="15b0b-112">Хранители должны быть добавлены в дело, прежде чем вы можете загрузить и связать не Microsoft 365 к ним.</span><span class="sxs-lookup"><span data-stu-id="15b0b-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="15b0b-113">Данные, не относящиеся к Microsoft 365, должны иметь тип файла, поддерживаемый службой Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15b0b-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="15b0b-114">Дополнительные сведения см. в разделе [Поддерживаемые типы файлов в Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="15b0b-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="15b0b-115">Все файлы, отправляемые в набор для проверки, должны располагаться в папках, где каждая папка связана с определенным хранителем.</span><span class="sxs-lookup"><span data-stu-id="15b0b-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="15b0b-116">Для имен этих папок должен использоваться следующий формат именования: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="15b0b-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="15b0b-117">Псевдоним@имядомена должен быть псевдонимом и доменом Microsoft 365 пользователя.</span><span class="sxs-lookup"><span data-stu-id="15b0b-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="15b0b-118">Вы можете собрать все alias@domainname папки в корневой папке.</span><span class="sxs-lookup"><span data-stu-id="15b0b-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="15b0b-119">Корневая папка может содержать только alias@domainname папки.</span><span class="sxs-lookup"><span data-stu-id="15b0b-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="15b0b-120">Свободные файлы в корневой папке не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="15b0b-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="15b0b-121">Структура папок для незавернутых Microsoft 365, которые необходимо загрузить, будет похожа на следующий пример:</span><span class="sxs-lookup"><span data-stu-id="15b0b-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="15b0b-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15b0b-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="15b0b-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15b0b-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="15b0b-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15b0b-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="15b0b-125">Если abraham.mcmahon@contoso.com, jewell.gordon@contoso.com и staci.gonzalez@contoso.com являются smTP-адреса хранителей в данном случае.</span><span class="sxs-lookup"><span data-stu-id="15b0b-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Структура папки Microsoft 365 для загрузки данных](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="15b0b-127">Учетная запись, назначенная группе ролей диспетчера электронных открытий (и добавленная в качестве администратора электронных открытий).</span><span class="sxs-lookup"><span data-stu-id="15b0b-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="15b0b-128">Средство AzCopy v8.1, установленное на компьютере, который имеет доступ к структуре папок Microsoft 365 контента.</span><span class="sxs-lookup"><span data-stu-id="15b0b-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="15b0b-129">Чтобы установить AzCopy, см. в этой ссылке сведения о переносе с [помощью azCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)на Windows.</span><span class="sxs-lookup"><span data-stu-id="15b0b-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="15b0b-130">Обязательно установите AzCopy в расположении по умолчанию, которое является **%ProgramFiles (x86)%\Microsoft SDKs\Azure\AzCopy.**</span><span class="sxs-lookup"><span data-stu-id="15b0b-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="15b0b-131">Необходимо использовать azCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="15b0b-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="15b0b-132">Другие версии AzCopy могут не работать при загрузке Microsoft 365 в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15b0b-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="15b0b-133">Upload контент Microsoft 365 в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="15b0b-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="15b0b-134">В качестве диспетчера или администратора электронных данных откройте Advanced eDiscovery и перейдите к делу, в который будут загружены Microsoft 365 данные, не Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15b0b-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="15b0b-135">Щелкните **наборы** обзоров, а затем выберите набор отзывов, чтобы загрузить Microsoft 365 данные.</span><span class="sxs-lookup"><span data-stu-id="15b0b-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="15b0b-136">Если у вас нет набора отзывов, можно создать его.</span><span class="sxs-lookup"><span data-stu-id="15b0b-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="15b0b-137">В набор для проверки нажмите **Управление набором для проверки**, а затем **Просмотр отправок** на плитке **Данные, не относящиеся к Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="15b0b-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="15b0b-138">Щелкните **Отправить данные**, чтобы запустить мастер импорта данных.</span><span class="sxs-lookup"><span data-stu-id="15b0b-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Отправьте файлы](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="15b0b-140">Первый шаг мастера подготавливает безопасное хранилище Azure, предоставленное Microsoft, для отправки файлов.</span><span class="sxs-lookup"><span data-stu-id="15b0b-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="15b0b-141">Когда подготовка будет завершена, станет активной кнопка **Далее: Загрузить файлы**.</span><span class="sxs-lookup"><span data-stu-id="15b0b-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Импорт Microsoft 365: подготовка](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="15b0b-143">Нажмите **Далее: Отправить файлы**.</span><span class="sxs-lookup"><span data-stu-id="15b0b-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="15b0b-144">На странице **Upload файлы** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="15b0b-144">On the **Upload files** page, do the following:</span></span>

   ![Импорт Microsoft 365: Upload файлов](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="15b0b-146">а.</span><span class="sxs-lookup"><span data-stu-id="15b0b-146">a.</span></span> <span data-ttu-id="15b0b-147">В поле **Путь** к расположению файлов убедитесь или введите расположение корневой папки, в которой сохранены незавернутые Microsoft 365, которые необходимо загрузить.</span><span class="sxs-lookup"><span data-stu-id="15b0b-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="15b0b-148">Например, для расположения примеров файлов, показанных в разделе Before **you begin,** введите **%USERPROFILE\Downloads\nonO365.**</span><span class="sxs-lookup"><span data-stu-id="15b0b-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="15b0b-149">Правильное расположение обеспечивает правильное обновление команды AzCopy, отображаемой в поле под дорожкой.</span><span class="sxs-lookup"><span data-stu-id="15b0b-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="15b0b-150">б.</span><span class="sxs-lookup"><span data-stu-id="15b0b-150">b.</span></span> <span data-ttu-id="15b0b-151">Щелкните **Копию для буфера** обмена, чтобы скопировать команду, отображаемую в поле.</span><span class="sxs-lookup"><span data-stu-id="15b0b-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="15b0b-152">Запустите Windows команду, введите команду, скопированную на предыдущем шаге, а затем нажмите кнопку **Ввод,** чтобы запустить команду AzCopy.</span><span class="sxs-lookup"><span data-stu-id="15b0b-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="15b0b-153">После запуска команды файлы, не Microsoft 365, будут загружены в расположение служба хранилища Azure, подготовленное на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="15b0b-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Импорт Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="15b0b-155">Как уже говорилось ранее, для успешного использования команды, предоставленной на странице Upload **файлов,** необходимо использовать azCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="15b0b-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="15b0b-156">Если поставленная команда AzCopy сбой, см. в [Advanced eDiscovery.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="15b0b-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="15b0b-157">Возвращайся в Центр & безопасности и нажмите **кнопку Далее: Процесс файлов** в мастере.</span><span class="sxs-lookup"><span data-stu-id="15b0b-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="15b0b-158">Это инициирует обработку, извлечение текста и индексирование файлов, не относящихся к Microsoft 365, которые были отправлены в хранилище Azure.</span><span class="sxs-lookup"><span data-stu-id="15b0b-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="15b0b-159">Отслеживайте ход обработки файлов на странице **Process files** или на вкладке **Jobs,** просматривая задание с именем Добавление не Microsoft 365 данных в набор **отзывов.**</span><span class="sxs-lookup"><span data-stu-id="15b0b-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="15b0b-160">После завершения задания новые файлы будут доступны в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="15b0b-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Импорт Microsoft 365: файлы процесса](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="15b0b-162">Закройте мастер после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="15b0b-162">After the processing is finished, you can close the wizard.</span></span>