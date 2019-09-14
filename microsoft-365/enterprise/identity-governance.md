---
title: Шаг 7. Настройка управления удостоверениями
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Обзор и настройка управления удостоверениями для клиента Azure AD.
ms.openlocfilehash: a965b74afc680c2ff506e0fc2ddebc280ee312a1
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982912"
---
# <a name="step-7-configure-identity-governance"></a>Шаг 7. Настройка управления удостоверениями

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников. Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.

Дополнительные сведения об управлении удостоверениями для Azure Active Directory (Azure AD) см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Настройка проверок доступа Azure AD

*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*

На этом этапе вы настроите проверки доступа Azure AD, позволяющие проверять доступ пользователя, чтобы сохранять доступ только для соответствующих пользователей. Например:

- При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.
- Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.
- Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.

Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.

Дополнительные сведения о проверках доступа Azure AD см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).

Сведения о настройке различных типов проверок доступа см. в следующих статьях:

- [Группы и приложения](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Роли Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Роли ресурсов Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-access-reviews).

## <a name="next-step"></a>Следующее действие

[Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной](identity-exit-criteria.md)

