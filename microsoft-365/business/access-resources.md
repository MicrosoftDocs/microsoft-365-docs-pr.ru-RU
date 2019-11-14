---
title: Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры из Azure Active Directory, подключенной к устройству Windows 10.
ms.openlocfilehash: fdc1eca6913ba6af4f6b65691fdee2165e7c827e
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323402"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business

Все устройства с Windows 10, которые присоединены к Azure Active Directory, имеют доступ ко всем облачным ресурсам, таким как приложения Office 365, и могут быть защищены корпорацией Майкрософт 365 Business. Вы также можете разрешить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры. Чтобы разрешить доступ, используйте [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) для синхронизации локальной службы Active Directory с Azure Active Directory. 

Чтобы узнать больше, ознакомьтесь со статьей общие сведения об [управлении устройствами в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
Эти действия также описаны в следующих разделах.

## <a name="run-azure-ad-connect"></a>Запуск Azure AD Connect

Выполните следующие действия, чтобы разрешить подключенным устройствам Azure AD в организации получать доступ к локальным ресурсам.
  
1. Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD Connect, как описано в статье [Настройка синхронизации каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. По завершении синхронизации службы каталогов убедитесь, что устройства Windows 10 в вашей организации присоединены к Azure AD. Этот шаг выполняется отдельно для каждого устройства с Windows 10. Дополнительные сведения: [Set Up Windows Devices for Microsoft 365 Business Users](set-up-windows-devices.md) . 
    
3. Когда устройства с Windows 10 будут присоединены к Azure AD, каждый пользователь должен перезагрузить свои устройства и войти с помощью учетных данных Microsoft 365 Business. Теперь все устройства имеют доступ к локальным ресурсам.
    
Для получения доступа к локальным ресурсам для устройств с присоединением Azure AD дополнительные действия не требуются. Эта функция встроена в Windows 10. 
  
Если ваша организация не готова к развертыванию в описанной выше конфигурации устройства с подключением Azure AD, рассмотрите возможность настройки [конфигурации гибридного устройства с присоединенной службой Azure AD](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Рекомендации по присоединению устройств Windows к Azure AD

Если устройство Windows, к которому присоединена служба Azure AD, было ранее присоединено к домену или в Рабочей группе, учитывайте следующие ограничения.
  
- Когда устройство Azure AD присоединяется, оно создает нового пользователя без обращения к существующему профилю. Профили необходимо перенести вручную. Профиль пользователя содержит такие сведения, как "Избранное", "Локальные файлы", "Параметры браузера" и "Параметры меню" Пуск ". Лучший подход — найти стороннее средство для сопоставления существующих файлов и параметров с новым профилем.

- Если устройство использует объекты групповой политики (GPO), некоторые объекты групповой политики не могут иметь сравнимого [поставщика службы конфигурации](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) в Intune. Запустите [средство ммат](https://www.microsoft.com/download/details.aspx?id=45520) , чтобы найти сравниваемые поставщики служб шифрования для существующих объектов групповой политики.

- Пользователи не смогут проходить проверку подлинности в приложениях, зависящих от проверки подлинности Active Directory. Оцените старое приложение и обновите приложение, использующее современные проверки подлинности, если это возможно.

- Обнаружение принтеров Active Directory не работает. Вы можете предоставить прямые пути к принтеру для всех пользователей или использовать [Печать в гибридном облаке](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
