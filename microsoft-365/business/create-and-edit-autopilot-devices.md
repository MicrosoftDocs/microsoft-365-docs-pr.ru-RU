---
title: Создание и изменение устройств AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Узнайте, как отправка устройств с помощью автопилот в Microsoft 365 Business. Можно назначить профиль устройство или группу устройств.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870688"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="a7e39-104">Создание и изменение устройств AutoPilot</span><span class="sxs-lookup"><span data-stu-id="a7e39-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="a7e39-105">Отправка списка устройств</span><span class="sxs-lookup"><span data-stu-id="a7e39-105">Upload a list of devices</span></span>

<span data-ttu-id="a7e39-106">Добавить устройства можно с помощью [пошагового мастера](add-autopilot-devices-and-profile.md), а также на вкладке **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="a7e39-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="a7e39-107">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="a7e39-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="a7e39-108">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="a7e39-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="a7e39-109">новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.</span><span class="sxs-lookup"><span data-stu-id="a7e39-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="a7e39-110">В Центре администрирования Office 365 бизнес в карточке **Действия устройств** выберите пункт **Развертывание Windows с помощью AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="a7e39-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="a7e39-112">На странице **Подготовка Windows** откройте вкладку **устройств** \> **Добавить устройств**.</span><span class="sxs-lookup"><span data-stu-id="a7e39-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="a7e39-114">На панели **устройств добавить** Обзор, чтобы [список устройств CSV-файла](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , в котором вы подготовили \> **Сохранить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a7e39-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="a7e39-115">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="a7e39-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="a7e39-116">Назначение профиля устройству или группе устройств</span><span class="sxs-lookup"><span data-stu-id="a7e39-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="a7e39-117">На странице **Подготовка Windows** перейдите на вкладку **Устройства** и установите флажки рядом с одним или несколькими устройствами.</span><span class="sxs-lookup"><span data-stu-id="a7e39-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="a7e39-118">На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**.</span><span class="sxs-lookup"><span data-stu-id="a7e39-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="a7e39-119">Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a7e39-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
