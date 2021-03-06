---
title: Применение модели осмысления документации к библиотеке документов
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
description: Сведения о применении опубликованной модели к библиотеке документов SharePoint
ms.openlocfilehash: cda9de43d0139c52f950527eb75d050602005fd2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843298"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Применение модели осмысления документации в Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

После публикации модель осмысления документации можно применить к одной или нескольким библиотекам документов SharePoint в клиенте Microsoft 365.

> [!NOTE]
> Вы можете применить модель только к тем библиотекам документов, к которым у вас есть доступ.


## <a name="apply-your-model-to-a-document-library"></a>Примените модель к библиотеке документов.

Чтобы применить модель к библиотеке документов SharePoint, выполните указанные ниже действия.

1. На домашней странице модели на плитке **Применение модели к библиотекам** выберите **Опубликовать модель**. Вы также можете выбрать пункт **+ Добавить библиотеку** в разделе **Библиотеки с этой моделью**. </br>

    ![Добавление модели в библиотеку](../media/content-understanding/apply-to-library.png)</br>

2. Затем вы можете выбрать сайт SharePoint, содержащий библиотеку документов, к которой нужно применить модель. Если сайт не отображается в списке, используйте поле поиска, чтобы найти его.</br>

    ![Выбор сайта](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > Вам потребуются разрешения *Управление списком* или права на *редактирование* для библиотеки документов, к которой применяется модель.</br>

3. Выбрав сайт, выберите библиотеку документов, к которой нужно применить модель. В приведенном примере выберите библиотеку документов *Документы* на сайте *Отслеживание обращения в Contoso*.</br>

    ![Выбор библиотеки документов](../media/content-understanding/select-doc-library.png)</br>

4. Поскольку модель связана с типом контента, при ее применении к библиотеке будет добавлен тип контента и его представление с извлеченными метками в виде столбцов. Это представление по умолчанию является представлением библиотеки по умолчанию, но при желании можно не использовать его как таковое. Для этого выберите **Дополнительные параметры** и отмените выбор пункта **Использовать это новое представление по умолчанию**.</br>

    ![Представление библиотеки](../media/content-understanding/library-view.png)</br>

5. Нажмите кнопку **Добавить**, чтобы применить модель к библиотеке. 
6. На домашней странице модели в разделе **Библиотеки с этой моделью** вы увидите URL-адрес указанного сайта SharePoint.</br>

    ![Выбранная библиотека](../media/content-understanding/selected-library.png)</br>

7. Перейдите в библиотеку документов и убедитесь, что вы находитесь в представлении библиотеки документов, к которой применяется модель. Обратите внимание, что при нажатии кнопки сведений рядом с именем библиотеки документов появляется сообщение о том, что к библиотеке документов применена модель.

    ![Представление сведений](../media/content-understanding/info-du.png)</br> 

    Чтобы просмотреть подробные сведения о любой модели, примененной к библиотеке документов, выберите **Просмотр активных моделей**.

8. В области **Активные модели** можно просмотреть модели, примененные к библиотеке документов. Выберите модель, чтобы просмотреть дополнительные сведения о ней, например описание модели, кто ее опубликовал, а также сведения о том, применяет ли модель метку хранения к файлам, которые она классифицирует.

    ![Область "Активные модели"](../media/content-understanding/active-models.png)</br> 

После применения модели к библиотеке документов можно начать отправку документов на сайт и просмотр результатов.

Модель определяет все файлы со связанным типом контента и выводит их в представлении. Если модель содержит средства извлечения, в представлении отображаются столбцы для данных, извлекаемых из каждого файла.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Применение модели к файлам, уже находящимся в библиотеке документов

В результате применения модели выполняется обработка всех файлов, отправленных в библиотеку документов. Чтобы запустить модель для файлов, которые уже находились в библиотеке документов до применения модели, выполните указанные ниже действия.

1. В библиотеке документов выберите файлы, которые нужно обработать с помощью модели.
2. После того как вы выберете файлы, на ленте библиотеки документов появится элемент **Классификация и извлечение**. Выберите элемент **Классификация и извлечение**.
3. Выбранные файлы будут добавлены в очередь на обработку.

      ![Классификация и извлечение](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> Вы можете скопировать отдельные файлы в библиотеку и применить их к модели, но не к папкам.

### <a name="the-classification-date-field"></a>Поле "Дата классификации"

Если к библиотеке документов применяется модель обработки форм или осмысления документации SharePoint Syntex, поле <b>Дата классификации</b> добавляется в схему библиотеки. По умолчанию это поле не заполнено, но если документы обрабатываются и классифицируются моделью, в это поле будет добавлена метка даты и времени завершения. 

   ![Столбец "Дата классификации"](../media/content-understanding/class-date-column.png)</br> 

Поле "Дата классификации" используется [триггером <b>Когда файл классифицируется моделью осмысления контента</b>](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) для запуска потока Power Automate, после того как модель осмысления контента Syntex завершит обработку файла и обновление поля "Дата классификации".

   ![Триггер потока](../media/content-understanding/trigger.png)</br>

Затем триггер <b>Когда файл классифицируется моделью осмысления контента</b> можно использовать для запуска другого рабочего процесса с использованием любой извлеченной из файла информации.



## <a name="see-also"></a>См. также
[Создание классификатора](create-a-classifier.md)

[Создание средства извлечения](create-an-extractor.md)

[Общие сведения об осмыслении документации](document-understanding-overview.md)
