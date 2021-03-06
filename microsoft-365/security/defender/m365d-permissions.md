---
title: Управление доступом к Microsoft 365 Defender данным в центре Microsoft 365 безопасности
description: Узнайте, как управлять разрешениями на данные в Microsoft 365 Defender
keywords: доступ, разрешения, Microsoft 365 Defender, M365, безопасность, MCAS, Cloud App Security, Microsoft Defender для конечной точки, область, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 738315c446fd57d4cd027de92eb77b0029f84323
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177534"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Управление доступом к Microsoft 365 Defender с Azure Active Directory глобальными ролями

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Существует два способа управления доступом к Microsoft 365 Defender
- **Роли Azure Active Directory (AD)**
- **Пользовательский доступ к роли**

Учетные записи, задав следующие роли **глобальной Azure Active Directory (AD),** могут получать доступ к Microsoft 365 Defender и данным:
- Глобальный администратор
- Администратор безопасности
- Оператор безопасности
- Глобальный читатель
- Читатель сведений о безопасности

Чтобы просмотреть учетные записи с этими ролями, см. раздел [Разрешения в Центре безопасности Microsoft 365](https://security.microsoft.com/permissions).

**Пользовательский** доступ к роли — это новая возможность в Microsoft 365 Defender и позволяет управлять доступом к определенным данным, задачам и возможностям в Microsoft Defender 365. Настраиваемые роли предоставляют больше управления, чем глобальные роли Azure AD, предоставляя пользователям только необходимый доступ с наименьшими допустимыми ролями.  Кроме глобальных ролей Azure AD можно создавать настраиваемые роли. [Дополнительные информацию о настраиваемой роли](custom-roles.md).

> [!NOTE]
> Эта статья применяется только к управлению глобальными Azure Active Directory ролей. Дополнительные сведения об использовании настраиваемого управления доступом на основе ролей см. в пользовательских ролях для управления доступом на основе [ролей.](custom-roles.md)

## <a name="access-to-functionality"></a>Доступ к функциям
Доступ к определенным функциям зависит от [роли Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Обратитесь к глобальному администратору, если вам нужен доступ к определенным функциям, для которых вам или вашей группе пользователей требуется назначить новую роль.

### <a name="approve-pending-automated-tasks"></a>Утверждение ожидающих автоматизированных задач
[Автоматический анализ угроз и защита от атак](m365d-autoir-actions.md) может выполнять действия с сообщениями электронной почты, пересылая правила, файлы, механизмы сохраняемости и другие артефакты, обнаруженные во время анализа. Чтобы утвердить или отклонить ожидающие действия, требующие явного утверждения, вам необходимы определенные роли, назначенные в Microsoft 365. Дополнительные сведения см. в статье [Разрешения центра уведомлений](m365d-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Доступ к данным
Доступ к Microsoft 365 Defender данным можно контролировать с помощью области, назначенной группам пользователей в Microsoft Defender для управления доступом на основе ролей конечных точек (RBAC). Если доступ к определенному набору устройств в конечной точке Defender для конечной точки не был областью охвата, вы будете иметь полный доступ к данным в Microsoft 365 Defender. Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.

Например, если вы принадлежите только к одной группе пользователей с ролью Microsoft Defender для конечной точки и эта группа пользователей имеет доступ только к устройствам продаж, в Microsoft 365 Defender. [Дополнительные новости о параметрах RBAC в Microsoft Defender для конечной точки](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Элементы управления доступом в Microsoft Cloud App Security
Во время предварительного просмотра Microsoft 365 Defender не применяет элементы управления доступом на основе Cloud App Security параметров. Доступ к Microsoft 365 Defender данным не зависит от этих параметров.

## <a name="related-topics"></a>Похожие темы
- [Настраиваемые роли в области управления доступом на основе ролей для Microsoft 365 Defender](custom-roles.md)
- [Роли Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender для endpoint RBAC](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Роли Cloud App Security](/cloud-app-security/manage-admins)
