---
title: Доступ к локальному ресурсу с устройства, присоединенного к Azure AD, в Microsoft 365 бизнес
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальному ресурсу, например к бизнес-приложениям, файловой папке и принтерам с устройства с Windows 10, присоединенного к Azure Active Directory.
ms.openlocfilehash: 22edf0c23d6318e1f70bcb21b2cd697ea0a75da4
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688240"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Доступ к локальному ресурсу с устройства, присоединенного к Azure AD, в Microsoft 365 бизнес премиум

Эта статья относится к Microsoft 365 бизнес премиум.

Любое устройство с Windows 10, присоединенное к Azure Active Directory, имеет доступ ко всем облачным ресурсам, таким как приложения Microsoft 365, и может быть защищено с помощью Microsoft 365 бизнес премиум. Вы также можете разрешить доступ к локальному ресурсу, например бизнес-приложениям, файловой папке и принтерам. Чтобы разрешить доступ, используйте [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) для синхронизации локальной службы Active Directory с Azure Active Directory. 

Дополнительные узнать см. [в введении в управление устройствами в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)
Эти действия также подводятся в следующих разделах.
 
## <a name="run-azure-ad-connect"></a>Запуск Azure AD Connect

Выполните следующие действия, чтобы позволить устройствам, присоединенным к Azure AD, получать доступ к локальному ресурсу.
  
1. Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory в Azure Active Directory, запустите мастер синхронизации службы каталогов и Azure AD Connect, как описано в описании в описании "Настройка синхронизации службы каталогов для [Office 365".](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
    
2. После завершения синхронизации службы каталогов убедитесь, что устройства с Windows 10 вашей организации присоединились к Azure AD. Это делается отдельно на каждом устройстве с Windows 10. Дополнительные сведения см. в подсети "Настройка устройств с Windows для [пользователей Microsoft 365 бизнес премиум".](set-up-windows-devices.md) 
    
3. После присоединив устройства с Windows 10 к Azure AD, каждый пользователь должен перезагрудить свои устройства и войти в учетные данные Microsoft 365 бизнес премиум. Все устройства теперь также имеют доступ к локальному ресурсу.
    
Для получения доступа к локальному ресурсу для устройств, присоединенных к Azure AD, не требуется никаких дополнительных действий. Эта функция встроена в Windows 10. 

Если у вас есть планы входа на устройство AADJ, которое не является паролем, например PIN-код или метрика bio-metric, через учетные данные WHFB, а затем доступ к локальному ресурсу (shares,printers.). и т. д.), следуйте https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Если ваша организация не готова к развертыванию в описанной выше конфигурации устройства, которая присоединилась к Azure AD, рассмотрите возможность настройки гибридной конфигурации устройств, которые присоединились к [Azure AD.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Вопросы присоединить устройства с Windows к Azure AD

Если устройство с Windows, которое вы присоединили к Azure-AD, ранее было в домене или в группе, рассмотрите следующие ограничения:
  
- Когда устройство Присоединяется к Azure AD, оно создает нового пользователя, не ссылаясь на существующий профиль. Профили необходимо перенести вручную. Профиль пользователя содержит такие сведения, как избранное, локальные файлы, параметры браузера и параметры меню "Пуск". Лучший подход — найти стороне средство для связи существующих файлов и параметров с новым профилем.

- Если устройство использует объекты групповой политики (GPO), некоторые [](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) объекты групповой политики могут не иметь сравнимого поставщика служб конфигурации (CSP) в Intune. Запустите [средство MMAT, чтобы](https://www.microsoft.com/download/details.aspx?id=45520) найти сравнимых CSP для существующих GGPOs.

- Пользователи не смогут проверить подлинность в приложениях, которые зависят от проверки подлинности Active Directory. Оцените устаревшее приложение и по возможности рассмотрите возможность обновления до приложения, которое использует современную auth.

- Обнаружение принтера Active Directory не будет работать. Вы можете предоставить прямой путь принтера для всех пользователей или использовать [универсальную печать.](https://aka.ms/UPDocs)
