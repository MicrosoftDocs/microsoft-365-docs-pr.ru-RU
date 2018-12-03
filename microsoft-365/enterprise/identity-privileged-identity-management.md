---
title: Шаг 3. Настройка роли глобального администратора, используемой по требованию
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить Azure AD Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870630"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>Шаг 3. Настройка роли глобального администратора, используемой по требованию

*Этот шаг — необязательный; он применяется только к плану E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

На этом шаге потребуется настроить Azure AD Privileged Identity Management (PIM), чтобы сократить количество времени, на протяжении которого ваши учетные записи глобального администратора будут уязвимы к атакам пользователей-злоумышленников. PIM по запросу предоставляет своевременное назначение роли глобального администратора, при необходимости.  

Вместо присвоения вашим учетным записям глобального администратора статуса администратора на бессрочной основе, им присваивается статус администратора, наделенного соответствующими полномочиями. Роль глобального администратора будет неактивной, пока она кому-либо не потребуется. Затем необходимо выполнить процесс активации, чтобы добавить роль глобального администратора в учетную запись глобального администратора на определенный период времени. По истечении такого периода PIM удаляет роль глобального администратора из учетной записи глобального администратора.

Функция Privileged Identity Management доступна с лицензией Azure Active Directory Premium P2, которая входит в план Microsoft 365 Enterprise E5. Кроме того, вы можете приобрести отдельные лицензии Azure Active Directory Premium P2 для ваших учетных записей глобального администратора.

Чтобы включить Azure PIM для вашего клиента Azure AD и учетных записей глобального администратора, см. [указания по настройке PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Чтобы разработать комплексный стратегический план защиты привилегированного доступа от кибератак, см. статью [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pim), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Упрощение процедуры сброса паролей](identity-password-reset.md) |

