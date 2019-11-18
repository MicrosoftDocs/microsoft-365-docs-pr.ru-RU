---
title: Загрузка данных, отличных от Office 365, в свидетельство
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
ms.openlocfilehash: e05dc26159545e4daf7a8f4109268a1657fd62d6
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2019
ms.locfileid: "38687448"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="81e07-102">Загрузка данных, отличных от Office 365, в свидетельство</span><span class="sxs-lookup"><span data-stu-id="81e07-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="81e07-103">Не все документы, которые могут потребоваться анализировать при расследовании данных, будут размещены в Office 365.</span><span class="sxs-lookup"><span data-stu-id="81e07-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="81e07-104">С помощью функции импорта содержимого, отличной от Office 365, вы можете отправлять в доказательства документы, которые не находятся в Office 365, поэтому их можно проанализировать в расследовании данных.</span><span class="sxs-lookup"><span data-stu-id="81e07-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

>[!Note]
><span data-ttu-id="81e07-105">Для расследования данных требуется Office 365 E3 с дополнительным соответствием по требованиям или с подпиской на систему с дополнительным соответствием в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="81e07-105">Data investigation requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="81e07-106">Если у вас нет этого плана и вы хотите попытаться использовать Расширенное обнаружение электронных данных, вы можете зарегистрироваться в пробной версии Office 365 Enterprise ~.</span><span class="sxs-lookup"><span data-stu-id="81e07-106">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="81e07-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="81e07-107">Before you begin</span></span>

<span data-ttu-id="81e07-108">Для использования функции отправки, отличной от Office 365, описанной в этой процедуре, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="81e07-108">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="81e07-109">Office 365 E3 с дополнительным подпискум на надстройку или на дополнительные требования.</span><span class="sxs-lookup"><span data-stu-id="81e07-109">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="81e07-110">Все custodians, для которых содержимое, не относящееся к Office 365, должно быть отправлено в виде E3 с дополнительными лицензиями на надстройку или для установки и возврата.</span><span class="sxs-lookup"><span data-stu-id="81e07-110">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="81e07-111">Существующее дело обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="81e07-111">An existing eDiscovery case.</span></span>

- <span data-ttu-id="81e07-112">Все файлы для отправки собраны в папки, для которых в одной папке есть папка хранитель, а имя папки в этом формате *Alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="81e07-112">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="81e07-113">*Alias@domainname* должны быть пользователями псевдонимов Office 365 и домена.</span><span class="sxs-lookup"><span data-stu-id="81e07-113">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="81e07-114">Вы можете собрать все *Alias@domainname* папки в корневую папку.</span><span class="sxs-lookup"><span data-stu-id="81e07-114">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="81e07-115">Корневая папка может содержать только папки *Alias@domainname* , но в корневой папке не должно быть свободных файлов.</span><span class="sxs-lookup"><span data-stu-id="81e07-115">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="81e07-116">Учетная запись, которая является диспетчером eDiscovery или Microsoft Azure Storage Tools, установленных на компьютере, который имеет доступ к структуре папки контента, отличной от Office 365.</span><span class="sxs-lookup"><span data-stu-id="81e07-116">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="81e07-117">Установите AzCopy, что можно сделать, выполнив указанные ниже действия.https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="81e07-117">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="81e07-118">Отправка контента, отличного от Office 365, во временный анализ данных</span><span class="sxs-lookup"><span data-stu-id="81e07-118">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="81e07-119">Откройте \* \* \* \* исследование данных \* \*, после чего выполняется загрузка данных, отличных от Office 365.</span><span class="sxs-lookup"><span data-stu-id="81e07-119">Open \*\*\*\*Data Investigations\*\*, then the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="81e07-120">Перейдите на вкладку **свидетельство** и выберите набор свидетельств, для которого необходимо загрузить данные 365, не относящиеся к Office.</span><span class="sxs-lookup"><span data-stu-id="81e07-120">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="81e07-121">Если вы еще не создали набор свидетельств, вы можете сделать это сейчас.</span><span class="sxs-lookup"><span data-stu-id="81e07-121">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="81e07-122">Наконец, щелкните **Управление свидетельством** , а затем **Просмотр отправок** в разделе данных, не относящемся к Office 365</span><span class="sxs-lookup"><span data-stu-id="81e07-122">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="81e07-123">Нажмите кнопку **отправить файлы** , чтобы запустить мастер импорта данных, не относящийся к Office 365.</span><span class="sxs-lookup"><span data-stu-id="81e07-123">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Отправка файлов](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="81e07-125">На первом этапе мастера просто подготавливается безопасный большой двоичный объект Azure для отправляемых файлов.</span><span class="sxs-lookup"><span data-stu-id="81e07-125">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="81e07-126">После завершения подготовки нажмите кнопку " **Далее: Отправка файлов** ".</span><span class="sxs-lookup"><span data-stu-id="81e07-126">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Подготовка к импорту данных, не относящегося к Office 365](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="81e07-128">На шаге **Отправка файлов** укажите **путь к расположению файлов**, где находятся данные, не относящиеся к Office 365, которые планируется импортировать.</span><span class="sxs-lookup"><span data-stu-id="81e07-128">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="81e07-129">Задание правильного расположения гарантирует, что команда AzCopy будет правильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="81e07-129">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="81e07-130">Если вы еще не установили AzCopy, вы можете сделать это следующим образом:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="81e07-130">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="81e07-131">Скопируйте предопределенную команду, щелкнув ссылку **Копировать в буфер обмена** .</span><span class="sxs-lookup"><span data-stu-id="81e07-131">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="81e07-132">Запустите командную строку Windows, вставьте команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="81e07-132">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="81e07-133">Файлы будут отправлены в безопасное хранилище BLOB-объектов Azure для следующего этапа.</span><span class="sxs-lookup"><span data-stu-id="81e07-133">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Отправка файлов для импорта данных, не относящихся к Office 365](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Использование AzCopy для импорта данных, отличных от Office 365](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="81e07-136">Наконец, вернитесь к & соответствия требованиям безопасности и нажмите кнопку **Далее: обработка файлов** .</span><span class="sxs-lookup"><span data-stu-id="81e07-136">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="81e07-137">Это инициирует обработку, извлечение текста и индексацию отправленных файлов.</span><span class="sxs-lookup"><span data-stu-id="81e07-137">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="81e07-138">Вы можете отслеживать ход обработки здесь или на вкладке **задания** .  После завершения новые файлы будут доступны в наборе свидетельств.</span><span class="sxs-lookup"><span data-stu-id="81e07-138">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="81e07-139">После завершения обработки можно закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="81e07-139">After processing is complete, you can dismiss the wizard.</span></span>

![Файлы процесса импорта, не относящиеся к Office 365](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

