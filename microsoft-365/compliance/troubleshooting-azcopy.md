---
title: Устранение неполадок AzCopy в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Устранение ошибок Azure AzCopy при загрузке данных, не относяющихся к Office 365, для устранения ошибок в Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4a4499bb9790ffeaec6a2be36b5eaff030afc010
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546459"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="38d49-103">Устранение неполадок AzCopy в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="38d49-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="38d49-104">При загрузке данных или документов, не вложенных в Microsoft 365, для устранения ошибок в Advanced eDiscovery пользовательский интерфейс передает команду Azure AzCopy, которая содержит параметры с расположением хранения файлов, которые вы хотите отправить, и места хранения Azure, в которое будут загружены файлы.</span><span class="sxs-lookup"><span data-stu-id="38d49-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="38d49-105">Чтобы отправить документы, скопируйте эту команду и запустите ее в командной области на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="38d49-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="38d49-106">На снимке экрана ниже показан пример команды AzCopy:</span><span class="sxs-lookup"><span data-stu-id="38d49-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Отправка файлов, не вложенных в Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="38d49-108">Обычно предоставленная команда работает при ее запуске.</span><span class="sxs-lookup"><span data-stu-id="38d49-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="38d49-109">Однако в некоторых случаях отображаемая команда не будет успешной.</span><span class="sxs-lookup"><span data-stu-id="38d49-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="38d49-110">Вот несколько возможных причин.</span><span class="sxs-lookup"><span data-stu-id="38d49-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="38d49-111">Поддерживаемая версия AzCopy не установлена на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="38d49-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="38d49-112">В настоящее время необходимо использовать AzCopy 8.1 для загрузки данных, не относячих к Microsoft 365, в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="38d49-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="38d49-113">Команда AzCopy, отображаемая на  странице "Отправка файлов", показанная на предыдущем снимке экрана, возвращает ошибку, если вы не используете AzCopy версии 8.1.</span><span class="sxs-lookup"><span data-stu-id="38d49-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="38d49-114">Чтобы установить эту версию, см. сведения о передаче [данных с AzCopy версии 8.1 в Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="38d49-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="38d49-115">AzCopy не установлен на локальном компьютере или в расположении по умолчанию</span><span class="sxs-lookup"><span data-stu-id="38d49-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="38d49-116">Если AzCopy не установлен или установлен в расположении, не установленном по умолчанию (т. е. в расположении), при запуске команды AzCopy может возникнуть следующая `%ProgramFiles(x86)%` ошибка:</span><span class="sxs-lookup"><span data-stu-id="38d49-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="38d49-117">Системе не удается найти указанный путь.</span><span class="sxs-lookup"><span data-stu-id="38d49-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="38d49-118">Если AzCopy не установлен на локальном компьютере, сведения об установке можно найти в данных передачи с [помощью AzCopy версии 8.1 в Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="38d49-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="38d49-119">Обязательно установите его в расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38d49-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="38d49-120">Если AzCopy установлен, но установлен в расположении, не в котором оно установлено по умолчанию, можно скопировать команду, вкопировать ее в текстовый файл, а затем изменить путь к расположению, в котором установлен AzCopy.</span><span class="sxs-lookup"><span data-stu-id="38d49-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="38d49-121">Например, если azcopy находится в , вы можете изменить первую часть команды `%ProgramFiles%` на `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="38d49-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="38d49-122">После внести это изменение скопируйте его из текстового файла и запустите его в командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="38d49-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="38d49-123">Если AzCopy установлен в другом расположении, по умолчанию его можно будет установить, а затем повторно установить в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38d49-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="38d49-124">Это поможет предотвратить эту проблему в будущем.</span><span class="sxs-lookup"><span data-stu-id="38d49-124">This will help prevent this issue in the future.</span></span>
