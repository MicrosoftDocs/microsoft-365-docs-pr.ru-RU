---
title: Создание и изменение устройств AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Узнайте, как загружать устройства с помощью AutoPilot в Microsoft 365 Business Premium. Вы можете назначить профиль устройству или группе устройств.
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578494"
---
# <a name="create-and-edit-autopilot-devices"></a>Создание и изменение устройств AutoPilot

## <a name="upload-a-list-of-devices"></a>Отправка списка устройств

Вы можете использовать [пошаговую](add-autopilot-devices-and-profile.md) руководство для загрузки устройств, но вы также можете загружать устройства на вкладке **Devices.** 
  
Устройства должны соответствовать этим требованиям:
  
- Windows 10, версия 1703 или более поздней версии
    
- Новые устройства, которые не прошли через windows вне окна

1. В центре администрирования Microsoft 365 выберите **Devices** \> **AutoPilot**.
  
2. На странице **АвтоПилот** выберите вкладку **Устройства** \> **Добавить устройства.**
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. На панели **Добавить устройства** просмотрите [CSV-файл списка](../admin/misc/device-list.md) устройств, который вы подготовили \> **Сохранить** \> **закрыть**.
    
    Эти сведения можно получить у поставщика оборудования или с помощью скрипта [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) для создания CSV-файла. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Назначение профиля устройству или группе устройств

1. На странице **Подготовка Windows** выберите вкладку **Устройства** и выберите поле рядом с одним или более устройствами. 
    
2. На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**. 
    
    Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md). 
