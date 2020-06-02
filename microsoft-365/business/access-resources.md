---
title: Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 Business
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
description: Узнайте, как получить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры из Azure Active Directory, подключенной к устройству Windows 10.
ms.openlocfilehash: 9615ecc9469992d3e5a7479f4799c610db11fb41
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471258"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Доступ к локальным ресурсам из устройства, подключенного к Azure AD, в Microsoft 365 бизнес премиум

Эта статья относится к Microsoft 365 Business Premium.

Любое устройство Windows 10, к которому присоединена служба Azure Active Directory, имеет доступ ко всем облачным ресурсам, таким как приложения Microsoft 365, и может быть защищено с помощью Microsoft 365 бизнес премиум. Вы также можете разрешить доступ к локальным ресурсам, таким как бизнес-приложения, общие файловые ресурсы и принтеры. Чтобы разрешить доступ, используйте [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) для синхронизации локальной службы Active Directory с Azure Active Directory. 

Чтобы узнать больше, ознакомьтесь со статьей общие сведения об [управлении устройствами в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
Эти действия также описаны в следующих разделах.

> [!IMPORTANT]
> Эта процедура относится только к OAuth и NTLM. Проверка подлинности Kerberos не поддерживается.
 
## <a name="run-azure-ad-connect"></a>Запуск Azure AD Connect

Выполните следующие действия, чтобы разрешить подключенным устройствам Azure AD в организации получать доступ к локальным ресурсам.
  
1. Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD Connect, как описано в статье [Настройка синхронизации каталогов для Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
    
2. По завершении синхронизации службы каталогов убедитесь, что устройства Windows 10 в вашей организации присоединены к Azure AD. Этот шаг выполняется отдельно для каждого устройства с Windows 10. Для получения дополнительных сведений см. раздел [Настройка устройств Windows для пользователей Microsoft 365 Business Premium](set-up-windows-devices.md) . 
    
3. Когда устройства с Windows 10 будут присоединены к Azure AD, каждый пользователь должен перезагрузить свои устройства и войти с помощью учетных данных Microsoft 365 Business Premium. Теперь все устройства имеют доступ к локальным ресурсам.
    
Для получения доступа к локальным ресурсам для устройств с присоединением Azure AD дополнительные действия не требуются. Эта функция встроена в Windows 10. 

Если вы планируете выполнить вход на устройство ААДЖ, отличное от пароля, например PIN/Bio-Metric, с помощью учетных данных для входа в ВХФБ и затем доступ к локальным ресурсам (Shares, Printers.. и т. д.), выполните следующие действияhttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Если ваша организация не готова к развертыванию в описанной выше конфигурации устройства с подключением Azure AD, рассмотрите возможность настройки [конфигурации гибридного устройства с присоединенной службой Azure AD](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Рекомендации по присоединению устройств Windows к Azure AD

Если устройство Windows, к которому присоединена служба Azure AD, было ранее присоединено к домену или в Рабочей группе, учитывайте следующие ограничения.
  
- Когда устройство Azure AD присоединяется, оно создает нового пользователя без обращения к существующему профилю. Профили необходимо перенести вручную. Профиль пользователя содержит такие сведения, как "Избранное", "Локальные файлы", "Параметры браузера" и "Параметры меню" Пуск ". Лучший подход — найти стороннее средство для сопоставления существующих файлов и параметров с новым профилем.

- Если устройство использует объекты групповой политики (GPO), некоторые объекты групповой политики не могут иметь сравнимого [поставщика службы конфигурации](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) в Intune. Запустите [средство ммат](https://www.microsoft.com/download/details.aspx?id=45520) , чтобы найти сравниваемые поставщики служб шифрования для существующих объектов групповой политики.

- Пользователи не смогут проходить проверку подлинности в приложениях, зависящих от проверки подлинности Active Directory. Оцените старое приложение и обновите приложение, использующее современные проверки подлинности, если это возможно.

- Обнаружение принтеров Active Directory не работает. Вы можете предоставить прямые пути к принтеру для всех пользователей или использовать [Печать в гибридном облаке](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
