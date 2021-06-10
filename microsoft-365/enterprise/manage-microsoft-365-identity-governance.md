---
title: Управление Microsoft 365 управления удостоверением
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
description: Узнайте, как использовать Microsoft 365 управления удостоверением.
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910958"
---
# <a name="manage-microsoft-365-identity-governance"></a>Управление Microsoft 365 управления удостоверением

Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников. Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.

Дополнительные сведения см. в этом обзоре управления удостоверением [для Azure Active Directory (Azure AD).](/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>Настройка проверок доступа Azure AD

Обзоры доступа к Azure AD позволяют просмотреть доступ пользователя, чтобы обеспечить постоянный доступ только нужным людям. Например:

- При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.
- Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.
- Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.

Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.

Дополнительные сведения см. в [обзоре обзоров доступа.](/azure/active-directory/governance/access-reviews-overview)

Сведения о настройке различных типов проверок доступа см. в следующих статьях:

- [Группы и приложения](/azure/active-directory/governance/create-access-review)
- [Роли Azure AD](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Роли ресурсов Azure](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Настройка управления правами Azure AD

Управление правами Wiht Azure AD, вы можете управлять удостоверением и получать доступ к жизненному циклу в масштабе путем автоматизации рабочего процесса запроса доступа, назначений доступа, отзывов и истечения срока действия.

Для выполнения своей работы сотрудникам необходим доступ к различным группам, приложениям и сайтам. Управление этим доступом может быть сложной задачей, так как требования изменяются, добавляются новые приложения или пользователям требуются дополнительные права доступа. При совместной работе с другими организациями вы можете не знать, кому в другой организации необходим доступ к ресурсам организации, а сторонние пользователи не будут знать, какие приложения, группы или сайты использует ваша организация.

Управление правами Azure AD поможет вам более эффективно управлять доступом к группам, приложениям и SharePoint для внутренних и внешних пользователей.
 
Дополнительные сведения см. в обзоре управления правами [Azure AD.](/azure/active-directory/governance/entitlement-management-overview)