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
description: Вы можете исправить ошибку обработки в документе в наборе для проверки в Advanced eDiscovery, не следуя процедуре исправления массовых ошибок.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751586"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="04434-103">Исправление ошибок одного элемента в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="04434-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="04434-104">Исправление ошибок дает пользователям Advanced eDiscovery возможность исправлять проблемы с данными, которые не дают Advanced eDiscovery правильно обрабатывать контент.</span><span class="sxs-lookup"><span data-stu-id="04434-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="04434-105">Например, файлы, защищенные паролем, не могут быть обработаны, так как они заблокированы или зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="04434-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="04434-106">Раньше массовое исправление ошибок можно было устранять только с помощью этого [рабочего процесса.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="04434-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="04434-107">Но иногда не имеет смысла устранять ошибки в нескольких файлах, если вы не уверены, что какой-либо из этих файлов реагирует на исследуемое дело.</span><span class="sxs-lookup"><span data-stu-id="04434-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="04434-108">Кроме того, не имеет смысла устранять ошибки до того, как вы сможете просмотреть метаданные файла (например, расположение файла или у кого был доступ) для принятия решений о быстром отклике.</span><span class="sxs-lookup"><span data-stu-id="04434-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="04434-109">Новая функция,  называемая исправлением ошибок одного элемента, позволяет менеджерам по обнаружению электронных данных просматривать метаданные файлов с ошибкой обработки и при необходимости устранять ошибку непосредственно в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="04434-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="04434-110">В этой статье обсуждается, как выявлять, игнорировать и устранять файлы с ошибками обработки в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="04434-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="04434-111">Определение документов с ошибками</span><span class="sxs-lookup"><span data-stu-id="04434-111">Identify documents with errors</span></span>

<span data-ttu-id="04434-112">Документы с ошибками обработки в наборе для проверки теперь идентифицированы (с баннером).</span><span class="sxs-lookup"><span data-stu-id="04434-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="04434-113">Ошибку можно устранять или игнорировать.</span><span class="sxs-lookup"><span data-stu-id="04434-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="04434-114">На следующем снимке экрана показан баннер об ошибке обработки для документа Word в наборе для проверки, защищенного паролем.</span><span class="sxs-lookup"><span data-stu-id="04434-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="04434-115">Также обратите внимание, что можно просматривать метаданные файлов документов с ошибками обработки.</span><span class="sxs-lookup"><span data-stu-id="04434-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Баннер, отображающийся для документа с ошибкой обработки](../media/SIERimage1.png)

<span data-ttu-id="04434-117">Вы также можете искать документы с ошибками  обработки, используя условие состояния обработки при запросе документов в [наборе для проверки.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="04434-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Использование условия состояния обработки для поиска документов об ошибках](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="04434-119">Игнорировать ошибки</span><span class="sxs-lookup"><span data-stu-id="04434-119">Ignore errors</span></span>

<span data-ttu-id="04434-120">Вы можете игнорировать ошибку обработки, щелкнув **"Игнорировать"** в баннере об ошибке обработки.</span><span class="sxs-lookup"><span data-stu-id="04434-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="04434-121">Если игнорировать ошибку, документ удаляется из рабочего процесса массовой устранения [ошибок.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="04434-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="04434-122">После игнорирования ошибки за баннер документа изменяется цвет и указывается, что ошибка обработки была проигнорирована.</span><span class="sxs-lookup"><span data-stu-id="04434-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="04434-123">В любое время вы можете отойдите от решения игнорировать ошибку, нажав кнопку **"Вернуться".**</span><span class="sxs-lookup"><span data-stu-id="04434-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Click Ignore to ignore the processing error](../media/SIERimage3.png)

<span data-ttu-id="04434-125">Вы также можете найти все документы с ошибкой обработки,  которая была проигнорирована с помощью условия "Игнорируются ошибки обработки" при запросе документов в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="04434-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Использование условия "Игнорировать ошибки обработки" для поиска игнорируемой ошибки](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="04434-127">Исправление документа с ошибками</span><span class="sxs-lookup"><span data-stu-id="04434-127">Remediate a document with errors</span></span>

<span data-ttu-id="04434-128">Иногда может потребоваться исправление ошибки обработки в документах (путем удаления пароля, расшифровки зашифрованного файла или восстановления поврежденного документа) и добавления исправленного документа в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="04434-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="04434-129">Это позволяет просмотреть и экспортировать документ об ошибке вместе с другими документами в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="04434-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="04434-130">Чтобы исправление одного документа, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="04434-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="04434-131">Щелкните   >  **"Скачать исходный** файл", чтобы скачать копию файла на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="04434-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Загрузка документа с ошибкой обработки](../media/SIERimage5.png)

2. <span data-ttu-id="04434-133">Исправлена ошибка в файле в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="04434-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="04434-134">Для зашифрованных файлов, для чего требуется программное обеспечение расшифровки, чтобы удалить защиту паролем, либо ввести пароль и сохранить файл, либо использовать взломщик паролей.</span><span class="sxs-lookup"><span data-stu-id="04434-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="04434-135">После того как вы укалите файл, перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="04434-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="04434-136">В наборе для проверки выберите файл с исправленной ошибкой обработки и нажмите кнопку **"Исправление".**</span><span class="sxs-lookup"><span data-stu-id="04434-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Щелкните "Исправление" в заголовке документа с ошибкой обработки](../media/SIERimage6.png)


4. <span data-ttu-id="04434-138">Нажмите **кнопку**"Обзор", перейдите к расположению исправленного файла на локальном компьютере и выберите файл.</span><span class="sxs-lookup"><span data-stu-id="04434-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Нажмите кнопку "Обзор" и выберите исправленный файл на локальном компьютере](../media/SIERimage7.png)

    <span data-ttu-id="04434-140">После выбора исправленного файла он автоматически загружается в набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="04434-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="04434-141">Вы можете отслеживать состояние обработки файла.</span><span class="sxs-lookup"><span data-stu-id="04434-141">You can track the processing status of the file.</span></span>

    ![Отображается состояние процесса устранения](../media/SIERimage8.png)

   <span data-ttu-id="04434-143">После завершения обработки вы можете просмотреть исправленный документ.</span><span class="sxs-lookup"><span data-stu-id="04434-143">After processing is completed, you can view the remediated document.</span></span>

    ![Вы можете просмотреть исправленный файл в формате native в наборе для проверки](../media/SIERimage9.png)

<span data-ttu-id="04434-145">Дополнительные сведения о том, что происходит при исправлении документа, см. в документе "Что происходит при исправлении [файлов".](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)</span><span class="sxs-lookup"><span data-stu-id="04434-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="04434-146">Поиск исправленных документов</span><span class="sxs-lookup"><span data-stu-id="04434-146">Search for remediated documents</span></span>

<span data-ttu-id="04434-147">Вы можете искать все документы в наборе для проверки, которые были исправлены с помощью условия **Keywords** и указания следующей пары свойство:значение: **IsFromErrorRemediation:true**.</span><span class="sxs-lookup"><span data-stu-id="04434-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="04434-148">Это свойство также доступно в файле загрузки экспорта при экспорте документов из набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="04434-148">This property is also available in the export load file when you export documents from a review set.</span></span>
