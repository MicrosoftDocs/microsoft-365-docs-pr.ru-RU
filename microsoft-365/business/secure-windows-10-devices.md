---
title: Защита устройств с Windows 10
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Узнайте о настройке параметров политики устройств по умолчанию, которые Windows 10 устройства при входе в свою работу или учетную запись школы.
ms.openlocfilehash: 86db1c152f9f6ac1fe6093b4a55a74b69fbd8b0f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579981"
---
# <a name="secure-windows-10-devices"></a>Защита устройств с Windows 10

Эта статья применима к Microsoft 365 бизнес премиум.

Описанные в этой статье параметры входят в стандартную политику для устройств с Windows 10. Все пользователи, которые подключают Windows 10, включая мобильные устройства и компьютеры, входя в свою учетную запись, автоматически получат эти параметры. Советуем во время настройки принять стандартную конфигурацию, а политики, предназначенные для определенных групп пользователей добавить позднее.
  
## <a name="settings-to-secure-windows-10-devices"></a>Параметры для защиты устройств с Windows 10

Все параметры **включены** по умолчанию. Доступны следующие параметры:
  
|||
|:-----|:-----|
|Параметр  <br/> |Описание  <br/> |
|Использование антивирусной программы "Защитник Windows"  <br/> |Требует включения антивирусной программы "Защитник Windows" для защиты компьютеров, подключенных к Интернету.  <br/> |
|Защитите компьютеры от угроз из Интернета в Microsoft Edge  <br/> |Включает параметры в Microsoft Edge, которые помогают защитить пользователей от вредоносных сайтов и скачиваний.  <br/> |
|Защитить файлы и папки на компьютерах от несанкционированного доступа с помощью BitLocker  <br/> |Bitlocker защищает данные, шифруя жесткие диски компьютера и защищая от воздействия данных, если компьютер потерян или украден. Дополнительные сведения см. [в faq Bitlocker.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)  <br/> |
|Выключать экран устройства, если оно неактивно в течение указанного периода времени  <br/> |Обеспечивает защиту корпоративных данных, когда пользователь неактивен. Пользователь может работать в общественном месте, например кафе, и на короткое время отойти или отвлечься. При этом посторонние могут случайно увидеть сведения на экране. Этот параметр управляет временем, на протяжении которого пользователь может оставаться неактивным, прежде чем экран выключится.  <br/> |
|