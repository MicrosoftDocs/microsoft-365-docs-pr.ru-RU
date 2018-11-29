---
title: Добавление устройств и профиля AutoPilot с помощью пошагового мастера
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Сведения об использовании Windows автопилот для настройки нового устройства Windows 10 для бизнеса.
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870437"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="e0675-103">Добавление устройств и профиля AutoPilot с помощью пошагового мастера</span><span class="sxs-lookup"><span data-stu-id="e0675-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="e0675-104">Решение Windows AutoPilot позволяет настраивать новые устройства с Windows 10, чтобы они были готовы к работе сразу после выдачи сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="e0675-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="e0675-105">Требования к устройствам</span><span class="sxs-lookup"><span data-stu-id="e0675-105">Device requirements</span></span>

<span data-ttu-id="e0675-106">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="e0675-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="e0675-107">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="e0675-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="e0675-108">новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.</span><span class="sxs-lookup"><span data-stu-id="e0675-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="e0675-109">Создание устройств и профилей с помощью мастера настройки</span><span class="sxs-lookup"><span data-stu-id="e0675-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="e0675-110">Если вы еще не создали группы устройств и профили, лучший способ приступить к работе  воспользоваться пошаговым мастером. Однако вы также можете [добавлять устройства](create-and-edit-autopilot-devices.md) и [назначать им профили](create-and-edit-autopilot-profiles.md) без его помощи.</span><span class="sxs-lookup"><span data-stu-id="e0675-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="e0675-111">В Центре администрирования Office 365 бизнес в карточке **Действия устройств** выберите пункт **Развертывание Windows с помощью AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="e0675-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="e0675-113">На странице **Подготовка Windows** нажмите кнопку **Запустить мастер**.</span><span class="sxs-lookup"><span data-stu-id="e0675-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="e0675-p101">На странице **загрузки CSV-файл с список устройств,** перейдите к расположения, где у вас есть подготовленной. CSV-файл, затем **Откройте** \> **Далее**. Файл должен иметь три верхних колонтитула:</span><span class="sxs-lookup"><span data-stu-id="e0675-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="e0675-117">Столбец A: Device Serial Number (Серийный номер устройства)</span><span class="sxs-lookup"><span data-stu-id="e0675-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="e0675-118">Столбец B: Windows Product ID (Идентификатор продукта Windows)</span><span class="sxs-lookup"><span data-stu-id="e0675-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="e0675-119">Столбец C: Hardware Hash (Хэш оборудования)</span><span class="sxs-lookup"><span data-stu-id="e0675-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="e0675-120">Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="e0675-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="e0675-p102">Дополнительные сведения см. в статье [CSV-файл со списком устройств](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Вы также можете скачать образец файла на странице **Отправка CSV-файла со списком устройств**.</span><span class="sxs-lookup"><span data-stu-id="e0675-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="e0675-p103">На странице **Назначение профиля** можно выбрать существующий профиль или создать новый. Если у вас еще нет профиля, вам будет предложено создать его.</span><span class="sxs-lookup"><span data-stu-id="e0675-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="e0675-125">Профиль  это совокупность настроек, которые можно применить к одному устройству или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="e0675-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="e0675-p104">Параметры по умолчанию являются обязательными и настраиваются автоматически. К ним относятся следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e0675-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="e0675-128">Пропуск регистрации Кортаны, OneDrive и OEM.</span><span class="sxs-lookup"><span data-stu-id="e0675-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="e0675-129">Создание интерфейса входа с использованием фирменной символики компании.</span><span class="sxs-lookup"><span data-stu-id="e0675-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="e0675-130">Устройства автоматически подключаются к учетным записям Azure Active Directory и регистрируются в Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="e0675-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="e0675-131">Дополнительные сведения см. в статье</span><span class="sxs-lookup"><span data-stu-id="e0675-131">For more information, see</span></span>
    
    <span data-ttu-id="e0675-132">[Сведения о параметрах профиля AutoPilot](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e0675-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="e0675-133">Также доступны параметры **Пропустить параметры конфиденциальности** и **Не разрешать пользователю становиться локальным администратором**. По умолчанию они **отключены**.</span><span class="sxs-lookup"><span data-stu-id="e0675-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="e0675-134">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e0675-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="e0675-p105">На странице **Готово** будет указано, что созданный (или выбранный) профиль будет применен к группе устройств, которую вы создали, отправив список устройств. Параметры вступят в силу при следующем входе пользователя на устройство. Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e0675-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    