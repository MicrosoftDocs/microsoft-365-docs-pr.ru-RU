---
title: Добавление устройств и профиля AutoPilot с помощью пошагового мастера
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Узнайте, как с помощью Windows AutoPilot настроить новые устройства с Windows 10 для своей компании, чтобы они были готовы к использованию для сотрудников.
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099757"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Добавление устройств и профиля AutoPilot с помощью пошагового мастера

Вы можете использовать Windows AutoPilot, чтобы настроить новые устройства **с** Windows 10 для своей компании, чтобы они были готовы к использованию при их отдаке сотрудникам.
  
## <a name="device-requirements"></a>Требования к устройству

Устройства должны соответствовать этим требованиям:
  
- Windows 10 версии 1703 или более поздней
    
- Новые устройства, которые не прошли сквозной опыт работы с Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Создание устройств и профилей с помощью мастера настройки

[![Надпись, оповещающая об изменении Центра администрирования. Дополнительные сведения см. на сайте aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Если вы еще не создали группы устройств или профили, лучший способ приступить к работе с помощью пошагового руководства. Вы также [можете добавлять устройства](create-and-edit-autopilot-devices.md) и назначать им [профили](create-and-edit-autopilot-profiles.md) без использования руководства. 
  
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. В левой области навигации выберите **"Устройства** \> **AutoPilot".**

    ![В Центре администрирования выберите устройства, а затем AutoPilot.](../media/AutoPilot.png)
  
2. На странице **AutoPilot** щелкните или коснитесь руководства **"Начните".**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. На странице **"Отправка CSV-файла** со списком устройств" перейдите к расположению, в котором вы подготовили файл. CSV-файл, а затем **откройте** \> **следующий файл.** Файл должен иметь три загона:
    
    - Столбец A: Device Serial Number (Серийный номер устройства)
    
    - Столбец B: Windows Product ID (Идентификатор продукта Windows)
    
    - Столбец C: Hardware Hash (Хэш оборудования)
    
    Эти сведения можно получить у поставщика оборудования или с помощью скрипта [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) для создания CSV-файла. 
    
    Дополнительные сведения см. в статье [CSV-файл со списком устройств](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). Вы также можете скачать образец файла на странице **Отправка CSV-файла со списком устройств**. 
    
> [!NOTE]
> Этот сценарий использует WMI для получения свойств, необходимых клиенту для регистрации устройства в Windows Autopilot. Обратите внимание, что в итоговом CSV-файле обычно не собираются значения продукта Windows (PKID), так как это не требуется для регистрации устройства, а для PKID значение NULL в выходном CSV-файле полностью нормально. Будут заполнены только серийный номер и аппаратный hash.
    
4. На странице **"Назначение профиля"** можно выбрать существующий профиль или создать новый. Если у вас его еще нет, вам будет предложено создать его. 
    
    Профиль  это совокупность настроек, которые можно применить к одному устройству или группе устройств.
    
    Функции по умолчанию являются обязательной и устанавливаются автоматически. К ним относятся следующие параметры:
    
    - Пропустите регистрацию Кортаны, OneDrive и OEM.
    
    - Создание интерфейса входа с использованием фирменной символики компании.
    
    - Подключите устройства к учетным записям Azure Active Directory и автоматически зарегистрите их для управления Microsoft 365 бизнес премиум.
    
    Дополнительные сведения [см. в сведениях о параметрах профиля AutoPilot.](autopilot-profile-settings.md) 
    
5. Также доступны параметры **Пропустить параметры конфиденциальности** и **Не разрешать пользователю становиться локальным администратором**. По умолчанию они **отключены**. 
    
    Нажмите кнопку **Далее**.
    
6. **Это означает,** что созданный (или выбранный) профиль будет применен к группе устройств, созданной путем отправки списка устройств. Параметры будут действовать при следующем входе пользователей устройства. Нажмите кнопку **Закрыть**.
    
