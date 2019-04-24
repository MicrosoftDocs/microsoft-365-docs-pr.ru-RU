---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как проверить параметры защиты Microsoft 365 бизнес-приложений на устройствах с Windows 10.
ms.openlocfilehash: 4f1f0993dff0ef8d3f6858a3749e063c7b5579c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280018"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Проверка параметров защиты приложений на компьютерах с Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на корпоративных устройствах

Политики защиты приложений для пользовательских устройств могут вступить в силу через несколько часов после их [настройки](protection-settings-for-windows-10-devices.md). Если для корпоративных устройств установить значение **Вкл.** для параметра **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**, его действие можно будет проверить на устройстве пользователя после подключения к Azure AD и входа. 
  
 **Проверка параметров подключения**
  
1. После входа с помощью учетных данных Office 365 бизнес и подключения к Azure AD, как описано в статье [Настройка устройств с Windows для пользователей Microsoft 365 бизнес](set-up-windows-devices.md), откройте **Параметры Windows** \> **Учетные записи** \> **Доступ к учетной записи места работы или учебного заведения**. Выберите пункт **Подключено к Azure AD \<имя клиента\>**, а затем нажмите кнопку **Сведения**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. На странице **Управляется** \<имя клиента\> просмотрите раздел **Сведения о подключении**, который содержит **Адрес сервера управления**, как показано на приведенном ниже рисунке. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Проверка отсутствия возможности вставки данных компании в неуправляемое приложение**
  
1. Откройте приложение Outlook 2016, установленное с помощью Office 365 бизнес.
    
2. Откройте письмо и скопируйте его фрагмент.
    
    Откройте Блокнот и попытайтесь вставить в него содержимое.
    
    Появляется предупреждение о том, что приложению не удается получить доступ к содержимому.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Однако это же содержимое можно вставить в Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Проверка отсутствия у пользователей возможности копирования данных компании в личные файлы на личных устройствах

 **Проверка параметров подключения**
  
1. On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.
    
2. На странице **Доступ к учетной записи места работы или учебного заведения** выберите команду **Подключить**.
    
3. Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.
    
4. На странице **Доступ к учетной записи места работы или учебного заведения** выберите элемент **Рабочая или учебная учетная запись** и нажмите кнопку **Сведения**.
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. На странице **Доступ к учетной записи места работы или учебного заведения** просмотрите раздел **Сведения о подключении**, который содержит **Адрес сервера управления** со словами  *wip*  и  *mam*  , как показано на приведенном ниже рисунке. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Проверка отсутствия возможности вставки данных компании в неуправляемое приложение**
  
1. Откройте Outlook 2016, при необходимости добавьте свою учетную запись Office 365 бизнес и выполните вход с помощью учетных данных Office 365 бизнес.
    
2. Откройте письмо и скопируйте его фрагмент.
    
    Откройте Блокнот и попытайтесь вставить в него содержимое.
    
    Появляется предупреждение о том, что приложению не удается получить доступ к содержимому.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Однако это же содержимое можно вставить в Word 2016.
    

