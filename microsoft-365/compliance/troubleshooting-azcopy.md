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
description: Устранение ошибок для Azure AzCopy при загрузке Office 365 для устранения ошибок в Advanced eDiscovery.
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
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Устранение неполадок AzCopy в Advanced eDiscovery

При загрузке Microsoft 365 данных или документов для устранения ошибок в Advanced eDiscovery пользовательский интерфейс поставляет команду Azure AzCopy, которая содержит параметры с расположением места хранения файлов, в которые будут загружены файлы, и расположение хранилища Azure, в которое будут загружены файлы. Чтобы загрузить документы, скопируйте эту команду и запустите ее в командной подсказке на локальном компьютере.  На скриншоте ниже показан пример команды AzCopy:

![Upload не Microsoft 365 файлы](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Обычно команда, которая предоставляется, работает при ее запуске. Однако могут быть случаи, когда отображаемая команда не будет успешно работать. Вот несколько возможных причин.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>Поддерживаемая версия AzCopy не установлена на локальном компьютере

В это время необходимо использовать AzCopy v8.1 для загрузки Microsoft 365 данных в Advanced eDiscovery. Команда AzCopy, отображаемая на  странице Upload файлов, показанной на предыдущем скриншоте, возвращает ошибку, если вы не используете AzCopy v8.1. Чтобы установить эту версию, см. в этой версии сведения о переносе с [помощью azCopy v8.1 на Windows](/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy не установлена на локальном компьютере или не установлена в расположении по умолчанию

Если AzCopy не установлен или установлен в другом расположении, кроме расположения установки по умолчанию (то есть), при запуске команды AzCopy вы можете получить следующую `%ProgramFiles(x86)%` ошибку:

> Система не может найти указанный путь.

Если azCopy не установлен на локальном компьютере, сведения об установке можно найти в данных transfer с [помощью приложения AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)на Windows . Обязательно установите его в расположении по умолчанию.

Если azCopy установлен, но установлен в расположении, не похожем на расположение по умолчанию, можно скопировать команду, вклеить ее в текстовый файл, а затем изменить путь к расположению, где установлена AzCopy. Например, если azcopy расположен в , то можно изменить первую часть команды с `%ProgramFiles%` `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` на `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . После внести это изменение скопируйте его из текстового файла и запустите командный запрос.

> [!TIP]
> Если AzCopy установлена в другом расположении, то по умолчанию установите его, рассмотрите возможность его расстановки и повторной установки в расположении по умолчанию. Это поможет предотвратить эту проблему в будущем.