---
title: Устранение неполадок AzCopy в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3153fc92cfae6e2feba122cc895e787c9b573ef7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080905"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Устранение неполадок AzCopy в Advanced eDiscovery

При загрузке данных или документов, отличных от Office 365, для исправления ошибок в Advanced eDiscovery, Пользовательский интерфейс предоставляет команду Azure AzCopy, содержащую параметры с расположением файлов, которые требуется отправить, и хранилищем Azure. расположение, в которое будут загружаться файлы. Чтобы отправить документы, скопируйте эту команду и запустите ее в командной строке на локальном компьютере.  На снимке экрана ниже показан пример команды AzCopy:

![Отправка файлов, отличных от Office 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Обычно предоставленная команда работает при ее запуске. Однако возможны случаи, когда отображаемая команда не запустится успешно. Вот несколько возможных причин.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>Поддерживаемая версия AzCopy не установлена на локальном компьютере

В настоящее время необходимо использовать AzCopy v 8.1 для загрузки данных 365, не относящихся к Office, в Advanced eDiscovery. Команда AzCopy, отображаемая на странице **отправки файлов** , показанная на предыдущем снимке экрана, возвращает ошибку, если вы не используете AzCopy v 8.1. Чтобы установить эту версию, просмотрите раздел [Передача данных с помощью AzCopy v 8.1 в Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy не установлен на локальном компьютере, или он не установлен в расположении по умолчанию

Если AzCopy не установлен или он установлен в расположении, отличном от расположения установки по умолчанию ( `%ProgramFiles(x86)%`то есть), при выполнении команды AzCopy может появиться следующее сообщение об ошибке:

    The system cannot find the path specified.

Если AzCopy не установлен на локальном компьютере, вы можете выполнить установку [отсюда](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Обязательно установите его в расположении по умолчанию.

Если AzCopy установлен, но он установлен в расположении, отличном от расположения по умолчанию, можно скопировать команду, вставить ее в текстовый файл, а затем изменить путь к расположению, где установлен AzCopy. Например, если Azcopy находится в `%ProgramFiles%`, то вы можете заменить первую часть команды `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` на. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` После внесения изменений скопируйте его из текстового файла и запустите в командной строки.

> [!TIP]
> Если AzCopy установлен в расположении, отличном от местоположения установки по умолчанию, попробуйте удалить его, а затем повторно установить в расположении по умолчанию. Это позволит избежать этой ситуации в будущем.
