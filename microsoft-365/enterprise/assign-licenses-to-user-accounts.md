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
description: Описывает, как назначать лицензии Microsoft 365 учетным записям пользователей по отдельности или на основе членства в группе.
ms.openlocfilehash: 6bba3cd767787f450840c5cae6c30f2be21bed1b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905444"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Назначение лицензий Microsoft 365 учетным записям пользователей

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Для облачной модели удостоверений можно назначить лицензии Microsoft 365 учетным записям пользователей по мере их создания в зависимости от их создания.

Для гибридной модели удостоверений, когда учетные записи пользователей Active Directory Domain Services (AD DS) синхронизируются впервые, им автоматически не назначено расположение или лицензия Microsoft 365. **Необходимо настроить каждую учетную запись пользователя с расположением пользователя до или вместе с назначением лицензии.**

В любом случае необходимо назначить лицензию учетным записям пользователей, чтобы пользователи могли получать доступ к службам Microsoft 365, таким как электронная почта и Microsoft Teams.

Лицензии можно назначать учетным записям пользователей как индивидуально, так и автоматически через членство в группе.

Чтобы назначить лицензии Microsoft 365 отдельным учетным записям пользователей, можно использовать:

- [Центр администрирования Microsoft 365](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Центр администрирования Azure AD

## <a name="group-based-licensing"></a>Лицензирование на основе групп

Можно настроить группы безопасности в Azure AD, чтобы автоматически назначать лицензии из набора подписок всем участникам группы. Это называется *лицензированием на основе групп*. Когда учетная запись добавляется в группу или удаляется из нее, лицензии для подписок группы автоматически назначаются этой учетной записи или отменяются для нее.

Убедитесь, что у вас есть достаточно лицензий для всех участников группы. Если лицензии закончатся, они не будут назначаться новым пользователям, пока эти лицензии не станут доступны.

>[!Note]
>Лицензирование на основе групп не следует настраивать для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.
>

Дополнительные новости см. в [групповых лицензиях в Azure AD.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

## <a name="next-steps"></a>Дальнейшие действия

С соответствующим набором учетных записей пользователей, которые были назначены лицензии, теперь вы готовы к:

- [Реализация безопасности](../security/office-365-security/security-roadmap.md)
- [Развертывание клиентского программного обеспечения, например Приложений Microsoft 365](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Настройка управления устройствами](device-management-roadmap-microsoft-365.md)
- [Настройка служб и приложений](configure-services-and-applications.md)