---
title: Устранение неполадок AzCopy в области расширенных электронных обнаружений
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
description: Ошибки устранения неполадок для Azure AzCopy при загрузке данных без Office 365 для устранения ошибок в advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919295"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="c9ad2-103">Устранение неполадок AzCopy в области расширенных электронных обнаружений</span><span class="sxs-lookup"><span data-stu-id="c9ad2-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="c9ad2-104">При загрузке данных или документов, не вложенных в Microsoft 365 для устранения ошибок в advanced eDiscovery, пользовательский интерфейс поставляет команду Azure AzCopy, которая содержит параметры с расположением места хранения файлов, которые вы хотите отправить, и расположение хранилища Azure, в которое будут загружены файлы.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="c9ad2-105">Чтобы загрузить документы, скопируйте эту команду и запустите ее в командной подсказке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="c9ad2-106">На скриншоте ниже показан пример команды AzCopy:</span><span class="sxs-lookup"><span data-stu-id="c9ad2-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Отправка файлов, не в microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="c9ad2-108">Обычно команда, которая предоставляется, работает при ее запуске.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="c9ad2-109">Однако могут быть случаи, когда отображаемая команда не будет успешно работать.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="c9ad2-110">Вот несколько возможных причин.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="c9ad2-111">Поддерживаемая версия AzCopy не установлена на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="c9ad2-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="c9ad2-112">В это время для загрузки данных, не в microsoft 365, в advanced eDiscovery необходимо использовать AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="c9ad2-113">Команда AzCopy, отображаемая на странице **Upload files,** показанной на предыдущем скриншоте, возвращает ошибку, если вы не используете AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="c9ad2-114">Чтобы установить эту версию, см. [в рублях Передача данных с помощью azCopy v8.1 в Windows.](/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="c9ad2-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="c9ad2-115">AzCopy не установлена на локальном компьютере или не установлена в расположении по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c9ad2-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="c9ad2-116">Если AzCopy не установлен или установлен в другом расположении, кроме расположения установки по умолчанию (то есть), при запуске команды AzCopy вы можете получить следующую `%ProgramFiles(x86)%` ошибку:</span><span class="sxs-lookup"><span data-stu-id="c9ad2-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="c9ad2-117">Система не может найти указанный путь.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="c9ad2-118">Если azCopy не установлен на локальном компьютере, сведения об установке можно найти в данных передачи с [помощью приложения AzCopy v8.1 в Windows.](/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="c9ad2-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="c9ad2-119">Обязательно установите его в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="c9ad2-120">Если azCopy установлен, но установлен в расположении, не похожем на расположение по умолчанию, можно скопировать команду, вклеить ее в текстовый файл, а затем изменить путь к расположению, где установлена AzCopy.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="c9ad2-121">Например, если azcopy расположен в , то можно изменить первую часть команды с `%ProgramFiles%` `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` на `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="c9ad2-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="c9ad2-122">После внести это изменение скопируйте его из текстового файла и запустите командный запрос.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="c9ad2-123">Если AzCopy установлена в другом расположении, то по умолчанию установите его, рассмотрите возможность его расстановки и повторной установки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="c9ad2-124">Это поможет предотвратить эту проблему в будущем.</span><span class="sxs-lookup"><span data-stu-id="c9ad2-124">This will help prevent this issue in the future.</span></span>