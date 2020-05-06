---
title: Загрузка данных, отличных от Microsoft 365, в свидетельство
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
description: Узнайте, как использовать компонент импорта содержимого, не относящийся к Office 365, для отправки документов, отличных от Office 365, в доказательства, проводимые при расследовании данных.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 499b1074b9a1e2026804eab2ac958fe7392e98ea
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034417"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a><span data-ttu-id="04cf8-103">Загрузка данных, отличных от Microsoft 365, в свидетельство</span><span class="sxs-lookup"><span data-stu-id="04cf8-103">Load non-Microsoft 365 data into evidence</span></span>

<span data-ttu-id="04cf8-104">Не все документы, которые могут потребоваться анализировать при расследовании данных, будут размещены в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04cf8-104">Not all documents that you may need to analyze in a data investigation will be located in Microsoft 365.</span></span> <span data-ttu-id="04cf8-105">С помощью функции импорта содержимого, отличной от Microsoft 365, вы можете отправлять в доказательства документы, которые не находятся в Microsoft 365, поэтому их можно проанализировать при расследовании данных.</span><span class="sxs-lookup"><span data-stu-id="04cf8-105">With the Non-Microsoft 365 content import feature you can upload documents that don't live in Microsoft 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="04cf8-106">Подготовка</span><span class="sxs-lookup"><span data-stu-id="04cf8-106">Before you begin</span></span>

<span data-ttu-id="04cf8-107">Для использования функции отправки, отличной от Microsoft 365, как описано в этой процедуре, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="04cf8-107">Using the upload Non-Microsoft 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="04cf8-108">Подписка на Microsoft 365 или Office 365 в.</span><span class="sxs-lookup"><span data-stu-id="04cf8-108">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="04cf8-109">Все интересующие вас люди, на которые не входит Корпорация Майкрософт 365, должны содержать соответствующую лицензию на надстройку, которая составляет от нуля до нуля.</span><span class="sxs-lookup"><span data-stu-id="04cf8-109">All people of interest whose non-Microsoft 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="04cf8-110">Существующее дело обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="04cf8-110">An existing eDiscovery case.</span></span>

- <span data-ttu-id="04cf8-111">Все файлы для отправки собраны в папки, для которых в одной папке есть папка хранитель, а имя папки в этом формате *Alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="04cf8-111">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="04cf8-112">*Alias@domainname* должен быть псевдонимом пользователя и доменом.</span><span class="sxs-lookup"><span data-stu-id="04cf8-112">The *alias@domainname* must be user's alias and domain.</span></span> <span data-ttu-id="04cf8-113">Вы можете собрать все *Alias@domainname* папки в корневую папку.</span><span class="sxs-lookup"><span data-stu-id="04cf8-113">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="04cf8-114">Корневая папка может содержать только папки *Alias@domainname* , но в корневой папке не должно быть свободных файлов.</span><span class="sxs-lookup"><span data-stu-id="04cf8-114">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="04cf8-115">Учетная запись, которая является диспетчером eDiscovery или Microsoft Azure Storage Tools, установленных на компьютере, который имеет доступ к структуре папки контента, отличной от Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04cf8-115">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span>

- <span data-ttu-id="04cf8-116">Установите AzCopy, что можно сделать, выполнив указанные ниже действия.https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="04cf8-116">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a><span data-ttu-id="04cf8-117">Отправка контента, отличного от Microsoft 365, во временный анализ данных</span><span class="sxs-lookup"><span data-stu-id="04cf8-117">Upload non-Microsoft 365 content in to a data investigation</span></span>

1. <span data-ttu-id="04cf8-118">Откройте исследование **данных** и переходите к исследованию того, что данные, не относящиеся к Microsoft 365, будут отправлены в.</span><span class="sxs-lookup"><span data-stu-id="04cf8-118">Open **Data Investigations** and go to the investigation that the non-Microsoft 365 data will be uploaded to.</span></span>  <span data-ttu-id="04cf8-119">Перейдите на вкладку **свидетельство** , а затем выберите набор свидетельств, в который вы хотите загрузить данные.</span><span class="sxs-lookup"><span data-stu-id="04cf8-119">Click the **Evidence** tab, then select the evidence set you wish to load the data to.</span></span>  <span data-ttu-id="04cf8-120">Если вы еще не создали набор свидетельств, вы можете сделать это сейчас.</span><span class="sxs-lookup"><span data-stu-id="04cf8-120">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="04cf8-121">Наконец, щелкните **Управление свидетельством** , а затем **Просмотр отправок** в разделе данные</span><span class="sxs-lookup"><span data-stu-id="04cf8-121">Finally, click **Manage evidence** then **View uploads** in the data section</span></span>

2. <span data-ttu-id="04cf8-122">Нажмите кнопку **отправить файлы** , чтобы запустить мастер импорта данных, не относящийся к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04cf8-122">Click the **Upload files** button to start the Non-Microsoft 365 data import wizard.</span></span>

![Отправка файлов](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="04cf8-124">На первом этапе мастера просто подготавливается безопасный большой двоичный объект Azure для отправляемых файлов.</span><span class="sxs-lookup"><span data-stu-id="04cf8-124">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="04cf8-125">После завершения подготовки нажмите кнопку " **Далее: Отправка файлов** ".</span><span class="sxs-lookup"><span data-stu-id="04cf8-125">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Подготовка к импорту данных не на основе Microsoft 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="04cf8-127">На шаге **Отправка файлов** укажите **путь к расположению файлов**, где находятся данные, не относящиеся к Microsoft 365, которые планируется импортировать.</span><span class="sxs-lookup"><span data-stu-id="04cf8-127">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Microsoft 365 data you plan on importing is located.</span></span>  <span data-ttu-id="04cf8-128">Задание правильного расположения гарантирует, что команда AzCopy будет правильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="04cf8-128">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf8-129">Если вы еще не установили AzCopy, вы можете сделать это следующим образом:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="04cf8-129">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="04cf8-130">Скопируйте предопределенную команду, щелкнув ссылку **Копировать в буфер обмена** .</span><span class="sxs-lookup"><span data-stu-id="04cf8-130">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="04cf8-131">Запустите командную строку Windows, вставьте команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="04cf8-131">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="04cf8-132">Файлы будут отправлены в безопасное хранилище BLOB-объектов Azure для следующего этапа.</span><span class="sxs-lookup"><span data-stu-id="04cf8-132">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Отправка файлов для импорта данных не из Microsoft 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Импорт данных, не относящихся к Microsoft 365, с помощью AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="04cf8-135">Наконец, вернитесь к & соответствия требованиям безопасности и нажмите кнопку **Далее: обработка файлов** .</span><span class="sxs-lookup"><span data-stu-id="04cf8-135">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="04cf8-136">Это инициирует обработку, извлечение текста и индексацию отправленных файлов.</span><span class="sxs-lookup"><span data-stu-id="04cf8-136">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="04cf8-137">Вы можете отслеживать ход обработки здесь или на вкладке **задания** .  После завершения новые файлы будут доступны в наборе свидетельств.</span><span class="sxs-lookup"><span data-stu-id="04cf8-137">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="04cf8-138">После завершения обработки можно закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="04cf8-138">After processing is complete, you can dismiss the wizard.</span></span>

![Файлы процесса импорта, отличные от Microsoft 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

