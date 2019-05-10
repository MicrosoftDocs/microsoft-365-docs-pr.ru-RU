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
description: Сведения о том, как отправлять устройства с помощью автопилота в Microsoft 365 Business. Вы можете назначить профиль устройству или группе устройств.
ms.openlocfilehash: 6492f1469a1ac9ea67750e9ffa071d19c88c743f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660452"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="9efda-104">Создание и изменение устройств AutoPilot</span><span class="sxs-lookup"><span data-stu-id="9efda-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="9efda-105">Отправка списка устройств</span><span class="sxs-lookup"><span data-stu-id="9efda-105">Upload a list of devices</span></span>

<span data-ttu-id="9efda-106">Добавить устройства можно с помощью [пошагового мастера](add-autopilot-devices-and-profile.md), а также на вкладке **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="9efda-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="9efda-107">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="9efda-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="9efda-108">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="9efda-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="9efda-109">новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.</span><span class="sxs-lookup"><span data-stu-id="9efda-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="9efda-110">В центре администрирования Microsoft 365 Business выберите **устройства** \> **автопилот**.</span><span class="sxs-lookup"><span data-stu-id="9efda-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="9efda-111">На странице "автопилотный **проект** " перейдите на \> вкладку **устройства** , чтобы **Добавить устройства**.</span><span class="sxs-lookup"><span data-stu-id="9efda-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="9efda-113">На панели **Add Devices (Добавление устройств** ) перейдите к [списку устройств CSV-файл](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , для \> которого подготовлено **Сохранение** \> , **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9efda-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="9efda-114">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="9efda-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="9efda-115">Назначение профиля устройству или группе устройств</span><span class="sxs-lookup"><span data-stu-id="9efda-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="9efda-116">На странице **Подготовка Windows** перейдите на вкладку **Устройства** и установите флажки рядом с одним или несколькими устройствами.</span><span class="sxs-lookup"><span data-stu-id="9efda-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="9efda-117">На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**.</span><span class="sxs-lookup"><span data-stu-id="9efda-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="9efda-118">Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9efda-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
