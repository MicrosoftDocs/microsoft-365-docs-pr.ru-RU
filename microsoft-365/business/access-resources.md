---
title: Доступ к локальным ресурсам с Azure присоединился к AD устройства в Microsoft 365 Business
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
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальным ресурсам, как приложения бизнес-систем, общих файлов и принтеры с Azure Active Directory в состав Windows 10 устройства.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870466"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Доступ к локальным ресурсам с Azure присоединился к AD устройства в Microsoft 365 Business

Все устройства Windows 10 Azure Active Directory в состав будут иметь доступ ко всем ресурсам, на основе облака, такие как приложения Office 365 и могут быть защищены Microsoft 365 для бизнеса. Разрешения на доступ к локальным ресурсам как строки из БИЗНЕС-приложений, общих файлов и принтеров, при синхронизации Active Directory локальной с Azure Active Directory с помощью [Azure AD подключение](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). В разделе [Общие сведения об управлении устройства в Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) для получения дополнительных сведений. 
  
## <a name="run-azure-ad-connect"></a>Подключение выполнения Azure AD

Выполните следующие действия для включения в состав Azure AD устройствах вашей организации для доступа к локальным ресурсам.
  
1. Чтобы синхронизировать пользователей, групп и контактов из локального Active Directory в Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD подключиться, как описано в [Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. После завершения синхронизации службы каталогов, убедитесь в том, что устройствах вашей организации Windows 10 Azure AD в состав. Этот шаг выполняется по отдельности на каждом устройстве Windows 10. [Устройства Windows для пользователей Microsoft 365 Business](set-up-windows-devices.md) для получения дополнительных сведений см. 
    
3. Имеющееся оборудование Windows 10 Azure AD в состав, каждому пользователю необходимо перезагрузить компьютер, их устройств и входа в систему с помощью их учетных данных в Microsoft 365 Business. Теперь все устройства будут иметь доступ к локальным ресурсам также.
    
Не дополнительные действия, необходимые для получения доступа к локальным, ресурсы, необходимые для Azure AD в состав устройств. Это встроенные функциональные возможности, доступные в Windows 10. 
  
Если ваша организация не готова для развертывания в Azure AD присоединился к конфигурации устройства описанных выше, рассмотрите возможность настройки [конфигурации устройства Соединяемая гибридного Azure AD](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Вопросы при присоединении устройство Windows Azure AD

При наличии Azure AD присоединения устройства Windows, которое ранее было присоединенный к домену или в рабочей группе, необходимо учитывать следующие ограничения:
  
- При присоединении устройства Azure AD, он создает новый пользователь без ссылки на существующий профиль. Чтобы устранить эту проблему, необходимо вручную перенести профили. Профиль пользователя содержит сведения, например, "Избранное", локальных файлов, параметров браузера, параметры главного меню, и т.д. — Это лучший подход для поиска средства сторонних производителей для сопоставления существующих файлов и параметров в новый профиль
    
- Если устройство использует объекты групповой политики (GPO), некоторые объекты групповой политики может отсутствовать сравнимые [Конфигурации поставщика услуг](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) в Intune. Запустите [средство MMAT](https://www.microsoft.com/download/details.aspx?id=45520) , чтобы найти соответствующее CSP для существующих объектов групповой политики. 
    
- Пользователи не смогут проходить проверку подлинности в приложениях, зависящих от проверки подлинности Active Directory. Для работы с оценить с помощью прежних версий приложения и рассмотрите возможность обновления приложения, использующего проверкой подлинности на основе современных, если это возможно.
    
- Обнаружение принтера Active Directory не будут работать. Чтобы устранить эту проблему, обеспечивают прямое принтера пути для всех пользователей или использовать [Print облачных гибридного](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
    

