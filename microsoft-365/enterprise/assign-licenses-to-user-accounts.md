---
title: Назначение лицензий Microsoft 365 учетным записям пользователей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326511"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Назначение лицензий Microsoft 365 учетным записям пользователей

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Для модели удостоверения, которая используется только в облаке, вы можете назначить лицензии Microsoft 365 для учетных записей пользователей при их создании, в зависимости от того, как они создаются.

Для модели гибридной идентификации, когда учетные записи пользователей доменных служб Active Directory (AD DS) синхронизируются в первый раз, они не назначаются автоматически как расположение или лицензия Microsoft 365. **Для каждой учетной записи пользователя необходимо указать расположение пользователя до или вместе с назначением лицензии.**

В любом случае необходимо назначить лицензии учетным записям пользователей, чтобы пользователи могли получить доступ к службам Microsoft 365, таким как электронная почта и Microsoft Teams.

Вы можете назначать лицензии учетным записям пользователей по отдельности или автоматически с помощью членства в группе.

Чтобы назначить лицензии Microsoft 365 отдельным учетным записям пользователей, можно использовать:

- [Центр администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Центр администрирования Azure AD

## <a name="group-based-licensing"></a>Лицензирование на основе групп

Вы можете настроить группы безопасности в Azure AD, чтобы автоматически назначать лицензии из набора подписок всем участникам группы. Это называется *лицензированием на основе групп*. Когда учетная запись добавляется в группу или удаляется из нее, лицензии для подписок группы автоматически назначаются этой учетной записи или отменяются для нее.

Убедитесь, что у вас есть достаточно лицензий для всех участников группы. Если лицензии закончатся, они не будут назначаться новым пользователям, пока эти лицензии не станут доступны.

>[!Note]
>Лицензирование на основе групп не следует настраивать для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.
>

Дополнительные сведения см. [в разделе Лицензирование на основе групп в Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Дальнейшие действия

С соответствующим набором учетных записей пользователей, которым назначены лицензии, вы можете:

- [Реализация безопасности](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Развертывание клиентского программного обеспечения, например Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Настройка управления устройствами](device-management-roadmap-microsoft-365.md)
- [Настройка служб и приложений](configure-services-and-applications.md)
