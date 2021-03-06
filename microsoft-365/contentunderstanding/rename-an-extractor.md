---
title: Переименование средства извлечения в Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Узнайте, как и зачем переименовывать средство извлечения в Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446056"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>Переименование средства извлечения в Microsoft SharePoint Syntex

В определенный момент может потребоваться переименовать извлечения, если вы хотите ссылаться на извлеченное поле данных с другим именем. Например, ваша организация решает вносить изменения в свои контрактные документы и называет "клиентов" (customers) в своих документах "клиентами" (clients). При извлечении поля "Клиент" (Customer) в модели, вы можете переименовать его в "Клиент" (Client).

При синхронизации обновленной модели с библиотекой документов SharePoint вы увидите новый столбец "Клиент" в представлении библиотеки документов. В вашем представлении сохранится столбец "Клиент" (Customer) для прошлых действий, но будет обновлен новый столбец "Клиент" (Client) для всех новых документов, обрабатываемых вашей моделью. 

> [!IMPORTANT]
>  Обязательно синхронизируйте обновленную модель с библиотеками документов, в которых она была ранее применена для отображения нового имени столбца. 

## <a name="rename-an-extractor"></a>Переименование средства извлечения

Выполните следующие действия, чтобы переименовать средство извлечения объектов.

1. В центре контента выберите **Модели**, чтобы просмотреть список моделей.

2. На странице **Модели** в столбце **Имя** выберите модель, для которой нужно переименовать средство извлечения.

3. В разделе **Средства извлечения объектов** выберите имя средства извлечения, которое вы хотите переименовать, а затем выберите **Переименовать**.</br>

    ![Снимок экрана: раздел "Средство извлечения объектов" с выбранным средством извлечения с выделенной опцией "Переименовать".](../media/content-understanding/entity-extractor-rename.png) </br>

4. На панели **Переименование средства извлечения объектов**:

   а. В разделе **Новое имя** введите новое имя средства извлечения.</br>

    ![Снимок экрана: панель средства извлечения объектов.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   б. (Необязательно) В разделе **Дополнительные параметры** выберите, следует ли связать существующий столбец сайта.

5. Выберите **Переименовать**.

## <a name="see-also"></a>См. также
[Создание средства извлечения](create-an-extractor.md)

[Создание классификатора](create-a-classifier.md)

[Переименование модели](rename-a-model.md)

[Типы объяснения](explanation-types-overview.md)

[Использование таксономии банка терминов при создании средства извлечения](leverage-term-store-taxonomy.md)

[Общие сведения об осмыслении документации](document-understanding-overview.md)

[Применение модели](apply-a-model.md) 
