---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как проверить параметры защиты Microsoft 365 бизнес-приложений на устройствах с Windows 10.
ms.openlocfilehash: 66e83df19e44419b37bcc1c5678ab13317162dbc
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288602"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Проверка параметров защиты устройств на компьютерах с Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Проверка настройки политик для устройств Windows 10

[Применение политик для устройств](protection-settings-for-windows-10-pcs.md) пользователей может занять до нескольких часов после их настройки. Чтобы убедиться в их применении, вы можете просмотреть несколько экранов параметров Windows на устройствах пользователей. Так как пользователи не смогут изменять параметры Центра обновления Windows и антивирусной программы "Защитник Windows" на своих устройствах Windows 10, многие из них будут затенены.
  
1. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out. 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out. 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Убедитесь в том, что красное сообщение "Некоторые параметры скрыты, или ими управляет ваша организация" отображается и все параметры затенены.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Убедитесь в том, что все параметры затенены. 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Статьи по теме

[Документы и ресурсы по Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Начало работы с Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Управление Microsoft 365 бизнес](manage.md)
  
[Настройка параметров защиты устройств для компьютеров с Windows 10](protection-settings-for-windows-10-pcs.md)
  

