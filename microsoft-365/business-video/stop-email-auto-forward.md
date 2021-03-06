---
title: Отмена автоматической переадресации электронной почты
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminTemplateSet
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как остановить автонападение электронных писем, создав правило потока почты, чтобы избежать кражи несвободных данных.
ms.openlocfilehash: 23b1afa7a851c0b00fb9fca574ca0bb32057ea42
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394801"
---
# <a name="stop-email-auto-forward"></a>Остановка автопродажа электронной почты

## <a name="watch-stop-auto-forwarding-emails"></a>Watch: Stop auto-forwarding emails

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Если хакер получает доступ к почтовому ящику пользователя, он может автоматически пересылать электронную почту пользователя на внешний адрес и украсть несвободные сведения. Это можно остановить, создав правило потока почты.

## <a name="try-it"></a>Проверьте, как это работает!

1. Из Центр администрирования Microsoft 365 выберите **Exchange,** поток почты **и** на  вкладке правила выберите знак плюс и **создайте новое правило.**
1. Выберите **дополнительные параметры**. Назови новое правило.
1. Затем откройте выпадаю для **применения этого правила,** если , выберите **отправитель**, а затем **внешний внутренний**.
1. Выберите **Внутри организации,** а затем **ОК**.
1. Выберите **условие добавить,** откройте выпадаемую, **выберите** свойства сообщения, а затем **включите тип сообщения.**
1. Откройте **выпадающего** типа сообщения, выберите **Авто-вперед**, а затем **ОК**.
1. Откройте сообщение **Do the Following** drop-down, выберите **Блок** сообщения, а затем отклонить сообщение и **включить объяснение.**
1. Введите текст сообщения для объяснения, а затем выберите **ОК**.
1. Прокрутите вниз и выберите **Сохранить**.

    Ваше правило создано, и хакеры больше не смогут автоматически отправлять сообщения.

## <a name="related-content"></a>См. также:

[Добавление дополнительных псевдонимов электронной почты для пользователя](../admin/email/add-another-email-alias-for-a-user.md) (статья)\
[Настройка переадресации электронной почты в Microsoft 365](../admin/email/configure-email-forwarding.md) (статья)\
Поиск и устранение проблем с доставкой электронной [почты в качестве Office 365 для бизнес-администратора](/exchange/troubleshoot/email-delivery/email-delivery-issues) (статья)