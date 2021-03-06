---
title: Использование Microsoft OneDrive Обучение средства
ms.author: heidip
author: MicrosoftHeidi
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
description: Создание и оценка назначений, создание и куратор контента курсов и совместное взаимодействие с файлами в режиме реального времени с новым приложением Microsoft OneDrive Обучение средства взаимодействия.
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322225"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Интеграция Microsoft OneDrive LTI с Canvas

Интеграция Microsoft OneDrive LTI с Canvas — это двухшаговая процедура. Первый шаг включает Microsoft OneDrive Canvas, а второй шаг делает Microsoft OneDrive LTI доступным в курсах Canvas.

## <a name="recommended-browser-settings"></a>Рекомендуемые параметры браузера

- Файлы cookie должны быть включены для Microsoft OneDrive.
- Всплывающие окантовки не должны быть заблокированы для Microsoft OneDrive.

> [!NOTE]
> - Cookie-файлы не включены по умолчанию в режиме инкогнито браузера Chrome, и их необходимо включить.
> - Microsoft OneDrive LTI работает в частном режиме в Microsoft Edge браузере. Убедитесь, что вы не заблокировали файлы cookie (которые включены по умолчанию).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Включить Microsoft OneDrive LTI в Canvas

> [!IMPORTANT]
> Человек, который выполняет эту интеграцию, должен быть администратором Canvas и администратором Microsoft 365 клиента.

1. Вход на <a href="https://onedrivelti.microsoft.com/admin" target="_blank">портал регистрации Microsoft OneDrive LTI</a>
1. Выберите **кнопку Согласие администратора** и примите разрешения.

> [!CAUTION]
> Если этот шаг не выполнен, следующий шаг даст вам ошибку, и вы не сможете сделать этот шаг в течение часа после того, как вы получили ошибку.

3. Выберите **кнопку Создание нового клиента LTI.** На странице Регистрация LTI выберите **Canvas** в отсеве и введите базовый URL-адрес экземпляра Canvas.

> [!NOTE]
> Если экземпляр Canvas , https://contoso.test.instructure.com например, ]( (, то полный https://contoso.test.instructure.com) URL-адрес должен быть введен.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Страница администрирования клиента LTI с полем для отсева для выбора потребительской платформы LTI и текстовым полем URL-адреса.":::

4. Скопируйте JSON, выбрав кнопку **Copy** (значок справа, который показывает две страницы поверх друг друга). Это будет использоваться для создания ключа в Canvas.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Изображение, на котором отображается кнопка копирования, которая скопирует отображаемого текста JSON и сделает его доступным для генерации ключей в Canvas.":::

5. Вопишите в экземпляр Canvas в качестве администратора и выберите **клавиши** разработчика из меню в левой части страницы. В отсеве создайте ключ разработчика, выбрав **ключ LTI** из отсева справа верхней части страницы.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Снимок экрана, на котором показана левая панели навигации с выбранными клавишами разработчика, и запись ключа LTI, выбранная из отсева справа от страницы.":::

6. На странице Настройка в отсеве **Метода** выберите в качестве метода вклейку JSON и вклеите текст **JSON,** скопированные в шаге 5 в текстовом поле, которое отображается.
7. Сохраните ключ, и он станет доступен в Canvas в **состоянии Off.** Включи ключ **и** скопируйте ключ, заданный в столбце **Details,** который будет использоваться на следующем шаге.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Страница Canvas с набором ключей в выключеном состоянии. Его необходимо будет включить, а ключ будет скопирован из столбца сведений на этой странице.":::

8. Вернись на Microsoft OneDrive портал регистрации LTI и вклей ключ в поле **Canvas Client ID.** Выберите **Далее,** когда вы будете готовы.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Страница регистрации клиента LTI, на которой показан текст JSON и текстовое поле, в которое должен быть скопирован ключ.":::

9. Просмотрите и сохраните изменения. Сообщение будет отображаться при успешной регистрации.
10. Сведения о регистрации также можно просмотреть, выбрав кнопку **View LTI Tenants** на домашней странице.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Включить Microsoft OneDrive LTI в курсах Canvas

Администратор Canvas может включить Microsoft OneDrive LTI для всех курсов. Если Microsoft OneDrive LTI необходим в определенном курсе (и не на всех курсах), преподавателю курса необходимо следовать тем же шагам в параметрах курса.

1. Войдите в качестве администратора и перейдите в **раздел Параметры.**
2. Перейдите в **раздел Приложения** и выберите кнопку **Настройка приложений** просмотра.
3. Выберите **кнопку Добавить приложение.**
4. В **отсеве типа** конфигурации выберите параметр **By Client ID.**
5. Вклеить значение ключа разработчика, сгенерированного ранее в поле **Client ID,** и выберите кнопку **Отправка.**

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Страница добавления приложения, показывающая параметр By client ID в меню выпадаемого типа конфигурации.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Совместная Параметры для Microsoft OneDrive LTI в canvas Courses

> [!NOTE]
> Для совместной работы преподавателей и учащихся не следует включить параметр совместной работы. Чтобы убедиться, что параметр не включен, выполните следующие действия.

1. Войдите в качестве администратора и перейдите в **раздел Параметры.**
1. Перейдите **в раздел Параметры** функций, а затем перейдите в раздел **Курс.**
1. Установите не **включенную функцию External Collaborations Tool.**

> [!NOTE]
> Совместная работа может быть назначена отдельным учащимся и группам учащихся. Назначение отдельным учащимся работает по умолчанию. Чтобы назначить совместную работу группе учащихся, выполните следующие действия:

1. Войдите в качестве администратора и перейдите в раздел **Ключи разработчика.**
1. Найдите ключ со значением 170000000000710 и установите его **на .**
