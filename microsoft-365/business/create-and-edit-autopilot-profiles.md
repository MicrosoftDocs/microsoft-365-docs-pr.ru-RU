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
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="0fc07-103">Создание и изменение профилей AutoPilot</span><span class="sxs-lookup"><span data-stu-id="0fc07-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="0fc07-104">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="0fc07-104">Create a profile</span></span>

<span data-ttu-id="0fc07-105">Профиль относится к устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="0fc07-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="0fc07-106">В центре администрирования Microsoft 365 Business выберите **устройства** \> **автопилот**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="0fc07-107">На странице **автопилот** выберите \> вкладку **Профили** **Создание профиля**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="0fc07-108">На странице **Создание профиля** введите имя профиля, по которому его можно будет определять, например "Маркетинг", выберите нужные параметры (дополнительные сведения см. в статье [Сведения о параметрах профиля AutoPilot](autopilot-profile-settings.md)) и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="0fc07-110">Применение профиля к устройству</span><span class="sxs-lookup"><span data-stu-id="0fc07-110">Apply profile to a device</span></span>

<span data-ttu-id="0fc07-p101">После создания профиля его можно применить к устройству или группе устройств. Вы можете выбрать существующий профиль с помощью [пошагового руководства](add-autopilot-devices-and-profile.md), применить профиль к новым устройствам или сменить профиль, который уже применяется к устройству или группе устройству.</span><span class="sxs-lookup"><span data-stu-id="0fc07-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="0fc07-113">На странице **Подготовка Windows** перейдите на вкладку **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="0fc07-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="0fc07-116">Изменение и удаление профиля</span><span class="sxs-lookup"><span data-stu-id="0fc07-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="0fc07-p102">После назначения профиля устройству вы можете изменить его, даже если вы уже выдали устройство пользователю. Когда устройство подключается к Интернету, в процессе настройки на него скачивается последняя версия профиля. Когда пользователь сбрасывает устройство до заводских настроек, на него снова скачивается обновленный профиль.</span><span class="sxs-lookup"><span data-stu-id="0fc07-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="0fc07-120">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="0fc07-120">Edit a profile</span></span>

1. <span data-ttu-id="0fc07-121">На странице **Подготовка Windows** перейдите на вкладку **Профили**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="0fc07-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="0fc07-123">Если сделать это до того, как устройство подключится к Интернету, профиль будет применен в процессе настройки.</span><span class="sxs-lookup"><span data-stu-id="0fc07-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="0fc07-124">Удаление профиля</span><span class="sxs-lookup"><span data-stu-id="0fc07-124">Delete a profile</span></span>

1. <span data-ttu-id="0fc07-125">На странице **Подготовка Windows** перейдите на вкладку **Профили**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="0fc07-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="0fc07-127">При удалении профиля он перестает действовать для устройства или группы устройств, которым он был назначен.</span><span class="sxs-lookup"><span data-stu-id="0fc07-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="0fc07-128">Отмена назначения профиля</span><span class="sxs-lookup"><span data-stu-id="0fc07-128">Remove a profile</span></span>

1. <span data-ttu-id="0fc07-129">На странице **Подготовка Windows** перейдите на вкладку **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="0fc07-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="0fc07-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
