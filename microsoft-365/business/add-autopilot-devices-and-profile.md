---
title: Добавление устройств и профиля AutoPilot с помощью пошагового мастера
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Узнайте, как использовать автопилот Windows для настройки новых устройств с Windows 10 для бизнеса.
ms.openlocfilehash: d028ea3e902965d55c445dc3b3a02aa315201b25
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574795"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="f7fa6-103">Добавление устройств и профиля AutoPilot с помощью пошагового мастера</span><span class="sxs-lookup"><span data-stu-id="f7fa6-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="f7fa6-104">Вы можете использовать автопилот Windows для настройки **новых** устройств с Windows 10 для бизнеса, чтобы они были готовы к эффективному использованию, как только вы передаете их сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="f7fa6-105">Требования к устройству</span><span class="sxs-lookup"><span data-stu-id="f7fa6-105">Device requirements</span></span>

<span data-ttu-id="f7fa6-106">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="f7fa6-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="f7fa6-107">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="f7fa6-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="f7fa6-108">новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="f7fa6-109">Создание устройств и профилей с помощью мастера настройки</span><span class="sxs-lookup"><span data-stu-id="f7fa6-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="f7fa6-110">[![Метка, с помощью которой вы узнаете, что центр администрирования изменяется, и вы можете получить дополнительные сведения по адресу aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="f7fa6-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="f7fa6-111">Если вы еще не создали группы устройств и профили, лучший способ приступить к работе  воспользоваться пошаговым мастером. Однако вы также можете [добавлять устройства](create-and-edit-autopilot-devices.md) и [назначать им профили](create-and-edit-autopilot-profiles.md) без его помощи.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="f7fa6-112">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f7fa6-113">В левой панели навигации выберите **устройства** \> **автопилот**.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![В центре администрирования выберите устройства, а затем — автопилот.](media/AutoPilot.png)
  
2. <span data-ttu-id="f7fa6-115">На странице " **Автопилотный проект** " щелкните или нажмите **начать руководство**.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="f7fa6-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span><span class="sxs-lookup"><span data-stu-id="f7fa6-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="f7fa6-119">Столбец A: Device Serial Number (Серийный номер устройства)</span><span class="sxs-lookup"><span data-stu-id="f7fa6-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="f7fa6-120">Столбец B: Windows Product ID (Идентификатор продукта Windows)</span><span class="sxs-lookup"><span data-stu-id="f7fa6-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="f7fa6-121">Столбец C: Hardware Hash (Хэш оборудования)</span><span class="sxs-lookup"><span data-stu-id="f7fa6-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="f7fa6-122">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="f7fa6-p102">Дополнительные сведения см. в статье [CSV-файл со списком устройств](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Вы также можете скачать образец файла на странице **Отправка CSV-файла со списком устройств**.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="f7fa6-p103">На странице **Назначение профиля** можно выбрать существующий профиль или создать новый. Если у вас еще нет профиля, вам будет предложено создать его.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="f7fa6-127">Профиль  это совокупность настроек, которые можно применить к одному устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="f7fa6-p104">Параметры по умолчанию являются обязательными и настраиваются автоматически. К ним относятся следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f7fa6-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="f7fa6-130">Пропуск регистрации Кортаны, OneDrive и OEM.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="f7fa6-131">Создание интерфейса входа с использованием фирменной символики компании.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="f7fa6-132">Устройства автоматически подключаются к учетным записям Azure Active Directory и регистрируются в Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="f7fa6-133">Дополнительные сведения см. в статье</span><span class="sxs-lookup"><span data-stu-id="f7fa6-133">For more information, see</span></span>
    
    <span data-ttu-id="f7fa6-134">[Сведения о параметрах профиля AutoPilot](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f7fa6-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="f7fa6-135">Также доступны параметры **Пропустить параметры конфиденциальности** и **Не разрешать пользователю становиться локальным администратором**. По умолчанию они **отключены**.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="f7fa6-136">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="f7fa6-p105">На странице **Готово** будет указано, что созданный (или выбранный) профиль будет применен к группе устройств, которую вы создали, отправив список устройств. Параметры вступят в силу при следующем входе пользователя на устройство. Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f7fa6-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    