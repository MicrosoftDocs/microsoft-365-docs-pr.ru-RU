---
title: Использование таксономии банка терминов при создании средства извлечения
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Используйте таксономию банка терминов при создании средства извлечения в модели осмысления документации в Microsoft SharePoint Syntex.
ms.openlocfilehash: b8dfc028e0a18f3345fec466ec5e0079ed2d11ce
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925348"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Использование таксономии банка терминов при создании средства извлечения

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

При создании средства извлечения в модели осмысления документации в SharePoint Syntex можно использовать глобальные наборы терминов в [банке терминов](/sharepoint/managed-metadata), чтобы отображать предпочитаемые термины для извлекаемых данных.  

В качестве примера модель определяет и классифицирует все документы **контракта**, отправленные в библиотеку документов.  Кроме того, модель также извлекает значение **службы контракта** из каждого контракта и отображает его в столбце в представлении библиотеки. Среди различных значений служб контрактов есть несколько старых значений, которые компания больше не использует, и которые были переименованы. Например, все ссылки на значения служб контрактов *Дизайн*, *Графика* и *Топография* должны быть заменены ссылками на *Творческая служба*. Когда модель извлекает один из устаревших терминов из документа контракта, желательно, чтобы в представлении библиотеки отображался текущий термин — "Творческая служба". В приведенном ниже примере при обучении модели один образец документа содержит устаревший термин *Дизайн*.

   ![Банк терминов](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a>Использование столбца управляемых метаданных в средстве извлечения

Наборы терминов настраиваются в банке терминов служб управляемых метаданных в Центре администрирования SharePoint. В приведенном ниже примере [набор терминов](/sharepoint/managed-metadata#term-set) *службы контрактов* включает несколько терминов, в том числе термин *Творческая служба*.  В сведениях указано, что термин имеет три синонима (*Дизайн*, *Графика* и *Топография*), которые должны быть преобразованы в *Творческая служба*. 

   ![Набор терминов](../media/content-understanding/term-store.png)</br>

Существует множество причин, по которым синонимы могут использоваться в наборе терминов. Например, имеются устаревшие либо переименованные термины или отделами организации используются различные вариации при именовании.

Чтобы поле управляемых метаданных можно было выбрать при создании средства извлечения в модели, нужно [добавить его в качестве столбца сайта управляемых метаданных](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f). После добавления столбец сайта можно выбрать при создании средства извлечения для модели.

   ![Служба контракта](../media/content-understanding/contract-services.png)</br>


После применения модели к библиотеке документов при отправке документов в библиотеку в столбце *Творческие службы* будет отображаться предпочитаемый термин (*Творческая служба*), если средство извлечения найдет одно из значений синонимов (*Дизайн*, *Графика* или *Топография*).

   ![Столбец службы контракта](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>См. также
[Общие сведения об управляемых метаданных](/sharepoint/managed-metadata#terms)

[Создание средства извлечения](create-an-extractor.md)

[Создание столбца управляемых метаданных](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)