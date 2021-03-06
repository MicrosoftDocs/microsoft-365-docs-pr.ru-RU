---
title: Применение метки хранения к модели
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
localization_priority: Normal
description: В этой статье объясняется, как применить метку хранения к модели в SharePoint Syntex
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861615"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>Применение метки хранения к модели в SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Вы можете легко применить [метку хранения](../compliance/retention.md) к модели в Microsoft SharePoint Syntex. Вы можете это сделать как для модели осмысления документации, так и для модели обработки форм.

Метки хранения позволяют применить параметры хранения к документам, определяемым моделями.  Например, вы хотите, чтобы ваша модель не только определяла любые документы с *уведомлением о страховании*, которые загружаются в вашу библиотеку документов, но также применяла к ним тег хранения *Бизнес*, чтобы эти документы нельзя было удалить из библиотеки документов в течение указанного периода времени (например, в течение следующих пяти месяцев).

Вы можете применить существующую метку хранения к вашей модели с помощью параметров модели на ее домашней странице. 

> [!Important]
> Чтобы метки хранения были доступны для применения к вашей модели осмысления документации, они должны быть [созданы и опубликованы в Центре соответствия требованиям Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Чтобы добавить метку хранения к модели понимания документа, выполните следующие действия:

1. На домашней странице модели выберите **Параметры модели**.</br>
2. В **Параметрах модели**, в разделе **Безопасность и соответствие требованиям** выберите меню **Метка хранения**, чтобы просмотреть список меток хранения, которые можно применить к модели.</br>
 ![Меню метки хранения](../media/content-understanding/retention-labels-menu.png)</br> 
3. Выберите метку хранения, которую вы хотите применить к модели, и нажмите кнопку **Сохранить**.</br>

Добавив метку хранения к модели, вы можете применить ее к:
- Новой библиотеке документов
- Библиотеке документов, к которой уже применена модель
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Примените метку хранения к библиотеке документов, к которой уже применена модель

Если модель понимания документа уже была применена к библиотеке документов, вы можете выполнить следующие действия, чтобы синхронизировать обновление метки хранения, чтобы применить его к библиотеке документов:</br>

1. На домашней странице модели в разделе **Библиотеки с этой моделью**, выберите библиотеку документов, к которой вы хотите применить обновление метки хранения. </br> 
2. Выберите команду **Синхронизировать**. </br>
 ![Модель синхронизации](../media/content-understanding/sync-model.png)</br> 


После применения обновления и его синхронизации с моделью вы можете подтвердить, что оно было применено, выполнив следующие действия:

1. В Центре содержимого в разделе **Библиотеки с этой моделью**, щелкните библиотеку, к которой была применена обновленная модель. </br>
2. В представлении «Библиотека документов» щелкните значок сведений, чтобы проверить свойства модели.</br>  
3. В списке **Активные модели** выберите обновленную модель.</br>
4. В разделе **Метка хранения** будет указано имя примененной метки хранения.</br>


На странице представления модели в библиотеке документов будет отображаться новая **Метка хранения**.  Поскольку ваша модель классифицирует файлы, которые она идентифицирует как принадлежащие к своему типу контента, и перечисляет их в представлении библиотеки, в столбце «Метка хранения» также отображается имя метки хранения, которая была применена к ней через модель.


Например, ко всем документам с *уведомлением о страховании*, которые определяет ваша модель, также будет применена метка хранения *Бизнес*, предотвращающая их удаление из библиотеки документов в течение пяти месяцев. При попытке удалить файл из библиотеки документов будет отображаться сообщение о том, что это запрещено из-за примененной метки сохранения.

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>Добавление метки хранения в модель обработки форм

> [!Important]
> Чтобы метки хранения были доступны для применения к вашей модели обработки форм, они должны быть [созданы и опубликованы в Центре соответствия требованиям Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

Метку хранения можно применить к модели обработки форм при создании модели или применить ее к существующей модели.

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>Добавление метки хранения при создании модели обработки форм

1. При [создании модели обработки форм](./create-a-form-processing-model.md) выберите <b>Дополнительные параметры</b>.
2. В области <b>Дополнительные параметры</b> в разделе <b>Метка хранения</b> откройте меню и выберите метку хранения, которую нужно применить к модели.</b>

 
     ![Добавление в новую модель обработки форм](../media/content-understanding/retention-label-forms.png)</br>

3.  Завершив настройку оставшихся параметров модели, выберите <b>Создать</b>, чтобы создать модель.

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>Добавление метки хранения в существующую модель обработки форм

Вы можете добавить метку хранения в существующую модель обработки форм разными способами:
- В меню автоматизации в библиотеке документов
- В параметрах активной модели в библиотеке документов 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>Добавление метки хранения в существующую модель обработки форм в меню автоматизации

Вы можете добавить метку хранения в существующую модель обработки форм, которой вы владеете, с помощью меню автоматизации в библиотеке документов, к которой применяется модель.


1. В библиотеке документов, к которой применяется модель обработки форм, откройте меню <b>Автоматизация</b>, выберите <b>AI Builder</b> и нажмите <b>Просмотр сведений о модели обработки форм</b>.

   ![Меню "Автоматизация"](../media/content-understanding/automate-menu.png)</br>

2. В сведениях о модели в разделе <b>Метка хранения</b> выберите метку хранения, которую нужно применить.  Нажмите <b>Сохранить</b>.

     ![Добавление в существующую модель обработки форм](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>Добавление метки хранения в существующую модель обработки форм в параметрах активной модели

Вы можете добавить метку хранения в существующую модель обработки форм, которой вы владеете, с помощью параметров активной модели в библиотеке документов, к которой применяется модель.

1. В библиотеке документов SharePoint, к которой применяется модель, щелкните значок <b>Просмотреть активные модели</b> и выберите <b>Просмотреть активные модели</b>.</b>

   ![Просмотр активных моделей](../media/content-understanding/info-du.png)</br> 

2. В разделе <b>Активные модели</b> выберите модель обработки форм, к которой нужно применить метку хранения.

     ![Сведения о модели](../media/content-understanding/retention-label-model-details.png)</br> 


3. В сведениях о модели в разделе <b>Метка хранения</b> выберите метку хранения, которую нужно применить.  Нажмите <b>Сохранить</b>.

> [!NOTE]
> Чтобы вносить изменения в области параметров модели, вы должны быть владельцем модели. 


## <a name="see-also"></a>См. также
[Создание классификатора](create-a-classifier.md)

[Создание средства извлечения](create-an-extractor.md)

[Общие сведения об осмыслении документации](document-understanding-overview.md)
