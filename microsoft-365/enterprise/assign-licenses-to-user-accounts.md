---
title: Назначение лицензий Microsoft 365 учетным записям пользователей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: В этой статье описано, как назначать лицензии на Microsoft 365 для учетных записей пользователей по отдельности или в зависимости от принадлежности к группе.
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693003"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Назначение лицензий Microsoft 365 учетным записям пользователей

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Для модели удостоверения, которая используется только в облаке, вы можете назначить лицензии Microsoft 365 для учетных записей пользователей при их создании, в зависимости от того, как они создаются.

Для модели гибридной идентификации при первой синхронизации учетных записей пользователей доменных служб Active Directory (AD DS) они не назначаются автоматически лицензии Microsoft 365. Сначала необходимо настроить для каждой учетной записи пользователя расположение пользователя.

В любом случае необходимо назначить лицензии учетным записям пользователей, чтобы пользователи могли получить доступ к службам Microsoft 365, таким как электронная почта и Microsoft Teams.

Вы можете назначать лицензии учетным записям пользователей по отдельности или автоматически с помощью членства в группе.

Чтобы назначить лицензии Microsoft 365 отдельным учетным записям пользователей, можно использовать:

- [Центр администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell для Microsoft 365](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

Для автоматического назначения лицензий просмотрите раздел [Лицензирование на основе групп в Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Дальнейшие действия

С полным набором учетных записей пользователей, которым были назначены лицензии, вы можете:

- [Реализация безопасности](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Развертывание клиентского программного обеспечения, например Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Настройка управления мобильными устройствами в Microsoft 365](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [Настройка служб и приложений](configure-services-and-applications.md)
