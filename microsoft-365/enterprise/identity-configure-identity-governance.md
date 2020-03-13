---
title: Шаг 7. Настройка управления удостоверениями
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Обзор и настройка управления удостоверениями для клиента Azure AD.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543998"
---
# <a name="step-6-configure-identity-governance"></a>Шаг 6. Настройка управления удостоверениями

![Этап 2. Удостоверения](../media/deploy-foundation-infrastructure/identity_icon-small.png)

Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников. Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.

Дополнительные сведения об управлении удостоверениями для Azure Active Directory (Azure AD) см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).


*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Настройка проверок доступа Azure AD

*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*

На этом этапе вы настроите проверки доступа Azure AD, позволяющие проверять доступ пользователя, чтобы сохранять доступ только для соответствующих пользователей. Например:

- При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.
- Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.
- Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.

Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.

Дополнительные сведения о проверках доступа Azure AD см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).

Azure AD Privileged Identity Management (PIM) предоставляет целый ряд средств управления, предназначенных для защиты прав доступа к ресурсам в AAD, Azure и других облачных службах Майкрософт. Azure AD PIM предоставляет полный набор средств управления, помогающих защитить ресурсы компании, такие как каталог, Office 365 и роли ресурсов Azure. Как и для других видов доступа, с помощью проверок доступа можно настроить регулярные сертификации прав доступа для всех пользователей с ролями администратора. Служба Azure AD PIM доступна только в версии E5 Microsoft 365 корпоративный.

Сведения о настройке различных типов проверок доступа см. в следующих статьях:

- [Группы и приложения](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Роли Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Роли ресурсов Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-access-reviews).

## <a name="next-step"></a>Следующее действие

[Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной](identity-exit-criteria.md)

