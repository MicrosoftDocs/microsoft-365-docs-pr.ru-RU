---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Узнайте, как проверить, Microsoft 365 для параметров защиты бизнес-приложений вступили в силу на устройствах Windows 10 пользователей.
ms.openlocfilehash: fcb463fd98f692f7d4802689e0c03fe4e3e648a1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579849"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Проверка параметров защиты устройств на компьютерах с Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Проверка настройки политик для устройств Windows 10

[Применение политик для устройств](protection-settings-for-windows-10-pcs.md) пользователей может занять до нескольких часов после их настройки. Чтобы убедиться в их применении, вы можете просмотреть несколько экранов параметров Windows на устройствах пользователей. Так как пользователи не смогут изменять параметры Windows и антивирусная программа на Windows 10 устройствах, многие параметры будут серыми.
  
1. Перейдите **Параметры** обновления Windows обновления перезапуска и подтвердите, что все \> **&amp;** \>  \>  параметры серые. 
    
    ![Все параметры перезапуска серые.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Перейдите **Параметры** обновления Windows обновления расширенных параметров и подтвердив, что все \> **&amp;** \>  \>  параметры серые. 
    
    ![Windows Расширенные параметры обновлений все серые.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Подтвердите, что вы можете увидеть сообщение (красным цветом) о том, что некоторые параметры скрыты или управляются организацией, и все параметры серые.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Убедитесь, что все параметры серые. 
    
    ![Параметры защиты от вирусов и угроз серые.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Статьи по теме

[Microsoft 365 для бизнес-документации и ресурсов](./index.yml)
  
[Начало работы с Microsoft 365 для бизнеса](microsoft-365-business-overview.md)
  
[Управление Microsoft 365 для бизнеса](manage.md)
  
[Настройка параметров защиты устройств для компьютеров с Windows 10](protection-settings-for-windows-10-pcs.md)
