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
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Устранение неполадок AzCopy в Advanced eDiscovery

При загрузке данных или документов, отличных от Microsoft 365, для исправления ошибок в Advanced eDiscovery, Пользовательский интерфейс предоставляет команду Azure AzCopy, содержащую параметры с расположением файлов, которые требуется отправить, и расположением хранилища Azure, в которое будут отправляться файлы. Чтобы отправить документы, скопируйте эту команду и запустите ее в командной строке на локальном компьютере.  На снимке экрана ниже показан пример команды AzCopy:

![Отправка файлов, отличных от Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Обычно предоставленная команда работает при ее запуске. Однако возможны случаи, когда отображаемая команда не запустится успешно. Вот несколько возможных причин.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>Поддерживаемая версия AzCopy не установлена на локальном компьютере

В настоящее время необходимо использовать AzCopy v 8.1 для загрузки данных не из Microsoft 365 в Advanced eDiscovery. Команда AzCopy, отображаемая на странице **отправки файлов** , показанная на предыдущем снимке экрана, возвращает ошибку, если вы не используете AzCopy v 8.1. Чтобы установить эту версию, просмотрите раздел [Передача данных с помощью AzCopy v 8.1 в Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy не установлен на локальном компьютере, или он не установлен в расположении по умолчанию

Если AzCopy не установлен или он установлен в расположении, отличном от расположения установки по умолчанию (то есть `%ProgramFiles(x86)%` ), при выполнении команды AzCopy может появиться следующее сообщение об ошибке:

> Системе не удается найти указанный путь.

Если AzCopy не установлен на локальном компьютере, сведения об установке можно найти в разделе [Transfer Data с помощью AzCopy v 8.1 в Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Обязательно установите его в расположении по умолчанию.

Если AzCopy установлен, но он установлен в расположении, отличном от расположения по умолчанию, можно скопировать команду, вставить ее в текстовый файл, а затем изменить путь к расположению, где установлен AzCopy. Например, если Azcopy находится в `%ProgramFiles%` , то вы можете заменить первую часть команды `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` на `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . После внесения изменений скопируйте его из текстового файла и запустите в командной строки.

> [!TIP]
> Если AzCopy установлен в расположении, отличном от местоположения установки по умолчанию, попробуйте удалить его, а затем повторно установить в расположении по умолчанию. Это позволит избежать этой ситуации в будущем.
