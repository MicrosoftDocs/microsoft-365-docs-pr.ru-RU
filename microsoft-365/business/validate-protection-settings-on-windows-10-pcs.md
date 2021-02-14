---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
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
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Проверьте параметры защиты приложений Microsoft 365 бизнес премиум на устройствах с Windows 10 и убедитесь, что пользователи не могут копировать данные компании в личные файлы или неуправимые приложения.
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403397"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Проверка параметров защиты приложений на компьютерах с Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на корпоративных устройствах

После того [как вы настроили](protection-settings-for-windows-10-devices.md)политики защиты приложений, может потребоваться до нескольких часов, чтобы политика вступила в силу на устройствах пользователей. Если вы  включили параметр "Запретить пользователям копировать данные компании в личные файлы" и заставить их сохранять файлы в **OneDrive** для бизнеса на устройствах, владельцем которых является компания, вы можете проверить это на устройстве пользователя после подключения к Azure AD и входящего подключения. 
  
 **Проверка параметров подключения**
  
1. После входа с помощью учетных данных Microsoft 365 бизнес премиум и подключения к Azure AD, как описано в описании настройки устройств с Windows для пользователей [Microsoft 365 бизнес премиум,](set-up-windows-devices.md)перейдите к учетным записям Windows **Settings** Access на работе или в учебном зачете. \>  \>  Выберите **"Подключено к \<tenant name\> Azure AD"** и выберите **"Сведения".**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. На странице **"Управление по** страницам" можно увидеть сведения о подсети, включаемую адрес сервера управления, как показано на \<tenant name\> следующем рисунке.   
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Убедитесь, что невозможно в paste company data in a non-managed app**
  
1. Откройте Outlook 2016, установленный с помощью Microsoft 365 бизнес премиум.
    
2. Откройте письмо и скопируйте его фрагмент.
    
    Откройте Блокнот и попытайтесь вставить в него содержимое.
    
    Вы получите сообщение об ошибке, в том, что приложение не может получить доступ к содержимому.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Однако это же содержимое можно вставить в Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на личных устройствах

 **Проверка параметров подключения**
  
1. На личном устройстве с Windows 10, на котором вы вошли как локальный  пользователь, перейдите в "Параметры **Windows"** и щелкните или коснитесь "Учетные записи" для работы или учебного \> **заведения.**
    
2. На странице **Доступ к учетной записи места работы или учебного заведения** выберите команду **Подключить**.
    
3. Введите свои учетные данные Microsoft  365 бизнес премиум в диалоговое окно "Настройка учетной записи для работы или учебного \> **заведения".**
    
4. На странице **Доступ к учетной записи места работы или учебного заведения** выберите элемент **Рабочая или учебная учетная запись** и нажмите кнопку **Сведения**.
    
    ![Щелкните или коснитесь "Сведения" в диалоговом оке "Сведения о работе или учебном зачете".](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. На странице **"Доступ** к работе или  учебному заму" можно увидеть сведения о подсети, которые включают адрес сервера управления, как на следующем рисунке, и содержат слова *wip* и  *mam.* 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Убедитесь, что невозможно в paste company data in a non-managed app**
  
1. Откройте Outlook 2016 и при необходимости добавьте свою учетную запись Microsoft 365 бизнес премиум и войте в нее учетные данные Microsoft 365 бизнес премиум.
    
2. Откройте письмо и скопируйте его фрагмент.
    
    Откройте Блокнот и попытайтесь вставить в него содержимое.
    
    Вы получите сообщение об ошибке, в том, что приложение не может получить доступ к содержимому.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Однако это же содержимое можно вставить в Word 2016.
    

