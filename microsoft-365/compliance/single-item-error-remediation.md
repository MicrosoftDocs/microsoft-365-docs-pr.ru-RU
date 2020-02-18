---
title: Исправление ошибки одного элемента
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
description: Ошибку обработки можно исправить в документе в наборе рецензирования в Advanced eDiscovery, не выполняя процесс исправления ошибок с пакетом исправлений.
ms.openlocfilehash: 3c50f9dcd1448ee36edd0e82e5b2c2879c11d6b5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069707"
---
# <a name="single-item-error-remediation"></a><span data-ttu-id="729f7-103">Исправление ошибки одного элемента</span><span class="sxs-lookup"><span data-stu-id="729f7-103">Single item error remediation</span></span>

<span data-ttu-id="729f7-104">Устранение ошибок дает расширенным пользователям обнаружения электронных данных возможность исправить проблемы с данными, которые препятствуют правильной обработке содержимого с помощью расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="729f7-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="729f7-105">Например, невозможно обработать файлы, защищенные паролем, так как эти файлы заблокированы или зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="729f7-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="729f7-106">Ранее при использовании [этого рабочего процесса](error-remediation-when-processing-data-in-advanced-ediscovery.md)можно исправить ошибки только в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="729f7-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="729f7-107">Однако в некоторых случаях не имеет смысла устранять ошибки в нескольких файлах, если вы не уверены в том, что какой – либо из этих файлов отвечает на случай, если вы изучаете их.</span><span class="sxs-lookup"><span data-stu-id="729f7-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="729f7-108">Кроме того, не имеет смысла устранять ошибки перед тем, как вы сможете просматривать метаданные файлов (например, расположение файлов или доступ к ним), которые помогут вам принять решение о реагировании.</span><span class="sxs-lookup"><span data-stu-id="729f7-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="729f7-109">Новая функция, называемая *одним элементом исправления ошибок* , дает менеджерам обнаружения электронных данных возможность просматривать метаданные файлов с ошибкой обработки и при необходимости исправлять ошибку непосредственно в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="729f7-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="729f7-110">В этой статье описывается, как определять, игнорировать и исправлять файлы с ошибками обработки в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="729f7-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="729f7-111">Определение документов с ошибками</span><span class="sxs-lookup"><span data-stu-id="729f7-111">Identify documents with errors</span></span>

<span data-ttu-id="729f7-112">Документы с ошибками обработки в наборе проверки теперь определены (с заголовком).</span><span class="sxs-lookup"><span data-stu-id="729f7-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="729f7-113">Вы можете исправить или пропустить ошибку.</span><span class="sxs-lookup"><span data-stu-id="729f7-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="729f7-114">На следующем снимке экрана показан баннер ошибки обработки документа Word в наборе рецензирования, защищенном паролем.</span><span class="sxs-lookup"><span data-stu-id="729f7-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="729f7-115">Кроме того, обратите внимание на то, что вы можете просматривать метаданные файлов документов с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="729f7-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Баннер, отображаемый для документа с ошибкой обработки](../media/SIERimage1.png)

<span data-ttu-id="729f7-117">Кроме того, можно выполнять поиск документов, содержащих ошибки обработки, с помощью условия **состояния обработки** при [запросе документов в наборе рецензирования](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="729f7-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Использование условия состояния обработки для поиска документов об ошибках](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="729f7-119">Игнорировать ошибки</span><span class="sxs-lookup"><span data-stu-id="729f7-119">Ignore errors</span></span>

<span data-ttu-id="729f7-120">Ошибку обработки можно игнорировать, нажав кнопку **пропустить** в заголовке ошибки обработки.</span><span class="sxs-lookup"><span data-stu-id="729f7-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="729f7-121">При пропуске ошибки документ удаляется из [рабочего процесса массового исправления ошибок](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="729f7-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="729f7-122">После того как сообщение об ошибке будет пропущено, баннер документа изменит цвет и указывает на то, что ошибка обработки игнорируется.</span><span class="sxs-lookup"><span data-stu-id="729f7-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="729f7-123">В любое время вы можете отменить решение, чтобы игнорировать ошибку, нажав кнопку **восстановить**.</span><span class="sxs-lookup"><span data-stu-id="729f7-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Нажмите кнопку Пропустить, чтобы пропустить ошибку обработки](../media/SIERimage3.png)

<span data-ttu-id="729f7-125">Кроме того, можно выполнить поиск всех документов, в которых возникла ошибка обработки, проигнорированных при использовании условия " *пропущенные ошибки обработки* " при запросе документов в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="729f7-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Использование условия "пропущенные ошибки обработки" для поиска пропущенных документов об ошибках](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="729f7-127">Исправление документа с ошибками</span><span class="sxs-lookup"><span data-stu-id="729f7-127">Remediate a document with errors</span></span>

<span data-ttu-id="729f7-128">Иногда может потребоваться исправить ошибку обработки в документах (удалив пароль, расшифровать зашифрованный файл или восстановить поврежденный документ), а затем добавить исправленный документ в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="729f7-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="729f7-129">Это позволяет просматривать и экспортировать документ об ошибке вместе с другими документами в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="729f7-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="729f7-130">Чтобы исправить один документ, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="729f7-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="729f7-131">Нажмите **загрузить** > **Скачать оригинал** , чтобы скачать копию файла на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="729f7-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Загрузка документа с ошибкой обработки](../media/SIERimage5.png)

2. <span data-ttu-id="729f7-133">Исправление ошибки в файле в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="729f7-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="729f7-134">Для зашифрованных файлов, которые требуют программного обеспечения для расшифровки, для удаления защиты паролем предоставьте пароль и сохраните файл или используйте средства взлома паролей.</span><span class="sxs-lookup"><span data-stu-id="729f7-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="729f7-135">После исправления файла перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="729f7-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="729f7-136">В наборе проверки выберите файл с ошибкой обработки, который вы исправлены, и нажмите кнопку **исправление**.</span><span class="sxs-lookup"><span data-stu-id="729f7-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Нажмите кнопку "исправление" в заголовке документа с ошибкой обработки](../media/SIERimage6.png)


4. <span data-ttu-id="729f7-138">Нажмите кнопку **Обзор**, перейдите к расположению исправленного файла на локальном компьютере, а затем выберите файл.</span><span class="sxs-lookup"><span data-stu-id="729f7-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Нажмите кнопку Обзор и выберите исправленный файл на локальном компьютере.](../media/SIERimage7.png)

    <span data-ttu-id="729f7-140">После выбора исправленного файла он автоматически загружается в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="729f7-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="729f7-141">Вы можете отслеживать состояние обработки файла.</span><span class="sxs-lookup"><span data-stu-id="729f7-141">You can track the processing status of the file.</span></span>

    ![Отображается состояние процесса исправления](../media/SIERimage8.png)

   <span data-ttu-id="729f7-143">После завершения обработки можно просмотреть исправленный документ.</span><span class="sxs-lookup"><span data-stu-id="729f7-143">After processing is completed, you can view the remediated document.</span></span>

    ![Вы можете просмотреть исправленный файл в собственном формате в наборе рецензирования.](../media/SIERimage9.png)

<span data-ttu-id="729f7-145">Для получения дополнительных сведений о том, что происходит при исправлении документа, посмотрите, [что происходит при исправлении файлов](error-remediation.md#what-happens-when-files-are-remediated).</span><span class="sxs-lookup"><span data-stu-id="729f7-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="729f7-146">Поиск исправленных документов</span><span class="sxs-lookup"><span data-stu-id="729f7-146">Search for remediated documents</span></span>

<span data-ttu-id="729f7-147">Можно выполнить поиск по всем документам в наборе пересмотров, которые были исправлены с помощью условия **ключевых слов** , и указав следующее свойство: значение **исфромеррорремедиатион: true**.</span><span class="sxs-lookup"><span data-stu-id="729f7-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="729f7-148">Это свойство также доступно в экспортируемом файле загрузки при экспорте документов из набора рецензирования.</span><span class="sxs-lookup"><span data-stu-id="729f7-148">This property is also available in the export load file when you export documents from a review set.</span></span>
