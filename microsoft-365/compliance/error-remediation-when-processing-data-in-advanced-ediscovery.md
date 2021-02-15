---
title: Исправление ошибок при обработке данных
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
description: Узнайте, как использовать исправление ошибок для устранения проблем с данными в Advanced eDiscovery, которые могут препятствовать правильной обработке контента.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6ef1076e44fca0d060d766fc85a435550c40059
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750802"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="43b16-103">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="43b16-103">Error remediation when processing data</span></span>

<span data-ttu-id="43b16-104">Исправление ошибок позволяет администраторам eDiscovery исправлять проблемы с данными, которые не позволяют Advanced eDiscovery правильно обрабатывать контент.</span><span class="sxs-lookup"><span data-stu-id="43b16-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="43b16-105">Например, файлы, защищенные паролем, не могут быть обработаны, так как они заблокированы или зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="43b16-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="43b16-106">Используя исправление ошибок, администраторы eDiscovery могут скачивать файлы с такими ошибками, удалять защиту паролем, а затем загружать исправленные файлы.</span><span class="sxs-lookup"><span data-stu-id="43b16-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="43b16-107">Используйте следующий рабочий процесс для устранения ошибок в случаях Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="43b16-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="43b16-108">Создание сеанса устранения ошибок для устранения файлов с ошибками обработки</span><span class="sxs-lookup"><span data-stu-id="43b16-108">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="43b16-109">Если мастер устранения ошибок в любое время закрывается в течение следующей процедуры, можно вернуться к  сеансу устранения  ошибок на вкладке "Обработка", выбрав "Исправление" в меню "Вид" в выпаданом меню. </span><span class="sxs-lookup"><span data-stu-id="43b16-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="43b16-110">На вкладке **"Обработка"** в случае Advanced eDiscovery выберите "Ошибки" в меню "Вид", а затем выберите набор для проверки или все дело в меню "Область".   </span><span class="sxs-lookup"><span data-stu-id="43b16-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="43b16-111">В этом разделе отображаются все ошибки из дела или ошибки из определенного набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="43b16-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![Исправление ошибок](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="43b16-113">Выберите ошибки, которые необходимо устранять, нажав кнопку радио рядом с типом ошибки или типом файла.</span><span class="sxs-lookup"><span data-stu-id="43b16-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="43b16-114">В следующем примере мы из исправлений файла, защищенного паролем.</span><span class="sxs-lookup"><span data-stu-id="43b16-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="43b16-115">Щелкните **"Новое исправление ошибки"**.</span><span class="sxs-lookup"><span data-stu-id="43b16-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="43b16-116">Рабочий процесс устранения ошибок начинается с этапа подготовки, на котором файлы с ошибками копируется в предоставленное Корпорацией Майкрософт хранилище Azure, чтобы вы могли скачать их на локальный компьютер для устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="43b16-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Подготовка устранения ошибок](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="43b16-118">После завершения подготовки нажмите кнопку **"Далее:" скачайте** файлы, чтобы продолжить скачивание.</span><span class="sxs-lookup"><span data-stu-id="43b16-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Загрузка файлов](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="43b16-120">Чтобы скачать файлы, укажите **путь назначения для скачивания.**</span><span class="sxs-lookup"><span data-stu-id="43b16-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="43b16-121">Это путь к родительской папке на локальном компьютере, куда будет загружен файл.</span><span class="sxs-lookup"><span data-stu-id="43b16-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="43b16-122">Путь по умолчанию % USERPROFILE%\Downloads\errors указывает на папку скачиваемых данных во время входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="43b16-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="43b16-123">При желании этот путь можно изменить.</span><span class="sxs-lookup"><span data-stu-id="43b16-123">You can change this path if desired.</span></span> <span data-ttu-id="43b16-124">Если вы измените его, рекомендуется использовать локальный путь к файлу для лучшей производительности.</span><span class="sxs-lookup"><span data-stu-id="43b16-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="43b16-125">Не используйте удаленный сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="43b16-125">Don't use a remote network path.</span></span> <span data-ttu-id="43b16-126">Например, можно использовать путь **C:\Remediation.**</span><span class="sxs-lookup"><span data-stu-id="43b16-126">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="43b16-127">Путь к родительской папке автоматически добавляется в команду AzCopy (в качестве значения параметра **/Dest).**</span><span class="sxs-lookup"><span data-stu-id="43b16-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="43b16-128">Скопируйте предопределную команду, нажав кнопку **"Копировать в буфер обмена".**</span><span class="sxs-lookup"><span data-stu-id="43b16-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="43b16-129">Откройте командную подсказку Windows, введите команду AzCopy и **нажмите** ввод.</span><span class="sxs-lookup"><span data-stu-id="43b16-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![Подготовка к исправлению ошибок](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="43b16-131">Для успешного использования команды, предоставленной на странице загрузки файлов,  необходимо использовать AzCopy 8.1.</span><span class="sxs-lookup"><span data-stu-id="43b16-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="43b16-132">Для отправки файлов на шаге 10 также необходимо использовать AzCopy 8.1.</span><span class="sxs-lookup"><span data-stu-id="43b16-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="43b16-133">Чтобы установить эту версию AzCopy, см. сведения о передаче данных [с AzCopy версии 8.1 в Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="43b16-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="43b16-134">Если сбой предоставленной команды AzCopy, см. "Устранение неполадок [AzCopy в Advanced eDiscovery".](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="43b16-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="43b16-135">Выбранные файлы загружаются в расположение, указанное на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="43b16-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="43b16-136">В родительской папке (например, **C:\Remediation)** автоматически создается следующая структура вложенных папок:</span><span class="sxs-lookup"><span data-stu-id="43b16-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="43b16-137">В зависимости от области действия, выбранной на шаге *1,* подпапка 1 называется с ИД для дела или набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="43b16-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="43b16-138">*Имя в папке 2—* с ИД загруженного файла</span><span class="sxs-lookup"><span data-stu-id="43b16-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="43b16-139">Загруженный файл находится во в *папке Subfolder 2* и имеет имя с ИД файла.</span><span class="sxs-lookup"><span data-stu-id="43b16-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="43b16-140">Вот пример пути к папке и имени файла ошибки, которые создаются при загрузке элементов в родительную папку **C:\Remediation:**</span><span class="sxs-lookup"><span data-stu-id="43b16-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="43b16-141">Если скачано несколько файлов, каждый из них загружается во в папку с именем с именем именем файла ID.</span><span class="sxs-lookup"><span data-stu-id="43b16-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="43b16-142">При отправке файлов в шаге 9 и 10, исправленные файлы должны иметь такое же имя файла и должны быть расположены в той же структуре вложенных вложенных файлов.</span><span class="sxs-lookup"><span data-stu-id="43b16-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="43b16-143">Имена вуза и файлов используются для связи исправленного файла с исходным файлом ошибки.</span><span class="sxs-lookup"><span data-stu-id="43b16-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="43b16-144">Если изменить структуру папок или имена файлов, вы получите следующую `Cannot apply Error Remediation to the current Workingset` ошибку:</span><span class="sxs-lookup"><span data-stu-id="43b16-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="43b16-145">Во избежание проблем рекомендуется хранить исправленные файлы в одной родительской папке и вложенной структуре.</span><span class="sxs-lookup"><span data-stu-id="43b16-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="43b16-146">Скачав файлы, вы можете их исправление с помощью соответствующего средства.</span><span class="sxs-lookup"><span data-stu-id="43b16-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="43b16-147">Для файлов, защищенных паролем, можно использовать несколько средств взлома паролей.</span><span class="sxs-lookup"><span data-stu-id="43b16-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="43b16-148">Если вы знаете пароли для файлов, вы можете открыть их и удалить защиту паролем.</span><span class="sxs-lookup"><span data-stu-id="43b16-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="43b16-149">Верните в Advanced eDiscovery и мастер устранения ошибок, а затем нажмите кнопку **"Далее: отправить файлы".**</span><span class="sxs-lookup"><span data-stu-id="43b16-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="43b16-150">Теперь файлы можно отправить на следующую страницу.</span><span class="sxs-lookup"><span data-stu-id="43b16-150">This moves to the next page where you can now upload the files.</span></span>

    ![Отправка файлов](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="43b16-152">Укажите родительская папка, в которой исправленные файлы находятся в поле "Путь к папке с **текстовым полем файлов".**</span><span class="sxs-lookup"><span data-stu-id="43b16-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="43b16-153">Опять же, родительская папка должна иметь ту же структуру вложенных папок, которая была создана при загрузке файлов.</span><span class="sxs-lookup"><span data-stu-id="43b16-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="43b16-154">Путь к родительской папке автоматически добавляется в команду AzCopy (в качестве значения параметра **/Source).**</span><span class="sxs-lookup"><span data-stu-id="43b16-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="43b16-155">Скопируйте предопределную команду, нажав кнопку **"Копировать в буфер обмена".**</span><span class="sxs-lookup"><span data-stu-id="43b16-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="43b16-156">Откройте командную подсказку Windows, введите команду AzCopy и **нажмите** ввод.</span><span class="sxs-lookup"><span data-stu-id="43b16-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="43b16-157">отправка файлов.</span><span class="sxs-lookup"><span data-stu-id="43b16-157">upload the files.</span></span>

    ![Результаты успешной отправки исправленных файлов в Azcopy](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="43b16-159">После запуска команды AzCopy нажмите кнопку **"Далее: обработка файлов".**</span><span class="sxs-lookup"><span data-stu-id="43b16-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="43b16-160">После завершения обработки можно перейти в набор для проверки и просмотреть исправленные файлы.</span><span class="sxs-lookup"><span data-stu-id="43b16-160">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="43b16-161">Устранение ошибок в файлах контейнеров</span><span class="sxs-lookup"><span data-stu-id="43b16-161">Remediating errors in container files</span></span>

<span data-ttu-id="43b16-162">В случаях, когда advanced eDiscovery не может извлечь содержимое файла контейнера (например, ZIP-файл), контейнеры можно загрузить и развернуть в той же папке, в которой находится исходный контейнер.</span><span class="sxs-lookup"><span data-stu-id="43b16-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="43b16-163">Расширенные файлы будут присвоены родительскому контейнеру, как если бы он был изначально расширен Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="43b16-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="43b16-164">Процесс работает, как описано выше, за исключением отправки одного файла в качестве заменяемой.</span><span class="sxs-lookup"><span data-stu-id="43b16-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="43b16-165">При отправке исправленных файлов не включите исходный файл контейнера.</span><span class="sxs-lookup"><span data-stu-id="43b16-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="43b16-166">Исправление ошибок путем отправки извлеченного текста</span><span class="sxs-lookup"><span data-stu-id="43b16-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="43b16-167">Иногда невозможно восстановить формат файла, который advanced eDiscovery может интерпретировать.</span><span class="sxs-lookup"><span data-stu-id="43b16-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="43b16-168">Но вы можете заменить исходный файл текстовым файлом, который содержит исходный текст исходного файла (в процессе, называемом *текстовым наложением).*</span><span class="sxs-lookup"><span data-stu-id="43b16-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="43b16-169">Для этого выполните действия, описанные в этой статье, но вместо того, чтобы устранять исходный файл в исходном формате, необходимо создать текстовый файл, содержащий извлеченный текст из исходного файла, а затем отправить текстовый файл с использованием исходного имени файла, добавленного с суффиксом TXT.</span><span class="sxs-lookup"><span data-stu-id="43b16-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="43b16-170">Например, вы скачиваете файл во время устранения ошибок с и имям файла 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span><span class="sxs-lookup"><span data-stu-id="43b16-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="43b16-171">Вы открываете файл в приложении, копируете текст, а затем в paste его в новый файл с именем 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span><span class="sxs-lookup"><span data-stu-id="43b16-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="43b16-172">При этом обязательно удалите исходный файл в исходном формате из расположения исправленных файлов на локальном компьютере перед отправкой исправленного текстового файла в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="43b16-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="43b16-173">Что происходит при исправлении файлов</span><span class="sxs-lookup"><span data-stu-id="43b16-173">What happens when files are remediated</span></span>

<span data-ttu-id="43b16-174">При отправке исправленных файлов исходные метаданные сохраняются за исключением следующих полей:</span><span class="sxs-lookup"><span data-stu-id="43b16-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="43b16-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="43b16-175">ExtractedTextSize</span></span>
- <span data-ttu-id="43b16-176">HasText</span><span class="sxs-lookup"><span data-stu-id="43b16-176">HasText</span></span>
- <span data-ttu-id="43b16-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="43b16-177">IsErrorRemediate</span></span>
- <span data-ttu-id="43b16-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="43b16-178">LoadId</span></span>
- <span data-ttu-id="43b16-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="43b16-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="43b16-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="43b16-180">ProcessingStatus</span></span>
- <span data-ttu-id="43b16-181">Текст</span><span class="sxs-lookup"><span data-stu-id="43b16-181">Text</span></span>
- <span data-ttu-id="43b16-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="43b16-182">WordCount</span></span>
- <span data-ttu-id="43b16-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="43b16-183">WorkingsetId</span></span>

<span data-ttu-id="43b16-184">Определение всех полей метаданных в Advanced eDiscovery см. в полях [метаданных документа.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="43b16-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
