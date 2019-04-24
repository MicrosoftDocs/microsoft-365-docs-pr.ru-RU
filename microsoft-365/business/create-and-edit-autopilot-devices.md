---
title: Создание и изменение устройств AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Сведения о том, как отправлять устройства с помощью автоПилота в Microsoft 365 Business. Вы можете назначить профиль устройству или группе устройств.
ms.openlocfilehash: fff2dbc6af45ef9d4189f23849d638172c19dfb2
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277059"
---
# <a name="create-and-edit-autopilot-devices"></a>Создание и изменение устройств AutoPilot

## <a name="upload-a-list-of-devices"></a>Отправка списка устройств

Добавить устройства можно с помощью [пошагового мастера](add-autopilot-devices-and-profile.md), а также на вкладке **Устройства**. 
  
Устройства должны отвечать следующим требованиям:
  
- Windows 10 версии 1703 или более поздней;
    
- новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.

1. в центре администрирования Microsoft 365 Business выберите элемент **устройства** \> **автопилот** \> **Add**.
  
2. On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. На панели **Add Devices (Добавление устройств** ) перейдите к [списку устройств CSV-файл](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , для \> которого подготовлено **Сохранение** \> , **Закрыть**.
    
    Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Назначение профиля устройству или группе устройств

1. На странице **Подготовка Windows** перейдите на вкладку **Устройства** и установите флажки рядом с одним или несколькими устройствами. 
    
2. На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**. 
    
    Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md). 
    
