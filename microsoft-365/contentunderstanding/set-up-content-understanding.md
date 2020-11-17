---
title: Настройка SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Настройка понимания содержимого в Project Cortex
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087575"
---
# <a name="set-up-sharepoint-syntex"></a>Настройка SharePoint Syntex

Администраторы могут использовать Центр администрирования Microsoft 365 для настройки [Microsoft SharePoint Syntex](index.md). 

Прежде чем начать, примите во внимание следующие моменты:

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- Как вы назовете свой центр содержимого по умолчанию?

Вы можете изменить параметры после начальной настройки в Центре администрирования Microsoft 365.

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- Сайтов SharePoint, на которых вы хотите включить обработку форм — всех из них, некоторых или выбранных сайтах
- Центра содержимого и имени главного администратора сайта

## <a name="requirements"></a>Требования 

> [!NOTE]
> У вас должны быть разрешения глобального администратора или администратора SharePoint, чтобы получить доступ к Центру администрирования Microsoft 365 и настраивать понимание содержимого.

Как администратор, вы также можете вносить изменения в выбранные параметры в любое время после завершения их настройки, а также во все параметры управления содержимым в Центре администрирования Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Чтобы настроить SharePoint Syntex, выполните следующие действия:

1. В Центре администрирования Microsoft 365 выберите **Настройка**, затем просмотрите раздел **Файлы и содержимое**.

2. В разделе **Файлы и содержимое** выберите **Автоматизировать понимание содержимого**.<br/>

3. На странице **Автоматизировать понимание содержимого**, нажмите **Начать** , чтобы начать процесс настройки.<br/>

    > [!div class="mx-imgBorder"]
    > ![Начало настройки](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     Для **каких библиотек SharePoint должен отображаться параметр создания модели обработки форм**, вы можете выбрать:</br>
      - **Все библиотеки SharePoint**, чтобы сделать его доступным для всех библиотек SharePoint в вашей организации.</br>
      - **Только библиотеки на выбранных сайтах**, а затем выберите сайты, в которых вы хотите сделать его доступным, или загрузите список, содержащий до 50 сайтов.</br>
      - **Не в библиотеках SharePoint**, если вы не хотите, чтобы он был доступен для всех сайтов (после настройки вы можете изменить эту настройку).

   > [!div class="mx-imgBorder"]
   > ![Настройка обработки форм](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Удаление сайта после его включения, не влияет на существующие модели, применяемые к библиотекам на этом сайте, или на возможность применять модели понимания документов к библиотеке. 
    
5. На странице **Создание Центра содержимого** можно создать сайт Центра содержимого SharePoint, на котором пользователи смогут создавать и управлять моделями понимания документов.

    1. В поле **Имя сайта** введите имя, которое вы хотите дать сайту Центра содержимого.
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![Создание Центра содержимого](../media/content-understanding/admin-cu-create-cc.png)</br>

       Нажмите кнопку **Далее**.

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. На странице подтверждения нажмите кнопку **Готово**.

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>Назначение лицензий

После настройки SharePoint Syntex необходимо назначить лицензии пользователям, которые будут использовать возможности SharePoint Syntex.

Чтобы назначить лицензии, выполните следующие действия:

1. В Центре администрирования Microsoft 365 в разделе **Пользователи**, щелкните **Активные пользователи**.

2. Выберите пользователей, которых вы хотите лицензировать, и щелкните **Управление лицензиями продуктов**.

3. Выберите **Назначить еще**.

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![Лицензии SharePoint Syntex в Центре администрирования Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Нажмите кнопку **Сохранить изменения**.

## <a name="ai-builder-credits"></a>Титры AI Builder

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

Вы можете оценить мощность AI Builder, которая подходит именно вам, с помощью [калькулятора AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).

Чтобы проверить титры и использование, перейдите в [Центр администрирования Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity).

## <a name="see-also"></a>См. также

[Обзор модели обработки форм](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Пошаговые инструкции: Создание модели понимания документа (видео)](https://www.youtube.com/watch?v=DymSHObD-bg)

