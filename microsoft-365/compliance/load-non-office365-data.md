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
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090436"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="45224-102">Загрузка данных, отличных от Office 365, в свидетельство</span><span class="sxs-lookup"><span data-stu-id="45224-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="45224-103">Не все документы, которые может потребоваться проанализировать с помощью Office 365 Advanced eDiscovery, будут жить в Office 365.</span><span class="sxs-lookup"><span data-stu-id="45224-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="45224-104">С помощью функции импорта содержимого, отличной от Office 365, в Advanced eDiscovery вы можете отправлять документы, не включенные в Office 365, в рабочий набор, чтобы их было анализировать с помощью расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="45224-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="45224-105">В этой процедуре показано, как перенести документы, не относящиеся к Office 365, в Расширенное обнаружение электронных данных для анализа.</span><span class="sxs-lookup"><span data-stu-id="45224-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="45224-106">Для расширенного обнаружения электронных данных требуется Office 365 E3 с дополнительным соответствием или подпиской на систему с дополнительным соответствием в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="45224-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="45224-107">Если у вас нет этого плана и вы хотите попытаться использовать Расширенное обнаружение электронных данных, вы можете зарегистрироваться в пробной версии Office 365 Enterprise ~.</span><span class="sxs-lookup"><span data-stu-id="45224-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="45224-108">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="45224-108">Before you begin</span></span>
<span data-ttu-id="45224-109">Для использования функции отправки, отличной от Office 365, описанной в этой процедуре, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="45224-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="45224-110">Office 365 E3 с дополнительным подпискум на надстройку или на дополнительные требования.</span><span class="sxs-lookup"><span data-stu-id="45224-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="45224-111">Все custodians, для которых содержимое, не относящееся к Office 365, должно быть отправлено в виде E3 с дополнительными лицензиями на надстройку или для установки и возврата.</span><span class="sxs-lookup"><span data-stu-id="45224-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="45224-112">Существующее дело обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="45224-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="45224-113">Все файлы для отправки собраны в папки, для которых в одной папке есть папка хранитель, а имя папки имеет следующий формат: *псевдоним @ имя_домена* .</span><span class="sxs-lookup"><span data-stu-id="45224-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="45224-114">*Псевдоним @ имя_домена* должен быть пользователем Office 365 Alias and domain.</span><span class="sxs-lookup"><span data-stu-id="45224-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="45224-115">Вы можете собрать все папки *Alias @ имя_домена* в корневую папку.</span><span class="sxs-lookup"><span data-stu-id="45224-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="45224-116">Корневая папка может содержать только папки *Alias @ имя_домена* , но в корневой папке не должно быть свободных файлов.</span><span class="sxs-lookup"><span data-stu-id="45224-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="45224-117">Учетная запись, которая является диспетчером eDiscovery или Microsoft Azure Storage Tools, установленных на компьютере, который имеет доступ к структуре папки контента, отличной от Office 365.</span><span class="sxs-lookup"><span data-stu-id="45224-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="45224-118">Установите AzCopy, что можно сделать, выполнив указанные ниже действия.https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="45224-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="45224-119">Отправка контента, отличного от Office 365, в Расширенное обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="45224-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="45224-120">В качестве диспетчера обнаружения электронных данных или администратора eDiscovery откройте компонент Advanced eDiscovery, а затем в случае отправки данных, отличных от Office 365.</span><span class="sxs-lookup"><span data-stu-id="45224-120">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="45224-121">Перейдите на вкладку **рабочие наборы** , а затем выберите рабочий набор, в который вы хотите загрузить данные, не относящиеся к Office 365.</span><span class="sxs-lookup"><span data-stu-id="45224-121">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="45224-122">Если вы еще не создали рабочее множество, вы можете сделать это сейчас.</span><span class="sxs-lookup"><span data-stu-id="45224-122">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="45224-123">Наконец, щелкните **Управление заданиями Set** , а затем **Просмотр отправок** в разделе данные, не относящиеся к Office 365</span><span class="sxs-lookup"><span data-stu-id="45224-123">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="45224-124">Нажмите кнопку **отправить файлы** , чтобы запустить мастер импорта данных, не относящийся к Office 365.</span><span class="sxs-lookup"><span data-stu-id="45224-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Отправка файлов](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="45224-126">На первом этапе мастера просто подготавливается безопасный большой двоичный объект Azure для отправляемых файлов.</span><span class="sxs-lookup"><span data-stu-id="45224-126">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="45224-127">После подготовки компелтед нажмите кнопку " **Далее: Отправка файлов** ".</span><span class="sxs-lookup"><span data-stu-id="45224-127">Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Импорт, не относящийся к Office 365, подготовка](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="45224-129">На шаге **Отправка файлов** укажите **путь к расположению файлов**, где находятся данные, не относящиеся к Office 365, которые планируется импортировать.</span><span class="sxs-lookup"><span data-stu-id="45224-129">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="45224-130">Задание правильного расположения гарантирует, что команда AzCopy будет правильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="45224-130">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="45224-131">Если вы еще не установили AzCopy, вы можете сделать это следующим образом:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="45224-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="45224-132">Скопируйте предопределенную команду, щелкнув ссылку **Копировать в буфер обмена** .</span><span class="sxs-lookup"><span data-stu-id="45224-132">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="45224-133">Запустите командную строку Windows, вставьте команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="45224-133">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="45224-134">Файлы будут отправлены в безопасное хранилище BLOB-объектов Azure для следующего этапа.</span><span class="sxs-lookup"><span data-stu-id="45224-134">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Импорт файлов, отличных от Office 365](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Импорт не для Office 365, AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="45224-137">Наконец, вернитесь к & соответствия требованиям безопасности и нажмите кнопку **Далее: обработка файлов** .</span><span class="sxs-lookup"><span data-stu-id="45224-137">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="45224-138">Это приведет к обработке, извлечению текста и индексированию отправленных файлов.</span><span class="sxs-lookup"><span data-stu-id="45224-138">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="45224-139">Вы можете отслеживать ход обработки здесь или на вкладке **задания** .  После завершения новые файлы будут доступны в рабочем наборе.</span><span class="sxs-lookup"><span data-stu-id="45224-139">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="45224-140">После завершения обработки можно закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="45224-140">Once processing is complete, you can dismiss the wizard.</span></span>

![Файлы импорта и обработки файлов, отличных от Office 365](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

