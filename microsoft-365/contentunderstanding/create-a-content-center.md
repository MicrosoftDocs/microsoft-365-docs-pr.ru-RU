---
title: Создание центра контента в Microsoft SharePoint Синтекс
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как создать центр управления контентом.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295436"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Создание центра контента в Microsoft SharePoint Синтекс

Содержимое этой статьи предназначено для проекта Кортекс Private Preview. [Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

Для создания и управления сведениями о моделях в документе необходимо, чтобы центр контента был первым. Центр контента — это интерфейс создания модели, а также сведения о том, к каким библиотекам документов применены опубликованные модели.</br>

   ![Выбор библиотеки документов](../media/content-understanding/content-center-page.png)</br>

Во время [установки](set-up-content-understanding.md)создается начальный центр контента. Кроме того, администратор SharePoint может создать дополнительные центры по мере необходимости. Несмотря на то, что один центр обработки контента может подключаться к средам, для которых требуется выполнить сведение по всей модели, может потребоваться наличие дополнительных центров для нескольких отделов в Организации, которые могут иметь различные требования и требования к их моделям.

> [!NOTE]
> Администратор SharePoint может создать сайт центра контента, как, например, для [создания любого другого сайта SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) с помощью шаблона сайта.

Для создания нового центра контента:

1. В центре администрирования Microsoft 365 перейдите в центр администрирования SharePoint.
2. В центре администрирования SharePoint в разделе **сайты**выберите **активные сайты**.
3. На странице **активные сайты** нажмите кнопку **создать**, а затем выберите **другие параметры**.
4. В меню **Выбор шаблона** выберите пункт **центр управления контентом**.
5. Для нового сайта укажите **имя сайта**, **основной администратор**и **язык**.</br>

> [!NOTE] 
> При необходимости можно выбрать сайт центра контента для отображения на любом из доступных языков. Для английских файлов можно создавать только текущие модели.</br>

6. Нажмите кнопку **Готово**.

### <a name="give-access-to-additional-users"></a>Предоставление доступа к дополнительным пользователям
 
После создания сайта вы можете предоставить им дополнительные пользователи доступ к сайту с помощью стандартной [модели разрешений сайта SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).

## <a name="see-also"></a>См. также
[Создание классификатора](create-a-classifier.md)</br>
[Создание средства извлечения](create-an-extractor.md)</br>
[Создание центра контента](create-a-content-center.md) 
 [Общие сведения о документе](document-understanding-overview.md)</br>
[Создание модели обработки форм](create-a-form-processing-model.md)</br>
[Применение модели](apply-a-model.md)    
