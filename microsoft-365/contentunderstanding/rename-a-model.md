---
title: Переименование модели в Microsoft SharePoint Syntex
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
description: Узнайте, как и зачем переименовывать модель в Microsoft SharePoint Syntex.
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446062"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a>Переименование модели в Microsoft SharePoint Syntex

В какой-то момент может потребоваться переименовать модель осмысления документации. Распространенным примером является создание исходного черновика модели, вы, возможно, не задумывались об окончательном имени (например, вы могли бы назвать его «AlexWilburModel1»). По мере приближения к завершению модели и ее использованию, вы понимаете, что более правильным названием было бы «Продление контракта», и вы хотите переименовать его.  

Еще один пример — когда ваша организация принимает решение ссылаться на процесс или тип документа под другим именем. Например, после создания модели и ее готовности к применению ваша организация может потребовать, чтобы все «Контракты» теперь формально назывались «Соглашениями». При необходимости вы можете переименовать модель с «Продление контракта» на «Продление соглашения».

> [!IMPORTANT]
> Модель осмысления документации можно переименовать, только если она не была применена к библиотеке документов. 

Переименование модели также переименовывает [тип контента](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview), связанный с моделью.

## <a name="rename-a-model"></a>Переименование модели

Выполните следующие действия, чтобы переименовать модель осмысления документации.

1. В центре контента выберите **Модели**, чтобы просмотреть список моделей.

2. На странице **Модели** выберите модель, которую нужно переименовать.

3. С помощью ленты или кнопки **Показать действия** (рядом с именем модели) выберите **Переименовать**. </br>

    ![Снимок экрана: страница "Модели", на которой показана выбранная модель с выделенными параметрами "Переименовать".](../media/content-understanding/select-model-rename-both.png) </br>

4. На панели **Переименование модели**:

   а. В разделе **Новое имя** введите новое имя модели, которую вы хотите переименовать.</br>

    ![Снимок экрана: панель переименования модели.](../media/content-understanding/rename-model-panel.png) </br>

   б. (Необязательно) В разделе **Дополнительные параметры** выберите, следует ли связать существующий [тип контента](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview). Если выбрать **Использовать существующий тип контента**, модель будет переименована в соответствие с выбранным типом контента.

5. Выберите **Переименовать**.

## <a name="see-also"></a>См. также
[Создание классификатора](create-a-classifier.md)

[Создание средства извлечения](create-an-extractor.md)

[Переименование средства извлечения](rename-an-extractor.md)

[Общие сведения об осмыслении документации](document-understanding-overview.md)

[Типы объяснения](explanation-types-overview.md)

[Применение модели](apply-a-model.md) 
