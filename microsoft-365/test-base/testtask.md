---
title: Настройка тестовых задач
description: Настройка тестовых задач
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322949"
---
# <a name="step-4-the-tasks-tab"></a>Шаг 4. Вкладка задач

На вкладке задачи предполагается предоставить пути для тестовых скриптов, которые находятся в папке zip, которую вы загрузили на вкладке binaries.

  - **Вне тестового скрипта box:** Введите относительные пути к сценариям установки, запуска, закрытия и списания. Вы также можете выбрать дополнительные параметры для сценария установки.
  - **Функциональные тестовые скрипты:** Введите относительный путь к каждому загруженным функциональным тест-скриптам. С помощью кнопки можно добавить дополнительные функциональные тестовые ```Add Script``` скрипты. Требуется как минимум один (1) скрипт, который может добавить до восьми (8) функциональных тестовых скриптов. 
  
    Сценарии выполняются в последовательности отправки, а сбой в конкретном скрипте остановит выполнение последующих сценариев.
    У вас также есть возможность выбора дополнительных параметров для каждого предоставленного сценария.

## <a name="set-script-path"></a>Настройка пути скрипта

![Изображение тестовой задачи](Media/testtask.png)

Пример относительного пути в структуре папок приведен ниже:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** бы. _ScriptX.ps1_ как относительный путь.
  - **Script.ps1** будет иметь _папку1/script.ps1_ в качестве относительного пути.


## <a name="next-steps"></a>Дальнейшие действия

Сведения о вкладке Тестовые параметры в следующей статье 
> [!div class="nextstepaction"]
> [Следующий этап](testoptions.md)
