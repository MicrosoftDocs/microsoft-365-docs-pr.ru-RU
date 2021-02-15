---
title: Подключение домена к Microsoft 365
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как подключить домен к Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925114"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Подключение домена к Microsoft 365 для бизнеса

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

После того как вы настроите Microsoft 365 и переместите данные электронной почты из Google Workspace, вы можете подключить свой домен к Microsoft 365. 

Сначала вам потребуется удалить существующие записи DNS из Google, а затем мы можем добавить новые записи DNS из Microsoft 365.

## <a name="try-it"></a>Проверьте, как это работает!

1. Во sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).
1. Select **Domains**, **Manage domains**, **View details**, Manage **domain**, then **DNS** in the left nav.
1. Прокрутите вниз до **искусственных записей,** откройте **Google Workspace,** выберите **"Удалить"** и **"Удалить** еще раз".
1. **Прокрутите** вниз до пользовательских записей ресурсов и удалите все существующие записи DNS, которые отображаются, включая те, которые вы ранее создали для Microsoft 365.
1. Перейдите в [Центр администрирования Microsoft 365.](https://admin.microsoft.com)
1. In the left nav, choose, **Show all**, **Settings**, **Domains**.
1. Затем выберите домен по умолчанию.
1. Выберите **"Продолжить** установку", а затем, чтобы подключить домен, выберите **"Продолжить".**
1. Прокрутите вниз, чтобы просмотреть записи DNS, которые необходимо скопировать в Google.
1. Откройте **записи MX** и в области **"Указывает на адрес" или "Значение"** скопируйте запись.
1. Вернись в Google и в **разделе** "Пользовательские записи ресурсов" откройте в dropdown тип записи и выберите **MX.**
1. В поле **"Данные"** в paste the record you copied.
1. Затем нажмите **Добавить**.
1. Повторите процесс для записей CNAME и TXT и добавьте значения на странице управления DNS Google.
1. Вернись в Центр администрирования Microsoft 365 и выберите **"Продолжить".**

    Настройка домена завершена.