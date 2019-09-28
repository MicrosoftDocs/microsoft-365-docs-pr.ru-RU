---
title: Создание и изменение устройств AutoPilot
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
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Сведения о том, как отправлять устройства с помощью автопилота в Microsoft 365 Business. Вы можете назначить профиль устройству или группе устройств.
ms.openlocfilehash: 9ae94266f5a41d8d115fc92f0f080a6fdbdc9f15
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288022"
---
# <a name="create-and-edit-autopilot-devices"></a>Создание и изменение устройств AutoPilot

## <a name="upload-a-list-of-devices"></a>Отправка списка устройств

Добавить устройства можно с помощью [пошагового мастера](add-autopilot-devices-and-profile.md), а также на вкладке **Устройства**. 
  
Устройства должны отвечать следующим требованиям:
  
- Windows 10 версии 1703 или более поздней;
    
- новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.

1. В центре администрирования Microsoft 365 Business выберите **устройства** \> **автопилот**.
  
2. На странице " **автопилотный проект** " перейдите на \> вкладку **устройства** , чтобы **Добавить устройства**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. На панели **Add Devices (Добавление устройств** ) перейдите к [списку устройств CSV-файл](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , для которого подготовлено \> **Сохранение** \> , **Закрыть**.
    
    Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Назначение профиля устройству или группе устройств

1. На странице **Подготовка Windows** перейдите на вкладку **Устройства** и установите флажки рядом с одним или несколькими устройствами. 
    
2. На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**. 
    
    Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md). 
    
