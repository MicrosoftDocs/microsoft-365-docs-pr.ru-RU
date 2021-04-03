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
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="46183-104">Создание и изменение устройств AutoPilot</span><span class="sxs-lookup"><span data-stu-id="46183-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="46183-105">Отправка списка устройств</span><span class="sxs-lookup"><span data-stu-id="46183-105">Upload a list of devices</span></span>

<span data-ttu-id="46183-106">Вы можете использовать [пошаговую](add-autopilot-devices-and-profile.md) руководство для загрузки устройств, но вы также можете загружать устройства на вкладке **Devices.**</span><span class="sxs-lookup"><span data-stu-id="46183-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="46183-107">Устройства должны соответствовать этим требованиям:</span><span class="sxs-lookup"><span data-stu-id="46183-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="46183-108">Windows 10, версия 1703 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="46183-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="46183-109">Новые устройства, которые не прошли через windows вне окна</span><span class="sxs-lookup"><span data-stu-id="46183-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="46183-110">В центре администрирования Microsoft 365 выберите **Devices** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="46183-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="46183-111">На странице **АвтоПилот** выберите вкладку **Устройства** \> **Добавить устройства.**</span><span class="sxs-lookup"><span data-stu-id="46183-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="46183-113">На панели **Добавить устройства** просмотрите [CSV-файл списка](../admin/misc/device-list.md) устройств, который вы подготовили \> **Сохранить** \> **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="46183-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="46183-114">Эти сведения можно получить у поставщика оборудования или с помощью скрипта [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) для создания CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="46183-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="46183-115">Назначение профиля устройству или группе устройств</span><span class="sxs-lookup"><span data-stu-id="46183-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="46183-116">На странице **Подготовка Windows** выберите вкладку **Устройства** и выберите поле рядом с одним или более устройствами.</span><span class="sxs-lookup"><span data-stu-id="46183-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="46183-117">На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**.</span><span class="sxs-lookup"><span data-stu-id="46183-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="46183-118">Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="46183-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
