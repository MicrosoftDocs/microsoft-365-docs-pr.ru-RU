---
title: Использование OneDrive Обучение средств
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Создание и оценка назначений, создание и куратор контента курсов и совместное взаимодействие с файлами в режиме реального времени с новым приложением OneDrive Обучение средства взаимодействия.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257048"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>Использование Microsoft OneDrive LTI с Canvas

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

## <a name="integrate-with-canvas"></a>Интеграция с Canvas

Человек, который выполняет эту интеграцию, должен быть администратором Canvas и администратором Microsoft 365 клиента.

1. Вопишитесь на Microsoft Azure с учетной записью администратора клиента. Администратор клиента Azure также должен иметь роль администратора Группы.

    ![Выделен администратор группы](../media/lti-media/lti-group-admin.png)

2. Во входе на портал [Microsoft OneDrive LTI](https://odltiappnl.azurewebsites.net/admin).

3. Примите разрешения для завершения регистрации.

    ![принимать разрешения](../media/lti-media/lti-permissions.png)

4. Выберите **Добавить клиента LTI**.

     ![добавление клиента LTI](../media/lti-media/lti-add-tenant.png)

5. Выберите **потребительскую платформу LTI в** **качестве Canvas** из отсева.

6. Выберите **URL-адрес базы Canvas** и выберите **Далее**.

    ![выберите Canvas и добавьте базовый URL-адрес](../media/lti-media/lti-canvas-base-url.png)

   На следующем экране показаны конфиденциальные для вас поля.

7. Выберите **Далее** от ?? (Почти готово!). МОГУТ ЛИ РЕЦЕНЗЕНТЫ ЗАПОЛНИТЬ ПРОБЕЛ ЗДЕСЬ?

8. Выберите **Далее** на экране, где показаны конфиденциальные сведения.

   На заключительном экране портала Azure показаны следующие действия для добавления экземпляра Canvas.

9. Скопируйте клавиши разработчика с этого экрана. Вы будете использовать при создании экземпляра Canvas.

## <a name="add-the-canvas-instance"></a>Добавление экземпляра Canvas

1. В экземпляре Canvas высеките **клавиши**  >  **разработчика администрирования.**

2. Выберите **клавишу LTI в** отсеве в **ключе разработчика.**

   ![Получить ключи разработчика LTI](../media/lti-media/lti-developer-keys.png)

3. Вклеить ключи разработчика здесь.

     ![Вклеить ключи разработчика](../media/lti-media/lti-developer-keys.png)

   Ключ создается в **режиме OFF**

   ![Созданные ключи разработчика в выключенном режиме](../media/lti-media/lti-copy-developer-keys.png)

4. Скопируйте выделенный текст.
    Это служит в качестве ID клиента на Microsoft OneDrive портале LTI.

5. Вклеить текст в **поле client ID** на Microsoft OneDrive портале LTI, а затем выберите **Далее**.

6. Нажмите **Сохранить**.

7. Просмотр параметров, выбрав **View LTI Tenants**.
