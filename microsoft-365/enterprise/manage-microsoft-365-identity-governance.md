---
title: Управление удостоверениями Microsoft 365
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
description: Узнайте, как использовать функции управления удостоверениями Microsoft 365.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370350"
---
# <a name="manage-microsoft-365-identity-governance"></a>Управление удостоверениями Microsoft 365

Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников. Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.

Дополнительные сведения см. в статье [Обзор управления удостоверениями для Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).

## <a name="set-up-azure-ad-access-reviews"></a>Настройка проверок доступа Azure AD

Проверка доступа Azure AD позволяет просматривать доступ пользователя, чтобы убедиться, что доступ к ним имеют только нужные пользователи. Например:

- При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.
- Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.
- Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.

Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.

Более подробную информацию можно узнать в статье [Обзор просмотров Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).

Сведения о настройке различных типов проверок доступа см. в следующих статьях:

- [Группы и приложения](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Роли Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Роли ресурсов Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Настройка управления обслуживанием Azure AD

ВИХТ управления обслуживанием Azure AD можно управлять жизненным циклом удостоверений и доступом в масштабе, автоматизируя рабочие процессы запросов на доступ, назначения доступа, обзоры и срок действия.

Вашим сотрудникам требуется доступ к различным группам, приложениям и сайтам для выполнения их работы. Управление этим доступом может быть проблематичным, так как изменяется требование, добавляются новые приложения или для пользователей требуются дополнительные права доступа. При совместной работе с другими организациями может быть неясно, что в другой организации требуется доступ к ресурсам вашей организации, а за пределами пользователей неизвестно, какие приложения, группы или сайты используются в Организации.

Управление обслуживанием Azure AD поможет вам эффективнее управлять доступом к группам, приложениям и сайтам SharePoint для внутренних и внешних пользователей.
 
Дополнительные сведения можно найти в статье [Обзор управления обслуживанием Azure AD](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).
