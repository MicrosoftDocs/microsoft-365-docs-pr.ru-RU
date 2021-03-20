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
description: Узнайте, как использовать устранение ошибок для устранения проблем с данными в advanced eDiscovery, которые могут предотвратить надлежащую обработку контента.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2067831a85e3b3a506917fac5b93acfa0b174db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906987"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="7d81a-103">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="7d81a-103">Error remediation when processing data</span></span>

<span data-ttu-id="7d81a-104">Устранение ошибок позволяет администраторам eDiscovery устранять проблемы с данными, которые не позволяют advanced eDiscovery правильно обрабатывать содержимое.</span><span class="sxs-lookup"><span data-stu-id="7d81a-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="7d81a-105">Например, файлы, защищенные паролем, не могут обрабатываться, так как файлы заблокированы или зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="7d81a-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="7d81a-106">С помощью устранения ошибок администраторы eDiscovery могут загружать файлы с такими ошибками, удалять защиту паролей, а затем загружать исправленные файлы.</span><span class="sxs-lookup"><span data-stu-id="7d81a-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="7d81a-107">Используйте следующий рабочий процесс для устранения файлов с ошибками в случаях предварительного электронного разбора.</span><span class="sxs-lookup"><span data-stu-id="7d81a-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="7d81a-108">Создание сеанса устранения ошибок для устранения файлов с помощью ошибок обработки</span><span class="sxs-lookup"><span data-stu-id="7d81a-108">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="7d81a-109">Если мастер устранения ошибок закрывается в любое время во время следующей процедуры, вы можете вернуться  к сеансу устранения ошибок со вкладки **Обработка,** выбрав исправление в выпадаемом меню **View.**</span><span class="sxs-lookup"><span data-stu-id="7d81a-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="7d81a-110">На вкладке **Обработка** в случае расширенных  данных об обнаружении электронных данных выберите Ошибки в выпадаемом меню **View,** а затем выберите набор отзывов или весь случай в выпадаемом меню **Scope.**</span><span class="sxs-lookup"><span data-stu-id="7d81a-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="7d81a-111">В этом разделе отображаются все ошибки из случая или ошибки из определенного набора обзоров.</span><span class="sxs-lookup"><span data-stu-id="7d81a-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![Устранение ошибок](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="7d81a-113">Выберите ошибки, которые необходимо устранять, нажав кнопку радио рядом с типом ошибки или типом файла.</span><span class="sxs-lookup"><span data-stu-id="7d81a-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="7d81a-114">В следующем примере мы устраняем защищенный паролем файл.</span><span class="sxs-lookup"><span data-stu-id="7d81a-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="7d81a-115">Щелкните **Новое исправление ошибок**.</span><span class="sxs-lookup"><span data-stu-id="7d81a-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="7d81a-116">Рабочий процесс устранения ошибок начинается с этапа подготовки, на котором файлы с ошибками копируется в расположение хранилища Azure, предоставленное Майкрософт, чтобы можно было скачать их на локальный компьютер для их устранения.</span><span class="sxs-lookup"><span data-stu-id="7d81a-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Подготовка устранения ошибок](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="7d81a-118">После завершения подготовки нажмите **кнопку Далее: Скачайте файлы** для загрузки.</span><span class="sxs-lookup"><span data-stu-id="7d81a-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Загрузка файлов](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="7d81a-120">Чтобы загрузить файлы, укажите **путь назначения для скачивания.**</span><span class="sxs-lookup"><span data-stu-id="7d81a-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="7d81a-121">Это путь к родительской папке на локальном компьютере, куда будет загружен файл.</span><span class="sxs-lookup"><span data-stu-id="7d81a-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="7d81a-122">Путь по умолчанию % USERPROFILE%\Downloads\errors указывает на папку скачиваемых пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d81a-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="7d81a-123">Этот путь можно изменить при желании.</span><span class="sxs-lookup"><span data-stu-id="7d81a-123">You can change this path if desired.</span></span> <span data-ttu-id="7d81a-124">Если вы измените его, рекомендуем использовать локальный путь к файлам для лучшей производительности.</span><span class="sxs-lookup"><span data-stu-id="7d81a-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="7d81a-125">Не используйте удаленный сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="7d81a-125">Don't use a remote network path.</span></span> <span data-ttu-id="7d81a-126">Например, можно использовать путь **C:\Remediation**.</span><span class="sxs-lookup"><span data-stu-id="7d81a-126">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="7d81a-127">Путь к родительской папке автоматически добавляется в команду AzCopy (как значение **параметра /Dest).**</span><span class="sxs-lookup"><span data-stu-id="7d81a-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="7d81a-128">Скопируйте предопределяемую команду, нажав **копию на буфер обмена.**</span><span class="sxs-lookup"><span data-stu-id="7d81a-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="7d81a-129">Откройте командную подсказку Windows, введите команду AzCopy и нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="7d81a-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![Подготовка к устранению ошибок](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="7d81a-131">Чтобы успешно использовать команду, предоставленную на странице Загрузка файлов,  необходимо использовать azCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="7d81a-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="7d81a-132">Для загрузки файлов в шаге 10 необходимо также использовать azCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="7d81a-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="7d81a-133">Чтобы установить эту версию AzCopy, см. в рублях Передача данных с [помощью приложения AzCopy v8.1 в Windows.](/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="7d81a-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="7d81a-134">Если предоставленная команда AzCopy сбой, см. в руб. Устранение неполадок [AzCopy в advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="7d81a-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="7d81a-135">Выбранные файлы загружаются в указанное в шаге 5 расположение.</span><span class="sxs-lookup"><span data-stu-id="7d81a-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="7d81a-136">В родительской папке (например, **C:\Remediation)** автоматически создается следующая структура подстройки:</span><span class="sxs-lookup"><span data-stu-id="7d81a-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="7d81a-137">*Subfolder 1* называется с ID для дела или набора отзывов в зависимости от области, выбранной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="7d81a-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="7d81a-138">*Subfolder 2* называется с файлом ID загруженного файла</span><span class="sxs-lookup"><span data-stu-id="7d81a-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="7d81a-139">Загруженный файл расположен в *Subfolder 2* и также называется с ИД файла.</span><span class="sxs-lookup"><span data-stu-id="7d81a-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="7d81a-140">Вот пример пути папки и имени файла ошибок, созданных при загрузке элементов в родительную папку **C:\Remediation:**</span><span class="sxs-lookup"><span data-stu-id="7d81a-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="7d81a-141">Если загружено несколько файлов, каждый из них загружается в подмостки, названные с ИД файла.</span><span class="sxs-lookup"><span data-stu-id="7d81a-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7d81a-142">При загрузке файлов на этапе 9 и шаге 10 исправленные файлы должны иметь то же имя файла и располагаться в одной структуре подложки.</span><span class="sxs-lookup"><span data-stu-id="7d81a-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="7d81a-143">Имена и имена файлов используются для связи исправленного файла с исходным файлом ошибок.</span><span class="sxs-lookup"><span data-stu-id="7d81a-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="7d81a-144">Если структура папки или имена файлов будут изменены, вы получите следующую ошибку: `Cannot apply Error Remediation to the current Workingset` .</span><span class="sxs-lookup"><span data-stu-id="7d81a-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="7d81a-145">Чтобы предотвратить какие-либо проблемы, рекомендуется хранить исправленные файлы в одной родительской папке и структуре подмостков.</span><span class="sxs-lookup"><span data-stu-id="7d81a-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="7d81a-146">После скачивания файлов можно их исправление с помощью соответствующего средства.</span><span class="sxs-lookup"><span data-stu-id="7d81a-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="7d81a-147">Для файлов, защищенных паролем, можно использовать несколько средств взлома паролей.</span><span class="sxs-lookup"><span data-stu-id="7d81a-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="7d81a-148">Если вы знаете пароли для файлов, вы можете открыть их и удалить защиту паролей.</span><span class="sxs-lookup"><span data-stu-id="7d81a-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="7d81a-149">Вернись к advanced eDiscovery и мастеру устранения ошибок, а затем нажмите **кнопку Далее: Загрузите файлы**.</span><span class="sxs-lookup"><span data-stu-id="7d81a-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="7d81a-150">Это перемещается на следующую страницу, на которой теперь можно загрузить файлы.</span><span class="sxs-lookup"><span data-stu-id="7d81a-150">This moves to the next page where you can now upload the files.</span></span>

    ![Загрузка файлов](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="7d81a-152">Укажите родительную папку, в которой исправленные файлы находятся в пути к **расположению текстового** окна файлов.</span><span class="sxs-lookup"><span data-stu-id="7d81a-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="7d81a-153">Опять же, родительская папка должна иметь ту же структуру подмостки, которая была создана при скачиве файлов.</span><span class="sxs-lookup"><span data-stu-id="7d81a-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="7d81a-154">Путь к родительской папке автоматически добавляется в команду AzCopy (как значение **параметра /Source).**</span><span class="sxs-lookup"><span data-stu-id="7d81a-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="7d81a-155">Скопируйте предопределяемую команду, нажав **копию на буфер обмена.**</span><span class="sxs-lookup"><span data-stu-id="7d81a-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="7d81a-156">Откройте командную подсказку Windows, введите команду AzCopy и нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="7d81a-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="7d81a-157">загрузите файлы.</span><span class="sxs-lookup"><span data-stu-id="7d81a-157">upload the files.</span></span>

    ![Результаты успешной загрузки исправленных файлов в Azcopy](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="7d81a-159">После запуска команды AzCopy нажмите **кнопку Далее: Файлы процесса**.</span><span class="sxs-lookup"><span data-stu-id="7d81a-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="7d81a-160">После завершения обработки можно просмотреть набор и просмотреть исправленные файлы.</span><span class="sxs-lookup"><span data-stu-id="7d81a-160">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="7d81a-161">Исправление ошибок в контейнерных файлах</span><span class="sxs-lookup"><span data-stu-id="7d81a-161">Remediating errors in container files</span></span>

<span data-ttu-id="7d81a-162">В ситуациях, когда содержимое контейнерного файла (например, почтовый файл) не может быть извлечено расширенным электронным открытием, контейнеры могут быть загружены и содержимое расширено в ту же папку, в которой находится исходный контейнер.</span><span class="sxs-lookup"><span data-stu-id="7d81a-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="7d81a-163">Расширенные файлы будут приписываться родительскому контейнеру, как если бы он был первоначально расширен расширенным электронным открытием.</span><span class="sxs-lookup"><span data-stu-id="7d81a-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="7d81a-164">Процесс работает так, как описано выше, за исключением отправки одного файла в качестве файла замены.</span><span class="sxs-lookup"><span data-stu-id="7d81a-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="7d81a-165">При отправке исправленных файлов не включите исходный файл контейнера.</span><span class="sxs-lookup"><span data-stu-id="7d81a-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="7d81a-166">Исправление ошибок путем отправки извлеченного текста</span><span class="sxs-lookup"><span data-stu-id="7d81a-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="7d81a-167">Иногда невозможно восстановить файл в родном формате, который может интерпретировать advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7d81a-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="7d81a-168">Но можно заменить исходный файл текстовым файлом, который содержит исходный текст исходного файла (в процессе, называемом *текстовым наложением).*</span><span class="sxs-lookup"><span data-stu-id="7d81a-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="7d81a-169">Для этого выполните действия, описанные в этой статье, но вместо восстановления исходного файла в родном формате создайте текстовый файл, содержащий извлеченный текст из исходного файла, а затем загрузите текстовый файл с помощью исходного имени файла, добавленного с суффиксом .txt.</span><span class="sxs-lookup"><span data-stu-id="7d81a-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="7d81a-170">Например, вы скачиваете файл во время устранения ошибок с помощью имени файла 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span><span class="sxs-lookup"><span data-stu-id="7d81a-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="7d81a-171">Вы откроете файл в родном приложении, скопируете текст и вклеите его в новый файл с именем 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span><span class="sxs-lookup"><span data-stu-id="7d81a-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="7d81a-172">При этом обязательно удалите исходный файл в исходном формате из исправленного расположения файла на локальном компьютере перед отправкой исправленного текстового файла в Расширенный электронный архив.</span><span class="sxs-lookup"><span data-stu-id="7d81a-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="7d81a-173">Что происходит при исправлении файлов</span><span class="sxs-lookup"><span data-stu-id="7d81a-173">What happens when files are remediated</span></span>

<span data-ttu-id="7d81a-174">При отправке исправленных файлов исходные метаданные сохраняются, за исключением следующих полей:</span><span class="sxs-lookup"><span data-stu-id="7d81a-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="7d81a-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="7d81a-175">ExtractedTextSize</span></span>
- <span data-ttu-id="7d81a-176">HasText</span><span class="sxs-lookup"><span data-stu-id="7d81a-176">HasText</span></span>
- <span data-ttu-id="7d81a-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="7d81a-177">IsErrorRemediate</span></span>
- <span data-ttu-id="7d81a-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="7d81a-178">LoadId</span></span>
- <span data-ttu-id="7d81a-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="7d81a-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="7d81a-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="7d81a-180">ProcessingStatus</span></span>
- <span data-ttu-id="7d81a-181">Текст</span><span class="sxs-lookup"><span data-stu-id="7d81a-181">Text</span></span>
- <span data-ttu-id="7d81a-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="7d81a-182">WordCount</span></span>
- <span data-ttu-id="7d81a-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="7d81a-183">WorkingsetId</span></span>

<span data-ttu-id="7d81a-184">Определение всех полей метаданных в advanced eDiscovery см. в [документе.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="7d81a-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields-in-advanced-ediscovery.md).</span></span>