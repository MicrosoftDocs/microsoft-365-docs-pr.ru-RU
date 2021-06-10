---
title: Добавление домена Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как переместить домен из рабочей области Google в Microsoft 365 для бизнеса.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578775"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Добавьте домен Google Workspace в Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Добавьте домен Google Workspace в Microsoft 365 для бизнеса, чтобы вы могли использовать бизнес-адрес электронной почты.

## <a name="try-it"></a>Проверьте, как это работает!

1. Перейдите в [центр Microsoft 365 администрирования.](https://admin.microsoft.com)
1. В центре администрирования Microsoft 365 в левом nav выберите **Показать** все , **Параметры** и **домены**.
1. Выберите **Добавить домен,** введите доменное имя, а затем **выберите Используйте этот домен.** 
1. Выберите, **добавьте запись TXT в** записи DNS доменов, выберите **Продолжить** и скопируйте значение TXT. 
1. Возвращайся к [консоли администратора Google,](https://admin.google.com)выберите домены, управление доменами, просмотр сведений, управление доменом,  **DNS,** а затем прокрутите до пользовательских **записей ресурсов.**  
1. Откройте падение типа записи, выберите **TXT,** введите скопированные значения TXT, а затем выберите **Добавить**. 

    Обновление обычно принимает факт в течение нескольких минут, но может занять до 48 часов. 
1. Вернись в центр администрирования Microsoft 365, выберите **Проверка** и **затем закрой**. 
1. Чтобы настроить домен в качестве основной электронной почты для пользователей, в левом nav выберите **пользователей Users**  >  **Active.** 
1. Выберите пользователя, выберите **Управление** и имя пользователя и электронную почту, **изменить,** выбрать домен из отсев, а затем выбрать **Сделано** **и сохранить изменения**. 
1. Повторите этот процесс для каждого пользователя. 

    По завершению вы будете готовы установить Office и перенести элементы электронной почты и календаря в Microsoft 365. 