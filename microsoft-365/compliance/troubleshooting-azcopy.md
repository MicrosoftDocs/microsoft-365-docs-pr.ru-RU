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
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Устранение ошибок для Azure AzCopy при загрузке данных 365, не относящихся к Office, для исправления ошибок в Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4bf8461cb02ca3601707f248a64d8a8a9741efab
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357709"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="6397a-103">Устранение неполадок AzCopy в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6397a-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="6397a-104">При загрузке данных или документов, отличных от Microsoft 365, для исправления ошибок в Advanced eDiscovery, Пользовательский интерфейс предоставляет команду Azure AzCopy, содержащую параметры с расположением файлов, которые требуется отправить, и расположением хранилища Azure, в которое будут отправляться файлы.</span><span class="sxs-lookup"><span data-stu-id="6397a-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="6397a-105">Чтобы отправить документы, скопируйте эту команду и запустите ее в командной строке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6397a-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="6397a-106">На снимке экрана ниже показан пример команды AzCopy:</span><span class="sxs-lookup"><span data-stu-id="6397a-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Отправка файлов, отличных от Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="6397a-108">Обычно предоставленная команда работает при ее запуске.</span><span class="sxs-lookup"><span data-stu-id="6397a-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="6397a-109">Однако возможны случаи, когда отображаемая команда не запустится успешно.</span><span class="sxs-lookup"><span data-stu-id="6397a-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="6397a-110">Вот несколько возможных причин.</span><span class="sxs-lookup"><span data-stu-id="6397a-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="6397a-111">Поддерживаемая версия AzCopy не установлена на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="6397a-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="6397a-112">В настоящее время необходимо использовать AzCopy v 8.1 для загрузки данных не из Microsoft 365 в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6397a-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="6397a-113">Команда AzCopy, отображаемая на странице **отправки файлов** , показанная на предыдущем снимке экрана, возвращает ошибку, если вы не используете AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="6397a-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="6397a-114">Чтобы установить эту версию, просмотрите раздел [Передача данных с помощью AzCopy v 8.1 в Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="6397a-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="6397a-115">AzCopy не установлен на локальном компьютере, или он не установлен в расположении по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6397a-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="6397a-116">Если AzCopy не установлен или он установлен в расположении, отличном от расположения установки по умолчанию (то есть `%ProgramFiles(x86)%` ), при выполнении команды AzCopy может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="6397a-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="6397a-117">Системе не удается найти указанный путь.</span><span class="sxs-lookup"><span data-stu-id="6397a-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="6397a-118">Если AzCopy не установлен на локальном компьютере, сведения об установке можно найти в разделе [Transfer Data с помощью AzCopy v 8.1 в Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="6397a-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="6397a-119">Обязательно установите его в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6397a-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="6397a-120">Если AzCopy установлен, но он установлен в расположении, отличном от расположения по умолчанию, можно скопировать команду, вставить ее в текстовый файл, а затем изменить путь к расположению, где установлен AzCopy.</span><span class="sxs-lookup"><span data-stu-id="6397a-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="6397a-121">Например, если Azcopy находится в `%ProgramFiles%` , то вы можете заменить первую часть команды `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` на `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="6397a-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="6397a-122">После внесения изменений скопируйте его из текстового файла и запустите в командной строки.</span><span class="sxs-lookup"><span data-stu-id="6397a-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="6397a-123">Если AzCopy установлен в расположении, отличном от местоположения установки по умолчанию, попробуйте удалить его, а затем повторно установить в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6397a-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="6397a-124">Это позволит избежать этой ситуации в будущем.</span><span class="sxs-lookup"><span data-stu-id="6397a-124">This will help prevent this issue in the future.</span></span>
