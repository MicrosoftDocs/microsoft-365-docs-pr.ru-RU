---
title: Общие сведения об обработке форм
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Узнайте об обработке форм в Microsoft SharePoint Syntex
ms.openlocfilehash: 6c2cb2ee3c1fc621e7814f4603ad2e6f0b891701
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087407"
---
# <a name="form-processing-overview"></a>Общие сведения об обработке форм

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Средство Microsoft SharePoint Syntex использует функцию обработки форм приложения Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) для создания моделей в библиотеках документов SharePoint.

Вы можете использовать функцию обработки форм AI Builder для создания моделей ИИ, использующих технологию машинного обучения для поиска и извлечения пар вида "ключ и значение" и табличных данных из структурированных или частично структурированных документов, таких как формы и счета.

Организации часто получают большое количество счетов по различным каналам, таким как почта, факс, электронная почта и т. д. Обработка этих документов и внесение их в базу данных вручную может занимать очень много времени. Применяя ИИ для извлечения из ваших документов текста, пар "ключ и значение" и табличных данных, функция обработки форм автоматизирует этот процесс. 

> [!NOTE]
> Дополнительные сведения о примерах сценариев обработки форм см. в статье [Внедрение SharePoint Syntex: руководство по началу работы](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).

Например, можно создать модель обработки форм, которая найдет все заказы на покупку, загруженные в библиотеку документов. Затем вы можете извлечь из каждого заказа и отобразить не или иные сведения, представляющие для вас важность, например *Номер заказа*, *Дата* или *Общая стоимость*.

![Представление библиотеки документов](../media/content-understanding/doc-lib-done.png)</br>  

Вы можете использовать образцы файлов, чтобы обучить модель, указав, какие данные нужно извлекать из форм. Во время обучения модель усваивает структуру ваших документов. Чтобы приступить к работе, вам нужно всего пять форм. Приложение AI Builder проанализирует ваши образцы файлов на предмет пар "ключ/значение", а те пары, которые могли быть пропущены, вы можете указать вручную.  AI Builder позволяет протестировать точность работы модели на образцах файлов.

Чтобы приступить к работе, вам нужно не менее пяти форм. Процесс построения ИИ включает анализ ваших образцов файлов на предмет пар "ключ/значение" и указание вручную тех пар, которые могли быть пропущены.  AI Builder позволяет протестировать точность работы модели на образцах файлов.

После обучения и публикации вашей модели она создаст рабочий процесс [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started). Этот процесс будет выполняться при загрузке файла в библиотеку документов SharePoint, извлекая данные, указанные в модели. Извлеченные данные будут отображаться в столбцах в представлении библиотеки документов вашей модели.

Администратору Office 365 необходимо [включить функцию обработки форм](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) для библиотеки документов SharePoint, чтобы пользователи могли [создавать модели обработки форм](create-a-form-processing-model.md) в этой библиотеке. Вы можете выбрать сайты во время настройки или после нее в параметрах управления.



## <a name="see-also"></a>См. также
  
[Документация Power Automate](https://docs.microsoft.com/power-automate/)

[Создание модели обработки форм](create-a-form-processing-model.md)

[Общие сведения об осмыслении документации](document-understanding-overview.md)

[Учебный курс. Повышение продуктивности бизнеса с помощью AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
