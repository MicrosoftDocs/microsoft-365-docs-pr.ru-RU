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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как убедиться, что параметры защиты приложений Microsoft 365 для бизнеса вступили в силу на устройствах пользователей с Windows 10.
ms.openlocfilehash: 39aee3bc811cb0090d58f9a282de7a8162c097b3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403597"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Проверка параметров защиты устройств на компьютерах с Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Проверка настройки политик для устройств Windows 10

[Применение политик для устройств](protection-settings-for-windows-10-pcs.md) пользователей может занять до нескольких часов после их настройки. Чтобы убедиться в их применении, вы можете просмотреть несколько экранов параметров Windows на устройствах пользователей. Так как пользователи не смогут изменять параметры Обновления Windows и Защитник Windows антивирусной программы на своих устройствах с Windows 10, многие параметры будут неавтерными.
  
1. Перейдите **в меню "Параметры** обновления \> **безопасности" &amp;** параметров перезапуска Обновлений Windows и подтвердите, что все параметры \>  \>  серые. 
    
    ![Все параметры перезапуска серые.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Перейдите **в меню "Параметры"** "Дополнительные параметры" "Обновление параметров Windows" и подтвердим, что все параметры \> **&amp;** \>  \>  серые. 
    
    ![Все параметры дополнительных обновлений Windows неав толма.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Подтвердите, что вы видите сообщение (красным цветом), что некоторые параметры скрыты или управляются вашей организацией, а все параметры серые.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Убедитесь, что все параметры серые. 
    
    ![Параметры защиты от вирусов и угроз серые.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Статьи по теме

[Документация и ресурсы по Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Начало работы с Microsoft 365 для бизнеса](microsoft-365-business-overview.md)
  
[Управление Microsoft 365 для бизнеса](manage.md)
  
[Настройка параметров защиты устройств для компьютеров с Windows 10](protection-settings-for-windows-10-pcs.md)
  

