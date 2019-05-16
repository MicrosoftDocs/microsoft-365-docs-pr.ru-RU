---
title: Создание и изменение профилей AutoPilot
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Узнайте, как создавать, редактировать, удалять и удалять профили автопилота. '
ms.openlocfilehash: 7987cafb3ea234d81be72c79aee8e584a3770875
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073497"
---
# <a name="create-and-edit-autopilot-profiles"></a>Создание и изменение профилей AutoPilot

## <a name="create-a-profile"></a>Создание профиля

Профиль относится к устройству или группе устройств.
  
1. В центре администрирования Microsoft 365 Business выберите **устройства** \> **автопилот**.
  
2. На странице **автопилот** выберите \> вкладку **Профили** **Создание профиля**.
    
3. На странице **Создание профиля** введите имя профиля, по которому его можно будет определять, например "Маркетинг", выберите нужные параметры (дополнительные сведения см. в статье [Сведения о параметрах профиля AutoPilot](autopilot-profile-settings.md)) и нажмите кнопку **Сохранить**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Применение профиля к устройству

После создания профиля его можно применить к устройству или группе устройств. Вы можете выбрать существующий профиль с помощью [пошагового руководства](add-autopilot-devices-and-profile.md), применить профиль к новым устройствам или сменить профиль, который уже применяется к устройству или группе устройству. 
  
1. На странице **Подготовка Windows** перейдите на вкладку **Устройства**. 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Изменение и удаление профиля

После назначения профиля устройству вы можете изменить его, даже если вы уже выдали устройство пользователю. Когда устройство подключается к Интернету, в процессе настройки на него скачивается последняя версия профиля. Когда пользователь сбрасывает устройство до заводских настроек, на него снова скачивается обновленный профиль. 
  
### <a name="edit-a-profile"></a>Изменение профиля

1. На странице **Подготовка Windows** перейдите на вкладку **Профили**. 
    
2. Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.
    
    Если сделать это до того, как устройство подключится к Интернету, профиль будет применен в процессе настройки.
    
### <a name="delete-a-profile"></a>Удаление профиля

1. На странице **Подготовка Windows** перейдите на вкладку **Профили**. 
    
2. Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.
    
    При удалении профиля он перестает действовать для устройства или группы устройств, которым он был назначен.
    
### <a name="remove-a-profile"></a>Отмена назначения профиля

1. На странице **Подготовка Windows** перейдите на вкладку **Устройства**. 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.
    
