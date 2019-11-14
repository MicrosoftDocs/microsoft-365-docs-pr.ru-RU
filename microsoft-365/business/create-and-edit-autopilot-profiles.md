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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Узнайте, как создавать, редактировать, удалять и удалять профили автопилота.
ms.openlocfilehash: f7fdc2632e93c48e043fe158842f8395d6a89e14
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320245"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="f9639-103">Создание и изменение профилей AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f9639-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="f9639-104">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="f9639-104">Create a profile</span></span>

<span data-ttu-id="f9639-105">Профиль относится к устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="f9639-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="f9639-106">В центре администрирования Microsoft 365 Business выберите **устройства** \> **автопилот**.</span><span class="sxs-lookup"><span data-stu-id="f9639-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="f9639-107">На странице **автопилот** выберите вкладку \> **Профили** **Создание профиля**.</span><span class="sxs-lookup"><span data-stu-id="f9639-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="f9639-108">На странице " **Создание профиля** " введите имя профиля, помогающее определить его, например "маркетинг".</span><span class="sxs-lookup"><span data-stu-id="f9639-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="f9639-109">Включите нужный параметр, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f9639-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="f9639-110">Дополнительные сведения о параметрах профиля автопилота см [.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f9639-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="f9639-112">Применение профиля к устройству</span><span class="sxs-lookup"><span data-stu-id="f9639-112">Apply profile to a device</span></span>

<span data-ttu-id="f9639-113">После создания профиля его можно применить к устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="f9639-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="f9639-114">Вы можете выбрать существующий профиль в пошаговом [руководстве](add-autopilot-devices-and-profile.md) и применить его к новым устройствам или заменить существующий профиль для устройства или группы устройств.</span><span class="sxs-lookup"><span data-stu-id="f9639-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="f9639-115">На странице **Подготовка Windows** перейдите на вкладку **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="f9639-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="f9639-116">Установите флажок рядом с именем устройства, а затем на панели Device ( **устройство** ) выберите профиль в раскрывающемся \> списке **назначенный профиль** **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f9639-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="f9639-118">Изменение и удаление профиля</span><span class="sxs-lookup"><span data-stu-id="f9639-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="f9639-p103">После назначения профиля устройству вы можете изменить его, даже если вы уже выдали устройство пользователю. Когда устройство подключается к Интернету, в процессе настройки на него скачивается последняя версия профиля. Когда пользователь сбрасывает устройство до заводских настроек, на него снова скачивается обновленный профиль.</span><span class="sxs-lookup"><span data-stu-id="f9639-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="f9639-122">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="f9639-122">Edit a profile</span></span>

1. <span data-ttu-id="f9639-123">На странице **Подготовка Windows** перейдите на вкладку **Профили**.</span><span class="sxs-lookup"><span data-stu-id="f9639-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="f9639-124">Установите флажок рядом с именем устройства, а затем в панели **профилей** обновите все доступные параметры \> **сохранения**.</span><span class="sxs-lookup"><span data-stu-id="f9639-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="f9639-125">Если сделать это до того, как устройство подключится к Интернету, профиль будет применен в процессе настройки.</span><span class="sxs-lookup"><span data-stu-id="f9639-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="f9639-126">Удаление профиля</span><span class="sxs-lookup"><span data-stu-id="f9639-126">Delete a profile</span></span>

1. <span data-ttu-id="f9639-127">На странице **Подготовка Windows** перейдите на вкладку **Профили**.</span><span class="sxs-lookup"><span data-stu-id="f9639-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="f9639-128">Установите флажок рядом с именем устройства, а затем на панели **профилей** выберите **Удалить** \> **Сохранение**профиля.</span><span class="sxs-lookup"><span data-stu-id="f9639-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="f9639-129">При удалении профиля он перестает действовать для устройства или группы устройств, которым он был назначен.</span><span class="sxs-lookup"><span data-stu-id="f9639-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="f9639-130">Отмена назначения профиля</span><span class="sxs-lookup"><span data-stu-id="f9639-130">Remove a profile</span></span>

1. <span data-ttu-id="f9639-131">На странице **Подготовка Windows** перейдите на вкладку **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="f9639-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="f9639-132">Установите флажок рядом с именем устройства, а затем на панели **устройство** выберите **нет** в раскрывающемся \> списке **назначенный профиль** **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f9639-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
