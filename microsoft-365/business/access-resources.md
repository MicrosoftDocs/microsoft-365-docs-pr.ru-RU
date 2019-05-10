---
title: Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры из Azure Active Directory, подключенной к устройству Windows 10.
ms.openlocfilehash: 2be8eb16b9d17547d3bc4c3e4fe499b4c14117a4
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660276"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business

Все устройства с Windows 10, которые присоединены к Azure Active Directory, будут иметь доступ ко всем облачным ресурсам, таким как приложения Office 365, и могут быть защищены корпорацией Майкрософт 365 Business. Чтобы разрешить доступ к локальным ресурсам, таким как бизнес-приложения, общие папки и принтеры, необходимо синхронизировать локальную службу Active Directory с Azure Active Directory с помощью [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Чтобы узнать больше, ознакомьтесь со статьей [Введение в Управление устройствами в Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) . 
  
## <a name="run-azure-ad-connect"></a>Запуск Azure AD Connect

Выполните следующие действия, чтобы разрешить подключенным устройствам Azure AD в организации получать доступ к локальным ресурсам.
  
1. Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD Connect, как описано в статье [Настройка синхронизации каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. После завершения синхронизации службы каталогов убедитесь, что устройства Windows 10 в вашей организации присоединены к Azure AD. Этот шаг выполняется отдельно для каждого устройства с Windows 10. Дополнительные сведения: [Set Up Windows Devices for Microsoft 365 Business Users](set-up-windows-devices.md) . 
    
3. Когда устройства Windows 10 будут присоединены к Azure AD, каждый пользователь должен перезагрузить свои устройства и войти с помощью учетных данных Microsoft 365 Business. Теперь все устройства будут иметь доступ к локальным ресурсам.
    
Для получения доступа к локальным ресурсам для устройств с присоединением Azure AD дополнительные действия не требуются. Это встроенные функции, доступные в Windows 10. 
  
Если ваша организация не готова к развертыванию в описанной выше конфигурации устройства с присоединением Azure AD, рассмотрите возможность настройки [конфигурации гибридного устройства с присоединенной службой Azure AD](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Рекомендации по присоединению устройств Windows к Azure AD

Если вы используете Azure AD для подключения к устройству Windows, которое ранее присоединяется к домену или в Рабочей группе, необходимо учитывать следующие ограничения:
  
- Когда устройство Azure AD присоединяется, оно создает нового пользователя без обращения к существующему профилю. Чтобы устранить эту проблему, необходимо вручную перенести профили. Профиль пользователя содержит такие сведения, как избранное, локальные файлы, параметры браузера, параметры меню "Пуск" и т. д. Лучший подход — найти стороннее средство для сопоставления существующих файлов и параметров с новым профилем.

- Если устройство использует объекты групповой политики (GPO), некоторые объекты групповой политики не могут иметь сравнимого [поставщика службы конфигурации](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) в Intune. Запустите [средство ммат](https://www.microsoft.com/download/details.aspx?id=45520) , чтобы найти сравниваемые поставщики служб шифрования для существующих объектов групповой политики.

- Пользователи не смогут проходить проверку подлинности в приложениях, зависящих от проверки подлинности Active Directory. Для этого оцените использование устаревшего приложения и при возможности обновите приложение, использующее современные проверки подлинности.

- Обнаружение принтеров Active Directory не будет работать. Чтобы устранить эту проблему, предоставьте прямые пути к принтерам для всех пользователей или используйте [Печать](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)в гибридном облаке.
