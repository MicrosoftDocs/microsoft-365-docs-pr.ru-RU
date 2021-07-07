---
title: Проверка
description: Обзор раздела после висят.
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
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323287"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Шаг 6. Просмотрите выбор, чтобы создать пакет.

1.  На этой вкладке служба отображает сведения о тесте и выполняет быструю проверку полноты. 

    A ```Validation passed``` или message shows ```Validation failed``` whether you can proceed to next steps or not.

2.  Просмотрите сведения о тесте, и если вы удовлетворены, нажмите ```Create``` кнопку. 

![Проверка просмотра](Media/validation.png)

3.  Это будет на борту пакета в среде тестовой базы. Если пакет успешно создан, запускается автоматический тест, который проверяет, можно ли успешно выполнять пакет в Azure.

![Успешный результат](Media/successful.png)

> [!Note]
> Вы получите уведомление с портала Azure, чтобы уведомить вас об успешности или сбое проверки пакета. 
>
> Обратите внимание, что процесс может занять до 24 часов, поэтому, скорее всего, ваш веб-сайт будет времявыполнения времени, если вы не активны на нем и, следовательно, уведомление не будет информировать вас о завершении этого по требованию выполнения. 

  - Peradventure это происходит, вы можете просмотреть состояние пакета на ```Manage packages``` вкладке.

![Изображение для управления пакетами](Media/managepackages.png)

  - Для результативных тестов их результаты можно увидеть через запланированные интервалы и страницы, которые часто начинаются через несколько дней после ```Test Summary``` ```Security Updates Results``` ```Feature Updates Results``` отправки.
  
  - Несмотря на сбой тестов, необходимо загрузить новый пакет. 
  
    Вы можете скачать ```test logs``` для дальнейшего анализа с ```Security update results``` "и ```Feature updates results``` страниц.

  - При повторных сбоях тестирования обратитесь к testbasepreview@microsoft.com с подробными сведениями об ошибке. 

## <a name="next-steps"></a>Дальнейшие действия

Откройте для себя рекомендации по контенту по ссылке ниже.
> [!div class="nextstepaction"]
> [Следующий этап](contentguideline.md)
