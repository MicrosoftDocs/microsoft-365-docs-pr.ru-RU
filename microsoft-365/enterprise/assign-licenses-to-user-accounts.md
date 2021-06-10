---
title: Назначение Microsoft 365 лицензий учетным записям пользователей
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
description: Описывает, как назначать Microsoft 365 учетным записям пользователей по отдельности или на основе членства в группе.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051536"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Назначение Microsoft 365 лицензий учетным записям пользователей

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Для облачной модели удостоверений можно назначать Microsoft 365 учетным записям пользователей по мере их создания в зависимости от их создания.

Для гибридной модели удостоверений, когда учетные записи пользователей Active Directory Domain Services (AD DS) синхронизируются впервые, им автоматически не назначено расположение или Microsoft 365 лицензия. **Необходимо настроить каждую учетную запись пользователя с расположением пользователя до или вместе с назначением лицензии.**

В любом случае необходимо назначить лицензию учетным записям пользователей, чтобы пользователи могли получать доступ к Microsoft 365, таким как электронная почта и Microsoft Teams.

Лицензии можно назначать учетным записям пользователей как индивидуально, так и автоматически через членство в группе.

Чтобы назначить Microsoft 365 лицензии отдельным учетным записям пользователей, можно использовать:

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

- [Реализация безопасности](../security/defender-365-security/security-roadmap.md)
- [Развертывание клиентского программного обеспечения, например Приложения Microsoft 365](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Настройка управления устройствами](device-management-roadmap-microsoft-365.md)
- [Настройка служб и приложений](configure-services-and-applications.md)