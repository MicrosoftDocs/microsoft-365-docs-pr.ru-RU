---
title: Остановка автоматической переададки сообщений электронной почты
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Узнайте, как остановить автоматическую переад вперед сообщения электронной почты.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702593"
---
# <a name="stop-email-auto-forward"></a>Остановка автоматической переададки электронной почты

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Если злоумышленник получает доступ к почтовому ящику пользователя, он может автоматически пересылать электронную почту пользователя на внешний адрес и украсть проприетарную информацию. Это можно остановить, создав правило потока почты.

## <a name="try-it"></a>Проверьте, как это работает!

1. В Центре администрирования Microsoft 365 выберите **Exchange,**  поток обработки почты **и** на вкладке "Правила" выберите знак "плюс" и создайте **новое правило.**
1. Выберите **дополнительные параметры.** Назовите новое правило.
1. Затем откройте drop-down для **применения этого правила,** если , выберите **отправитель**, а затем **внешний внутренний**.
1. Выберите **внутри организации,** а затем **ОК.**
1. Choose **add condition,** open the drop-down, select **The message properties**, then **include the message type**.
1. Откройте **выпадающего типа сообщения** выберите автоадран, а затем **ОК**.
1. Откройте в **следующем выпадаемом** окнове "Сделать", выберите "Заблокировать сообщение", а затем отклонить сообщение и **включите объяснение.**
1. Введите текст сообщения для пояснения и выберите **"ОК".**
1. Прокрутите вниз и выберите **"Сохранить".**

    Ваше правило создано, и злоумышленники больше не смогут автоматически перенаправить сообщения.