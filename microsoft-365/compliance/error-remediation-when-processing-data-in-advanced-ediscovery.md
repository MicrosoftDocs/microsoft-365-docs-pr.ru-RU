---
title: Исправление ошибок при обработке данных
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
description: ''
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090367"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="00ddf-102">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="00ddf-102">Error remediation when processing data</span></span>

<span data-ttu-id="00ddf-103">Устранение ошибок позволяет администраторам обнаружения электронных данных устранить проблемы с данными, которые предотвращают неправильное обработку содержимого для расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="00ddf-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="00ddf-104">Например, файлы, защищенные паролем, не могут быть обработаны, так как файлы заблокированы или зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="00ddf-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="00ddf-105">С помощью исправления ошибок администраторы обнаружения электронных данных могут загружать файлы с такими ошибками, удалять защиту паролем, а затем отправлять исправленные файлы.</span><span class="sxs-lookup"><span data-stu-id="00ddf-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="00ddf-106">Используйте следующий рабочий процесс для исправления файлов с ошибками в дополнительных случаях обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="00ddf-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="00ddf-107">Создание сеанса исправления ошибок для исправления файлов с ошибками обработки</span><span class="sxs-lookup"><span data-stu-id="00ddf-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="00ddf-108">Если мастер исправления ошибок закрыт в любой момент во время выполнения следующей процедуры, вы можете вернуться к сеансу исправления ошибок на вкладке **Обработка** , выбрав пункт **исправления** в раскрывающемся меню **вид** .</span><span class="sxs-lookup"><span data-stu-id="00ddf-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="00ddf-109">На вкладке **Обработка** в расширенном случае обнаружения электронных данных в раскрывающемся меню **вид** выберите **ошибки** , а затем в раскрывающемся меню **область** выберите набор проверок или все дела.</span><span class="sxs-lookup"><span data-stu-id="00ddf-109">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="00ddf-110">В этом разделе отображаются все ошибки из определенного набора рецензирования или сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="00ddf-110">This section displays all errors from the case or error from a specific review set.</span></span>

   ![Исправление ошибок](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="00ddf-112">Выберите подлежащие исправлению ошибки, нажав переключатель рядом с типом ошибки или типом файла.</span><span class="sxs-lookup"><span data-stu-id="00ddf-112">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="00ddf-113">В следующем примере мы устранение файл, защищенный паролем.</span><span class="sxs-lookup"><span data-stu-id="00ddf-113">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="00ddf-114">Нажмите кнопку **новое исправление ошибок**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-114">Click **New error remediation**.</span></span>

    <span data-ttu-id="00ddf-115">Рабочий процесс исправления ошибок начинается с стадии подготовки, где файлы с ошибками копируются в хранилище Azure, предоставленное корпорацией Майкрософт, чтобы их можно было загрузить на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="00ddf-115">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Подготовка исправления ошибок](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="00ddf-117">По завершении подготовки нажмите кнопку **Далее: Загрузка файлов** для продолжения загрузки.</span><span class="sxs-lookup"><span data-stu-id="00ddf-117">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Загрузка файлов](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="00ddf-119">Чтобы скачать файлы, укажите **целевой путь для скачивания**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="00ddf-120">Это путь к родительской папке на локальном компьютере, в которую будет загружен файл.</span><span class="sxs-lookup"><span data-stu-id="00ddf-120">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="00ddf-121">Путь по умолчанию,%Усерпрофиле%\довнлоадс\еррорс, указывает на папку загрузок пользователя, выполнившего вход в систему.</span><span class="sxs-lookup"><span data-stu-id="00ddf-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="00ddf-122">При необходимости вы можете изменить этот путь.</span><span class="sxs-lookup"><span data-stu-id="00ddf-122">You can change this path if desired.</span></span> <span data-ttu-id="00ddf-123">Если вы сделаете это, рекомендуем использовать локальный путь к файлу для достижения оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="00ddf-123">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="00ddf-124">Не используйте удаленный сетевой путь.</span><span class="sxs-lookup"><span data-stu-id="00ddf-124">Don't use a remote network path.</span></span> <span data-ttu-id="00ddf-125">Например, можно использовать путь **к:\ремедиатион**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-125">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="00ddf-126">Путь к родительской папке автоматически добавляется в команду AzCopy (в качестве значения параметра **/Дест** ).</span><span class="sxs-lookup"><span data-stu-id="00ddf-126">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="00ddf-127">Скопируйте предопределенную команду, нажав кнопку **Копировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-127">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="00ddf-128">Откройте командную строку Windows, вставьте команду AzCopy и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-128">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![Подготовка к исправлению ошибок](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="00ddf-130">Для успешного использования команды, указанной на странице **Загрузка файлов** , необходимо использовать AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="00ddf-130">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="00ddf-131">Кроме того, для отправки файлов на шаге 10 необходимо использовать AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="00ddf-131">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="00ddf-132">Чтобы установить эту версию AzCopy, обратитесь к разделу [Transfer Data with a AzCopy v 8.1 в Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="00ddf-132">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="00ddf-133">Если предоставленная команда AzCopy не удалась, обратитесь к разделу [Устранение неполадок AzCopy в Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="00ddf-133">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="00ddf-134">Выбранные файлы будут скачаны в папку, указанную в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="00ddf-134">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="00ddf-135">В родительской папке (например, **к:\ремедиатион**) автоматически создается следующая структура вложенных папок:</span><span class="sxs-lookup"><span data-stu-id="00ddf-135">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="00ddf-136">*Вложенная папка 1* называется идентификатором или набором проверки в зависимости от области, выбранной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="00ddf-136">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="00ddf-137">*Вложенная папка 2* называется идентификатором файла скачанного файла.</span><span class="sxs-lookup"><span data-stu-id="00ddf-137">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="00ddf-138">Загруженный файл находится в *подпапке 2* , а также называется идентификатором файла.</span><span class="sxs-lookup"><span data-stu-id="00ddf-138">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="00ddf-139">Ниже приведен пример пути к папке и имени файла ошибок, созданного при загрузке элементов в родительскую папку **к:\ремедиатион** :</span><span class="sxs-lookup"><span data-stu-id="00ddf-139">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="00ddf-140">Если загружено несколько файлов, каждый из них загружается в вложенную папку с именем файла.</span><span class="sxs-lookup"><span data-stu-id="00ddf-140">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="00ddf-141">При отправке файлов на шаге 9 и 10 файлы исправленных файлов должны быть расположены в той же структуре вложенных папок.</span><span class="sxs-lookup"><span data-stu-id="00ddf-141">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="00ddf-142">Подпапка и имена файлов используются для сопоставления исправленного файла с исходным файлом ошибок.</span><span class="sxs-lookup"><span data-stu-id="00ddf-142">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="00ddf-143">Если изменилась структура папок или имена файлов, появится следующее сообщение об ошибке: `Cannot apply Error Remediation to the current Workingset`.</span><span class="sxs-lookup"><span data-stu-id="00ddf-143">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="00ddf-144">Чтобы предотвратить возникновение проблем, рекомендуется хранить исправленные файлы в одной родительской папке и вложенной папке.</span><span class="sxs-lookup"><span data-stu-id="00ddf-144">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="00ddf-145">После загрузки файлов вы можете исправить их с помощью соответствующего средства.</span><span class="sxs-lookup"><span data-stu-id="00ddf-145">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="00ddf-146">Для файлов, защищенных паролем, можно использовать несколько средств взлома паролей.</span><span class="sxs-lookup"><span data-stu-id="00ddf-146">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="00ddf-147">Если вы знаете пароли этих файлов, вы можете открыть их и удалить защиту паролем.</span><span class="sxs-lookup"><span data-stu-id="00ddf-147">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="00ddf-148">Вернитесь к расширенному eDiscovery и мастеру исправления ошибок, а затем нажмите кнопку **Далее: отправить файлы**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-148">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="00ddf-149">Это перейдет на следующую страницу, где теперь можно отправить файлы.</span><span class="sxs-lookup"><span data-stu-id="00ddf-149">This moves to the next page where you can now upload the files.</span></span>

    ![Отправка файлов](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="00ddf-151">Укажите родительскую папку, в которой находятся исправленные файлы, в текстовом поле **путь к расположению файлов** .</span><span class="sxs-lookup"><span data-stu-id="00ddf-151">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="00ddf-152">Опять же, у родительской папки должна быть одна и та же структура вложенных папок, созданная при загрузке файлов.</span><span class="sxs-lookup"><span data-stu-id="00ddf-152">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="00ddf-153">Путь к родительской папке автоматически добавляется в команду AzCopy (в качестве значения параметра **/Source** ).</span><span class="sxs-lookup"><span data-stu-id="00ddf-153">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="00ddf-154">Скопируйте предопределенную команду, нажав кнопку **Копировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-154">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="00ddf-155">Откройте командную строку Windows, вставьте команду AzCopy и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-155">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="00ddf-156">Отправьте файлы.</span><span class="sxs-lookup"><span data-stu-id="00ddf-156">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="00ddf-158">После выполнения команды AzCopy нажмите кнопку **Далее: обработка файлов**.</span><span class="sxs-lookup"><span data-stu-id="00ddf-158">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="00ddf-159">После завершения обработки можно перейти к разделу Обзор Set и просмотреть исправленные файлы.</span><span class="sxs-lookup"><span data-stu-id="00ddf-159">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="00ddf-160">Что происходит при исправлении файлов</span><span class="sxs-lookup"><span data-stu-id="00ddf-160">What happens when files are remediated</span></span>

<span data-ttu-id="00ddf-161">При отправке исправленных файлов исходные метаданные сохраняются, за исключением следующих полей:</span><span class="sxs-lookup"><span data-stu-id="00ddf-161">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="00ddf-162">екстрактедтекстсизе</span><span class="sxs-lookup"><span data-stu-id="00ddf-162">ExtractedTextSize</span></span>
- <span data-ttu-id="00ddf-163">HasText</span><span class="sxs-lookup"><span data-stu-id="00ddf-163">HasText</span></span>
- <span data-ttu-id="00ddf-164">исеррорремедиате</span><span class="sxs-lookup"><span data-stu-id="00ddf-164">IsErrorRemediate</span></span>
- <span data-ttu-id="00ddf-165">лоадид</span><span class="sxs-lookup"><span data-stu-id="00ddf-165">LoadId</span></span>
- <span data-ttu-id="00ddf-166">процессинжеррормессаже</span><span class="sxs-lookup"><span data-stu-id="00ddf-166">ProcessingErrorMessage</span></span>
- <span data-ttu-id="00ddf-167">процессингстатус</span><span class="sxs-lookup"><span data-stu-id="00ddf-167">ProcessingStatus</span></span>
- <span data-ttu-id="00ddf-168">Текст</span><span class="sxs-lookup"><span data-stu-id="00ddf-168">Text</span></span>
- <span data-ttu-id="00ddf-169">WordCount</span><span class="sxs-lookup"><span data-stu-id="00ddf-169">WordCount</span></span>
- <span data-ttu-id="00ddf-170">воркингсетид</span><span class="sxs-lookup"><span data-stu-id="00ddf-170">WorkingsetId</span></span>

<span data-ttu-id="00ddf-171">Для определения всех полей метаданных в Advanced eDiscovery просмотрите [поля метаданных документа](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="00ddf-171">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
