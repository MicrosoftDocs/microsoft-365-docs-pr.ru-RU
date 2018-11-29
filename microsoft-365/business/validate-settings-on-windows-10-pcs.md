---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Сведения о проверке параметров защиты Microsoft 365 Business приложения в устройствах Windows 10.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870606"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Проверка параметров защиты устройств на компьютерах с Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Проверка настройки политик для устройств Windows 10

[Применение политик для устройств](protection-settings-for-windows-10-pcs.md) пользователей может занять до нескольких часов после их настройки. Чтобы убедиться в их применении, вы можете просмотреть несколько экранов параметров Windows на устройствах пользователей. Так как пользователи не смогут изменять параметры Центра обновления Windows и антивирусной программы "Защитник Windows" на своих устройствах Windows 10, многие из них будут затенены.
  
1. Перейдите на страницу **Параметры** \> **обновление &amp; безопасности** \> **Windows Update** \> **Параметры перезагрузки** и убедитесь, что все параметры имеют серый. 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Перейдите на страницу **Параметры** \> **обновление &amp; безопасности** \> **Windows Update** \> **Дополнительные параметры** и убедитесь, что все параметры имеют серый. 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Перейдите на страницу **Параметры** \> **обновление &amp; безопасности** \> **Windows Update** \> **Дополнительные параметры** \> **Выберите способ доставки обновлений**.
    
    Убедитесь в том, что красное сообщение "Некоторые параметры скрыты, или ими управляет ваша организация" отображается и все параметры затенены.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Чтобы открыть центр безопасности Защитника Windows, перейдите в раздел **Параметры** \> **обновление &amp; безопасности** \> **Защитник Windows** \> нажмите кнопку **Открыть центр безопасности Защитник Windows** \> **от вирусов &amp; потока Защита** \> **вирус &amp; угроз параметры защиты**. 
    
5. Убедитесь в том, что все параметры затенены. 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>См. также:

[Документы и ресурсы по Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Начало работы с Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Управление Microsoft 365 бизнес](manage.md)
  
[Настройка параметров защиты устройств для компьютеров с Windows 10](protection-settings-for-windows-10-pcs.md)
  

