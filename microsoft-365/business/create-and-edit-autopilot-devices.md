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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Сведения о том, как отправлять устройства с помощью автопилота в Microsoft 365 Business. Вы можете назначить профиль устройству или группе устройств.
ms.openlocfilehash: 1dd6b1a574166379e29465bf3699e47e3b155e0b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320265"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="ec04c-104">Создание и изменение устройств AutoPilot</span><span class="sxs-lookup"><span data-stu-id="ec04c-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="ec04c-105">Отправка списка устройств</span><span class="sxs-lookup"><span data-stu-id="ec04c-105">Upload a list of devices</span></span>

<span data-ttu-id="ec04c-106">Вы можете использовать [Пошаговое руководство](add-autopilot-devices-and-profile.md) по отправке устройств, но вы также можете загрузить устройства на вкладке " **устройства** ".</span><span class="sxs-lookup"><span data-stu-id="ec04c-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="ec04c-107">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="ec04c-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="ec04c-108">Windows 10 версии 1703 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ec04c-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="ec04c-109">Новые устройства, которые не прошли предварительный интерфейс Windows</span><span class="sxs-lookup"><span data-stu-id="ec04c-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="ec04c-110">В центре администрирования Microsoft 365 Business выберите **устройства** \> **автопилот**.</span><span class="sxs-lookup"><span data-stu-id="ec04c-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="ec04c-111">На странице " **автопилотный проект** " перейдите на \> вкладку **устройства** , чтобы **Добавить устройства**.</span><span class="sxs-lookup"><span data-stu-id="ec04c-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="ec04c-113">На панели **Add Devices (Добавление устройств** ) перейдите к [CSV-файлу списка устройств](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , подготовленный \> для **сохранения** \> **.**</span><span class="sxs-lookup"><span data-stu-id="ec04c-113">On the **Add devices** panel, browse to a [Device list CSV file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="ec04c-114">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) , чтобы создать CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="ec04c-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="ec04c-115">Назначение профиля устройству или группе устройств</span><span class="sxs-lookup"><span data-stu-id="ec04c-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="ec04c-116">На странице **Подготовка Windows** перейдите на вкладку **устройства** и установите флажок рядом с одним или несколькими устройствами.</span><span class="sxs-lookup"><span data-stu-id="ec04c-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="ec04c-117">На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**.</span><span class="sxs-lookup"><span data-stu-id="ec04c-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="ec04c-118">Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ec04c-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
