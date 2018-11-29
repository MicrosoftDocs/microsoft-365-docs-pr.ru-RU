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
# <a name="create-and-edit-autopilot-devices"></a>Создание и изменение устройств AutoPilot

## <a name="upload-a-list-of-devices"></a>Отправка списка устройств

Добавить устройства можно с помощью [пошагового мастера](add-autopilot-devices-and-profile.md), а также на вкладке **Устройства**. 
  
Устройства должны отвечать следующим требованиям:
  
- Windows 10 версии 1703 или более поздней;
    
- новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.
    
1. В Центре администрирования Office 365 бизнес в карточке **Действия устройств** выберите пункт **Развертывание Windows с помощью AutoPilot**. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. На странице **Подготовка Windows** откройте вкладку **устройств** \> **Добавить устройств**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. На панели **устройств добавить** Обзор, чтобы [список устройств CSV-файла](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , в котором вы подготовили \> **Сохранить** \> **Закрыть**.
    
    Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell с именем Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), который создаст CSV-файл. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Назначение профиля устройству или группе устройств

1. На странице **Подготовка Windows** перейдите на вкладку **Устройства** и установите флажки рядом с одним или несколькими устройствами. 
    
2. На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**. 
    
    Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md). 
    
