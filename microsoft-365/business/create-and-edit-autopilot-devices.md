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
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="1df62-104">Создание и изменение устройств AutoPilot</span><span class="sxs-lookup"><span data-stu-id="1df62-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="1df62-105">Отправка списка устройств</span><span class="sxs-lookup"><span data-stu-id="1df62-105">Upload a list of devices</span></span>

<span data-ttu-id="1df62-106">Вы можете использовать [пошаговую](add-autopilot-devices-and-profile.md) руководство для отправки устройств, но вы также можете отправить устройства на вкладке **"Устройства".**</span><span class="sxs-lookup"><span data-stu-id="1df62-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="1df62-107">Устройства должны соответствовать этим требованиям:</span><span class="sxs-lookup"><span data-stu-id="1df62-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="1df62-108">Windows 10 версии 1703 или более поздней</span><span class="sxs-lookup"><span data-stu-id="1df62-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="1df62-109">Новые устройства, которые не прошли сквозной опыт работы с Windows</span><span class="sxs-lookup"><span data-stu-id="1df62-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="1df62-110">В Центре администрирования Microsoft 365 выберите **"Устройства** \> **AutoPilot".**</span><span class="sxs-lookup"><span data-stu-id="1df62-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="1df62-111">На странице **AutoPilot** выберите вкладку **"Устройства"** \> **"Добавить устройства".**</span><span class="sxs-lookup"><span data-stu-id="1df62-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="1df62-113">На панели **"Добавление устройств"** перейдите к [CSV-файлу](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) списка устройств, который вы подготовили для \>  \> **сохранения закрытия.**</span><span class="sxs-lookup"><span data-stu-id="1df62-113">On the **Add devices** panel, browse to a [Device list CSV file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="1df62-114">Эти сведения можно получить у поставщика оборудования или с помощью скрипта [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) для создания CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="1df62-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="1df62-115">Назначение профиля устройству или группе устройств</span><span class="sxs-lookup"><span data-stu-id="1df62-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="1df62-116">На странице **"Подготовка Windows"** выберите вкладку **"Устройства"** и выберите этот вариант рядом с одним или более устройствами.</span><span class="sxs-lookup"><span data-stu-id="1df62-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="1df62-117">На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**.</span><span class="sxs-lookup"><span data-stu-id="1df62-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="1df62-118">Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1df62-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
