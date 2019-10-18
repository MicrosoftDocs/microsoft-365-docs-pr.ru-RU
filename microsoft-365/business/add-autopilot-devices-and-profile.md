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
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Добавление устройств и профиля AutoPilot с помощью пошагового мастера

Вы можете использовать автопилот Windows для настройки **новых** устройств с Windows 10 для бизнеса, чтобы они были готовы к эффективному использованию, как только вы передаете их сотрудникам.
  
## <a name="device-requirements"></a>Требования к устройству

Устройства должны отвечать следующим требованиям:
  
- Windows 10 версии 1703 или более поздней;
    
- новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Создание устройств и профилей с помощью мастера настройки

[![Метка, с помощью которой вы узнаете, что центр администрирования изменяется, и вы можете получить дополнительные сведения по адресу aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Если вы еще не создали группы устройств и профили, лучший способ приступить к работе  воспользоваться пошаговым мастером. Однако вы также можете [добавлять устройства](create-and-edit-autopilot-devices.md) и [назначать им профили](create-and-edit-autopilot-profiles.md) без его помощи. 
  
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. В левой панели навигации выберите **устройства** \> **автопилот**.

    ![В центре администрирования выберите устройства, а затем — автопилот.](media/AutoPilot.png)
  
2. На странице " **Автопилотный проект** " щелкните или нажмите **начать руководство**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:
    
  - Столбец A: Device Serial Number (Серийный номер устройства)
    
  - Столбец B: Windows Product ID (Идентификатор продукта Windows)
    
  - Столбец C: Hardware Hash (Хэш оборудования)
    
    Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл. 
    
    Дополнительные сведения см. в статье [CSV-файл со списком устройств](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Вы также можете скачать образец файла на странице **Отправка CSV-файла со списком устройств**. 
    
4. На странице **Назначение профиля** можно выбрать существующий профиль или создать новый. Если у вас еще нет профиля, вам будет предложено создать его. 
    
    Профиль  это совокупность настроек, которые можно применить к одному устройству или группе устройств.
    
    Параметры по умолчанию являются обязательными и настраиваются автоматически. К ним относятся следующие параметры:
    
  - Пропуск регистрации Кортаны, OneDrive и OEM.
    
  - Создание интерфейса входа с использованием фирменной символики компании.
    
  - Устройства автоматически подключаются к учетным записям Azure Active Directory и регистрируются в Office 365 бизнес.
    
    Дополнительные сведения см. в статье
    
    [Сведения о параметрах профиля AutoPilot](autopilot-profile-settings.md) 
    
5. Также доступны параметры **Пропустить параметры конфиденциальности** и **Не разрешать пользователю становиться локальным администратором**. По умолчанию они **отключены**. 
    
    Нажмите кнопку **Далее**.
    
6. На странице **Готово** будет указано, что созданный (или выбранный) профиль будет применен к группе устройств, которую вы создали, отправив список устройств. Параметры вступят в силу при следующем входе пользователя на устройство. Нажмите кнопку **Закрыть**.
    