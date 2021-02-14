---
title: Создание и изменение устройств AutoPilot
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Узнайте, как загружать устройства с помощью AutoPilot в Microsoft 365 бизнес премиум. Можно назначить профиль устройству или группе устройств.
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401001"
---
# <a name="create-and-edit-autopilot-devices"></a>Создание и изменение устройств AutoPilot

## <a name="upload-a-list-of-devices"></a>Отправка списка устройств

Вы можете использовать [пошаговую](add-autopilot-devices-and-profile.md) руководство для отправки устройств, но вы также можете отправить устройства на вкладке **"Устройства".** 
  
Устройства должны соответствовать этим требованиям:
  
- Windows 10 версии 1703 или более поздней
    
- Новые устройства, которые не прошли сквозной опыт работы с Windows

1. В Центре администрирования Microsoft 365 выберите **"Устройства** \> **AutoPilot".**
  
2. На странице **AutoPilot** выберите вкладку **"Устройства"** \> **"Добавить устройства".**
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. На панели **"Добавление устройств"** перейдите к [CSV-файлу](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) списка устройств, который вы подготовили для \>  \> **сохранения закрытия.**
    
    Эти сведения можно получить у поставщика оборудования или с помощью скрипта [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) для создания CSV-файла. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Назначение профиля устройству или группе устройств

1. На странице **"Подготовка Windows"** выберите вкладку **"Устройства"** и выберите этот вариант рядом с одним или более устройствами. 
    
2. На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**. 
    
    Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md). 
    
