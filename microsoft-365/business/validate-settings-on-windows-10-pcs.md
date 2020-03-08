---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как убедиться в том, что параметры защиты бизнес-приложений Microsoft 365 были применены к устройствам Windows 10 для пользователей.
ms.openlocfilehash: 47977f8d79eb6dbb2f4d087af8f8ad7da4313c61
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560687"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Проверка параметров защиты устройств на компьютерах с Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Проверка настройки политик для устройств Windows 10

[Применение политик для устройств](protection-settings-for-windows-10-pcs.md) пользователей может занять до нескольких часов после их настройки. Чтобы убедиться в их применении, вы можете просмотреть несколько экранов параметров Windows на устройствах пользователей. Так как пользователи не смогут изменять параметры Windows Update и антивирусной программы "Защитник Windows" на своих устройствах с Windows 10, многие параметры будут недоступны.
  
1. Перейдите к разделу **Параметры** \> **обновления &amp; для системы безопасности** \> **центра обновления** \> Windows **и убедитесь** , что все параметры неактивны. 
    
    ![Все варианты перезапуска выделены серым цветом.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Перейдите к разделу **Параметры** \> **Обновление &amp; безопасности** \> **Windows Update** \> **Advanced Options** и убедитесь, что все параметры отключены. 
    
    ![Параметры дополнительных обновлений Windows выделены серым цветом.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Подтвердите, что вы видите сообщение (в красном) о том, что некоторые параметры скрыты или управляются вашей организацией, а все параметры выделены серым цветом.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Убедитесь, что все параметры неактивны. 
    
    ![Параметры защиты от вирусов и угроз выделены серым цветом.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Статьи по теме

[Документы и ресурсы по Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Начало работы с Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Управление Microsoft 365 бизнес](manage.md)
  
[Настройка параметров защиты устройств для компьютеров с Windows 10](protection-settings-for-windows-10-pcs.md)
  

