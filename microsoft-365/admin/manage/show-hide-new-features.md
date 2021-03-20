---
title: Manage which ‎Office‎ features appear in What's New
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Определите, какие функции Office нужно показывать или скрывать, когда пользователь выбирает справку > Что нового в приложении Office в Windows, используя функцию "Что нового в Office" в центре администрирования Microsoft 365.
ms.openlocfilehash: b9d20e3df4a2de540316dce0e6a6905c07e65176
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915031"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>Manage which Office‎ features appear in What's New

When an important ‎Office‎ feature is released, users will get a message about it when they choose **Help**  >  **What's New** in their ‎‎Office‎‎ app on ‎Windows‎.

Вы можете контролировать, какие из этих сообщений функции показываются пользователям с помощью функции Что нового в **Office** в центре администрирования Microsoft 365. Если вы решите скрыть сообщение функции для пользователей, вы всегда можете вернуться позже и показать его им.

> [!NOTE]
> - Сокрытие сообщения-функции от пользователей не отключит эту функцию в приложении Office.
> - Для использования функции **What's new** в Office вам должна быть назначена роль глобального администратора или роль администратора приложений Office.

## <a name="show-or-hide-new-features"></a>Отображение и скрытие новых функций 

1. В центре администрирования Microsoft 365 в статье **Параметры** выберите **параметры Org.**
2. На **вкладке Services** выберите **что-то новое в Office.**
3. При нажатии на имя функции появляется панель вылетов со следующими сведениями:
     - Краткое описание функции.
     - Ссылка на статью, чтобы узнать больше об этой функции.
     - Приложения Office, в которые отображается эта функция.
     - Первая версия (выпуск), в которую эта функция доступна для этого канала.
4. Выберите **Скрыть от пользователей.** Или, если вы ранее скрывали эту функцию, выберите **Показать пользователям.**

You can also select multiple features on the **Manage which ‎Office‎ features appear in What's New** page, and then choose either **Hide** or **Show**.

> [!NOTE]
> - Если функция доступна в нескольких приложениях Office, настройка функции **Hidden** скрывает сообщение функции во всех этих приложениях Office.
> - Все сообщения функций показаны пользователям по умолчанию. Это состояние по умолчанию для всех функций, и статус изменяется только в том случае, если вы решили скрыть или показать сообщение функции.
> - Вы также можете получить новую функцию **Office** из центра администрирования приложений Microsoft 365 ( [https://config.office.com](https://config.office.com) ). Функция находится в статье **Настройка**  >  **Что такое новое управление**.

## <a name="list-of-features"></a>Список компонентов

You can filter which features appear on the **Manage which ‎Office‎ features appear in What's New** page. Вы можете фильтровать по каналу, приложению или статусу или по некоторому их сочетанию.

Новые функции отображаются на странице в соответствии со следующим расписанием:

||||
|:-----|:-----|:-----|
|**Канал** <br/> |**Дата** <br/> |**Принять меры** <br/> |
|**Current** <br/> |15-е место месяца  <br/> |1 — 3 недели до ежемесячного выпуска <br/> |
|**Monthly Enterprise** <br/> |Первый месяц  <br/> |За две недели до основной версии, которая приносит новые функции |
|**Semi-Annual Enterprise (Preview)** <br/> |1 сентября и 1 марта <br/> | За 2 недели до основной версии, которая приносит новые функции|
|**Полугодовой корпоративный** <br/> |1 января и 1 июля <br/> | За 2 недели до основной версии, которая приносит новые функции<br/> |

Дополнительные сведения о том, когда новые версии выпускаются на каждый канал обновлений, см. в этой ссылке История обновления для [приложений Microsoft 365 (указана по дате).](/officeupdates/update-history-microsoft365-apps-by-date)

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>Добавьте карточку "Что нового в Office" на домашней странице центра администрирования

1. На странице администрирования Microsoft 365 выберите **добавить** карту поверх страницы
2. Найдите управление функциями Office, которые отображаются в **списке What's New,** и выберите его.
3. После того как карта будет на домашней странице, вы можете выбрать новые функции **в Office,** чтобы показать или скрыть функции [организации.](#show-or-hide-new-features)


## <a name="related-articles"></a>Статьи по теме

[Управление Office What's New теперь доступно в общем доступе](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)