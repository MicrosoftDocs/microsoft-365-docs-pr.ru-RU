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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Сведения о том, как отправлять устройства с помощью автопилота в Microsoft 365 Business. Вы можете назначить профиль устройству или группе устройств.
ms.openlocfilehash: dee77a014ef519f3487a082edc3cf81058ec1c00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071647"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="127c4-104">Создание и изменение устройств AutoPilot</span><span class="sxs-lookup"><span data-stu-id="127c4-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="127c4-105">Отправка списка устройств</span><span class="sxs-lookup"><span data-stu-id="127c4-105">Upload a list of devices</span></span>

<span data-ttu-id="127c4-106">Добавить устройства можно с помощью [пошагового мастера](add-autopilot-devices-and-profile.md), а также на вкладке **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="127c4-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="127c4-107">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="127c4-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="127c4-108">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="127c4-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="127c4-109">новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.</span><span class="sxs-lookup"><span data-stu-id="127c4-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="127c4-110">В центре администрирования Microsoft 365 Business выберите **устройства** \> **автопилот**.</span><span class="sxs-lookup"><span data-stu-id="127c4-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="127c4-111">На странице "автопилотный **проект** " перейдите на \> вкладку **устройства** , чтобы **Добавить устройства**.</span><span class="sxs-lookup"><span data-stu-id="127c4-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="127c4-113">На панели **Add Devices (Добавление устройств** ) перейдите к [списку устройств CSV-файл](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , для \> которого подготовлено **Сохранение** \> , **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="127c4-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="127c4-114">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="127c4-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="127c4-115">Назначение профиля устройству или группе устройств</span><span class="sxs-lookup"><span data-stu-id="127c4-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="127c4-116">На странице **Подготовка Windows** перейдите на вкладку **Устройства** и установите флажки рядом с одним или несколькими устройствами.</span><span class="sxs-lookup"><span data-stu-id="127c4-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="127c4-117">На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**.</span><span class="sxs-lookup"><span data-stu-id="127c4-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="127c4-118">Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="127c4-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
