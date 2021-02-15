---
title: Управление удостоверением Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Узнайте, как использовать функции управления удостоверением Microsoft 365.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370350"
---
# <a name="manage-microsoft-365-identity-governance"></a>Управление удостоверением Microsoft 365

Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников. Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.

Дополнительные сведения см. в этом [обзоре управления удостоверением для Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>Настройка проверок доступа Azure AD

Проверки доступа Azure AD позволяют вам просмотреть доступ пользователя, чтобы обеспечить постоянный доступ только нужным пользователям. Например:

- При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.
- Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.
- Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.

Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.

Дополнительные сведения [см. в обзоре проверок доступа.](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Сведения о настройке различных типов проверок доступа см. в следующих статьях:

- [Группы и приложения](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Роли Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Роли ресурсов Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Настройка управления правами Azure AD

Управление правами Wiht в Azure AD. Вы можете управлять жизненным циклом удостоверений и доступа в масштабе путем автоматизации рабочего процесса запроса доступа, назначений доступа, отзывов и истечения срока действия.

Сотрудникам нужен доступ к различным группам, приложениям и сайтам для выполнения своей работы. Управление этим доступом может быть сложной задачей, так как требования меняются, добавляются новые приложения или пользователям требуются дополнительные права доступа. При совместной работе с другими организациями вы можете не знать, кому из других организаций нужен доступ к ресурсам вашей организации, а внешние пользователи не будут знать, какие приложения, группы или сайты использует ваша организация.

Управление правами Azure AD позволяет более эффективно управлять доступом к группам, приложениям и сайтам SharePoint для внутренних и внешних пользователей.
 
Дополнительные сведения см. в обзоре управления правами [Azure AD.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
