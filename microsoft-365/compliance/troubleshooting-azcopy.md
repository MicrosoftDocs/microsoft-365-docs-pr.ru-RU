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
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Устранение неполадок AzCopy в Advanced eDiscovery

При загрузке данных или документов, не вложенных в Microsoft 365, для устранения ошибок в Advanced eDiscovery пользовательский интерфейс передает команду Azure AzCopy, которая содержит параметры с расположением хранения файлов, которые вы хотите отправить, и места хранения Azure, в которое будут загружены файлы. Чтобы отправить документы, скопируйте эту команду и запустите ее в командной области на локальном компьютере.  На снимке экрана ниже показан пример команды AzCopy:

![Отправка файлов, не вложенных в Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Обычно предоставленная команда работает при ее запуске. Однако в некоторых случаях отображаемая команда не будет успешной. Вот несколько возможных причин.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>Поддерживаемая версия AzCopy не установлена на локальном компьютере

В настоящее время необходимо использовать AzCopy 8.1 для загрузки данных, не относячих к Microsoft 365, в Advanced eDiscovery. Команда AzCopy, отображаемая на  странице "Отправка файлов", показанная на предыдущем снимке экрана, возвращает ошибку, если вы не используете AzCopy версии 8.1. Чтобы установить эту версию, см. сведения о передаче [данных с AzCopy версии 8.1 в Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy не установлен на локальном компьютере или в расположении по умолчанию

Если AzCopy не установлен или установлен в расположении, не установленном по умолчанию (т. е. в расположении), при запуске команды AzCopy может возникнуть следующая `%ProgramFiles(x86)%` ошибка:

> Системе не удается найти указанный путь.

Если AzCopy не установлен на локальном компьютере, сведения об установке можно найти в данных передачи с [помощью AzCopy версии 8.1 в Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy) Обязательно установите его в расположение по умолчанию.

Если AzCopy установлен, но установлен в расположении, не в котором оно установлено по умолчанию, можно скопировать команду, вкопировать ее в текстовый файл, а затем изменить путь к расположению, в котором установлен AzCopy. Например, если azcopy находится в , вы можете изменить первую часть команды `%ProgramFiles%` на `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . После внести это изменение скопируйте его из текстового файла и запустите его в командной подсказке.

> [!TIP]
> Если AzCopy установлен в другом расположении, по умолчанию его можно будет установить, а затем повторно установить в расположении по умолчанию. Это поможет предотвратить эту проблему в будущем.
