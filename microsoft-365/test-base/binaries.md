---
title: Upload Разнонабные приложения
description: Как начать работу с помощью тестовой базы для M365
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323167"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Шаг 3. Upload, зависимостей и сценариев

На этой вкладке будет загружен один почтовый пакет, содержащий ваши сеяния, зависимости и скрипты, используемые для запуска тестового пакета.

## <a name="upload-package-zip-file"></a>Upload почтовый файл пакета

![Upload ваших бинарей](Media/AddBinaries.png)

  - Загруженные зависимости могут включать тестовые фреймворки, механизмы сценариев или данные, которые будут доступны для запуска приложений или тестовых случаев. Например, вы можете загрузить selenium и установщик веб-драйвера для запуска тестов на основе браузера.
  - Лучше всего обеспечить, чтобы действия скрипта были модульными, то есть. 
    - Скрипт ```Install``` выполняет только операции установки.
    - Скрипт ```Launch``` запускает только приложение.
    - Скрипт ```Close``` закрывает только приложение.
    - ```Uninstall```Необязательный скрипт только анинсталирует приложение.

**В настоящее время портал поддерживает только скрипты PowerShell.**


## <a name="next-steps"></a>Дальнейшие действия 

Перейти к следующей статье, чтобы перейти на шаг 4: **Установите тестовые задачи**.
> [!div class="nextstepaction"]
> [Вернуться](uploadApplication.md)
> [!div class="nextstepaction"]
> [Следующий этап](testtask.md)

