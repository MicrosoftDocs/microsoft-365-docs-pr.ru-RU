---
title: Добавление домена Google Workspace
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Узнайте, как переместить домен из Google Workspace в Microsoft 365 для бизнеса.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925006"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Добавление домена Google Workspace в Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Добавьте домен Google Workspace в Microsoft 365 для бизнеса, чтобы вы могли продолжать использовать свой адрес электронной почты.

## <a name="try-it"></a>Проверьте, как это работает!

1. Перейдите в [Центр администрирования Microsoft 365.](https://admin.microsoft.com)
1. In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.
1. Choose **Add domain**, enter your domain name then select Use this **domain**. 
1. Choose, **Add a TXT record to the domains DNS records,** select **Continue**, and copy the TXT value. 
1. Go back to the [Google Admin Console,](https://admin.google.com)choose **Domains**, Manage **domains**, **View Details**, **Manage domain**, **DNS**, and then scroll down to **Custom resource records**. 
1. Откройте в drop-down тип записи, выберите **TXT,** введите значение TXT, скопированные, а затем выберите **"Добавить".** 

    Обновление обычно занимает несколько минут, но может занять до 48 часов. 
1. Вернись в Центр администрирования Microsoft 365, выберите **"Проверить"** и **"Закрыть".** 
1. Чтобы настроить домен в качестве основного сообщения электронной почты для пользователей, в левой области nav выберите **"Активные**  >  **пользователи".** 
1. Выберите пользователя, выберите **"Управление иным** пользователем" и "Электронная почта", "Изменить", "Выберите свой домен" в выпадаке, а затем выберите "Готово" **и** **"Сохранить изменения".** 
1. Повторите этот процесс для каждого пользователя. 

    После завершения вы будете готовы установить приложения Office и перенести элементы электронной почты и календаря в Microsoft 365. 